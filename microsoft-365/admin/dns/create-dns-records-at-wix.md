---
title: 在 Wix 处为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 了解如何验证你的域并为电子邮件、Skype for Business Online 和其他 Microsoft 的服务设置 DNS 记录。
ms.openlocfilehash: fcc0f8e8187e22dde68149e0f2a80073312bff7f
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814440"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>在 Wix 处为 Microsoft 创建 DNS 记录

如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 DNS 托管提供者是 Wix，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。

下面是要添加的主要记录。 
  
- [添加 TXT 记录进行验证](#add-a-txt-record-for-verification)。
    
- [添加一条 MX 记录，以便发送你的域的电子邮件将会发送到 Microsoft。](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [添加 Microsoft 所需的 5 条 CNAME 记录](#add-the-five-cname-records-that-are-required-for-microsoft)。
    
- [为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)。
    
- [添加 Microsoft 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-microsoft)。
    
在 Wix 添加这些记录后，域将设置为使用 Microsoft 服务。
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 

  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_txt"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 

> [!NOTE]
> WIX 不支持子域的 DNS 条目。
  
1. 若要开始，请使用此链接转到您在 Wix 上的 [域页面](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。 系统将会提示您先登录。
    
2. 在" **我的域** "页面上的" **高级"** 区域中，选择" **编辑 DNS"** 按钮。 
    
3. Select **+ 在** **TXT 中使用 (键) ** DNS 编辑器的行。 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
   ||||
   |:-----|:-----|:-----|
   | 主机名 <br/> | TXT Value <br/> | TTL <br/> |
   |自动填充  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时 <br/> |          |
   
5. 选择 DNS **编辑器** 顶部的"保存 DNS"按钮。 
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
  
3. 在“**设置**”页面上，选择“**开始设置**”。
   
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_mx"> </a>

1. 若要开始，请使用此链接转到您在 Wix 上的 [域页面](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。 系统将会提示您先登录。
    
2. 在" **我的域** "页面上的" **邮箱** "区域中，选择" **配置 MX 记录"** 链接。 
    
3. 从 **"** 您的 **电子邮件提供程序"下拉列表中** 选择"其他"。 
    
4. 选择 **+ 添加另一个**。
    
5. 在新记录的框中，键入或复制并粘贴下表中的值：
    
   | 主机名 | Points to  | 优先级 | TTL |
   |:-----|:-----|:-----|:-----|
   |自动填充 <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。   如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md) |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) | 1 Hour|
   
6. 如果列有任何其他 MX 记录，请删除这些记录。 
    
7. 选择“确定”****。
    
8. 在确认对话框中，选择"确定 **"。**
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 5 条 CNAME 记录
<a name="BKMK_cname"> </a>

1. 若要开始，请使用此链接转到您在 Wix 上的 [域页面](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。 You'll be prompted to login first.
    
2. 在" **我的域** "页面上的" **高级"** 区域中，选择" **编辑 DNS"** 按钮。 
    
3. Select **+ Add another** in the **CNAME (Aliases) 行 ** 中每个 CNAME 记录。 
    
4. 在新记录的框中，键入或复制并粘贴下表中的值：
    
   | 主机名 | Points to  | TTL |
   |:-----|:-----|:-----|
   |自动发现  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
   |sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
   |lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
   |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 Hour <br/> |
   |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. 选择 DNS **编辑器** 顶部的"保存 DNS"按钮。 
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 可以将所需的 Microsoft 值添加到当前记录，这样就拥有  *包含*  两组值的单个 SPF 记录。  
  
1. 若要开始，请使用此链接转到您在 Wix 上的 [域页面](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。 系统将会提示您先登录。
    
2. 在" **我的域** "页面上的" **高级"** 区域中，选择" **编辑 DNS"** 按钮。 
    
3. Select **+ 在** **TXT 中使用 (键) ** DNS 编辑器的行。 
    
4. 在新记录的框中，键入或复制并粘贴下表中的值：
    
   | 主机名 | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[保留此空白]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。<br/> |TXT  <br/> | 1 Hour |
   
5. 选择 DNS **编辑器** 顶部的"保存 DNS"按钮。 
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_srv"> </a>

1. 若要开始，请使用此链接转到您在 Wix 上的 [域页面](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。 系统将会提示您先登录。
    
2. 在" **我的域** "页面上的" **高级"** 区域中，选择" **编辑 DNS"** 按钮。 
    
3. Select **+ 在** DNS 编辑器的 **SRV** 行中添加另一个。 
    
4. 在新记录的框中，键入或复制并粘贴下表中的值：
    
   | 服务 | 协议 | 名称 | 粗细 | 端口 | Target | 优先级 | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |自动填充 |1  |443   |sipdir.online.lync.com |100 |1 Hour |
   |sipfed|tcp |自动填充|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. 选择 DNS **编辑器** 顶部的"保存 DNS"按钮。 
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
