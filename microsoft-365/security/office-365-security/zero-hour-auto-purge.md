---
title: '零小时自动清除 (ZAP) '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 (ZAP) 如何在 Exchange Online 邮箱中追溯将传递的邮件移动到追溯被发现为垃圾邮件或网络钓鱼的 "垃圾邮件" 文件夹或隔离中的零小时自动清除。
ms.openlocfilehash: 31e546ddf6e93ed0a265aef3737182cf30ae5a95
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327971"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online 中的零小时自动清除 (ZAP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>ZAP 的基本功能

在 Exchange Online 中有邮箱的 Microsoft 365 组织中，零小时自动清除 (ZAP) 是一种电子邮件保护功能，追溯检测并 neutralizes 已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。

ZAP 在独立的 Exchange Online Protection (EOP) 保护本地 Exchange 邮箱的环境中不起作用。

## <a name="how-zap-works"></a>ZAP 的工作方式

垃圾邮件和恶意软件签名每天都会在服务中实时更新。 但是，用户仍可以出于各种原因（包括内容在传递给用户后 weaponized 的情况）接收恶意邮件。 ZAP 通过持续监控对服务中的垃圾邮件和恶意软件签名的更新来解决此问题。 ZAP 可以查找和删除用户邮箱中已有的邮件。

对于用户而言，ZAP 操作是无缝的;如果检测到并移动了邮件，则不会收到通知。

[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则 (也称为 "传输规则) "、"收件箱规则" 或 "其他筛选器" 优先于 ZAP。 与邮件流中的操作类似，这意味着即使服务确定所传递的邮件需要 ZAP，也不会由于安全发件人配置而导致邮件不起作用。 这是在将邮件配置为绕过筛选时要注意的另一个原因。

### <a name="malware-zap"></a>恶意软件 ZAP

对于在传递后发现包含恶意软件的已 **读或未读邮件** ，ZAP 将隔离包含恶意软件附件的邮件。 只有管理员可以查看和管理隔离中的恶意软件消息。

默认情况下，在反恶意软件策略中启用恶意软件 ZAP。 有关详细信息，请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>网络钓鱼 ZAP

对于在传递后被标识为网络钓鱼的已 **读或未读邮件** ，ZAP 结果取决于为适用的反垃圾邮件策略中的 **网络钓鱼电子邮件** 筛选判定的操作。 以下列表介绍了针对网络钓鱼的可用筛选判定操作及其可能的 ZAP 结果：

- **添加 X 标头，将****带有文本的主题行预置**： ZAP 对邮件不执行任何操作。

- **将邮件移动到垃圾邮件**： ZAP 将邮件移动到 "垃圾邮件" 文件夹，只要邮箱中启用了垃圾邮件规则 (默认情况下，将启用该规则) 。 有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

- **将邮件重定向到电子邮件地址**， **删除邮件**， **隔离邮件**： ZAP 隔离邮件。

默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，而 **仿冒电子邮件** 筛选判定的默认操作是 **隔离邮件**，这意味着网络钓鱼 ZAP 默认隔离邮件。

有关配置垃圾邮件筛选 verdicts 的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="spam-zap"></a>垃圾邮件 ZAP

对于在传递后被标识为垃圾邮件的 **未读邮件** ，ZAP 结果取决于为适用的反垃圾邮件策略中的 **垃圾邮件** 筛选判定所配置的操作。 以下列表介绍了针对垃圾邮件的可用筛选判定操作及其可能的 ZAP 结果：

- **添加 X 标头，将****带有文本的主题行预置**： ZAP 对邮件不执行任何操作。

- **将邮件移动到垃圾邮件**： ZAP 将邮件移动到 "垃圾邮件" 文件夹，只要邮箱中启用了垃圾邮件规则 (默认情况下，将启用该规则) 。 有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

- **将邮件重定向到电子邮件地址**， **删除邮件**， **隔离邮件**： ZAP 隔离邮件。 最终用户可以查看和管理自己的垃圾邮件隔离邮件。

默认情况下，在反垃圾邮件策略中启用垃圾邮件 ZAP， **垃圾** 邮件筛选判定的默认操作是 **将邮件移动到垃圾邮件文件夹**，这意味着垃圾邮件 ZAP 在默认情况下将 **未读** 邮件移动到 "垃圾邮件" 文件夹。

有关配置垃圾邮件筛选 verdicts 的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Office 365 高级威胁防护 (Office 365 ATP) 的 ZAP 注意事项

ZAP 不会隔离在安全附件扫描中的 [动态传递](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 过程中的任何邮件，或者 EOP 恶意软件筛选已将附件替换为 **恶意软件警报 Text.txt** 文件。 如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并将反垃圾邮件策略中的筛选判定项设置为对邮件执行某些操作 (移至 "垃圾邮件"、"重定向"、"删除" 或 "隔离) "，则 ZAP 将默认为 "移动到垃圾邮件" 操作。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否移动了邮件

若要确定 ZAP 是否移动了邮件，可以使用 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report) 或 [威胁浏览器 (和实时检测) ](threat-explorer.md)。 请注意，作为系统操作，不会在 Exchange 邮箱审核日志中记录 ZAP。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>如果将合法邮件移动到 "垃圾邮件" 文件夹中，会发生什么情况？

您应遵循正常的报告过程 [误报](report-junk-email-messages-to-microsoft.md)。 将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是，该服务已确定邮件是垃圾邮件还是恶意邮件。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>如果我使用隔离文件夹而不是垃圾邮件文件夹，该怎么办？

根据本主题前面所述的配置反垃圾邮件策略，ZAP 将对邮件执行操作。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>如果我使用安全发件人、邮件流规则或允许/阻止的发件人列表，该怎么办？

安全发件人、邮件流规则或阻止和允许组织设置优先。 由于服务正在执行您配置的操作，这些邮件将从 ZAP 中排除。 这是在将邮件配置为绕过筛选时要注意的另一个原因。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>如果邮件移动到另一个文件夹 (例如收件箱规则) ，该怎么办？

只要邮件尚未删除，或者只要相同或更强的操作尚未应用，ZAP 仍可正常工作。 例如，如果网络钓鱼策略设置为 "隔离"，并且用户或管理员已经 junked 了该电子邮件，则隔离将执行操作以隔离该文件。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP 对邮箱的保留有何影响？

ZAP 不会在保留邮箱时隔离邮箱中的邮件。 ZAP 可以根据为反垃圾邮件策略中的垃圾邮件或网络钓鱼判定所配置的操作将邮件移动到 "垃圾邮件" 文件夹。

有关 Exchange Online 中的保留的详细信息，请参阅 [Exchange online 中的就地保留和诉讼保留](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。
