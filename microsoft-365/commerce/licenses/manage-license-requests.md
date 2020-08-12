---
title: 管理许可证请求
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: 了解如何查看和批准或拒绝来自适用于 Microsoft 365 for business 订阅的用户的许可证请求。
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597648"
---
# <a name="manage-license-requests"></a><span data-ttu-id="017da-103">管理许可证请求</span><span class="sxs-lookup"><span data-stu-id="017da-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="017da-104">本文中的信息仅适用于自助服务购买的产品。</span><span class="sxs-lookup"><span data-stu-id="017da-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="017da-105">若要了解详细信息，请参阅[自助式购买常见问题解答](../subscriptions/self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="017da-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="017da-106">如果您在组织中禁用了自助式购买，则可以使用许可证请求来管理用户的许可证请求流程。</span><span class="sxs-lookup"><span data-stu-id="017da-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="017da-107">当用户尝试为已阻止的产品进行自助服务购买时，他们可以向管理员提交许可证请求。在发出请求时，他们可以添加还需要产品许可证的其他用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="017da-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="017da-108">如果阻止用户进行自助购买，Microsoft 不会向其发送营销电子邮件。</span><span class="sxs-lookup"><span data-stu-id="017da-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="017da-109">此外，如果他们使用的是试用版产品，他们将不会看到要购买的提示。</span><span class="sxs-lookup"><span data-stu-id="017da-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="017da-110">若要了解详细信息，请参阅[管理自助购买 (管理员) ](../subscriptions/manage-self-service-purchases-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="017da-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="017da-111">若要查看和管理许可证请求，管理员使用 "**许可**" 页面上的 "**请求**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="017da-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="017da-112">该列表显示所请求的产品的名称、请求许可证的人员的姓名、请求的日期以及请求的状态。</span><span class="sxs-lookup"><span data-stu-id="017da-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="017da-113">管理员可以筛选列表以显示挂起或已完成的请求。</span><span class="sxs-lookup"><span data-stu-id="017da-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="017da-114">请求保留30天。</span><span class="sxs-lookup"><span data-stu-id="017da-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="017da-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="017da-115">Before you begin</span></span>

<span data-ttu-id="017da-116">若要执行本文中的任务，您必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="017da-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="017da-117">有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="017da-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="017da-118">使用您自己的请求过程</span><span class="sxs-lookup"><span data-stu-id="017da-118">Use your own request process</span></span>

<span data-ttu-id="017da-119">如果您的组织有自己的请求过程，则可以改为使用它。</span><span class="sxs-lookup"><span data-stu-id="017da-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="017da-120">创建一个在用户请求许可证时向其显示的消息。</span><span class="sxs-lookup"><span data-stu-id="017da-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="017da-121">如果您使用自己的请求过程，则 "**请求**" 选项卡上将不会显示任何请求。在您添加邮件之前，现有请求将一直显示，直到您批准或拒绝它们为止。</span><span class="sxs-lookup"><span data-stu-id="017da-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="017da-122">在管理中心中，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面，然后选择 "**请求**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="017da-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="017da-123">选择 "**使用现有的请求过程**"。</span><span class="sxs-lookup"><span data-stu-id="017da-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="017da-124">在右侧窗格中的 "**消息**" 框中，键入您希望用户在请求许可证时看到的消息。</span><span class="sxs-lookup"><span data-stu-id="017da-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="017da-125">如果要同时包含指向组织策略或其他文档的链接，请在 "\*\*指向文档的链接" (可选) \*\* "文本框中输入 URL。</span><span class="sxs-lookup"><span data-stu-id="017da-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="017da-126">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="017da-126">Select **Save**.</span></span>

<span data-ttu-id="017da-127">当您返回 "**请求**" 列表时，您会看到您**使用的是自己的许可证请求过程**的消息。</span><span class="sxs-lookup"><span data-stu-id="017da-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="017da-128">若要对发送给用户的邮件进行更改，请选择 "**使用现有请求过程**"。</span><span class="sxs-lookup"><span data-stu-id="017da-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="017da-129">停止使用自己的请求过程</span><span class="sxs-lookup"><span data-stu-id="017da-129">Stop using your own request process</span></span>

1. <span data-ttu-id="017da-130">在管理中心中，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面，然后选择 "**请求**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="017da-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="017da-131">选择 "**使用现有的请求过程**"。</span><span class="sxs-lookup"><span data-stu-id="017da-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="017da-132">在右窗格中，清除 "**使用我的组织的请求过程**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="017da-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="017da-133">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="017da-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="017da-134">批准或拒绝许可证请求</span><span class="sxs-lookup"><span data-stu-id="017da-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="017da-135">在管理中心中，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面，然后选择 "**请求**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="017da-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="017da-136">选择包含您要查看的请求的行。</span><span class="sxs-lookup"><span data-stu-id="017da-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="017da-137">右窗格显示有关用户需要许可证的产品的详细信息。</span><span class="sxs-lookup"><span data-stu-id="017da-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="017da-138">若要拒绝整个请求，请选择 "**不批准**"，并在对话框中，选择 "**不批准**"。</span><span class="sxs-lookup"><span data-stu-id="017da-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="017da-139">若要为请求拒绝某些用户，但要批准其他用户，请按要删除的用户的名称选择 X。</span><span class="sxs-lookup"><span data-stu-id="017da-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="017da-140">它们的名称在不**分配给这些用户**的情况下被移动。</span><span class="sxs-lookup"><span data-stu-id="017da-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="017da-141">如果您有多个产品，请在 "**选择产品**" 下，选择要用于为其分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="017da-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="017da-142">若要拒绝用户访问某些应用和服务，请展开 **"打开或关闭应用程序和服务**"，然后清除要排除的应用和服务的复选框。</span><span class="sxs-lookup"><span data-stu-id="017da-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="017da-143">在窗格底部的文本框中，键入可选消息。</span><span class="sxs-lookup"><span data-stu-id="017da-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="017da-144">完成后，选择 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="017da-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="017da-145">右窗格显示请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="017da-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="017da-146">关闭右窗格。</span><span class="sxs-lookup"><span data-stu-id="017da-146">Close the right pane.</span></span>
    <span data-ttu-id="017da-147">用户收到一封电子邮件，告知其请求已被批准或拒绝。</span><span class="sxs-lookup"><span data-stu-id="017da-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="017da-148">相关内容</span><span class="sxs-lookup"><span data-stu-id="017da-148">Related content</span></span>

<span data-ttu-id="017da-149">[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="017da-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="017da-150">[将用户移动到其他订阅](../subscriptions/move-users-different-subscription.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="017da-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="017da-151"> (文章) [购买或删除订阅许可证](buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="017da-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>