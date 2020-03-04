---
title: 在 Office 365 中执行内部管理员接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何验证您的电子邮件和域所有权，以接管 Office 365 中的非托管租户
ms.openlocfilehash: e3c89e122264808e2a8631c07269ea263c87fdaa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240360"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a><span data-ttu-id="625b4-103">在 Office 365 中执行内部管理员接管</span><span class="sxs-lookup"><span data-stu-id="625b4-103">Perform an internal admin takeover in Office 365</span></span>

 <span data-ttu-id="625b4-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="625b4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="625b4-105">如果你是管理员，并且想要接管自助服务用户注册创建的非托管租户，则可以使用内部管理员接管执行此操作。</span><span class="sxs-lookup"><span data-stu-id="625b4-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="625b4-106">为使用 Azure AD 的任何云服务注册自助服务会将用户添加到非托管或 "卷影" Azure AD 目录，并创建非托管租户。</span><span class="sxs-lookup"><span data-stu-id="625b4-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="625b4-107">非托管租户是没有全局管理员的目录。</span><span class="sxs-lookup"><span data-stu-id="625b4-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="625b4-108">若要确定租户是否为托管或非托管，请参阅[确定租户类型](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。</span><span class="sxs-lookup"><span data-stu-id="625b4-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="625b4-109">步骤1：验证您的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="625b4-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="625b4-110">如果在租户中启用了自助服务，则用户可以自行订阅免费服务，例如 Power BI。</span><span class="sxs-lookup"><span data-stu-id="625b4-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="625b4-111">这些步骤假定自助服务用户订阅已创建要作为管理员接管的非托管租户。在第一步中，使用 Power BI 演示管理接管路径，在非托管租户中创建用户上下文。</span><span class="sxs-lookup"><span data-stu-id="625b4-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="625b4-112">若要注册 power bi，请转到[power bi 网站](https://powerbi.com)，然后选择 **"启动免费** > **启动免费试用版**" （在 "与 Power BI Pro 共享" 框中）。</span><span class="sxs-lookup"><span data-stu-id="625b4-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="625b4-113">使用您的组织的域名（如`powerbiadmin@contoso.com`）注册用户帐户。</span><span class="sxs-lookup"><span data-stu-id="625b4-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="625b4-114">如果你的帐户已在使用中，请使用你的当前密码登录。</span><span class="sxs-lookup"><span data-stu-id="625b4-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="625b4-115">检查您的电子邮件中的**验证代码**，并输入验证您的电子邮件地址的代码。</span><span class="sxs-lookup"><span data-stu-id="625b4-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="625b4-116">步骤2：创建新帐户</span><span class="sxs-lookup"><span data-stu-id="625b4-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="625b4-117">当您输入验证代码时，您将进入一个页面，可以在其中创建新帐户。</span><span class="sxs-lookup"><span data-stu-id="625b4-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="625b4-118">在 "用户名" 和 "密码" 字段中填写要使用的帐户，然后选择 "**启动**"。</span><span class="sxs-lookup"><span data-stu-id="625b4-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="625b4-119">步骤3：验证域所有权并成为管理员</span><span class="sxs-lookup"><span data-stu-id="625b4-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="625b4-120">即会打开 "**管理员**向导"。</span><span class="sxs-lookup"><span data-stu-id="625b4-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="625b4-121">如果向导不启动，请查找 "**管理**" 磁贴并选择它。</span><span class="sxs-lookup"><span data-stu-id="625b4-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="625b4-122">选择 **"是，我想要成为管理员"**。</span><span class="sxs-lookup"><span data-stu-id="625b4-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="625b4-123">通过向域注册机构添加 TXT 记录来验证您是否拥有要接管的域。</span><span class="sxs-lookup"><span data-stu-id="625b4-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="625b4-124">向导将为你提供要添加的 TXT 记录，并提供指向你的注册机构网站的链接以及指向分步说明的链接。</span><span class="sxs-lookup"><span data-stu-id="625b4-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="625b4-125">将 TXT 记录添加到注册器网站后，返回到向导，然后选择 "确定 **"，我已添加记录**。</span><span class="sxs-lookup"><span data-stu-id="625b4-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="625b4-126">对卷影租户进行接管不会影响任何现有信息或服务。</span><span class="sxs-lookup"><span data-stu-id="625b4-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="625b4-127">但是，如果域中的任何用户已注册需要许可证的服务，则系统将要求你为其购买许可证，作为接管管理员角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="625b4-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="625b4-128">管理员设置过程完成后，您可以添加或删除许可证。</span><span class="sxs-lookup"><span data-stu-id="625b4-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="625b4-129">相关文章</span><span class="sxs-lookup"><span data-stu-id="625b4-129">Related articles</span></span>

<span data-ttu-id="625b4-130">YouTube：[接管 Power BI 和 Office 365 IT 管理员角色的 3 个步骤](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="625b4-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="625b4-131">Azure AD 中的管理员接管</span><span class="sxs-lookup"><span data-stu-id="625b4-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="625b4-132">获取 Office 365 域的帮助</span><span class="sxs-lookup"><span data-stu-id="625b4-132">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="625b4-133">在你的组织中使用自助服务注册</span><span class="sxs-lookup"><span data-stu-id="625b4-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="625b4-134">了解 Power BI 服务管理员角色</span><span class="sxs-lookup"><span data-stu-id="625b4-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)
