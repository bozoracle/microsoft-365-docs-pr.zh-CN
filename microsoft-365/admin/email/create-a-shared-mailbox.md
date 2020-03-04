---
title: 创建共享邮箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 创建共享邮箱，让企业中的多名人员分担查看和答复发送到同一地址的电子邮件的责任。
ms.openlocfilehash: 2ceec37928eafab0c4f02382dd24aa3fa91aa9cd
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362297"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="f1b0a-103">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f1b0a-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="f1b0a-104">如果你的组织使用的是混合 Exchange 环境，则你应使用本地 Exchange 管理中心 (EAC) 创建和管理共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="f1b0a-105">请参阅[在 Exchange 管理中心创建共享邮箱](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="f1b0a-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="f1b0a-106">如果不确定是应为 Outlook 创建共享邮箱还是 Office 365 组，可参阅[比较组](../create-groups/compare-groups.md)获取一些指导。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-106">If you're not sure if you should create a shared mailbox or an Office 365 Group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="f1b0a-107">请注意，目前不能将共享邮箱迁移到 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-107">Note that currently, it's not possible to migrate a shared mailbox to an Office 365 Group.</span></span> <span data-ttu-id="f1b0a-108">如果这不是你想要的结果，请通过[在此处投票](https://go.microsoft.com/fwlink/?linkid=871518)告诉我们。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="f1b0a-p103">创建共享邮箱很容易，通过共享邮箱，多位人员可以从一个公用电子邮件地址（如 info@contoso.com）监控和发送电子邮件。当群组中的某个人员答复发送到共享邮箱的邮件时，系统显示电子邮件来自共享邮箱，而不是单个用户。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="f1b0a-111">共享邮箱包含共享日历。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="f1b0a-112">许多小型企业喜欢使用共享日历，方便每个人在其中输入约会。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="f1b0a-113">例如，如果有 3 个人在进行客户访问工作，则他们都可以使用共享日历来输入约会。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="f1b0a-114">这是使每个人都知道他人位置的简便方法。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="f1b0a-115">创建共享邮箱之前，请务必阅读[关于共享邮箱](about-shared-mailboxes.md)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="f1b0a-116">创建共享邮箱并添加成员</span><span class="sxs-lookup"><span data-stu-id="f1b0a-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="f1b0a-117">使用 Office 365 全局管理员帐户或 Exchange 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-117">Sign in with an Office 365 global admin account or Exchange admin account.</span></span> <span data-ttu-id="f1b0a-118">如果收到消息“**你没有访问此页面或执行此操作的权限**”，则表明你不是管理员。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="f1b0a-119">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="f1b0a-120">在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)，转到“**组**”\>“**共享邮箱**”页面。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="f1b0a-121">在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)，转到“**组**”\>“**共享邮箱**”页面。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="f1b0a-122">在“**共享邮箱**”页面上，选择“**+添加邮箱**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="f1b0a-123">输入共享邮箱的名称。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="f1b0a-124">然后向导会选择电子邮件地址，但你也可以编辑电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![为共享邮箱命名。](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="f1b0a-126">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-126">Select **Add**.</span></span> <span data-ttu-id="f1b0a-127">可能需要几分钟时间，才可以添加成员。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="f1b0a-128">在“**后续步骤**”下，选择“**将成员添加到此邮箱**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="f1b0a-129">成员能够查看此共享邮箱收到的邮件及发出的答复。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![选择“添加成员”。](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="f1b0a-131">选择“**+添加成员**”按钮。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-131">Select the **+Add members** button.</span></span> <span data-ttu-id="f1b0a-132">在希望其使用共享邮箱的人员旁添加一个复选标记，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![向共享邮箱分配成员。](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="f1b0a-134">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-134">Select **Close**.</span></span>

<span data-ttu-id="f1b0a-135">你有一个共享邮箱，而且它包含一个共享日历。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="f1b0a-136">现转到下一步：阻止登录共享邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="f1b0a-137">阻止登录共享邮箱帐户</span><span class="sxs-lookup"><span data-stu-id="f1b0a-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="f1b0a-138">每个共享邮箱都有相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="f1b0a-139">注意到你在创建共享邮箱时未被要求提供密码？</span><span class="sxs-lookup"><span data-stu-id="f1b0a-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="f1b0a-140">该帐户有一个密码，但密码是系统生成的（未知）。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="f1b0a-141">不得使用该帐户登录共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="f1b0a-142">但如果管理员重置了共享邮箱用户帐户的密码，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="f1b0a-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="f1b0a-143">如果攻击者获取了对共享邮箱用户帐户的密码，又该怎么办？</span><span class="sxs-lookup"><span data-stu-id="f1b0a-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="f1b0a-144">这将使得用户帐户能够登录共享邮箱并发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="f1b0a-145">要阻止此操作，需要阻止登录与共享邮箱关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f1b0a-146">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-146">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="f1b0a-147">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f1b0a-148">在用户帐户列表中，找到共享邮箱的帐户（例如，将筛选器更改为“**未经授权的用户**”）。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-148">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="f1b0a-149">选择该用户以打开其属性窗格，然后 选择“**阻止此用户**”图标 ![“阻止此用户”图标的屏幕截图](../../media/block-user-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-149">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="f1b0a-150">**注意**：如果已阻止该帐户，则将在顶部显示“**已阻止登录**”，并且图标将显示“**取消阻止此用户**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-150">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="f1b0a-151">在“**阻止此用户?**”窗格中，选择“**阻止用户登录**”，然后选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-151">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f1b0a-152">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f1b0a-153">在用户帐户列表中，找到共享邮箱的帐户（例如，将视图更改为“**未经授权的用户**”），然后选择该帐户。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-153">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="f1b0a-154">在“属性”浮出控件中，选择“**阻止登录**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-154">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="f1b0a-155">**注意：** 如果已阻止该帐户，该按钮将显示“**取消阻止登录**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-155">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="f1b0a-156">在“**登录状态**”浮出控件中，验证确定已选择“阻止用户登录”，选择“**保存**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-156">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f1b0a-157">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f1b0a-158">在用户帐户列表中，找到共享邮箱的帐户（例如，将视图更改为“**未经授权的用户**”），然后选择该帐户。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-158">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="f1b0a-159">在“属性”浮出控件中，选择“**阻止登录**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-159">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="f1b0a-160">**注意：** 如果已阻止该帐户，该按钮将显示“**取消阻止登录**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-160">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="f1b0a-161">在“**登录状态**”浮出控件中，验证确定已选择“阻止用户登录”，选择“**保存**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-161">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="f1b0a-162">有关如何使用 Azure AD PowerShell 阻止登录帐户（包括同时登录多个帐户）的说明，请参阅 [使用 Office 365 PowerShell 阻止用户帐户](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-162">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="f1b0a-163">向 Outlook 添加共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f1b0a-163">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="f1b0a-164">如果企业启用了自动映射（默认情况下，大部分用户都会启用此功能），共享邮箱将在用户关闭并重启 Outlook 后自动出现在其 Outlook 应用中。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-164">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="f1b0a-165">在用户邮箱（而非共享邮箱）上设置自动映射。  </span><span class="sxs-lookup"><span data-stu-id="f1b0a-165">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="f1b0a-166">这意味着如果尝试使用安全组来管理有权访问共享邮箱的人员，自动映射将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-166">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="f1b0a-167">因此，如果想要自动映射，必须显式分配权限。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-167">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="f1b0a-168">自动映射默认启用。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-168">Automapping is on by default.</span></span> <span data-ttu-id="f1b0a-169">要了解如何将其关闭，请参阅 [删除共享邮箱的自动映射](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-169">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="f1b0a-170">要详细了解 Outlook 中的共享邮箱，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f1b0a-170">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="f1b0a-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">在 Outlook 中打开和使用共享邮箱</a></span><span class="sxs-lookup"><span data-stu-id="f1b0a-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="f1b0a-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">将共享邮箱添加到 Outlook 网页版</a></span><span class="sxs-lookup"><span data-stu-id="f1b0a-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="f1b0a-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">将共享邮箱添加到 Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="f1b0a-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="f1b0a-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">在 Outlook for Mac 中打开共享文件夹或邮箱</a></span><span class="sxs-lookup"><span data-stu-id="f1b0a-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="f1b0a-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">向共享邮箱添加规则</a></span><span class="sxs-lookup"><span data-stu-id="f1b0a-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="f1b0a-176">在移动设备（手机或平板电脑）上使用共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f1b0a-176">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="f1b0a-177">可采用下列两种方式在移动设备上访问共享邮箱：</span><span class="sxs-lookup"><span data-stu-id="f1b0a-177">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="f1b0a-178">在 <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS 应用</a>或 <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android 移动应用</a>中添加共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-178">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="f1b0a-179">有关说明，请参阅<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">在 Outlook Mobile 中添加共享邮箱</a>。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-179">For instructions, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="f1b0a-180">打开浏览器、登录 Office 365，然后转到 Outlook 网页版。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-180">Open your browser, sign in to Office 365, and then go to Outlook on the web.</span></span> <span data-ttu-id="f1b0a-181">可从 Outlook 网页版访问共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-181">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="f1b0a-182">有关说明，请参阅<a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">在 Outlook 网页版中添加共享邮箱</a>。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-182">For instructions, see <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="f1b0a-183">使用共享日历</span><span class="sxs-lookup"><span data-stu-id="f1b0a-183">Use the shared calendar</span></span>

<span data-ttu-id="f1b0a-184">创建共享邮箱时，会自动创建共享日历。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="f1b0a-185">我们希望使用共享邮箱日历（而不是 SharePoint 日历）来跟踪约会和位置。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="f1b0a-186">共享日历与 Outlook 集成，与 SharePoint 日历相比更易于使用。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="f1b0a-187">在 Outlook 应用中，转到日历视图，然后选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="f1b0a-188">输入约会后，共享邮箱的每个成员都能看到它们。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="f1b0a-189">共享邮箱的所有成员都可以在该日历上创建、查看和管理约会，就像处理自己的个人约会一样。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="f1b0a-190">共享邮箱的所有成员都可以看到他们对共享日历所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f1b0a-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f1b0a-191">相关文章</span><span class="sxs-lookup"><span data-stu-id="f1b0a-191">Related articles</span></span>

[<span data-ttu-id="f1b0a-192">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f1b0a-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f1b0a-193">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f1b0a-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f1b0a-194">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f1b0a-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f1b0a-195">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="f1b0a-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="f1b0a-196">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="f1b0a-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)




