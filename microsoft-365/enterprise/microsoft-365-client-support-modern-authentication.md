---
title: Microsoft 365 客户端应用支持—新式验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，了解哪些平台、客户端和 Powershell 模块支持适用于 Microsoft 365 的新式验证。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0357c357de2b8db355c539acda851fca7802d17
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687791"
---
# <a name="microsoft-365-client-app-support---modern-authentication"></a><span data-ttu-id="ca88a-103">Microsoft 365 客户端应用程序支持-新式验证</span><span class="sxs-lookup"><span data-stu-id="ca88a-103">Microsoft 365 Client App Support - Modern Authentication</span></span>

<span data-ttu-id="ca88a-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="ca88a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ca88a-105">新式验证为不同平台上的 Office 客户端应用程序启用 Active Directory 身份验证库 (基于) 的基于 ADAL 的登录。</span><span class="sxs-lookup"><span data-stu-id="ca88a-105">Modern Authentication enables Active Directory Authentication Library (ADAL)-based sign-in for Office client apps across different platforms.</span></span> <span data-ttu-id="ca88a-106">这将启用多因素身份验证 (MFA) 、智能卡和基于证书的身份验证等登录功能。</span><span class="sxs-lookup"><span data-stu-id="ca88a-106">This enables sign-in features such as Multi-Factor Authentication (MFA), smart card, and certificate-based authentication.</span></span>

<span data-ttu-id="ca88a-107">了解有关 [多因素身份验证](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) 和 [基于证书的身份验证](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ca88a-107">Learn more about [multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) and [certificate-based authentication](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="ca88a-108">支持的平台</span><span class="sxs-lookup"><span data-stu-id="ca88a-108">Supported platforms</span></span>

 - <span data-ttu-id="ca88a-109">Windows 10 桌面版</span><span class="sxs-lookup"><span data-stu-id="ca88a-109">Windows 10 Desktop</span></span>
 - <span data-ttu-id="ca88a-110">Windows 10 新式应用</span><span class="sxs-lookup"><span data-stu-id="ca88a-110">Windows 10 Modern Apps</span></span>
 - <span data-ttu-id="ca88a-111">Web 浏览器<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca88a-111">Web browsers<sup>1</sup></span></span>
 - <span data-ttu-id="ca88a-112">Android<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ca88a-112">Android<sup>2</sup></span></span>
 - <span data-ttu-id="ca88a-113">iOS</span><span class="sxs-lookup"><span data-stu-id="ca88a-113">iOS</span></span>
 - <span data-ttu-id="ca88a-114">macOS</span><span class="sxs-lookup"><span data-stu-id="ca88a-114">macOS</span></span>

<span data-ttu-id="ca88a-115">有关 Microsoft 365 中平台支持的详细信息，请参阅 [microsoft 365 的系统要求](https://products.office.com/office-system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="ca88a-115">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-clients"></a><span data-ttu-id="ca88a-116">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="ca88a-116">Supported clients</span></span>

<span data-ttu-id="ca88a-117">以下客户端的最新版本支持新式验证：</span><span class="sxs-lookup"><span data-stu-id="ca88a-117">The latest versions of the following clients support modern authentication:</span></span>

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="ca88a-118">![Access 图标](../media/o365-access-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-118">![Access icon](../media/o365-access-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-119">Access</span><span class="sxs-lookup"><span data-stu-id="ca88a-119">Access</span></span>](https://products.office.com/access) | <span data-ttu-id="ca88a-120">![Azure 图标](../media/o365-azure-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-120">![Azure icon](../media/o365-azure-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-121">Azure <br> 门户 </span><span class="sxs-lookup"><span data-stu-id="ca88a-121">Azure <br> Portal </span></span>](https://azure.microsoft.com/features/azure-portal/) | <span data-ttu-id="ca88a-122">![公司门户图标](../media/o365-microsoft-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-122">![Company portal icon](../media/o365-microsoft-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-123">公司 <br> 门户 </span><span class="sxs-lookup"><span data-stu-id="ca88a-123">Company <br> Portal </span></span>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | <span data-ttu-id="ca88a-124">![Delve 图标](../media/o365-delve-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-124">![Delve icon](../media/o365-delve-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-125">Delve</span><span class="sxs-lookup"><span data-stu-id="ca88a-125">Delve</span></span>](https://products.office.com/business/intelligent-search) | <span data-ttu-id="ca88a-126">![Dynamics 365 图标](../media/o365-dynamics365-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-126">![Dynamics 365 icon](../media/o365-dynamics365-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-127">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ca88a-127">Dynamics 365</span></span>](https://dynamics.microsoft.com) 
| <span data-ttu-id="ca88a-128">![边缘图标](../media/o365-edge-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-128">![Edge icon](../media/o365-edge-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-129">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ca88a-129">Edge</span></span>](https://www.microsoft.com/windows/microsoft-edge) | <span data-ttu-id="ca88a-130">![Excel 图标](../media/o365-excel-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-130">![Excel icon](../media/o365-excel-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-131">Excel</span><span class="sxs-lookup"><span data-stu-id="ca88a-131">Excel</span></span>](https://products.office.com/excel) | <span data-ttu-id="ca88a-132">![Forms 图标](../media/o365-forms-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-132">![Forms icon](../media/o365-forms-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-133">Forms</span><span class="sxs-lookup"><span data-stu-id="ca88a-133">Forms</span></span>](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | <span data-ttu-id="ca88a-134">![Kaizala 图标](../media/o365-kaizala-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-134">![Kaizala icon](../media/o365-kaizala-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-135">Kaizala</span><span class="sxs-lookup"><span data-stu-id="ca88a-135">Kaizala</span></span>](https://products.office.com/en/business/microsoft-kaizala) | <span data-ttu-id="ca88a-136">![Office.com 图标](../media/o365-office-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-136">![Office.com icon](../media/o365-office-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-137">Office.com</span><span class="sxs-lookup"><span data-stu-id="ca88a-137">Office.com</span></span>](https://www.office.com/) 
| <span data-ttu-id="ca88a-138">![Office 365 管理员图标](../media/o365-o365admin-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-138">![Office 365 Admin icon](../media/o365-o365admin-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-139">Microsoft 365 <br> 管理员</span><span class="sxs-lookup"><span data-stu-id="ca88a-139">Microsoft 365 <br> Admin</span></span>](https://products.office.com/business/manage-office-365-admin-app) | <span data-ttu-id="ca88a-140">![镜头图标](../media/o365-lens-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-140">![Lens icon](../media/o365-lens-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-141">Office Lens</span><span class="sxs-lookup"><span data-stu-id="ca88a-141">Office Lens</span></span>](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | <span data-ttu-id="ca88a-142">![OneDrive for Business 图标](../media/o365-OneDrive-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-142">![OneDrive for Business icon](../media/o365-OneDrive-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-143">OneDrive</span><span class="sxs-lookup"><span data-stu-id="ca88a-143">OneDrive</span></span>](https://products.office.com/onedrive-for-business/online-cloud-storage) |  <span data-ttu-id="ca88a-144">![OneNote 图标](../media/o365-OneNote-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-144">![OneNote icon](../media/o365-OneNote-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-145">OneNote</span><span class="sxs-lookup"><span data-stu-id="ca88a-145">OneNote</span></span>](https://products.office.com/onenote) | <span data-ttu-id="ca88a-146">![Outlook 图标](../media/o365-outlook-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-146">![Outlook icon](../media/o365-outlook-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="ca88a-147">Outlook</span></span>](https://products.office.com/outlook) 
| <span data-ttu-id="ca88a-148">![Planner 图标](../media/o365-planner-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-148">![Planner icon](../media/o365-planner-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-149">Planner</span><span class="sxs-lookup"><span data-stu-id="ca88a-149">Planner</span></span>](https://products.office.com/business/task-management-software) | <span data-ttu-id="ca88a-150">![PowerApps 图标](../media/o365-powerapps-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-150">![PowerApps icon](../media/o365-powerapps-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-151">PowerApps </span><span class="sxs-lookup"><span data-stu-id="ca88a-151">PowerApps </span></span>](https://powerapps.microsoft.com) | <span data-ttu-id="ca88a-152">![电源自动图标](../media/o365-flow-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-152">![Power Automate icon](../media/o365-flow-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-153">电源 <br> 自动化</span><span class="sxs-lookup"><span data-stu-id="ca88a-153">Power <br> Automate</span></span>](https://flow.microsoft.com) | <span data-ttu-id="ca88a-154">![PowerBI 图标](../media/o365-powerbi-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-154">![PowerBI icon](../media/o365-powerbi-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-155">Power BI</span><span class="sxs-lookup"><span data-stu-id="ca88a-155">Power BI</span></span>](https://powerbi.microsoft.com)| <span data-ttu-id="ca88a-156">![PowerPoint 图标](../media/o365-powerpoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-156">![PowerPoint icon](../media/o365-powerpoint-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-157">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ca88a-157">PowerPoint</span></span>](https://products.office.com/powerpoint) 
| <span data-ttu-id="ca88a-158">![Project 图标](../media/o365-project-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-158">![Project icon](../media/o365-project-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-159">Project</span><span class="sxs-lookup"><span data-stu-id="ca88a-159">Project</span></span>](https://products.office.com/project) | <span data-ttu-id="ca88a-160">![Publisher 图标](../media/o365-publisher-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-160">![Publisher icon](../media/o365-publisher-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-161">Publisher</span><span class="sxs-lookup"><span data-stu-id="ca88a-161">Publisher</span></span>](https://products.office.com/publisher) | <span data-ttu-id="ca88a-162">![SharePoint 图标](../media/o365-sharepoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-162">![SharePoint icon](../media/o365-sharepoint-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-163">Sharepoint</span><span class="sxs-lookup"><span data-stu-id="ca88a-163">Sharepoint</span></span>](https://products.office.com/sharepoint) | <span data-ttu-id="ca88a-164">![Skype for Business 图标](../media/o365-skypeforbusiness-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-164">![Skype for Business icon](../media/o365-skypeforbusiness-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-165">Skype for <br> business<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca88a-165">Skype for <br> Business<sup>1</sup></span></span>](https://www.skype.com/business/) | <span data-ttu-id="ca88a-166">![StaffHub 图标](../media/o365-staffhub-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-166">![StaffHub icon](../media/o365-staffhub-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-167">StaffHub</span><span class="sxs-lookup"><span data-stu-id="ca88a-167">StaffHub</span></span>](https://products.office.com/microsoft-staffhub/staff-scheduling-software)
| <span data-ttu-id="ca88a-168">![粘滞便笺图标](../media/o365-stickynotes-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-168">![Sticky Notes icon](../media/o365-stickynotes-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-169">粘滞便笺</span><span class="sxs-lookup"><span data-stu-id="ca88a-169">Sticky Notes</span></span>](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | <span data-ttu-id="ca88a-170">![Stream 图标](../media/o365-stream-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-170">![Stream icon](../media/o365-stream-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-171">Stream</span><span class="sxs-lookup"><span data-stu-id="ca88a-171">Stream</span></span>](https://stream.microsoft.com) | <span data-ttu-id="ca88a-172">![Sway 图标](../media/o365-sway-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-172">![Sway icon](../media/o365-sway-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-173">Sway</span><span class="sxs-lookup"><span data-stu-id="ca88a-173">Sway</span></span>](https://sway.com) | <span data-ttu-id="ca88a-174">![Teams 图标](../media/o365-teams-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-174">![Teams icon](../media/o365-teams-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-175">Teams</span><span class="sxs-lookup"><span data-stu-id="ca88a-175">Teams</span></span>](https://products.office.com/microsoft-teams/group-chat-software) | <span data-ttu-id="ca88a-176">![To Do 图标](../media/o365-todo-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-176">![To Do icon](../media/o365-todo-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-177">待办事项</span><span class="sxs-lookup"><span data-stu-id="ca88a-177">To Do</span></span>](https://todo.microsoft.com) 
| <span data-ttu-id="ca88a-178">![Visio 图标](../media/o365-visio-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-178">![Visio icon](../media/o365-visio-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-179">Visio</span><span class="sxs-lookup"><span data-stu-id="ca88a-179">Visio</span></span>](https://products.office.com/visio/flowchart-software) | <span data-ttu-id="ca88a-180">![Whiteboard 图标](../media/o365-whiteboard-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-180">![Whiteboard icon](../media/o365-whiteboard-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-181">白板<sup>1</sup>、<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ca88a-181">Whiteboard<sup>1</sup>,<sup>2</sup></span></span>](https://whiteboard.microsoft.com/) | <span data-ttu-id="ca88a-182">![Word 图标](../media/o365-word-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-182">![Word icon](../media/o365-word-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-183">Word</span><span class="sxs-lookup"><span data-stu-id="ca88a-183">Word</span></span>](https://products.office.com/word) | <span data-ttu-id="ca88a-184">![Yammer 图标](../media/o365-yammer-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-184">![Yammer icon](../media/o365-yammer-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-185">Yammer</span><span class="sxs-lookup"><span data-stu-id="ca88a-185">Yammer</span></span>](https://products.office.com/yammer/yammer-overview) | <span data-ttu-id="ca88a-186">![Yammer 图标](../media/o365-yammer-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-186">![Yammer icon](../media/o365-yammer-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-187">Yammer <br> 通知程序</span><span class="sxs-lookup"><span data-stu-id="ca88a-187">Yammer <br> Notifier</span></span>](https://products.office.com/yammer/yammer-overview) |  |

## <a name="supported-powershell-modules"></a><span data-ttu-id="ca88a-188">支持的 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="ca88a-188">Supported PowerShell modules</span></span>

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="ca88a-189">![Azure 图标](../media/o365-azure-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-189">![Azure icon](../media/o365-azure-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-190">Azure AD <br> PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca88a-190">Azure AD <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | <span data-ttu-id="ca88a-191">![Exchange 图标](../media/o365-exchange-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-191">![Exchange icon](../media/o365-exchange-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-192">Exchange Online <br> PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca88a-192">Exchange Online <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | <span data-ttu-id="ca88a-193">![SharePoint 图标](../media/o365-sharepoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="ca88a-193">![SharePoint icon](../media/o365-sharepoint-64x64.png)</span></span> <br> [<span data-ttu-id="ca88a-194">SharePoint Online <br> PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca88a-194">SharePoint Online <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <span data-ttu-id="ca88a-195"><sup>1</sup> 对白板和 Skype for business 的 web 应用程序的支持即将推出。</span><span class="sxs-lookup"><span data-stu-id="ca88a-195"><sup>1</sup> Support for Whiteboard and Skype for Business on web app available soon.</span></span> <br>
> <span data-ttu-id="ca88a-196"><sup>2</sup> 对 Android 上的白板支持很快可用。</span><span class="sxs-lookup"><span data-stu-id="ca88a-196"><sup>2</sup> Support for Whiteboard on Android available soon.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca88a-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca88a-197">See also</span></span>

[<span data-ttu-id="ca88a-198">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="ca88a-198">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)