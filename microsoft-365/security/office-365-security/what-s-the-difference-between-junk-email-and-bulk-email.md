---
title: '&apos;垃圾邮件和批量电子邮件之间有何区别？'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的垃圾邮件 (垃圾邮件) 和批量邮件 (灰色邮件) 之间的差异。
ms.openlocfilehash: 1e11f897a145f7b34acc81e1d132d6babac08979
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195469"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP 中的垃圾邮件和批量电子邮件之间有何区别？

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online 保护的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，客户有时会问： "垃圾邮件和批量电子邮件的区别是什么？" 本主题介绍 EOP 中可用的控件的区别和说明。

- **垃圾邮件** 是垃圾邮件，它是在正确识别) 的情况下 (的主动和不需要的邮件。 默认情况下，EOP 会根据源电子邮件服务器的信誉拒绝垃圾邮件。 如果邮件通过源 IP 检查，则会将其发送到垃圾邮件筛选。 如果通过垃圾邮件筛选功能将邮件分类为垃圾邮件，则默认情况下邮件将 () 传递给预期收件人并移至其 "垃圾邮件" 文件夹。

  - 您可以配置要对垃圾邮件筛选 verdicts 执行的操作。 有关说明，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

  - 如果您不同意垃圾邮件筛选结论，可以通过多种方式报告您认为是垃圾邮件或非垃圾邮件的邮件，如 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)中所述。

- **批量电子邮件** (也称为 " _灰色邮件_) "，更难以分类。 垃圾邮件是一种恒定的威胁，而批量电子邮件通常是一次性广告或市场营销邮件。 有些用户希望批量电子邮件 (，事实上，他们已特意注册以接收) ，而其他用户认为批量电子邮件是垃圾邮件。 例如，某些用户希望接收来自 Contoso Corporation 的广告邮件或对即将到来的会议的网络安全的邀请，而其他用户认为这些邮件是垃圾邮件。

  有关标识批量电子邮件的详细信息，请参阅 [EOP 中的批量投诉级别 (BCL) ](bulk-complaint-level-values.md)。

## <a name="how-to-manage-bulk-email"></a>如何管理批量邮件

由于批量电子邮件的混合反应，没有适用于每个组织的通用指南。

反垃圾邮件策略具有用于将批量电子邮件标识为垃圾邮件的默认 BCL 阈值。 管理员可以增加或减少阈值。 有关详细信息，请参阅下列主题：

- [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

易于忽略的另一个选项：如果用户 complains 接收批量电子邮件，但邮件来自传递 EOP 中的垃圾邮件筛选的著名发件人，请让用户在批量电子邮件中检查是否有 "取消订阅" 选项。
