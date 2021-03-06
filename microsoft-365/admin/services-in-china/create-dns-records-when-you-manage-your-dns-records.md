---
title: 管理 DNS 记录时为 Office 365 创建 DNS 记录
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: '了解如何在管理 DNS 记录时，为由世纪互联运营的 Office 365 创建 DNS 记录。 '
monikerRange: o365-21vianet
ms.openlocfilehash: c05dc1c84465ea06572021610744f0cbe5aa9fea
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779901"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>管理 DNS 记录时为 Office 365 创建 DNS 记录

有关如何为由世纪互联运营的 Office 365 创建 DNS 记录的详细说明，包括邮件路由所需的 MX 记录，请参阅[在 Office 365 的任意 DNS 托管提供程序中创建 dns 记录](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 
  
  
更多选项和要注意的一些事项：
      
-  如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。 有关 DNS 记录所执行的操作的说明，请参阅[DNS 基础知识](../get-help-with-domains/dns-basics.md)。
    
-  某些 DNS 托管提供程序不允许您创建所有必需的记录类型，这会导致[托管提供程序不支持 SRV、CNAME、TXT 或重定向时的服务限制](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。 如果您的提供商不支持 SRV、TXT 或 CNAME 记录，我们建议您将您的[域转移](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name)到[支持所有必需的记录类型的提供商](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。 
    
- 若要查看哪些 DNS 记录是必需的，并找到要用于每个记录的值（包括电子邮件的 MX 记录），请参阅[收集创建 Office 365 DNS 记录所需的信息](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)。 有关 DNS 记录所执行的操作的说明，请参阅[DNS 基础知识](../get-help-with-domains/dns-basics.md)。
    

