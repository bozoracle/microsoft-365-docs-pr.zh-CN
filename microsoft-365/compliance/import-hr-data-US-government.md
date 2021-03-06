---
title: 设置连接器以将 HR 数据导入美国政府云
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 美国政府云中的管理员可以设置数据连接器，以将员工数据从组织的人力资源 (HR) 系统导入 Microsoft 365。 这使您可以使用内幕风险管理策略中的 HR 数据来帮助您检测可能对组织造成内部威胁的特定用户执行的活动。
ms.openlocfilehash: c1382cd94fcbba1d2ba561657c756e509af21dae
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196385"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>设置连接器以在美国政府版中导入 HR 数据

您可以在 Microsoft 365 合规性中心中设置数据连接器，以将人力资源 (HR) 数据导入美国政府组织。 与 HR 相关的数据包括员工提交其辞职的日期和员工最后一天的日期。 这样，Microsoft 信息保护解决方案（如 [内幕风险管理解决方案](insider-risk-management.md)）可以使用这种 HR 数据来帮助您的组织防止在组织内遭受恶意活动或数据被盗。 设置 HR 连接器包含在 Azure Active Directory 中创建一个应用程序，该应用程序用于按连接器进行身份验证，创建包含 HR 数据的 CSV 映射文件，在合规性中心中创建一个数据连接器，然后以 ingests 的方式在 CSV 文件中将 HR 数据 (运行到 Microsoft 云中的计划基础) 。 然后，内幕风险管理工具使用数据连接器访问导入到 Microsoft 365 美国政府组织的 HR 数据。

## <a name="before-you-begin"></a>准备工作

- 您的组织必须同意允许 Office 365 导入服务访问组织中的数据。 若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤3中成功创建 HR 连接器。

- 必须在 Exchange Online 中为在步骤3中创建 HR 连接器的用户分配邮箱导入导出角色。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建新的角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

- 您需要确定如何) 定期检索或导出组织的 HR 系统 (中的数据，并将其添加到步骤2中所述的 CSV 文件。 您在步骤4中运行的脚本会将 CSV 文件中的 HR 数据上传到 Microsoft 云。

- 您在步骤4中运行的示例脚本会将 HR 数据上载到 Microsoft 云，以便其他 Microsoft 工具（如内幕风险管理解决方案）可以使用它。 在任何 Microsoft standard 支持计划或服务下，不支持此示例脚本。 示例脚本按原样提供，而不提供任何种类的担保。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 因使用或性能示例脚本和文档而导致的全部风险都将保留给您。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤1：在 Azure Active Directory 中创建应用程序

第一步是在 Azure Active Directory (Azure AD) 中创建和注册新应用程序。 应用将与您在步骤3中创建的 HR 连接器相对应。 创建此应用程序将允许 Azure AD 在运行 HR 连接器时对其进行身份验证，并尝试访问你的组织。 此应用程序还将用于对您在步骤4中运行的脚本进行身份验证，以将 HR 数据上传到 Microsoft 云。 在创建此 Azure AD 应用过程中，请务必保存以下信息。 这些值将在后续步骤中使用。

- Azure AD 应用程序 ID (也称为 " *应用程序 id* " 或 " *客户端 id* ") 

- Azure AD 应用程序机密 (也称为 *客户端密码*) 

- 租户 Id (也称为 *目录 Id*) 

有关在 Azure AD 中创建应用程序的分步说明，请参阅 [使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>步骤2：使用 HR 数据准备 CSV 文件

下一步是创建一个 CSV 文件，其中包含有关已离开组织的员工的信息。 如 "开始之前" 一节中所述，您需要确定如何从组织的 HR 系统生成此 CSV 文件。 下面的示例演示了一个完整的 CSV 文件 (在) 中打开，其中包含 (列) 的三个必需参数。 在 Microsoft Excel 中编辑 CSV 文件要容易得多。

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

CSV 文件的第一行（即标题行）列出了所需的列名称。 在每个列标题中使用的名称由您 (上一示例中的名称作为建议) 。 但是，当您在步骤3中创建 HR 连接器时， *必须* 指定在 CSV 文件中使用的相同列名称。 不要在列名称中包含空格。

下表介绍了 CSV 文件中的每个列：

|**列名称**|**说明**|
|:-----|:-----|
| **EmailAddress** <br/> |指定已终止的雇员的电子邮件地址。|
| **TerminationDate** <br/> |指定在您的组织中正式终止此人的雇佣的日期。 例如，这可能是员工在离开你的组织时给出通知的日期。 此日期可能与人员的最后一天的工作日期不同。 使用以下日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` （ [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)）。|
|**LastWorkingDate**|指定终止的员工的最后一天的工作。 使用以下日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` （ [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)）。|
|||

创建具有所需 HR 数据的 CSV 文件后，将其存储在与步骤4中运行的脚本相同的系统上。 请务必实施更新策略，以便 CSV 文件始终包含最新信息。 这样做可确保在运行脚本的情况下，将最新的员工终止数据上载到 Microsoft 云。

## <a name="step-3-create-the-hr-connector"></a>步骤3：创建 HR 连接器

下一步是在 Microsoft 365 合规性中心中创建 HR 连接器。 在步骤4中运行脚本后，您创建的 HR 连接器会将 HR 数据从 CSV 文件中接收到 Microsoft 365 组织。 在此步骤中，请务必复制创建连接器时生成的作业 ID。 运行脚本时，将使用作业 ID。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后单击左侧导航中的 " **数据连接器** "。

2. 在**HR**下的 "**数据连接器**" 页上，单击 "**查看**"。

3. 在 **HR** 页上，单击 " **添加连接器**"。

4. 在 " **身份验证凭据** " 页上，执行以下操作，然后单击 " **下一步**"：

   a. 键入或粘贴您在步骤1中创建的 Azure 应用程序的 Azure AD 应用程序 ID。

   b. 键入 HR 连接器的名称。

5. 在 " **文件映射** " 页上的每个相应框中，键入在步骤2中创建的 CSV 文件 *中)  (* 的三个列标题的名称。 名称不区分大小写。 如前面所述，在这些框中键入的名称必须与 CSV 文件中的参数名称相匹配。 例如，下面的屏幕截图显示了在第2步中显示的示例 CSV 文件示例中的参数名称。

   ![列标题名称与 CSV 文件中的名称相匹配](../media/HRConnectorWizard3.png)

6. 在 " **检查** " 页上，查看您的设置，然后单击 " **完成** " 以创建连接器。

   将显示 "状态" 页，确认已创建连接器。 此页面包含完成下一步以运行示例脚本以上载 HR 数据所需的两个重要事项。

   ![查看包含作业 ID 的页面并链接到 github 以获取示例脚本](../media/HRConnector_Confirmation.png)

   a. **作业 ID。** 在下一步中，你将需要此作业 ID 来运行脚本。 您可以从此页面或从 "连接线" 飞出页面复制它。
   
   b. **指向示例脚本的链接。** 单击 **此处** 链接转到 GitHub 站点以访问示例脚本 (链接将) 中打开新的窗口。 保持此窗口处于打开状态，以便您可以在第4步中复制脚本。 或者，您可以为目标添加书签或复制 URL，以便您可以在第4步中再次访问它。 此链接在 "连接线" 弹出页面上也可用。

7. 单击“完成”****。

   新的连接器将显示在 " **连接器** " 选项卡上的列表中。 

8. 单击刚创建的 HR 连接器以显示弹出页面，其中包含有关连接器的属性和其他信息。

   ![新 HR 连接器的飞出页面](../media/HRConnectorWizard7.png)

   如果还未执行此操作，则可以复制 **Azure 应用 id** 和 **连接器作业 ID**的值。 在下一步中，你将需要这些脚本来运行脚本。 您还可以从弹出页面下载脚本， (或在下一步中使用链接下载。 ) 

   您还可以单击 " **编辑** " 更改在 " **文件映射** " 页上定义的 Azure 应用 ID 或列标题名称。

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>步骤4：运行示例脚本以上传 HR 数据

设置 HR 连接器的最后一步是运行一个示例脚本，该脚本将把在第2步中创建的 CSV 文件 (中创建的 HR 数据上载到 Microsoft 云) 中。 具体来说，该脚本会将数据上载到 HR 连接器。 运行该脚本后，您在步骤3中创建的 HR 连接器会将 HR 数据导入到 Microsoft 365 组织中，以供其他合规性工具（如内幕风险管理解决方案）进行访问。 运行脚本后，请考虑计划任务每天定期自动运行，以便将最新的员工终止数据上载到 Microsoft 云。 请参阅 [安排脚本自动运行](#optional-step-6-schedule-the-script-to-run-automatically)。

1. 转到您在上一步中打开的窗口以使用示例脚本访问 GitHub 网站。 或者，也可以打开已加书签的网站或使用您复制的 URL。

2. 单击 " **原始** " 按钮以在文本视图中显示脚本。

3. 复制示例脚本中的所有行，然后将它们保存到一个文本文件中。

4. 如有必要，请修改组织的示例脚本。

5. 将文本文件另存为 Windows PowerShell 脚本文件，方法是使用文件名后缀 `.ps1` ; 例如， `HRConnector.ps1` 。

6. 在本地计算机上打开命令提示符，并转到保存该脚本的目录。

7. 运行以下命令，将 CSV 文件中的 HR 数据上传到 Microsoft 云;例如：

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   下表介绍了要与此脚本一起使用的参数及其必需的值。 您在前面步骤中获取的信息用于这些参数的值。

   |**Parameter**|**说明**
   |:-----|:-----|:-----|
   |`tenantId`|您在步骤1中获取的 Microsoft 365 组织的 Id。 您还可以在 Azure AD 管理中心的 **概述** 边栏中获取组织的租户 Id。 这用于标识你的组织。|
   |`appId` |您在第1步中的 Azure AD 中创建的应用程序的 Azure AD 应用程序 Id。 当脚本尝试访问 Microsoft 365 组织时，Azure AD 使用此方法进行身份验证。 |
   |`appSecret`|您在第1步中的 Azure AD 中创建的应用程序的 Azure AD 应用程序密码。 这也用于身份验证。|
   |`jobId`|您在步骤3中创建的 HR 连接器的作业 ID。 这用于将上载到 Microsoft 云的 HR 数据与 HR 连接器相关联。|
   |`csvFilePath`|CSV 文件的文件路径 (与您在步骤2中创建的脚本) 存储在同一系统上。 请尝试避免在文件路径中包含空格;否则，请使用单引号。|
   |||
   
   下面的示例展示了使用每个参数的实际值的 HR 连接器脚本的语法：

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   如果上载成功，则脚本将显示 **上传成功** 消息。

   > [!NOTE]
   > 如果由于执行策略而运行上一个命令时遇到问题，请参阅 [关于执行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) 和 [ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) ，以获取有关设置执行策略的指南。

## <a name="step-5-monitor-the-hr-connector"></a>步骤5：监视 HR 连接器

创建 HR 连接器并运行脚本以上载您的 HR 数据后，您可以在 Microsoft 365 合规性中心查看连接器和上传状态。 如果将脚本安排为定期自动运行，还可以在上次脚本运行之后查看当前状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。

2. 单击 " **连接器** " 选项卡，然后选择 HR 连接器以显示弹出页面，其中包含有关连接器的属性和信息。

   ![带有属性和状态的 HR 连接器浮出控件页](../media/HRConnectorFlyout1.png)

3. 在 " **进度**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。 此日志包含有关每次脚本运行的信息，并将数据从 CSV 文件上载到 Microsoft 云。 

   ![HR 连接器日志文件显示从 CSV 文件上载的编号行数](../media/HRConnectorLogFile.png)

   该 `RecordsSaved` 字段指示上传的 CSV 文件中的行数。 例如，如果 CSV 文件包含四行，则字段的值 `RecordsSaved` 为4，如果脚本成功上传了 CSV 文件中的所有行。

如果您没有在步骤4中运行该脚本，则在 " **上次导入**" 下将显示下载该脚本的链接。 您可以下载该脚本，然后按照步骤4中的步骤运行它。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤6：安排脚本自动运行

若要确保组织中的最新 HR 数据对类似于内幕风险管理解决方案的工具可用，我们建议您安排脚本定期（例如一天一次）自动运行。 这还要求在类似 (上更新 CSV 文件中的 HR 数据（如果不是相同的) 计划），以便它包含有关离开组织的员工的最新信息。 目标是上载最新的 HR 数据，以便 HR 连接器可以将其提供给内幕风险管理解决方案。

您可以在 Windows 中将 "任务计划程序" 应用程序用户每天自动运行该脚本。

1. 在本地计算机上，单击 Windows " **开始** " 按钮，然后键入 " **任务计划程序**"。

2. 单击 " **任务计划** 程序" 应用将其打开。

3. 在 " **操作** " 部分，单击 " **创建任务**"。

4. 在 " **常规** " 选项卡上，为计划的任务键入一个描述性名称;例如， **HR 连接器脚本**。 您还可以添加可选的说明。

5. 在 " **安全选项**" 下，执行下列操作：

   a. 确定是仅在登录到计算机时运行脚本，还是在登录时运行脚本。
   
   b. 确保选中 " **以最高特权运行** " 复选框。

6. 选择 " **触发器** " 选项卡，单击 " **新建**"，然后执行以下操作：

   a. 在 " **设置**" 下，选择 " **每日** " 选项，然后选择第一次运行脚本的日期和时间。 脚本每天都在指定的时间。
   
   b. 在 " **高级设置**" 下，确保选中 " **启用** " 复选框。
   
   c. 单击“确定”****。

7. 选择 " **操作** " 选项卡，单击 " **新建**"，然后执行以下操作：

   ![为 HR 连接器脚本创建新的计划任务的操作设置](../media/HRConnectorScheduleTask1.png)

   a. 在 " **操作** " 下拉列表中，确保选择 " **启动程序** "。

   b. 在 " **程序/脚本** " 框中，单击 " **浏览**"，然后转到以下位置并选择它，以使路径显示在框中： `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` 。

   c. 在 " **添加参数" (可选) ** 框中，粘贴您在步骤4中运行的相同脚本命令。 例如，`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. 在 " **开始 (可选) ** " 框中，粘贴您在步骤4中运行的脚本的文件夹位置。 例如，`C:\Users\contosoadmin\Desktop\Scripts`。

   e. 单击 **"确定"** 保存新操作的设置。

8. 在 " **创建任务** " 窗口中，单击 **"确定"** 以保存计划的任务。 系统可能会提示您输入您的用户帐户凭据。

   新任务将显示在 "任务计划程序库" 中。

   ![新任务将显示在任务计划程序库中](../media/HRConnectorTaskSchedulerLibrary.png)

   最后一次运行脚本并显示下一次计划运行时。 您可以双击该任务以对其进行编辑。

   您还可以验证在符合性中心中对应 HR 连接器的飞出页面上，脚本的上次运行时间。
