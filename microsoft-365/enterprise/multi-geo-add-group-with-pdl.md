---
title: 创建具有特定 PDL 的 Microsoft 365 组
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: 了解如何在多地理位置环境中创建具有指定首选数据位置的 Microsoft 365 组。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5af32827d11289f7a966311080d2c15197786799
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547730"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>创建具有特定 PDL 的 Microsoft 365 组

在多地理位置环境中的用户创建 Microsoft 365 组时，组首选数据位置将自动设置为用户的。 全局管理员、SharePoint 管理员和 Exchange 管理员可在其所选的任何区域中创建组。 

如需使用特定 PDL 创建组，可使用 SharePoint 管理中心或 Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet 执行该操作。 执行此操作时，将在指定 PDL 中设置组邮箱以及与该组相关联的 SharePoint 站点。

若要使用您指定的 PDL 创建 Microsoft 365 组，请转到要在其中创建组网站的地理位置中的 SharePoint 管理中心。

例如：

如果想要在澳大利亚位置创建一个组站点，可转到 https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. 选择“**+创建**”。
2. 按照流程创建组站点。

将在与你发起站点创建请求的 SharePoint 管理中心相对应的地理位置中预配组站点。 

使用 Exchange PowerShell 

连接到 Exchange Online PowerShell，并传递包含地理位置代码的 *-MailBoxRegion* 参数。

例如： 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![New-UnifiedGroup PowerShell cmdlet 及语法的屏幕截图](../media/multi-geo-new-group-with-pdl-powershell.png)

请注意，SharePoint 组站点设置是按需进行的。 将在组所有者或成员首次试图访问站点时对其进行设置。

## <a name="geo-location-codes"></a>地理位置代码

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>相关主题

[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
