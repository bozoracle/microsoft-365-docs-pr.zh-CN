---
title: 撤销由高级邮件加密加密的电子邮件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为管理员和邮件发件人，您可以吊销使用 Office 365 高级邮件加密进行加密的某些电子邮件。
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868932"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>撤销由高级邮件加密加密的电子邮件

电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。 Office 365 高级邮件加密包含在 [Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 (非盈利性员工定价) 、Office 365 企业版 E5 (非盈利性员工定价) 和 Office 365 教育版 A5。 如果您的组织具有不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加 Microsoft 365 E3、Microsoft 365 E3 (非盈利性的员工定价) 或 Office 365 高级合规性 SKU 附加 for Microsoft 365 E3、Microsoft 365 E3 (非盈利性员工定价) 或 Office 365 Sku 购买。

本文是有关 [Office 365 邮件加密](ome.md)的更多系列文章的一部分。

如果使用 Office 365 高级邮件加密对邮件进行了加密，并且您是 Microsoft 365 管理员，或者是邮件的发件人，则可以在特定条件下撤销邮件。 管理员使用 PowerShell 撤消邮件。 作为发件人，您可以吊销直接从 Outlook 网页上发送的邮件。 本文介绍了可以进行吊销的情况以及执行操作的方法。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤销的加密电子邮件

如果收件人收到基于链接的、品牌加密的电子邮件，则管理员和邮件发件人可以撤销加密电子邮件。 如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验，则无法撤消该邮件。

收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型： Office 365 和 Microsoft 帐户收件人 (例如，outlook.com 用户) 在受支持的 Outlook 客户端中获取内嵌体验。 所有其他收件人类型（如 Gmail 和 Yahoo 收件人）都获得了基于链接的体验。

管理员和邮件发件人可以使用从 web 上的 Outlook 直接应用的加密来吊销加密邮件。 例如，使用 "仅加密" 选项加密的邮件。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="显示 web 上的 Outlook 中的 "仅加密" 选项的屏幕截图。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已撤销加密电子邮件的收件人体验

一旦电子邮件被吊销，收件人通过 Office 365 邮件加密门户访问加密的电子邮件时，会收到错误消息： "邮件已被发件人吊销"。

![显示已吊销加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>如何撤消已发送的加密邮件

若要撤消已发送的加密邮件，请完成以下步骤

1. 在 web 上的 Outlook 中，在 " **已发送** " 文件夹中浏览到要撤消的邮件。

   如果邮件是可吊销的，您将在邮件顶部看到 "删除外部访问" 链接。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="显示要在 Outlook 网页版中吊销的加密邮件的屏幕截图。":::

2. 单击 " **删除外部访问权限** " 以撤消邮件。

   该消息显示其状态为 "已吊销"。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="在 Outlook 网页版中显示已撤销加密邮件的屏幕截图。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>如何以管理员身份撤消加密邮件

Microsoft 365 管理员按照以下常规步骤撤销符合条件的加密电子邮件：

- 获取电子邮件的邮件 ID。
- 验证您是否可以撤消邮件。
- 吊销邮件。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步骤 1. 获取电子邮件的邮件 ID

在您可以撤销加密邮件之前，请先收集邮件的邮件 ID。 MessageId 的格式通常为：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多种方法可查找要吊销的电子邮件的邮件 ID。 本节介绍了几个选项，但您可以使用任何提供该 ID 的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>使用安全 &amp; 合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID

1. [在安全 & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)，按发件人或收件人搜索电子邮件。

2. 找到电子邮件后，选择它以显示 **邮件跟踪详细信息** 窗格。 展开 **详细信息** 以查找邮件 ID。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>在安全合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID &amp;

1. 在 "安全 &amp; 合规性中心" 中，导航到 " **邮件加密" 报告**。 有关此报告的信息，请参阅 [查看安全 &amp; 合规性中心中的电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。

2. 选择 " **查看详细信息** " 表，并确定要撤消的邮件。

3. 双击邮件以查看包含邮件 ID 的详细信息。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步骤 2. 验证邮件是否可吊销

若要验证是否可以撤消邮件，请检查安全合规性中心的 **详细信息** 表中的加密报告中是否显示 "吊销状态" 字段 &amp; 。

若要验证是否可以使用 Windows PowerShell 撤消特定的电子邮件，请完成以下步骤。

1. 使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。

2. 运行 OMEMessageStatus cmdlet，如下所示：

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   此命令返回邮件的主题以及邮件是否是不可吊销的。 例如，

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>步骤 3. 撤销邮件

一旦您知道要吊销的电子邮件的邮件 ID，并且已验证该邮件是可吊销的，则可以使用安全 &amp; 合规性中心或 Windows PowerShell 吊销该电子邮件。

使用安全 &amp; 合规中心撤销邮件

1. 使用组织中具有全局管理员权限的工作或学校帐户，连接到安全 & 合规性中心。

2. 在 **加密报告**中，在邮件的 **详细信息** 表中，选择 " **撤消邮件**"。

若要使用 Windows PowerShell 吊销电子邮件，请使用 OMEMessageRevocation cmdlet。

1. 使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行 OMEMessageRevocation cmdlet，如下所示：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要检查电子邮件是否已被吊销，请运行 OMEMessageStatus cmdlet，如下所示：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果吊销成功，则 cmdlet 将返回以下结果：  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [Office 365 高级邮件加密-电子邮件过期](ome-advanced-expiration.md)

- [邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
