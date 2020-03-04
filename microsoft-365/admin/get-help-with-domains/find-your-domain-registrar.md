---
title: 查找你的域注册机构以便使用 Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: 了解如何使用 InterNIC 搜索查找域注册机构和 DNS 托管提供商。
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251153"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="822c3-103">查找你的域注册机构以便使用 Office 365</span><span class="sxs-lookup"><span data-stu-id="822c3-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="822c3-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="822c3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="822c3-105">域名注册机构</span><span class="sxs-lookup"><span data-stu-id="822c3-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="822c3-106">查找域名注册机构</span><span class="sxs-lookup"><span data-stu-id="822c3-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="822c3-107">只有以 *.COM*、*.NET*和 *.EDU*结尾的域才可以使用此工具。</span><span class="sxs-lookup"><span data-stu-id="822c3-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="822c3-108">在[InterNIC 搜索页面](https://go.microsoft.com/fwlink/p/?LinkId=402770)上的“**Whois 搜索**”框中，键入你的域。</span><span class="sxs-lookup"><span data-stu-id="822c3-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="822c3-109">例如  *contoso.com。*</span><span class="sxs-lookup"><span data-stu-id="822c3-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="822c3-110">选择"**域**"选项，然后选择"**提交**"。</span><span class="sxs-lookup"><span data-stu-id="822c3-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="822c3-111">在" **Whois 搜索结果**"页上，查找" **注册机构**"条目。</span><span class="sxs-lookup"><span data-stu-id="822c3-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="822c3-112">此条目列出了针对您的域提供注册机构服务的组织的名称。</span><span class="sxs-lookup"><span data-stu-id="822c3-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="822c3-113">DNS 托管提供商</span><span class="sxs-lookup"><span data-stu-id="822c3-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="822c3-114">查找 DNS 托管提供商</span><span class="sxs-lookup"><span data-stu-id="822c3-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="822c3-115">只有以 *.COM*、*.NET*和 *.EDU*结尾的域才可以使用此工具。</span><span class="sxs-lookup"><span data-stu-id="822c3-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="822c3-116">在 [InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) 搜索页面上的" **Whois 搜索**"框中，键入你的域。</span><span class="sxs-lookup"><span data-stu-id="822c3-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="822c3-117">例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="822c3-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="822c3-118">选择"**域**"选项，然后选择"**提交**"。</span><span class="sxs-lookup"><span data-stu-id="822c3-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="822c3-119">在“**Whois 搜索结果**”页上，查找第一个“**名称服务器**”条目。</span><span class="sxs-lookup"><span data-stu-id="822c3-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="822c3-120">复制在冒号 (:) 之后显示的名称服务器 (NS) 信息，然后将其粘贴到页面顶部的" **搜索**"框中。</span><span class="sxs-lookup"><span data-stu-id="822c3-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="822c3-121">选择"**名称服务器**"，然后选择"**提交**"。</span><span class="sxs-lookup"><span data-stu-id="822c3-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="822c3-p105">在“**Whois 搜索结果**”页上，查找“**注册机构**”条目。此条目列出了拥有您的域的名称服务器的 DNS 托管提供商。</span><span class="sxs-lookup"><span data-stu-id="822c3-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---
