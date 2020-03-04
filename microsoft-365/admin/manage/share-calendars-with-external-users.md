---
title: 与外部用户共享日历
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: '了解如何让你的用户与外部用户共享会议和约会的日历。 '
ms.openlocfilehash: 42bce53c3963c41684644d02dab18210f9ed828a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251077"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="2d8ca-103">与外部用户共享日历</span><span class="sxs-lookup"><span data-stu-id="2d8ca-103">Share calendars with external users</span></span>

<span data-ttu-id="2d8ca-p101">通常有必要安排与组织外的人员的会议。 要简化查找相互同意的会议时间这一过程，您可以通过 Office 365 向"外部用户"（需要查看忙/闲时间但不具备您的 Office 365 环境的用户帐户的用户）提供日历。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-p101">It's often necessary to schedule meetings with people outside your organization. To simplify the process of finding mutually agreeable meeting times, Office 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Office 365 environment.</span></span>
  
<span data-ttu-id="2d8ca-106">日历共享是全局设置，表示您（管理员）可以为租户中的所有用户启用它。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="2d8ca-107">一旦已启用共享，用户就可以使用 Outlook Web App 与组织内外的任何人共享其日历。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="2d8ca-108">组织内部的人员可以并排查看共享日历和其自己的日历。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="2d8ca-109">组织外部的人员将收到可用于查看日历的 URL。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="2d8ca-110">用户可以决定何时共享、共享量以及何时保持日历私密。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d8ca-p103">如果要与使用 Exchange Server 2013（内部部署解决方案）的组织共享日历，Exchange 管理员需要设置与云的身份验证关系。这称为"联盟"，必须满足最低的软件要求。有关详细信息，请参阅[共享](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="2d8ca-114">使用 Microsoft 365 管理中心启用日历共享</span><span class="sxs-lookup"><span data-stu-id="2d8ca-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="2d8ca-115">在 "管理中心" 中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务" & "加载项</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="2d8ca-116">在 "**服务&amp;外接程序**" 页上，选择 "**日历**"。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="2d8ca-117">在打开的 "**日历**" 页上，选择是否希望让用户与组织外部的人员共享其日历（Office 365 或 Exchange）。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Office 365 or Exchange.</span></span>
    
4. <span data-ttu-id="2d8ca-118">选择是否要允许匿名用户（没有登录凭据的用户）通过电子邮件邀请访问日历。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="2d8ca-119">选择对用户可用的日历信息的类型。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="2d8ca-120">您可以允许所有信息，也可以将其限制为仅时间或时间、主题和位置。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="2d8ca-121">邀请其他人访问日历</span><span class="sxs-lookup"><span data-stu-id="2d8ca-121">Invite people to access calendars</span></span>

<span data-ttu-id="2d8ca-p105">一旦为租户启用共享，日历所有者就可以将邀请扩展到特定用户。 有关说明，请参阅[在 Outlook Web App 中共享日历](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2d8ca-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  
