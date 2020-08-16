---
title: 将 SharePoint 网站内容限制到某个地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: 在本文中，您将了解如何将 SharePoint 网站限制为多地理位置环境中的指定地理位置。
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687652"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="004b6-103">将 SharePoint 网站内容限制到某个地理位置</span><span class="sxs-lookup"><span data-stu-id="004b6-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="004b6-104">在某些情况下，你可能会选择通过以下方式将某个站点及其文件内容强制保留在（在其中创建了站点的）地理位置中：防止转移站点，或者防止将站点的文件内容缓存在另一个地理位置中。</span><span class="sxs-lookup"><span data-stu-id="004b6-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="004b6-105">可使用 **RestrictedToGeo** 参数通过 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) cmdlet 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="004b6-105">You can do this by using the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="004b6-106">此参数的默认值为 NULL，但你可以将其更改为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="004b6-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="004b6-107">限制</span><span class="sxs-lookup"><span data-stu-id="004b6-107">Restriction</span></span>|<span data-ttu-id="004b6-108">说明</span><span class="sxs-lookup"><span data-stu-id="004b6-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="004b6-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="004b6-109">NoRestriction</span></span>|<span data-ttu-id="004b6-110">可将站点转移到另一个地理位置。</span><span class="sxs-lookup"><span data-stu-id="004b6-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="004b6-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="004b6-111">BlockMoveOnly</span></span>|<span data-ttu-id="004b6-112">无法将站点转移到另一个地理位置，但可将站点内容缓存在其他地理位置中。</span><span class="sxs-lookup"><span data-stu-id="004b6-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="004b6-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="004b6-113">BlockFull</span></span>|<span data-ttu-id="004b6-114">无法将站点转移到另一个地理位置，并且不会在其他地理位置中缓存完整文件内容。</span><span class="sxs-lookup"><span data-stu-id="004b6-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="004b6-115">文件的标题（从内容中获取）、文件名和文件的其他属性仍可缓存在其他地理位置中。</span><span class="sxs-lookup"><span data-stu-id="004b6-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="004b6-116">将该参数配置为 BlockFull 之前存储在站点中的内容可能继续缓存在其他地理位置中。</span><span class="sxs-lookup"><span data-stu-id="004b6-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="004b6-117">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="004b6-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="004b6-118">例如：</span><span class="sxs-lookup"><span data-stu-id="004b6-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`