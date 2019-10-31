---
title: 从 Microsoft 365 Business 迁移到 Microsoft 365 企业版
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何将企业从 Microsoft 365 企业移动到 Microsoft 365 企业版 E3。
ms.openlocfilehash: efdf4030a2a638a3fd56d1c415fcc6e6ac261c1a
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772707"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a><span data-ttu-id="64562-103">从 Microsoft 365 Business 迁移到 Microsoft 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="64562-103">Migrate from Microsoft 365 Business to Microsoft 365 Enterprise E3</span></span>

<span data-ttu-id="64562-104">Microsoft 365 商业版为小型企业提供了所需的一切，将同类最佳的基于云的工作效率应用与简单的设备管理和安全性相结合，使员工能够完成其最佳工作。</span><span class="sxs-lookup"><span data-stu-id="64562-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="64562-105">但在某些情况下，可能需要将 Microsoft 365 业务订阅迁移到 Microsoft 365 企业版。</span><span class="sxs-lookup"><span data-stu-id="64562-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="64562-106">例如，您的企业增长并需要300以上的许可证（顺便说一下）。</span><span class="sxs-lookup"><span data-stu-id="64562-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="64562-107">或者，您的业务需要企业版功能，如 Office 365 专业增强版、Windows 10 企业版 E3 或企业客户端访问许可证（Cal）。</span><span class="sxs-lookup"><span data-stu-id="64562-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="64562-108">迁移非常简单：仅交换许可证。</span><span class="sxs-lookup"><span data-stu-id="64562-108">Migrating is easy: Just switch licenses.</span></span> <span data-ttu-id="64562-109">保留当前订阅中的所有数据和配置。</span><span class="sxs-lookup"><span data-stu-id="64562-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="64562-110">无需为迁移做准备，也无需执行任何操作，除非利用新功能。</span><span class="sxs-lookup"><span data-stu-id="64562-110">There is nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="64562-111">您还可以使用 Microsoft 365 商业版订阅进行最多300个座位，并获取 Microsoft 365 企业版 E3 订阅（适用于超过300的座位）。</span><span class="sxs-lookup"><span data-stu-id="64562-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 Enterprise E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="64562-112">但是，Office 365 ATP 不包含在 Microsoft 365 企业版 E3 中。</span><span class="sxs-lookup"><span data-stu-id="64562-112">However, Office 365 ATP is not included with Microsoft 365 Enterprise E3.</span></span> <span data-ttu-id="64562-113">应为 Microsoft 365 企业版 E3 订阅中的用户添加其他 Office 365 ATP 许可证。</span><span class="sxs-lookup"><span data-stu-id="64562-113">You should add additional Office 365 ATP licenses for the users in your Microsoft 365 Enterprise E3 subscription.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="64562-114">Microsoft 365 商业版与 Microsoft 365 企业版之间的区别</span><span class="sxs-lookup"><span data-stu-id="64562-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="64562-115">此表显示了 Microsoft 365 商业版和 Microsoft 365 企业版 E3 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="64562-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 Enterprise E3.</span></span>

| <span data-ttu-id="64562-116">功能</span><span class="sxs-lookup"><span data-stu-id="64562-116">Feature</span></span>   | <span data-ttu-id="64562-117">Microsoft 365 商业版中的支持</span><span class="sxs-lookup"><span data-stu-id="64562-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="64562-118">Microsoft 365 企业版 E3 中的支持</span><span class="sxs-lookup"><span data-stu-id="64562-118">Support in Microsoft 365 Enterprise E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="64562-119">**本地**</span><span class="sxs-lookup"><span data-stu-id="64562-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="64562-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="64562-120">Windows 10</span></span>    | <span data-ttu-id="64562-121">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="64562-121">Windows 10 Business</span></span>  |    <span data-ttu-id="64562-122">Windows 10 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="64562-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="64562-123">Office 应用程序 \*</span><span class="sxs-lookup"><span data-stu-id="64562-123">Office apps\*</span></span>  | [<span data-ttu-id="64562-124">Office 365 商业版</span><span class="sxs-lookup"><span data-stu-id="64562-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="64562-125">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="64562-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="64562-126">**云生产力应用程序**</span><span class="sxs-lookup"><span data-stu-id="64562-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="64562-127">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="64562-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="64562-128">每个邮箱 50 GB 存储限制和不受限制的 Exchange Online 存档</span><span class="sxs-lookup"><span data-stu-id="64562-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="64562-129">每个邮箱 100 GB 存储限制和不受限制的 Exchange Online 存档</span><span class="sxs-lookup"><span data-stu-id="64562-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="64562-130">Teams</span><span class="sxs-lookup"><span data-stu-id="64562-130">Teams</span></span> | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="64562-133">OneDrive for Business</span></span> | <span data-ttu-id="64562-134">每个用户 1 TB 存储限制</span><span class="sxs-lookup"><span data-stu-id="64562-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="64562-135">无限制</span><span class="sxs-lookup"><span data-stu-id="64562-135">Unlimited</span></span> | 
| <span data-ttu-id="64562-136">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="64562-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-139">StaffHub</span><span class="sxs-lookup"><span data-stu-id="64562-139">StaffHub</span></span>  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-142">Outlook 客户管理器，MileIQ</span><span class="sxs-lookup"><span data-stu-id="64562-142">Outlook Customer Manager, MileIQ</span></span>  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | | 
| <span data-ttu-id="64562-144">**威胁防护**</span><span class="sxs-lookup"><span data-stu-id="64562-144">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="64562-145">攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="64562-145">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="64562-146">查看此列表</span><span class="sxs-lookup"><span data-stu-id="64562-146">See this list</span></span>](#threat-protection) | <span data-ttu-id="64562-147">Microsoft Edge 基于硬件的隔离的企业管理</span><span class="sxs-lookup"><span data-stu-id="64562-147">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="64562-148">Office 365 高级威胁防护（ATP）计划1</span><span class="sxs-lookup"><span data-stu-id="64562-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)  | <span data-ttu-id="64562-150">不包括在内，但可以添加到</span><span class="sxs-lookup"><span data-stu-id="64562-150">Not included, but can be added on</span></span> | 
| <span data-ttu-id="64562-151">**身份管理**</span><span class="sxs-lookup"><span data-stu-id="64562-151">**Identity management**</span></span>       | | | 
| <span data-ttu-id="64562-152">混合 Azure Active Directory （Azure AD）帐户、Azure 多重身份验证（MFA）、条件访问、本地标识的密码写回的自助密码重置</span><span class="sxs-lookup"><span data-stu-id="64562-152">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![包含在 Microsoft 365 商业版中](./media/check-mark.png) | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-155">云应用发现、Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="64562-155">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-157">Azure AD Office 365 应用单一登录（SSO）：每个用户10个应用程序（库 SaaS 应用程序，如 Salesforce） \*</span><span class="sxs-lookup"><span data-stu-id="64562-157">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![包含在 Microsoft 365 商业版中](./media/check-mark.png) | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-160">Azure AD Premium 1 SSO：无限制（通过使用自助式应用集成模板的 Azure AD 应用程序代理和非库应用的内部部署应用）</span><span class="sxs-lookup"><span data-stu-id="64562-160">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-162">**设备和应用程序管理**</span><span class="sxs-lookup"><span data-stu-id="64562-162">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="64562-163">Microsoft Intune、Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="64562-163">Microsoft Intune, Windows Autopilot</span></span>|  ![包含在 Microsoft 365 商业版中](./media/check-mark.png) | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
|<span data-ttu-id="64562-166">虚拟桌面访问（VDA）</span><span class="sxs-lookup"><span data-stu-id="64562-166">Virtual Desktop Access (VDA)</span></span>   |  |    ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
|<span data-ttu-id="64562-168">Windows 虚拟桌面（WVD）</span><span class="sxs-lookup"><span data-stu-id="64562-168">Windows Virtual Desktop (WVD)</span></span>  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png) |     ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
|<span data-ttu-id="64562-171">共享计算机激活（SCA）</span><span class="sxs-lookup"><span data-stu-id="64562-171">Shared Computer Activation (SCA)</span></span>   | ![包含在 Microsoft 365 商业版中](./media/check-mark.png) |     ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-174">Microsoft 桌面优化包</span><span class="sxs-lookup"><span data-stu-id="64562-174">Microsoft Desktop Optimization Package</span></span>    | |     ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-176">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="64562-176">**Information protection**</span></span>        | | | 
| <span data-ttu-id="64562-177">Office 365 数据丢失防护，Azure 信息保护计划1</span><span class="sxs-lookup"><span data-stu-id="64562-177">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-180">Endpoint DLP 的窗口信息保护</span><span class="sxs-lookup"><span data-stu-id="64562-180">Window Information Protection for endpoint DLP</span></span>    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-183">**客户端访问许可证（CAL 权限）**</span><span class="sxs-lookup"><span data-stu-id="64562-183">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="64562-184">企业 CAL 套件（Exchange、SharePoint、Skype、Windows、System Center Configuration Manager、Windows 权限管理）</span><span class="sxs-lookup"><span data-stu-id="64562-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span></span>| |        ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-186">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="64562-186">**Compliance**</span></span>        | | | 
| <span data-ttu-id="64562-187">无限制的电子邮件存档</span><span class="sxs-lookup"><span data-stu-id="64562-187">Unlimited email archiving</span></span> | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-190">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="64562-190">Compliance Manager</span></span>    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-193">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="64562-193">eDiscovery</span></span>    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-196">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="64562-196">In-place hold and litigation hold</span></span> | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| <span data-ttu-id="64562-199">邮件记录管理（MRM）保留标记和保留策略</span><span class="sxs-lookup"><span data-stu-id="64562-199">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
||||

<span data-ttu-id="64562-202">\*分配了对 SaaS 应用程序的访问权限的用户可以获取最大10个应用程序的 SSO 访问权限。</span><span class="sxs-lookup"><span data-stu-id="64562-202">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="64562-203">管理员可以配置 SSO 并更改用户对不同 SaaS 应用程序的访问权限，但每次仅允许对每个用户的10个应用程序进行 SSO 访问。</span><span class="sxs-lookup"><span data-stu-id="64562-203">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="64562-204">所有 Office 365 应用程序均计为一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="64562-204">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="64562-205">迁移</span><span class="sxs-lookup"><span data-stu-id="64562-205">Migration</span></span>

<span data-ttu-id="64562-206">若要迁移，请与合作伙伴合作以将 Microsoft 365 业务订阅和许可证移动到合适的 Microsoft 365 企业版 E3 订阅及其许可证。</span><span class="sxs-lookup"><span data-stu-id="64562-206">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to suitable a Microsoft 365 Enterprise E3 subscription with its licenses.</span></span>

<span data-ttu-id="64562-207">以下各节介绍了需要进行哪些更改（如果有），以及迁移后可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="64562-207">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="64562-208">Microsoft 365 订阅配置和数据</span><span class="sxs-lookup"><span data-stu-id="64562-208">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="64562-209">您不需要在迁移之前对当前订阅或数据进行任何更改，其中包括：</span><span class="sxs-lookup"><span data-stu-id="64562-209">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="64562-210">订阅配置，如 DNS 域名。</span><span class="sxs-lookup"><span data-stu-id="64562-210">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="64562-211">用户和组帐户以及身份验证设置，例如多重因素身份验证或条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="64562-211">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="64562-212">生产率服务配置及其数据，如团队、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。</span><span class="sxs-lookup"><span data-stu-id="64562-212">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="64562-213">现在，你的用户可以在 Exchange Online 邮箱和 OneDrive for business 文件夹中享受无限存储。</span><span class="sxs-lookup"><span data-stu-id="64562-213">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="64562-214">您可以开始对10个以上的应用程序使用云应用发现、Azure AD Connect Health 和 SSO。</span><span class="sxs-lookup"><span data-stu-id="64562-214">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="64562-215">迁移到 Microsoft 365 企业版 E3 后，不再是 Outlook 客户经理和 MileIQ。</span><span class="sxs-lookup"><span data-stu-id="64562-215">After migrating to Microsoft 365 Enterprise E3, you no longer Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="64562-216">威胁防护</span><span class="sxs-lookup"><span data-stu-id="64562-216">Threat protection</span></span>

<span data-ttu-id="64562-217">Windows 10 商业版包括以下保护：</span><span class="sxs-lookup"><span data-stu-id="64562-217">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="64562-218">操作系统启动过程的完整性强制实施</span><span class="sxs-lookup"><span data-stu-id="64562-218">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="64562-219">敏感操作组件的完整性实施</span><span class="sxs-lookup"><span data-stu-id="64562-219">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="64562-220">高级漏洞和零日利用缓解措施</span><span class="sxs-lookup"><span data-stu-id="64562-220">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="64562-221">Microsoft Edge、Internet Explorer 和 Chrome 的基于信誉的网络保护</span><span class="sxs-lookup"><span data-stu-id="64562-221">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="64562-222">基于主机的防火墙</span><span class="sxs-lookup"><span data-stu-id="64562-222">Host-based firewall</span></span>
- <span data-ttu-id="64562-223">勒索软件缓解</span><span class="sxs-lookup"><span data-stu-id="64562-223">Ransomware mitigations</span></span>
- <span data-ttu-id="64562-224">Microsoft Edge 的基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="64562-224">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="64562-225">由智能安全图形支持的应用程序控制</span><span class="sxs-lookup"><span data-stu-id="64562-225">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="64562-226">设备控制（USB）</span><span class="sxs-lookup"><span data-stu-id="64562-226">Device control (USB)</span></span>
- <span data-ttu-id="64562-227">基于 web 的威胁的网络保护</span><span class="sxs-lookup"><span data-stu-id="64562-227">Network protection for web-based threats</span></span>
- <span data-ttu-id="64562-228">主机入侵防护规则</span><span class="sxs-lookup"><span data-stu-id="64562-228">Host intrusion prevention rules</span></span>

<span data-ttu-id="64562-229">Windows 10 企业版 E3 还包括针对 Microsoft Edge 的基于硬件的隔离的企业管理。</span><span class="sxs-lookup"><span data-stu-id="64562-229">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="64562-230">迁移到 Microsoft 365 企业版 E3 后，您不再拥有 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="64562-230">After migrating to Microsoft 365 Enterprise E3, you no longer have Office 365 ATP.</span></span> <span data-ttu-id="64562-231">您可以为您的 Microsoft 365 企业版 E3 订阅购买额外的 Office 365 ATP 许可证，并将其分配给您的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="64562-231">You can purchase additional Office 365 ATP licenses for your Microsoft 365 Enterprise E3 subscription and assign them to your user accounts.</span></span>
>

### <a name="device-management-with-intune"></a><span data-ttu-id="64562-232">使用 Intune 的设备管理</span><span class="sxs-lookup"><span data-stu-id="64562-232">Device management with Intune</span></span>

<span data-ttu-id="64562-233">您无需在迁移前对当前 Intune 配置进行任何更改，包括注册的设备和设备以及应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="64562-233">You don’t need to do any changes to your current Intune configuration prior to migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="64562-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="64562-234">Windows 10</span></span>

<span data-ttu-id="64562-235">Microsoft 365 Business 包括 Windows 10 商业版，可以通过 Windows Autopilot 安装。</span><span class="sxs-lookup"><span data-stu-id="64562-235">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows Autopilot.</span></span> <span data-ttu-id="64562-236">当迁移到 Microsoft 365 企业版 E3 时，每个用户许可证都包含 Windows 10 企业版 E3，您还可以使用 Windows Autopilot 进行安装。</span><span class="sxs-lookup"><span data-stu-id="64562-236">When you migrate to Microsoft 365 Enterprise E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="64562-237">Office 365 商业版</span><span class="sxs-lookup"><span data-stu-id="64562-237">Office 365 Business</span></span>

<span data-ttu-id="64562-238">您的设备上安装的 Office 365 业务客户端将自动开始使用 Office 365 专业增强版的功能。</span><span class="sxs-lookup"><span data-stu-id="64562-238">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="64562-239">迁移之后，您现在可以使用：</span><span class="sxs-lookup"><span data-stu-id="64562-239">After migration, you can now use:</span></span>

 - <span data-ttu-id="64562-240">通过组策略激活卷</span><span class="sxs-lookup"><span data-stu-id="64562-240">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="64562-241">应用遥测</span><span class="sxs-lookup"><span data-stu-id="64562-241">App telemetry</span></span>
 - <span data-ttu-id="64562-242">更新控件</span><span class="sxs-lookup"><span data-stu-id="64562-242">Update controls</span></span>
 - <span data-ttu-id="64562-243">电子表格比较和查询</span><span class="sxs-lookup"><span data-stu-id="64562-243">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="64562-244">商业智能</span><span class="sxs-lookup"><span data-stu-id="64562-244">Business intelligence</span></span>
