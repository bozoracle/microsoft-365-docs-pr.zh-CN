---
title: 用于 Skype for Business Server 的 GDPR
description: 了解如何解决本地 Skype for Business Server 和 Lync Server 中的 GDPR 要求。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: aa0d66bcf727b7dd3c545384ec3a4838667a9183
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596399"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a>用于 Skype for Business Server 和 Lync Server 的 GDPR

大多数 Skype for Business Server 和 Lync Server 数据存储在 Exchange Server 中。这包括：

-   对话历史记录

-   语音邮件通知和听录

-   会议邀请

使用[用于 Exchange Server 的 GDPR](gdpr-for-exchange-server.md) 概述的过程来查找、导出或删除这些类型的 GDPR 请求数据。

联系人列表存储在 SQL Server 数据库中。它们可以通过以下方式导出：

-   最终用户自身可以通过右键单击组标题并选择“复制”来导出联系人。这会将该组中的所有联系人复制到剪贴板，然后将其粘贴到任何应用中。

-   可以使用 [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet 导出此类数据。

上传到会议的内容（例如 PowerPoint 文件或讲义）或在会议中生成的内容（例如白板、投票或 Q/A）存储在文件管理器中。如果最终用户重新登录到任何尚未过期的会议并下载任何上传的内容，或在生成内容的情况下创建屏幕截图，也可以导出此类信息。

不在 Exchange 日历和联系人列表中的 MeetNow 会议以及联系人权限（家人、同事等）位于用户数据库中。在 Lync Server 2013 及更高版本中，可以使用 [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet 导出此类数据。
