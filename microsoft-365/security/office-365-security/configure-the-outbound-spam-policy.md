---
title: 配置出站垃圾邮件筛选
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中查看、创建、修改和删除出站垃圾邮件策略。
ms.openlocfilehash: 2c7a48280487944352f4ee8afc1e7f0596186a3d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203295"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>在 EOP 中配置出站垃圾邮件筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online 保护的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，通过 EOP 发送的出站电子邮件将自动检查垃圾邮件和异常发送活动。

您组织中的用户的出站垃圾邮件通常表示已损坏的帐户。 可疑的出站邮件会被标记为垃圾邮件 (无论垃圾邮件可信度或 SCL) 并通过 [高风险传递池](high-risk-delivery-pool-for-outbound-messages.md) 路由，以帮助保护服务的声誉 (也就是说，将 Microsoft 365 源电子邮件服务器从 IP 阻止列表) 保留。 系统会自动通知管理员可疑的出站电子邮件活动，并通过 [通知策略](../../compliance/alert-policies.md)阻止用户。

EOP 使用出站垃圾邮件策略作为组织的整体防御垃圾邮件的一部分。 有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。

管理员可以查看、编辑和配置 (，但不能删除) 默认出站垃圾邮件策略。 为了更细致，您还可以创建适用于组织中的特定用户、组或域的自定义出站垃圾邮件策略。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置出站垃圾邮件策略，以使用 Exchange Online 中的邮箱的 Microsoft 365 组织;没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。

EOP 中的出站垃圾邮件策略的基本元素为：

- **出站垃圾邮件筛选器策略**：指定出站垃圾邮件筛选 verdicts 和通知选项的操作。
- **出站垃圾邮件筛选器规则**：指定策略应用于出站垃圾邮件筛选器策略的) 的优先级和收件人筛选器 (。

在安全 & 合规中心中管理出站垃圾邮件策略时，这两个元素之间的差异并不明显：

- 创建策略时，实际上是创建出站垃圾邮件筛选器规则和关联的出站垃圾邮件筛选器策略，同时为两者使用相同的名称。
- 修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改出站垃圾邮件筛选器规则。 所有其他设置修改关联的出站垃圾邮件筛选器策略。
- 删除策略时，会删除出站垃圾邮件筛选器规则和关联的出站垃圾邮件筛选器策略。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本主题后面的 [使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 部分。

每个组织都有一个名为 Default 的内置出站垃圾邮件策略，其中包含以下属性：

- 该策略将应用于组织中的所有收件人，即使没有出站垃圾邮件筛选规则 (收件人筛选器规则与该策略关联) 。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略的优先级始终高于名为“默认”的策略。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高出站垃圾邮件筛选的有效性，可以使用应用于特定用户或用户组的更严格的设置来创建自定义出站垃圾邮件策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要添加、修改和删除出站垃圾邮件策略，您必须是下列角色组之一的成员：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 若要对出站垃圾邮件策略进行只读访问，您必须是下列角色组之一的成员：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

- 有关出站垃圾邮件策略的建议设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。

- 已**超过电子邮件发送限制**的默认[警报策略](../../compliance/alert-policies.md)，**检测到可疑电子邮件发送模式**，并且**限制发送电子邮件的用户**已将电子邮件通知发送到 (**TenantAdmins**的成员 **。) 组**关于异常出站电子邮件活动和阻止的用户（由于出站垃圾邮件）。 有关详细信息，请参阅 [验证受限制用户的通知设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 我们建议您使用这些通知策略，而不是在出站垃圾邮件策略中的通知选项。

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>使用安全 & 合规性中心创建出站垃圾邮件策略

在安全 & 合规中心中创建自定义出站垃圾邮件策略将同时为两者创建垃圾邮件筛选器规则和关联的垃圾邮件筛选器策略，同时使用相同的名称。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，单击 " **创建出站策略**"。

3. 在打开的 **出站垃圾邮件筛选器策略** 飞出后，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

4.  (可选) 展开 " **通知** " 部分，以配置应接收可疑出站电子邮件的副本和通知的其他用户：

   - 向**特定人员发送可疑的出站电子邮件的副本**：此设置将指定的用户添加为可疑的出站邮件的密件抄送收件人。

     > [!NOTE]
     > 此设置仅适用于默认的出站垃圾邮件策略。 它在您创建的自定义出站垃圾邮件策略中不起作用。

     要启用此设置，请执行以下操作：

     1. 选中该复选框以启用该设置。

     1. 单击 " **添加人员**"。 在显示的 " **添加或删除收件人** " 浮出控件中：

     1. 输入发件人的电子邮件地址。 可以指定用分号分隔的多个电子邮件地址 (; ) 或每行一个收件人。

     1. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加收件人。

        根据需要重复执行这些步骤（次数不限）。

        您添加的收件人将显示在浮出控件的 " **收件人列表** " 部分。 若要删除收件人，请单击 " ![ 删除" 按钮 ](../../media/scc-remove-icon.png) 。

     1. 完成时，请单击“保存”****。

        若要禁用此设置，请清除该复选框。

   - **如果发件人因发送出站垃圾邮件而被阻止，请通知特定人员**：

     > [!IMPORTANT]
     >
     > - 此设置正在从出站垃圾邮件策略中弃用。
     >
     > - 被**限制为用户发送电子邮件**的默认[通知策略](../../compliance/alert-policies.md)已将电子邮件通知发送到**TenantAdmins**的成员。当用户因超出 "**收件人限制**" 部分中的限制而被阻止时，会将电子邮件通知发送给 (**全局) 管理员**"。 **强烈建议您在出站垃圾邮件策略中使用通知策略而不是此设置来通知管理员和其他用户**。 有关说明，请参阅 [验证受限制用户的通知设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

5.  (可选) 展开 " **收件人限制** " 部分，为可疑的出站电子邮件配置限制和操作：

   > [!NOTE]
   > 这些设置仅适用于基于云的邮箱。

   - **每个用户的最大收件人数**

     有效的值为0到10000。 默认值为0，表示使用服务默认值。 有关详细信息，请参阅 [发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

     - **外部小时限制**：每个小时的最大外部收件人数。

     - **内部每小时限制**：每小时最大内部收件人数。

     - **每日限制**：每天的最大收件人总数。

   - **当用户超过以上限制时的操作**：配置超出任何一个 **收件人限制** 时要执行的操作。 对于所有操作，如果在出站垃圾邮件通知中发送出站垃圾邮件通知，由于在出站垃圾邮件通知中**发送出站垃圾**邮件设置，在用户中指定的收件人**受到限制，无法发送电子邮件**通知策略 (和现在的冗余通知特定人员。

     - **限制用户在以下日期之前发送邮件**：这是默认值。 发送电子邮件通知，用户在下一天（基于 UTC 时间）之前，将无法发送更多的邮件。 管理员无法替代此块。

       - 名为 " **用户限制发送电子邮件** " 的活动通知将通过电子邮件通知管理员 (，并在 " **查看通知** " 页面) 。

       - **如果发件人因在策略中发送出站垃圾邮件设置而被阻止**，则在 "通知特定人员" 中指定的任何收件人也会收到通知。

       - 在下一天，用户将不能再根据 UTC 时间发送更多的邮件。 管理员无法替代此块。

     - **限制用户发送邮件**：发送电子邮件通知，则会将用户添加到 Security & 合规性中心中的 **[受限用户] <https://sip.protection.office.com/restrictedusers> **门户中，并且在管理员将邮件从**受限制的用户**门户中删除之前，用户将无法发送电子邮件。管理员将用户从列表中删除后，该用户将不会再次限制该用户这一天。 有关说明，请参阅 [发送垃圾电子邮件后，从受限用户门户中删除用户](removing-user-from-restricted-users-portal-after-spam.md)。

     - **不执行任何操作，仅通知**：发送电子邮件通知。

6.  (可选) 展开 " **自动转发** " 部分，以控制用户自动将电子邮件转发给外部发件人。 有关自动转发的详细信息，请参阅 [配置电子邮件转发](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)。

   > [!NOTE]
   >
   > - 在9月2020之前，这些设置可用，但不是强制实施。
   >
   > - 这些设置仅适用于基于云的邮箱。
   >
   > - 这些设置不会影响到内部收件人的自动转发。

   可用值有：

   - **自动系统控制**：允许出站垃圾邮件筛选以控制自动外部电子邮件转发。 此值为默认值。

   - **启用**：策略不禁用自动外部电子邮件转发。

   - **Off**：策略禁用所有自动外部电子邮件转发。

7.  (必需的) 展开 " **应用于** " 部分，以确定该策略适用于的内部发件人。

    只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<sender1\>_ 或 _\<sender2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<sender1\>_ 和 _\<member of group 1\>_）。

    若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。 若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

    - **发件人域为**：指定组织中一个或多个已配置的接受域中的发件人。 单击 **“添加标记”** 框，以查看并选择域。 如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。

    - **发件人为**：指定组织中的一个或多个用户。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 再次单击 " **添加标记** " 框以选择 "其他发件人"。

    - **发件人是以下成员**：指定组织中的一个或多个组。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 再次单击 " **添加标记** " 框以选择 "其他发件人"。

    - **下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。 设置和行为与条件完全相同。

8. 完成后，单击 **“保存”**。

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>使用安全 & 合规性中心查看出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 以展开出站垃圾邮件策略：

   - 名为 " **出站垃圾邮件筛选器策略**" 的默认策略。

   - 您创建的自定义策略，在该策略中，" **类型** " 列中的值是 **自定义出站垃圾邮件策略**。

3. 策略设置将显示在显示的展开策略详细信息中，也可以单击 " **编辑策略**"。

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>使用安全 & 合规性中心修改出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 以展开出站垃圾邮件策略：

   - 名为 " **出站垃圾邮件筛选器策略**" 的默认策略。

   - 您创建的自定义策略，在该策略中，" **类型** " 列中的值是 **自定义出站垃圾邮件策略**。

3. 单击 **“编辑策略”**。

对于自定义出站垃圾邮件策略，显示的浮出控件中的可用设置与 [使用 Security & 合规中心创建出站垃圾邮件策略](#use-the-security--compliance-center-to-create-outbound-spam-policies) 部分中所述的相同。

对于名为 " **出站垃圾邮件筛选器策略**" 的默认出站垃圾邮件策略，" **应用** 于" 部分不可用 (策略适用于) 的所有人，并且您无法重命名该策略。

若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。

### <a name="enable-or-disable-outbound-spam-policies"></a>启用或禁用出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 以展开您创建的自定义策略 (" **类型** " 列中的值是 " **自定义出站垃圾邮件策略** ") 。

3. 在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。

   将切换开关移动到左侧可禁用策略： ![切换开关关闭](../../media/scc-toggle-off.png)

   将切换开关移动到右侧可启用策略： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

您不能禁用默认出站垃圾邮件策略。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>设置自定义出站垃圾邮件策略的优先级

默认情况下，会为出站垃圾邮件策略指定一个优先级，这取决于在 (较旧策略中创建它们的顺序低于旧策略) 的优先级。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

自定义出站垃圾邮件策略按其处理的顺序显示 (第一个策略的 **优先级** 值为 0) 。 名为 " **出站垃圾邮件筛选器策略** " 的默认出站垃圾邮件策略的优先级值为 **最低**，无法进行更改。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，找到 " **类型** " 列中的值为 " **自定义出站垃圾邮件策略**" 的策略。 注意 **“优先级”** 列中的值：

   - 具有最高优先级的自定义出站垃圾邮件策略的值为 ![ 向下箭头图标 ](../../media/ITPro-EAC-DownArrowIcon.png) **0**。

   - 优先级最低的自定义出站垃圾邮件策略具有值 ![ 向上箭头图标 ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (例如， ![ 向上箭头图标 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) 。

   - 如果有三个或更多自定义出站垃圾邮件策略，则在最高和最低优先级之间的策略具有值 ![ 向上箭头图标 ](../../media/ITPro-EAC-UpArrowIcon.png)![ 下箭头图标 ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如， ![ 向上箭头图标 ](../../media/ITPro-EAC-UpArrowIcon.png)![ 下箭头图标 ](../../media/ITPro-EAC-DownArrowIcon.png) **2**) 。

3. 单击 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) 或 ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) 在 "优先级" 列表中向上或向下移动自定义出站垃圾邮件策略。

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>使用安全 & 合规性中心删除出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，单击 " ![ 展开图标 ](../../media/scc-expand-icon.png) " 以展开要删除的自定义策略 (" **类型** " 列是 " **自定义出站垃圾邮件策略** ") 。

3. 在随即显示的展开策略详细信息中，单击 **“删除策略”**。

4. 在随即显示的警告对话框中，单击 **“是”**。

无法删除默认策略。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略

如前所述，出站垃圾邮件策略由出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则组成。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则之间的差异很明显。 您可以使用** \* -HostedOutboundSpamFilterPolicy** cmdlet 管理出站垃圾邮件筛选器策略，还可以使用** \* -HostedOutboundSpamFilterRule** cmdlet 管理出站垃圾邮件筛选器规则。

- 在 PowerShell 中，先创建出站垃圾邮件筛选器策略，然后创建出站垃圾邮件筛选器规则，以标识应用该规则的策略。
- 在 PowerShell 中，可以单独修改出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则中的设置。
- 从 PowerShell 删除出站垃圾邮件筛选器策略时，不会自动删除相应的出站垃圾邮件筛选器规则，反之亦然。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>使用 PowerShell 创建出站垃圾邮件策略

在 PowerShell 中创建出站垃圾邮件策略的过程分为两个步骤：

1. 创建出站垃圾邮件筛选器策略。
2. 创建用于指定应用规则的出站垃圾邮件筛选器策略的出站垃圾邮件筛选器规则。

 **注意**：

- 您可以创建新的出站垃圾邮件筛选器规则，并向其分配现有的未关联的出站垃圾邮件筛选器策略。 一个出站垃圾邮件筛选器规则不能与多个出站垃圾邮件筛选器策略相关联。

- 您可以在 PowerShell 中的新出站垃圾邮件筛选器策略中配置以下设置，这些设置在安全 & 合规性中心中不可用，直到您创建了策略：

  - 将新策略创建为_Enabled_ `$false` **HostedOutboundSpamFilterRule** cmdlet) 上启用的禁用 (。
  - 在_Priority_ _\<Number\>_ **HostedOutboundSpamFilterRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。

- 在 PowerShell 中创建的新的出站垃圾邮件筛选器策略在安全 & 合规性中心中不可见，除非您将策略分配给垃圾邮件筛选器规则。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>步骤1：使用 PowerShell 创建出站垃圾邮件筛选器策略

若要创建出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本示例将使用以下设置创建名为 Contoso 行政主管的新出站垃圾邮件筛选器策略：

- 收件人速率限制限制为默认值的较小值。 有关详细信息，请参阅 [在 Microsoft 365 选项中发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 达到其中一个限制后，用户将被阻止发送邮件。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>步骤2：使用 PowerShell 创建出站垃圾邮件筛选器规则

若要创建出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

本示例使用以下设置创建名为 Contoso 行政主管的新出站垃圾邮件筛选器规则：

- 名为 "Contoso 行政主管" 的出站垃圾邮件筛选器策略与规则相关联。

- 此规则应用于“Contoso Executives Group”组中的成员。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>使用 PowerShell 查看出站垃圾邮件筛选器策略

若要返回所有出站垃圾邮件筛选器策略的摘要列表，请运行以下命令：

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

若要返回有关特定出站垃圾邮件筛选器策略的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

本示例将返回名为 "主管" 的出站垃圾邮件筛选器策略的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>使用 PowerShell 查看出站垃圾邮件筛选器规则

若要查看现有的出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

若要返回所有出站垃圾邮件筛选器规则的摘要列表，请运行以下命令：

```PowerShell
Get-HostedOutboundSpamFilterRule
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

若要返回有关特定出站垃圾邮件筛选器规则的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

本示例将返回名为 Contoso 行政主管的出站垃圾邮件筛选器规则的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>使用 PowerShell 修改出站垃圾邮件筛选器策略

按照本主题前面的 " [步骤1：使用 PowerShell 创建出站垃圾邮件筛选器策略](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) " 一节中所述，在 PowerShell 中修改恶意软件筛选器策略时，可以使用相同的设置。

> [!NOTE]
> 无法重命名出站垃圾邮件筛选器策略， (**HostedOutboundSpamFilterPolicy** Cmdlet 没有 _名称_ 参数) 。 当您在安全 & 合规中心中重命名出站垃圾邮件策略时，您只是重命名出站垃圾邮件筛选器 _规则_。

若要修改出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>使用 PowerShell 修改出站垃圾邮件筛选器规则

在 PowerShell 中修改出站垃圾邮件筛选器规则时，唯一不可用的设置是允许您创建已禁用规则的 _启用_ 参数。 若要启用或禁用现有的出站垃圾邮件筛选器规则，请参阅下一节。

否则，在 PowerShell 中修改出站垃圾邮件筛选器规则时，没有其他设置可用。 按照本主题前面的 " [步骤2：使用 PowerShell 创建出站垃圾邮件筛选器规则](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) " 一节中所述，创建规则时，可以使用相同的设置。

若要修改出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>使用 PowerShell 启用或禁用出站垃圾邮件筛选器规则

启用或禁用 PowerShell 中的出站垃圾邮件筛选器规则可启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选器规则和分配的出站垃圾邮件筛选器策略) 。 您不能启用或禁用默认出站垃圾邮件策略 (始终将其应用于所有收件人) 。

若要在 PowerShell 中启用或禁用出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

本示例禁用名为 "Marketing 部门" 的出站垃圾邮件筛选器规则。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>使用 PowerShell 设置出站垃圾邮件筛选器规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置出站垃圾邮件筛选器规则的优先级，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - 若要在创建时设置新规则的优先级，请改用**HostedOutboundSpamFilterRule** cmdlet 上的_priority_参数。
>
> - 出站默认垃圾邮件筛选器策略不具有相应的垃圾邮件筛选器规则，它始终具有不可修改的优先级值 **下限**。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>使用 PowerShell 删除出站垃圾邮件筛选器策略

当您使用 PowerShell 删除出站垃圾邮件筛选器策略时，不会删除相应的出站垃圾邮件筛选器规则。

若要删除 PowerShell 中的出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

本示例删除名为 "Marketing 部门" 的出站垃圾邮件筛选器策略。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>使用 PowerShell 删除出站垃圾邮件筛选器规则

当您使用 PowerShell 删除出站垃圾邮件筛选器规则时，将不会删除相应的出站垃圾邮件筛选器策略。

若要删除 PowerShell 中的出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

本示例删除名为 "Marketing 部门" 的出站垃圾邮件筛选器规则。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>详细信息

[从“受限的用户”门户中删除被阻止的用户](removing-user-from-restricted-users-portal-after-spam.md)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

[自动转发的消息报告](mfi-auto-forwarded-messages-report.md)
