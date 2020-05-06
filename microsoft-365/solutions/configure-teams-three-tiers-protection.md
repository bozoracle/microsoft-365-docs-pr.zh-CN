---
title: 配置具有三层保护的 Teams
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 保护 Microsoft Teams 中文件的配置建议。
ms.openlocfilehash: ae15956579c87241096c24347878f0644d0c6929
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002596"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a><span data-ttu-id="e4ac7-103">配置具有三层保护的 Teams</span><span class="sxs-lookup"><span data-stu-id="e4ac7-103">Configure Teams with three tiers of protection</span></span>

<span data-ttu-id="e4ac7-104">本系列中的文章为如何在 Microsoft Teams 中配置团队及其关联 SharePoint 网站以实现通过轻松协作权衡安全性的文件保护提供了相关建议。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-104">The articles in this series provide recommendations for configuring teams in Microsoft Teams and their associated SharePoint sites for file protection that balances security with ease of collaboration.</span></span>

<span data-ttu-id="e4ac7-105">本文定义了四个不同的配置，首先介绍的是具有最开放的共享策略的公共团队。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-105">This article defines four different configurations, starting with a public team with the most open sharing policies.</span></span> <span data-ttu-id="e4ac7-106">每个额外配置均表示有意义的保护设置，对 Teams 中存储的文件的访问和协作限定为一组相关团队成员。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-106">Each additional configuration represents a meaningful step up in protection, while the ability to access and collaborate on files stored within teams is reduced to the relevant set of team members.</span></span> 

<span data-ttu-id="e4ac7-107">本文中的配置符合 Microsoft 针对数据、标识和设备的三层保护的建议：</span><span class="sxs-lookup"><span data-stu-id="e4ac7-107">The configurations in this article align with Microsoft's recommendations for three tiers of protection for data, identities, and devices:</span></span>

- <span data-ttu-id="e4ac7-108">基线保护</span><span class="sxs-lookup"><span data-stu-id="e4ac7-108">Baseline protection</span></span>

- <span data-ttu-id="e4ac7-109">敏感保护</span><span class="sxs-lookup"><span data-stu-id="e4ac7-109">sensitive protection</span></span>

- <span data-ttu-id="e4ac7-110">高度敏感保护</span><span class="sxs-lookup"><span data-stu-id="e4ac7-110">Highly sensitive protection</span></span>

<span data-ttu-id="e4ac7-111">有关这些保护层以及针对每层建议的功能的详细信息，请参阅以下资源。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-111">For more information about these tiers and capabilities recommended for each tier, see the following resources.</span></span>

- [<span data-ttu-id="e4ac7-112">Office 365 的标识和设备保护</span><span class="sxs-lookup"><span data-stu-id="e4ac7-112">Identity and Device Protection for Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [<span data-ttu-id="e4ac7-113">Office 365 中的文件保护解决方案</span><span class="sxs-lookup"><span data-stu-id="e4ac7-113">File Protection Solutions in Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="three-tiers-at-a-glance"></a><span data-ttu-id="e4ac7-114">三个层级概览</span><span class="sxs-lookup"><span data-stu-id="e4ac7-114">Three tiers at a glance</span></span>

<span data-ttu-id="e4ac7-115">下表总结了各层的配置。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-115">The following table summarizes the configurations for each tier.</span></span> <span data-ttu-id="e4ac7-116">使用这些配置作为起点建议并调整网站配置，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-116">Use these configurations as starting point recommendations and adjust the configurations to meet the needs of your organization.</span></span> <span data-ttu-id="e4ac7-117">可能不需要每一层。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-117">You may not need every tier.</span></span>

||<span data-ttu-id="e4ac7-118">**基准（公共）**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-118">**Baseline (Public)**</span></span>|<span data-ttu-id="e4ac7-119">**基准（专用）**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-119">**Baseline (Private)**</span></span>|<span data-ttu-id="e4ac7-120">**敏感**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-120">**Sensitive**</span></span>|<span data-ttu-id="e4ac7-121">**高度敏感**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-121">**Highly sensitive**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4ac7-122">专用或公用团队</span><span class="sxs-lookup"><span data-stu-id="e4ac7-122">Private or public team</span></span>|<span data-ttu-id="e4ac7-123">公开</span><span class="sxs-lookup"><span data-stu-id="e4ac7-123">Public</span></span>|<span data-ttu-id="e4ac7-124">Private</span><span class="sxs-lookup"><span data-stu-id="e4ac7-124">Private</span></span>|<span data-ttu-id="e4ac7-125">Private</span><span class="sxs-lookup"><span data-stu-id="e4ac7-125">Private</span></span>|<span data-ttu-id="e4ac7-126">Private</span><span class="sxs-lookup"><span data-stu-id="e4ac7-126">Private</span></span>|
|<span data-ttu-id="e4ac7-127">谁可以访问？</span><span class="sxs-lookup"><span data-stu-id="e4ac7-127">Who has access?</span></span>|<span data-ttu-id="e4ac7-128">组织中的每个人（包括 B2B 用户）。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-128">Everybody in the organization, including B2B users.</span></span>|<span data-ttu-id="e4ac7-129">仅限团队成员。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-129">Only members of the team.</span></span> <span data-ttu-id="e4ac7-130">其他人可以请求访问关联的网站。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-130">Others can request access to the associated site.</span></span>|<span data-ttu-id="e4ac7-131">仅限团队成员。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-131">Only members of the team.</span></span>|<span data-ttu-id="e4ac7-132">仅限团队成员。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-132">Only members of the team.</span></span>|
|<span data-ttu-id="e4ac7-133">专用频道</span><span class="sxs-lookup"><span data-stu-id="e4ac7-133">Private channels</span></span>|<span data-ttu-id="e4ac7-134">所有者和成员可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="e4ac7-134">Owners and members can create private channels</span></span>|<span data-ttu-id="e4ac7-135">所有者和成员可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="e4ac7-135">Owners and members can create private channels</span></span>|<span data-ttu-id="e4ac7-136">仅所有者可创建专用频道</span><span class="sxs-lookup"><span data-stu-id="e4ac7-136">Only owners can create private channels</span></span>|<span data-ttu-id="e4ac7-137">仅所有者可创建专用频道</span><span class="sxs-lookup"><span data-stu-id="e4ac7-137">Only owners can create private channels</span></span>|
|<span data-ttu-id="e4ac7-138">网站级别来宾访问</span><span class="sxs-lookup"><span data-stu-id="e4ac7-138">Site-level guest access</span></span>|<span data-ttu-id="e4ac7-139">**新来宾和现有来宾**（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-139">**New and existing guests** (default).</span></span>|<span data-ttu-id="e4ac7-140">**新来宾和现有来宾**（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-140">**New and existing guests** (default).</span></span>|<span data-ttu-id="e4ac7-141">**新来宾和现有来宾** 或 **仅组织中的人员** 取决于团队需求。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-141">**New and existing guests** or **Only people in your organization** depending on team needs.</span></span>|<span data-ttu-id="e4ac7-142">**新来宾和现有来宾** 或 **仅组织中的人员** 取决于团队需求。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-142">**New and existing guests** or **Only people in your organization** depending on team needs.</span></span>|
|<span data-ttu-id="e4ac7-143">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="e4ac7-143">Site sharing settings</span></span>|<span data-ttu-id="e4ac7-144">**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-144">**Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>|<span data-ttu-id="e4ac7-145">**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-145">**Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>|<span data-ttu-id="e4ac7-146">**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-146">**Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>|<span data-ttu-id="e4ac7-147">**仅网站所有者可以共享文件、文件夹和网站**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-147">**Only site owners can share files, folders, and the site**.</span></span><br><span data-ttu-id="e4ac7-148">访问请求**关闭**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-148">Access requests **Off**.</span></span>|
|<span data-ttu-id="e4ac7-149">网站级别未托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="e4ac7-149">Site-level unmanaged device access</span></span>|<span data-ttu-id="e4ac7-150">**从桌面版应用程序、移动应用程序和 web 完全访问**（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-150">**Full access from desktop apps, mobile apps, and the web** (default).</span></span>|<span data-ttu-id="e4ac7-151">**从桌面版应用程序、移动应用程序和 web 完全访问**（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-151">**Full access from desktop apps, mobile apps, and the web** (default).</span></span>|<span data-ttu-id="e4ac7-152">**允许限制性的 web 访问**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-152">**Allow limited, web-only access**.</span></span>|<span data-ttu-id="e4ac7-153">**阻止访问**。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-153">**Block access**.</span></span>|
|<span data-ttu-id="e4ac7-154">默认共享链接类型</span><span class="sxs-lookup"><span data-stu-id="e4ac7-154">Default sharing link type</span></span>|<span data-ttu-id="e4ac7-155">**仅组织内部人员**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-155">**Ony people in your organization**</span></span>|<span data-ttu-id="e4ac7-156">**仅组织内部人员**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-156">**Ony people in your organization**</span></span>|<span data-ttu-id="e4ac7-157">**特定人员**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-157">**Specific people**</span></span>|<span data-ttu-id="e4ac7-158">**现有访问权限者**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-158">**People with existing access**</span></span>|
|<span data-ttu-id="e4ac7-159">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="e4ac7-159">Sensitivity labels</span></span>|<span data-ttu-id="e4ac7-160">无</span><span class="sxs-lookup"><span data-stu-id="e4ac7-160">None</span></span>|<span data-ttu-id="e4ac7-161">无</span><span class="sxs-lookup"><span data-stu-id="e4ac7-161">None</span></span>|<span data-ttu-id="e4ac7-162">敏感度标签用于对团队进行分类并控制来宾共享和未托管设备访问。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-162">Sensitivity label used to classify the team and control guest sharing and unmanaged device access.</span></span>|<span data-ttu-id="e4ac7-163">敏感度标签用于对团队进行分类并控制来宾共享和未托管设备访问。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-163">Sensitivity label used to classify the team and control guest sharing and unmanaged device access.</span></span> <span data-ttu-id="e4ac7-164">还可在文件上使用标签对文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-164">Label can also be used on files to encrypt files.</span></span>|

<span data-ttu-id="e4ac7-165">[具有安全隔离的团队](secure-teams-security-isolation.md)是高度敏感选项的变体，为一个团队使用唯一敏感度标签，从而提供更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-165">A variation of the Highly sensitive option, [Teams with security isolation](secure-teams-security-isolation.md) uses a unique sensitivity label for one team, which provides additional security.</span></span> <span data-ttu-id="e4ac7-166">可以使用此标签来加密文件，只有该团队成员才能读取它们。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-166">You can use this label to encrypt files, and only members of that team will be able to read them.</span></span>

<span data-ttu-id="e4ac7-167">基线保护同时公共和私人团队。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-167">Baseline protection includes public private teams.</span></span> <span data-ttu-id="e4ac7-168">组织中的任何人均可发现和访问公共团队。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-168">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="e4ac7-169">只有团队成员可以发现和访问私人团队。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-169">Private teams can only be discovered and accessed by members of the team.</span></span> <span data-ttu-id="e4ac7-170">这两种配置都将共享 SharePoint 网站的共享限制为团队所有者，以帮助进行权限管理。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-170">Both of these configurations restrict sharing of the associated SharePoint site to team owners to assist in permissions management.</span></span>

<span data-ttu-id="e4ac7-171">敏感和高度敏感保护团队是私有团队，在该团队中对关联站点的共享和访问请求受到限制，并且敏感度标签用于设置有关来宾共享、设备访问和内容加密策略。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-171">Teams for sensitive and highly sensitive protection are private teams in which sharing and the requesting of access for the associated site is limited and sensitivity labels are used to set policies around guest sharing, device access, and content encryption.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="e4ac7-172">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="e4ac7-172">Sensitivity labels</span></span>

<span data-ttu-id="e4ac7-173">敏感层和高度敏感层使用敏感度标签来帮助保护团队和其文件。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-173">The sensitive and highly sensitive tiers use sensitivity labels to help secure the team and its files.</span></span> <span data-ttu-id="e4ac7-174">为实现这些层，必须启用[用于保护 Microsoft Teams、Office 365 和 SharePoint 网站中内容的敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-174">To implement these tiers, you must enable [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

<span data-ttu-id="e4ac7-175">虽然基线层不需要敏感度标签，但请考虑创建“常规”标签，然后要求标记所有团队。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-175">While the baseline tier does not require sensitivity labels, consider creating a "general" label and then requiring that all teams be labeled.</span></span> <span data-ttu-id="e4ac7-176">这将有助于确保用户在创建团队时就敏感度做出有意识的选择。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-176">This will help ensure that users make a conscious choice about sensitivity when they create a team.</span></span> <span data-ttu-id="e4ac7-177">如果计划部署敏感或高度敏感层，建议创建一个“常规”标签，该标签可用于基线团队和不敏感的文件。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-177">If you plan to deploy the sensitive or highly sensitive tiers, we do recommend creating a "general" label that you can use for baseline teams and for files that are not sensitive.</span></span>

<span data-ttu-id="e4ac7-178">如果不熟悉敏感度标签，建议阅读[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels)以开始使用。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-178">If you're new to using sensitivity labels, we recommend reading [Get started with sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels) to get started.</span></span> 

<span data-ttu-id="e4ac7-179">如果已经在组织中推出了敏感度标签，请考虑敏感和高度敏感层中所使用的标签如何与整体标签策略配合使用。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-179">If you have already rolled out sensitivity labels in your organization, consider how the labels used in the sensitive and highly sensitive tiers fit with your overall label strategy.</span></span> 

## <a name="sharing-the-sharepoint-site"></a><span data-ttu-id="e4ac7-180">共享 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="e4ac7-180">Sharing the SharePoint site</span></span>

<span data-ttu-id="e4ac7-181">每个团队都有存储文档的关联 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-181">Each team has an associated SharePoint site where documents are stored.</span></span> <span data-ttu-id="e4ac7-182">（这是团队渠道中的“**文件**”选项卡。）SharePoint 网站保留自己的权限管理，但关联到团队权限。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-182">(This is the **Files** tab in a teams channel.) The SharePoint site retains its own permission management, but is linked to team permissions.</span></span> <span data-ttu-id="e4ac7-183">团队所有者被包含为网站所有者，而团队成员被包含为关联网站中的站点成员。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-183">Team owners are included as site owners and team members are included as site members in the associated site.</span></span>

<span data-ttu-id="e4ac7-184">生成的权限允许：</span><span class="sxs-lookup"><span data-stu-id="e4ac7-184">The resulting permissions allow:</span></span>

- <span data-ttu-id="e4ac7-185">团队所有者管理网站，并对网站内容拥有完全控制权。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-185">Team owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="e4ac7-186">团队成员在网站上创建和编辑文件。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-186">Team members to create and edit files on the site.</span></span> 

<span data-ttu-id="e4ac7-187">默认情况下，团队所有者和成员可以与团队外部的人员共享网站本身，而无需将其实际添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-187">By default, team owners and members can share the site itself with people outside the team without actually adding them to the team.</span></span> <span data-ttu-id="e4ac7-188">建议不要使用此方法，因为这会让用户管理变得复杂，并可能会导致非团队成员的人员能够在团队拥有者不知情的情况下存取团队文件。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-188">We recommend against this as it complicates user management and can lead to people who are not team members having access to team files without team owners realizing it.</span></span> <span data-ttu-id="e4ac7-189">为了防止这种情况，从基线保护级别开始，我们建议仅允许所有者直接共享站点。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-189">To help prevent this, starting in the baseline level of protection, we recommend that only owners be allowed to share the site directly.</span></span>

<span data-ttu-id="e4ac7-190">尽管团队没有只读权限选项，但 SharePoint 网站有此权限。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-190">While teams do not have a read-only permission option, the SharePoint site does.</span></span> <span data-ttu-id="e4ac7-191">如果你的合作伙伴组利益干系人能够查看团队文件但是不能编辑，考虑直接将其添加至具有“读取”权限的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-191">If you have stakeholders of partner groups who need to be able to view team files but not edit them, consider adding them directly to the SharePoint site with Read permissions.</span></span>

## <a name="sharing-files-and-folders"></a><span data-ttu-id="e4ac7-192">共享文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="e4ac7-192">Sharing files and folders</span></span>

<span data-ttu-id="e4ac7-193">默认情况下，团队所有者和成员都可以与团队外部的人员共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-193">By default, both owners and members of the team can share files and folders with people outside the team.</span></span> <span data-ttu-id="e4ac7-194">如果允许来宾共享，则其中可能包括组织外部人员。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-194">This may include people outside your organization, if you have allowed guest sharing.</span></span> <span data-ttu-id="e4ac7-195">在所有三个层中，我们都会更新默认共享链接类型，有助于避免意外的过度共享。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-195">In all three tiers, we update the default sharing link type to help avoid accidental oversharing.</span></span> <span data-ttu-id="e4ac7-196">在高度敏感层中，我们仅将这种共享限制为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-196">In the highly sensitive tier, we restrict such sharing to team owners only.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="e4ac7-197">来宾共享</span><span class="sxs-lookup"><span data-stu-id="e4ac7-197">Guest sharing</span></span>

<span data-ttu-id="e4ac7-198">如果需要与组织外部人员进行协作，建议配置 [SharePoint 和 OneDrive 与 Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) 集成，以获得最佳的共享和管理体验。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-198">If you need to collaborate with people outside your organization, we recommend configuring [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) for the best sharing and administration experience.</span></span>

<span data-ttu-id="e4ac7-199">默认情况下，团队来宾共享处于关闭状态，但 Office 365 组（存储团队成员资格）和 SharePoint 的共享处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-199">Teams guest sharing is off by default, though sharing for Office 365 groups (where team membership is stored) and SharePoint is on.</span></span> <span data-ttu-id="e4ac7-200">我们在基线层中启用 Teams共享，如果需要，可以使用敏感度标签在敏感层和高度敏感层中将其关闭。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-200">We turn Teams sharing on in the baseline tier, and you can turn it off if needed in the sensitive and highly sensitive tiers by using a sensitivity label.</span></span>

<span data-ttu-id="e4ac7-201">敏感度标签仅影响团队的来宾共享。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-201">The sensitivity label only affects guest sharing for the team.</span></span> <span data-ttu-id="e4ac7-202">关联 SharePoint 网站的来宾共享设置是单独控制的，我们协调敏感层和高度敏感层的设置。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-202">Guest sharing settings for the associated SharePoint site are controlled separately, and we have you align the two settings for both the sensitive and highly sensitive tiers.</span></span>

<span data-ttu-id="e4ac7-203">在高度敏感层，我们将敏感度标签配置为加密应用标签的文件。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-203">In the highly sensitive tier, we configure the sensitivity label to encrypt files to which it is applied.</span></span> <span data-ttu-id="e4ac7-204">如果需要来宾访问这些文件，必须在创建标签时必须授予他们权限。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-204">If you need guests to have access to these files, you must give them permissions when you create the label.</span></span>

<span data-ttu-id="e4ac7-205">如果需要与组织外部的人员进行协作，强烈建议基线层和敏感层或高度敏感层启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-205">We highly recommend that you leave guest sharing on for the baseline tier and for the sensitive or highly sensitive tiers if you need to collaborate with people outside your organization.</span></span> <span data-ttu-id="e4ac7-206">相比将文件作为附件发送到电子邮件中，Microsoft 365 的来宾共享功能提供了更为安全和可管理的共享体验。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-206">The guest sharing features in Microsoft 365 provide a much more secure and governable sharing experience than sending files as attachments in email messages.</span></span> <span data-ttu-id="e4ac7-207">用户使用不受管制的消费产品与合法的外部合作者共享时，还降低了影子 IT 的风险。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-207">It also reduces the risk of shadow IT where users use ungoverned consumer products to share with legitimate external collaborators.</span></span>

<span data-ttu-id="e4ac7-208">请参阅以下参考材料，为组织创建安全高效的来宾共享环境：</span><span class="sxs-lookup"><span data-stu-id="e4ac7-208">See the following references to create a secure and productive guest sharing environment for your organization:</span></span>

- [<span data-ttu-id="e4ac7-209">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="e4ac7-209">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="e4ac7-210">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="e4ac7-210">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="e4ac7-211">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="e4ac7-211">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a><span data-ttu-id="e4ac7-212">非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="e4ac7-212">Access from unmanaged devices</span></span>

<span data-ttu-id="e4ac7-213">对于敏感层和高度敏感层，我们使用敏感度标签限制对 SharePoint 内容的访问。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-213">For the sensitive and highly sensitive tiers, we restrict access to SharePoint content with sensitivity labels.</span></span> <span data-ttu-id="e4ac7-214">Azure AD 条件访问提供很多用于确定用户如何访问 Microsoft 365 的选项，包括基于位置、风险、设备合规性和其他因素的限制。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-214">Azure AD conditional access offers many options for determining how people access Microsoft 365, including limitations based on location, risk, device compliance, and other factors.</span></span> <span data-ttu-id="e4ac7-215">建议阅读[什么是条件访问？](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)，并考虑哪些其他策略可能适用于你的组织。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-215">We recommend you read [What is Conditional Access?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) and consider which additional policies might be appropriate for your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="e4ac7-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e4ac7-216">Next step</span></span>

<span data-ttu-id="e4ac7-217">首先[配置基线保护级别](configure-teams-baseline-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-217">Start by [configuring the baseline level of protection](configure-teams-baseline-protection.md).</span></span> <span data-ttu-id="e4ac7-218">如果需要，可在基线上添加[敏感保护](configure-teams-sensitive-protection.md)和[高度敏感保护](configure-teams-highly-sensitive-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac7-218">If needed you can add [sensitive protection](configure-teams-sensitive-protection.md) and [highly sensitive protection](configure-teams-highly-sensitive-protection.md) on top of the baseline.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ac7-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4ac7-219">See also</span></span>

[<span data-ttu-id="e4ac7-220">Microsoft Teams 中的安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="e4ac7-220">Security and compliance in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[<span data-ttu-id="e4ac7-221">安全与合规中心警报策略</span><span class="sxs-lookup"><span data-stu-id="e4ac7-221">Alert policies in the security and compliance center</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)