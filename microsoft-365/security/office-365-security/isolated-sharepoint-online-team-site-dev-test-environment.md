---
title: 独立的 SharePoint Online 团队网站开发/测试环境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 摘要：在 Microsoft 365 开发/测试环境中配置与组织的其余部分隔离的 SharePoint Online 团队网站。
ms.openlocfilehash: e21dccb9ef535bb997d6e62b70e5576bf531041c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199657"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>独立的 SharePoint Online 团队网站开发/测试环境

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **摘要：** 在 Microsoft 365 开发/测试环境中配置与组织的其余部分隔离的 SharePoint Online 团队网站。

Microsoft 365 中的 SharePoint Online 团队网站是使用通用文档库、OneNote 笔记本和其他服务进行协作的位置。 在大多数情况下，需要跨部门或组织实现广泛访问和协作。 但是，在某些情况下，您希望在一小部分人员之间严格控制协作的访问权限和权限。

对 SharePoint Online 团队网站的访问权限以及用户可以执行的操作由 SharePoint 组和权限级别控制。 默认情况下，SharePoint Online 网站有三种访问级别：

- **成员**：可以在网站上查看、创建和修改资源。

- **所有者**：可完全控制网站，包括能够更改权限。

- **访问者**：只能在网站上查看资源。

本文将指导您完成对名为 ProjectX 的机密研究项目的独立 SharePoint Online 团队网站的配置。 访问要求为：

- 只有此项目的成员才能访问网站及其内容（文档、OneNote 笔记本、网页），编辑和查看 SharePoint 权限级别是通过组成员身份进行控制。

- 只有网站创建者和网站管理员组成员才能管理网站，包括可以修改网站级权限。

在 Microsoft 365 开发/测试环境中设置独立的 SharePoint Online 团队网站有三个阶段：

1. 创建 Microsoft 365 开发/测试环境。

2. 创建 ProjectX 用户和组。

3. 创建一个新的 ProjectX SharePoint Online 团队网站并将其隔离。

> [!TIP]
> 单击[此处](https://aka.ms/catlgstack)可直观映射到 One Microsoft 云测试实验室指南堆栈中的所有文章。

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>第1阶段：构建轻型或模拟的企业 Microsoft 365 开发/测试环境

如果只想使用最低要求以轻量方式创建独立的 SharePoint Online 团队网站，请按照 [轻型基本配置](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)的第2阶段和第3阶段中的说明进行操作。

如果要在模拟的企业配置中创建独立的 SharePoint Online 团队网站，请按照 [针对 Microsoft 365 测试环境的密码哈希同步](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)中的说明进行操作。

> [!NOTE]
> 创建独立的 SharePoint Online 网站不需要模拟企业开发/测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 可以根据需要选择此选项，以便能够测试独立 SharePoint Online 网站，并在代表典型组织的环境中对其进行试验。

## <a name="phase-2-create-user-accounts-and-access-groups"></a>第2阶段：创建用户帐户和访问组

使用 [连接到 Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) 中的说明，通过全局管理员帐户连接到你的试用订阅：

- 您的计算机 (的轻型 Microsoft 365 开发/测试环境) 。

- 模拟企业 Microsoft 365 开发/测试环境的 CLIENT1 虚拟机 () 。

若要为 ProjectX SharePoint Online 团队网站创建新的访问组，请从 Windows PowerShell 提示符的 Windows Azure Active Directory 模块运行以下命令：

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

填写组织名称（示例：contosotoycompany），你所在位置的两位字符的国家/地区代码，然后从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

在安全的位置上，记下显示的 **New-MsolUser** 命令中为 Lead Designer 帐户生成的密码。

从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

在安全的位置上，记下显示的 **New-MsolUser** 命令中为 Lead Researcher 帐户生成的密码。

从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

在安全的位置上，记下显示的 **New-MsolUser** 命令中为 Development VP 帐户生成的密码。

接下来，若要将新帐户添加到新的访问组，请从 Windows PowerShell 提示符的 Windows Azure Active Directory 模块中运行这些 PowerShell 命令：

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

引起

- ProjectX 访问组包含潜在客户设计人员和潜在客户研究工具用户帐户

- ProjectX 访问组包含试用订阅的全局管理员帐户

- ProjectX 访问组包含开发副总裁用户帐户

图1显示了访问组及其成员资格。

**图1**

![适用于独立 SharePoint Online 组网站的 Microsoft 365 组及其成员资格](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>第3阶段：创建新的 ProjectX SharePoint Online 团队网站并将其隔离

若要为 ProjectX 创建 SharePoint Online 团队网站，请执行以下操作：

1. 使用本地计算机上的浏览器 (轻量配置) 或在 CLIENT1 (模拟企业配置) 上，使用全局管理员帐户登录 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 。

2. 在磁贴列表中，单击“SharePoint”****。

3. 在浏览器上的新“SharePoint”选项卡中，单击“+ 创建网站”****。

4. 在“团队网站名称”**** 中，键入“ProjectX”****。 在 " **隐私设置**" 中，选择 " **仅专用成员可以访问此网站**"。

5. 在“团队网站描述”**** 中，键入“ProjectX 的 SharePoint 网站”****，然后单击“下一步”****。

6. 在“想添加什么人员?”**** 窗格中，单击“完成”****。

7. 在浏览器上的新“ProjectX-主页”**** 选项卡上，依次单击工具栏中的设置图标和“网站权限”****。

8. 在“网站权限”**** 窗格中，单击“高级权限设置”****。

9. 在浏览器上的新“权限：**** Project X”选项卡中，单击“访问请求设置”****。

10. 在“访问请求设置”**** 对话框中，取消选中“允许成员共享网站以及个别文件和文件夹”**** 和“允许访问请求”****（以便取消选中全部三个复选框），然后单击“确定”****。

11. 单击列表中的“ProjectX 成员”****。

12. 在“**人员和组**”页面上，单击“**新建**”。

13. 在“共享”**** 对话框中，键入并选择“ProjectX-Members”****，然后单击“共享”****。

14. 单击浏览器上的后退按钮。

15. 单击列表中的“ProjectX 所有者”****。

16. 在“**人员和组**”页面上，单击“**新建**”。

17. 在“共享”**** 对话框中，键入并选择“ProjectX-Admins”****，然后单击“共享”****。

18. 单击浏览器上的后退按钮。

19. 单击列表中的“ProjectX 访问者”****。

20. 在“人员和组”**** 页面上，单击“新建”****。

21. 在“共享”**** 对话框中，键入并选择“ProjectX-Viewers”****，然后单击“共享”****。

22. 关闭浏览器上的“人员和组”**** 选项卡，单击浏览器上的“ProjectX-主页”**** 选项卡，然后关闭“网站权限”**** 窗格。

下面介绍了权限配置结果：

- ProjectX Members SharePoint 组仅包含 ProjectX 成员访问组 (，其中仅包含领导设计人员和负责人研究人员用户帐户) 以及仅包含全局管理员用户帐户) 的 ProjectX 组 (。

- ProjectX 所有者 SharePoint 组仅包含 ProjectX 访问组 (仅包含全局管理员用户帐户的) 。

- "ProjectX 访问者" SharePoint 组仅包含 "ProjectX" 访问组 (，其中仅包含 "开发副总裁" 用户帐户) 。

- 成员无法修改网站级权限（只有 ProjectX-Admins 组成员才能修改）。

- 其他用户帐户无法访问网站及其资源，也无法请求访问网站。

图 2 展示了 SharePoint 组及其成员身份。

**图2**

![SharePoint Online 组及其针对独立 SharePoint Online 组网站的成员身份](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

现在，让我们来演示如何使用主导 Designer 用户帐户进行访问：

1. 关闭浏览器中的“ProjectX-主页”**** 选项卡，然后单击浏览器中的“Microsoft Office 主页”**** 选项卡。

2. 依次单击全局管理员名称和“注销”****。

3. [https://admin.microsoft.com](https://admin.microsoft.com)使用主导 Designer 帐户名称及其密码登录到 Microsoft 365 管理中心 () 。

4. 在磁贴列表中，单击“SharePoint”****。

5. 在浏览器的 "新建 **SharePoint** " 选项卡上，在 "搜索" 框中键入 **ProjectX** ，激活搜索，然后单击 " **ProjectX** 团队网站"。 您应该会在浏览器中看到一个用于 ProjectX 团队网站的新选项卡。

6. 单击设置图标。请注意，没有“网站权限”**** 选项。这没有问题，因为只有 ProjectX-Admins 组成员才能修改网站级权限

7. 打开选择的记事本或文本编辑器。

8. 复制 ProjectX 团队网站的 URL，并将其粘贴到记事本或文本编辑器中的新行上。

9. 在浏览器上的新“ProjectX-主页”**** 选项卡中，单击“文档”****。

10. 将 ProjectX 文档文件夹的 URL 复制并粘贴到记事本或文本编辑器中的新行上。

11. 在浏览器上的新“ProjectX-文档”**** 选项卡中，依次单击“新建”>“Word 文档”****。

12. 在页面上键入一些文本，等待状态显示为 " **已保存**"，单击浏览器上的 "后退" 按钮，然后刷新页面。 应该会看到“文档”**** 文件夹中有新的“Document.docx”****。

13. 依次单击“Document.docx”**** 文档对应的省略号和“获取链接”****。

14. 复制 **共享 "Document.docx"** 对话框中的 URL，并将其粘贴到记事本或文本编辑器中的新行上，然后关闭 **共享 "Document.docx"** 对话框。

15. 关闭浏览器中的“ProjectX-文档”**** 和“SharePoint”**** 选项卡，然后单击“Microsoft Office 主页”**** 选项卡。

16. 依次单击“Lead Designer”**** 名称和“注销”****。

现在，让我们来演示如何使用开发 VP 用户帐户进行访问：

1. [https://admin.microsoft.com](https://admin.microsoft.com)使用开发副总裁帐户名称及其密码登录到 Microsoft 365 管理中心 () 。

2. 在磁贴列表中，单击“SharePoint”****。

3. 在浏览器的 "新建 **SharePoint** " 选项卡上，在 "搜索" 框中键入 **ProjectX** ，激活搜索，然后单击 " **ProjectX** 团队网站"。 您应该会在浏览器中看到一个用于 ProjectX 团队网站的新选项卡。

4. 依次单击“文档”**** 和“Document.docx”**** 文件。

5. 在浏览器上的“Document.docx”**** 选项卡中，尝试修改文本。应该会看到一条内容为“此文档为只读”**** 的消息。这属于正常情况，因为 Development VP 用户帐户仅拥有对网站的查看权限。

6. 关闭浏览器中的“Document.docx”****、“ProjectX-文档”**** 和“SharePoint”**** 选项卡。

7. 依次单击“Microsoft Office 主页”**** 选项卡、“Development VP”**** 名称和“注销”****。

现在，让我们使用没有权限的用户帐户演示访问权限：

1. [https://admin.microsoft.com](https://admin.microsoft.com)使用用户3帐户名称及其密码登录到 Microsoft 365 管理中心 () 。

2. 在磁贴列表中，单击“SharePoint”****。

3. 	在浏览器上的新“SharePoint”**** 选项卡中，在搜索框中键入“ProjectX”****，然后开始搜索。应该会看到一条内容为“这里没有与你的搜索相匹配的内容”**** 的消息。

4. 将 ProjectX 网站的 URL 从记事本或文本编辑器的打开实例复制到浏览器的地址栏中，然后按“Enter”****。应该会看到“拒绝访问”**** 网页。

5. 将 ProjectX 文档文件夹的 URL 从记事本或文本编辑器复制到浏览器的地址栏中，然后按“Enter”****。应该会看到“拒绝访问”**** 网页。

6. 将 Documents.docx 文件的 URL 从记事本或文本编辑器复制到浏览器的地址栏中，然后按“Enter”****。应该会看到“拒绝访问”**** 网页。

7. 关闭浏览器中的“SharePoint”**** 选项卡，然后依次单击“Microsoft Office 主页”**** 选项卡、“用户 3”**** 名称和“注销”****。

你的独立 SharePoint Online 网站现已准备好进行额外的实验。

## <a name="next-step"></a>后续步骤

当准备好在生产中部署单独的 SharePoint Online 团队网站后，请参阅[设计单独的 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)中的分步设计注意事项。

## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)

[云采用测试实验室指南 (TLG)](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[模拟企业基础配置](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[轻型基本配置](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[云应用和混合解决方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
