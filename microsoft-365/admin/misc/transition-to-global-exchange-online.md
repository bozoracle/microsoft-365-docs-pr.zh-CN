---
title: 更新 MX 记录以转换到全局 Exchange Online 服务
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何从 Microsoft 云德国 Exchange Online 转换到全局 Exchange Online 服务
ms.openlocfilehash: 41628b3032f5b268d5e32501b393fef31663dfc3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399226"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a>更新 MX 记录以转换到全局 Exchange Online 服务

1. 登录到[Microsoft 365 管理门户](https://admin.microsoft.com)，然后转到**设置**  >  **域**

2. 状态将显示在每个域的右侧。 如果你的组织的域指向 Microsoft 云德国 Exchange Online，你将需要更新你的 MX 记录。

3. 单击域，然后单击 "**检测到 DNS 错误"，单击此处查看**。

4. 此页面将提供说明如何修复 MX 记录的说明。 如果你的域注册机构使用[域连接](../setup/add-domain.md#registrars-with-domain-connect)，则可以单击顶部的 "修复我的记录"。 否则，可以按照向导中的链接，获取注册器的分步**说明**。