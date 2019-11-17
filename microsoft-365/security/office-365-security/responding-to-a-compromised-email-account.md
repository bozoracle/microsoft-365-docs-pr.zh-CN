---
title: 响应 Office 365 中遭到入侵的电子邮件帐户
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何识别并响应 Office 365 中遭到入侵的电子邮件帐户
ms.openlocfilehash: af57d1fb52718561b1d8e9feef90a46613d753ee
ms.sourcegitcommit: 8aa9f204b056f01bfb4c357347dc1592d0c9b688
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38669841"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="3fdaa-103">响应 Office 365 中遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="3fdaa-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="3fdaa-104">**摘要** 了解如何识别并响应 Office 365 中遭到入侵的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="3fdaa-105">什么是 Office 365 中遭到入侵的电子邮件帐户？</span><span class="sxs-lookup"><span data-stu-id="3fdaa-105">What is a Compromised Email Account in Office 365?</span></span>

<span data-ttu-id="3fdaa-106">通过使用凭据（例如用户名和密码或 PIN）来控制对 Office 365 邮箱、数据和其他服务的访问。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-106">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="3fdaa-107">如果除预期用户以外的其他人窃取了这些凭据，则被盗的凭据将视为遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="3fdaa-108">借助这些凭据，攻击者能够以原始用户的身份登录并执行非法操作。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="3fdaa-109">通过使用窃取的凭据，攻击者可以访问用户的 Office 365 邮箱、SharePoint 文件夹或用户 OneDrive 中的文件。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-109">Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="3fdaa-110">其中一种常见操作是攻击者以原始用户的身份将电子邮件发送给组织内外的收件人。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="3fdaa-111">当攻击者通过电子邮件将数据发送给外部收件人时，这称为数据泄露。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="3fdaa-112">遭到入侵的 Office 365 电子邮件帐户的症状</span><span class="sxs-lookup"><span data-stu-id="3fdaa-112">Symptoms of a Compromised Office 365 Email Account</span></span>

<span data-ttu-id="3fdaa-113">用户可能会注意到并报告其 Office 365 邮箱中的异常活动。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-113">Users might notice and report unusual activity in their Office 365 mailboxes.</span></span> <span data-ttu-id="3fdaa-114">下面是一些常见症状：</span><span class="sxs-lookup"><span data-stu-id="3fdaa-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="3fdaa-115">可疑活动，例如丢失或删除的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-115">Suspicious activity, such as missing or deleted emails.</span></span>
- <span data-ttu-id="3fdaa-116">其他用户可能会收到来自遭到入侵的帐户的电子邮件，而发件人的“**已发送邮件**”文件夹中没有相应的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>
- <span data-ttu-id="3fdaa-117">存在并非由预期用户或管理员创建的收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="3fdaa-118">这些规则可以自动将电子邮件转发到未知地址，或将其移动到“**便笺**”、“**垃圾邮件**”或“**RSS 订阅**”文件夹。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>
- <span data-ttu-id="3fdaa-119">在全局地址列表中，用户的显示名称可能已发生更改。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-119">The user's display name might be changed in the Global Address List.</span></span>
- <span data-ttu-id="3fdaa-120">用户的邮箱被阻止发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-120">The user's mailbox is blocked from sending email.</span></span>
- <span data-ttu-id="3fdaa-121">Microsoft Outlook 或 Outlook 网页版（以前称为 Outlook Web App）中的“已发送邮件”或“已删除邮件”文件夹包含常见的黑客帐户邮件，例如“我被困在伦敦，请给我汇款”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>
- <span data-ttu-id="3fdaa-122">异常的个人资料更改，例如更新了姓名、电话号码或邮政编码。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>
- <span data-ttu-id="3fdaa-123">异常的凭据更改，例如多次要求进行密码更改。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-123">Unusual credential changes, such as multiple password changes are required.</span></span>
- <span data-ttu-id="3fdaa-124">最近添加了邮件转发功能。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-124">Mail forwarding was recently added.</span></span>
- <span data-ttu-id="3fdaa-125">最近添加了异常的签名，例如假银行签名或处方药签名。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="3fdaa-126">如果用户报告了上述任何症状，你应该进一步展开调查。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="3fdaa-127">Microsoft 365 安全与合规中心和 Azure 门户提供了各种工具，可帮助你对疑似遭到入侵的用户帐户的活动展开调查。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="3fdaa-128">安全与合规中心中的 Office 365 统一审核日志 - 通过筛选从可疑活动发生前一天到当前日期之间的日期范围的结果，检查可疑帐户的所有活动。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-128">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="3fdaa-129">不要在搜索过程中筛选活动。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-129">Do not filter on the activities during the search.</span></span>
- <span data-ttu-id="3fdaa-130">使用 Azure AD 登录日志和 Azure AD 门户中提供的其他风险报告。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-130">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal.</span></span> <span data-ttu-id="3fdaa-131">检查以下列中的值：</span><span class="sxs-lookup"><span data-stu-id="3fdaa-131">Examine the values in these columns:</span></span>
    - <span data-ttu-id="3fdaa-132">查看 IP 地址</span><span class="sxs-lookup"><span data-stu-id="3fdaa-132">Review IP address</span></span>
    - <span data-ttu-id="3fdaa-133">登录位置</span><span class="sxs-lookup"><span data-stu-id="3fdaa-133">sign-in locations</span></span>
    - <span data-ttu-id="3fdaa-134">登录时间</span><span class="sxs-lookup"><span data-stu-id="3fdaa-134">sign-in times</span></span>
    - <span data-ttu-id="3fdaa-135">登录成功或失败</span><span class="sxs-lookup"><span data-stu-id="3fdaa-135">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="3fdaa-136">如何保护和恢复疑似遭到入侵的 Office 365 帐户和邮箱的电子邮件功能</span><span class="sxs-lookup"><span data-stu-id="3fdaa-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="3fdaa-137">即使你重新获得对帐户的访问权限，攻击者也可能添加了后门条目，这让攻击者能够恢复对该帐户的控制权。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="3fdaa-138">你必须执行以下所有步骤才能重新获得对帐户的访问权限，以便更快地确保劫持者无法继续控制你的帐户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-138">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="3fdaa-139">这些步骤可帮助你删除劫持者可能已添加到你帐户的任何后门条目。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-139">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="3fdaa-140">执行这些步骤后，我们建议你运行病毒扫描以确保你的计算机不会遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-140">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="3fdaa-141">步骤 1 重置用户密码</span><span class="sxs-lookup"><span data-stu-id="3fdaa-141">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="3fdaa-142">不要通过电子邮件将新密码发送给预期用户，因为此时攻击者仍可以访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="3fdaa-143">按照“[管理员：重置 Office 365 商业版密码](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)”中的“为其他人重置 Office 365 商业版密码”步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span></span>

<span data-ttu-id="3fdaa-144">**注意：**</span><span class="sxs-lookup"><span data-stu-id="3fdaa-144">**Notes:**</span></span>
- <span data-ttu-id="3fdaa-145">确保密码为强密码，并且包含大写和小写字母、至少一个数字和至少一个特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span> 
- <span data-ttu-id="3fdaa-146">不要重复使用过去五个密码中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-146">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="3fdaa-147">即使密码历史记录要求允许你重复使用最近使用过的密码，你也应该选择攻击者无法猜到的密码。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-147">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
- <span data-ttu-id="3fdaa-148">如果你的本地标识已与 Office 365 联合，则必须在本地更改密码，然后通知管理员帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="3fdaa-149">强烈建议你启用多重身份验证 (MFA) 以防止入侵，尤其是对于具有管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-149">It is highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="3fdaa-150">你可以在[此处](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-150">You can learn more [here](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="3fdaa-151">步骤 2 删除可疑的电子邮件转发地址</span><span class="sxs-lookup"><span data-stu-id="3fdaa-151">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="3fdaa-152">打开“**Microsoft 365 管理中心 > 活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-152">Open the **Microsoft 365 admin center > Active Users**.</span></span>
2. <span data-ttu-id="3fdaa-153">找到存在问题的用户帐户并展开“**邮件设置**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-153">Find the user account in question and expand **Mail Settings**.</span></span>
3. <span data-ttu-id="3fdaa-154">对于“**电子邮件转发**”，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-154">For **Email forwarding**, click **Edit**.</span></span>
4. <span data-ttu-id="3fdaa-155">删除所有可疑的转发地址。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-155">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="3fdaa-156">步骤 3 禁用任何可疑的收件箱规则</span><span class="sxs-lookup"><span data-stu-id="3fdaa-156">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="3fdaa-157">使用 Outlook 网页版登录用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-157">Sign in to the user's mailbox using Outlook on the web.</span></span>
2. <span data-ttu-id="3fdaa-158">单击齿轮图标，然后单击“**邮件**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-158">Click on the gear icon and click **Mail**.</span></span>
3. <span data-ttu-id="3fdaa-159">单击“**收件箱和整理规则**”并查看规则。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-159">Click **Inbox and sweep rules** and review the rules.</span></span>
4. <span data-ttu-id="3fdaa-160">禁用或删除可疑的规则。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-160">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="3fdaa-161">步骤 4 取消阻止用户发送邮件</span><span class="sxs-lookup"><span data-stu-id="3fdaa-161">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="3fdaa-162">如果疑似遭到入侵的邮箱被非法用于发送垃圾电子邮件，则可能是该邮箱已被阻止发送邮件。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-162">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>
1. <span data-ttu-id="3fdaa-163">若要取消阻止邮箱发送邮件，请按照[在发送垃圾电子邮件后从阻止列表中删除用户、域或 IP 地址](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam)中的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-163">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="3fdaa-164">步骤 5（可选）阻止用户帐户登录</span><span class="sxs-lookup"><span data-stu-id="3fdaa-164">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fdaa-165">你可以阻止疑似遭到入侵的帐户登录，直到你认为重新启用访问权限是安全的。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-165">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="3fdaa-166">转到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-166">Go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="3fdaa-167">在 Microsoft 365 管理中心，选择“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-167">In the Microsoft 365 admin center, select **Users**.</span></span>
3. <span data-ttu-id="3fdaa-168">选择要阻止的员工，然后在用户窗格中选择“**登录状态**”旁边的“**编辑**”</span><span class="sxs-lookup"><span data-stu-id="3fdaa-168">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>
4. <span data-ttu-id="3fdaa-169">在“**登录状态**”窗格上，选择“**阻止登录**”，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-169">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span> 
5. <span data-ttu-id="3fdaa-170">在管理中心左下方的导航窗格中，展开“**管理中心**”，然后选择“**Exchange**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-170">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>
6. <span data-ttu-id="3fdaa-171">在 Exchange 管理中心，导航到“**收件人 > 邮箱**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-171">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>
7. <span data-ttu-id="3fdaa-172">选择用户，然后在用户属性页面的“**移动设备**”下，单击“**禁用 Exchange ActivcSync**”和“**禁用适用于设备的 OWA**”，并对两者选择“**是**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-172">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>
8. <span data-ttu-id="3fdaa-173">在“**电子邮件连接**”下，单击“**禁用**”并选择“**是**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-173">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span> 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="3fdaa-174">步骤 6（可选）从所有管理角色组中删除疑似遭到入侵的帐户</span><span class="sxs-lookup"><span data-stu-id="3fdaa-174">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="3fdaa-175">在帐户受到保护后，可以恢复管理角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-175">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="3fdaa-176">使用全局管理员帐户登录 Microsoft 365 管理中心，然后打开“**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-176">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>
2. <span data-ttu-id="3fdaa-177">找到疑似遭到入侵的帐户并手动检查是否为该帐户分配了任何管理角色。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-177">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>
3. <span data-ttu-id="3fdaa-178">打开“**安全与合规中心**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-178">Open the **Security & Compliance Center**.</span></span>
4. <span data-ttu-id="3fdaa-179">单击“**权限**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-179">Click **Permissions**.</span></span>
5. <span data-ttu-id="3fdaa-180">手动检查角色组以查看疑似遭到入侵的帐户是否是其中任何一个组的成员。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-180">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="3fdaa-181">如果是，a.</span><span class="sxs-lookup"><span data-stu-id="3fdaa-181">If it is: a.</span></span> <span data-ttu-id="3fdaa-182">单击角色组，然后单击“**编辑角色组**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-182">Click the role group and click **Edit Role Group**.</span></span>
    <span data-ttu-id="3fdaa-183">b.</span><span class="sxs-lookup"><span data-stu-id="3fdaa-183">b.</span></span> <span data-ttu-id="3fdaa-184">单击“**选择成员**”和“**编辑**”以从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-184">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>
6. <span data-ttu-id="3fdaa-185">打开“**Exchange 管理中心**”</span><span class="sxs-lookup"><span data-stu-id="3fdaa-185">Open the **Exchange admin center**</span></span>
7. <span data-ttu-id="3fdaa-186">单击“**权限**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-186">Click **Permissions**.</span></span>
8. <span data-ttu-id="3fdaa-187">手动检查角色组以查看疑似遭到入侵的帐户是否是其中任何一个组的成员。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-187">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="3fdaa-188">如果是，a.</span><span class="sxs-lookup"><span data-stu-id="3fdaa-188">If it is: a.</span></span> <span data-ttu-id="3fdaa-189">单击角色组，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-189">Click the role group and click **Edit**.</span></span>
    <span data-ttu-id="3fdaa-190">b.</span><span class="sxs-lookup"><span data-stu-id="3fdaa-190">b.</span></span> <span data-ttu-id="3fdaa-191">使用“**成员**”部分从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-191">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="3fdaa-192">步骤 7（可选）其他预防措施</span><span class="sxs-lookup"><span data-stu-id="3fdaa-192">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="3fdaa-193">确保验证已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-193">Make sure that you verify your sent items.</span></span> <span data-ttu-id="3fdaa-194">你可能需要通知联系人列表中的人员你的帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-194">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="3fdaa-195">例如，攻击者可能会向他们要钱，谎称他们被困在另一个国家/地区并且需要钱，也可能会向他们发送病毒以便劫持其计算机。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-195">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>
2. <span data-ttu-id="3fdaa-196">将此 Exchange 帐户用作其备用电子邮件帐户的任何其他服务可能已遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-196">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="3fdaa-197">首先，为 Office 365 订阅执行这些步骤，然后为其他帐户执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-197">First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>
3. <span data-ttu-id="3fdaa-198">确保你的联系信息（如电话号码和地址）正确无误。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-198">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="3fdaa-199">像网络安全专家那样保护 Office 365</span><span class="sxs-lookup"><span data-stu-id="3fdaa-199">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="3fdaa-200">你的 Office 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-200">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="3fdaa-201">使用“[Office 365 安全路线图：前 30 天、90 天内以及之后的首要行动](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)”，通过实施 Microsoft 建议的最佳做法来保护你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-201">Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="3fdaa-202">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-202">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="3fdaa-203">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-203">These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="3fdaa-204">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-204">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="3fdaa-205">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-205">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="3fdaa-206">90 天后。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-206">Beyond 90 days.</span></span> <span data-ttu-id="3fdaa-207">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-207">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fdaa-208">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="3fdaa-208">See also:</span></span>

- [<span data-ttu-id="3fdaa-209">Office 365 的安全最佳做法</span><span class="sxs-lookup"><span data-stu-id="3fdaa-209">Security best practices for Office 365</span></span>](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [<span data-ttu-id="3fdaa-210">在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="3fdaa-210">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](/security/office-365-security/detect-and-remediate-outlook-rules-forms-attack.md)
- [<span data-ttu-id="3fdaa-211">Internet 犯罪投诉中心</span><span class="sxs-lookup"><span data-stu-id="3fdaa-211">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)
- [<span data-ttu-id="3fdaa-212">证券交易委员会 -“网络钓鱼”诈骗</span><span class="sxs-lookup"><span data-stu-id="3fdaa-212">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)
- <span data-ttu-id="3fdaa-213">[使用报告消息加载项](https://support.office.com/zh-CN/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)直接向 Microsoft 和你的管理员报告垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="3fdaa-213">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/zh-CN/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>