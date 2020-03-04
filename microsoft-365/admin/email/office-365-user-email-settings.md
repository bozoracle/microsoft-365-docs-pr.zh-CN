---
title: Office 365 用户电子邮件设置
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.collection:
- Adm_O365
- Adm_TOC
localization_priority: Priority
ms.assetid: 03083fdf-bc52-409a-b2ac-2a5f5c308fa0
description: 本文提供有关管理用户设置的信息。
ms.openlocfilehash: 7f79f90c9fe94596a5901d8ce9e6b31ba0af881e
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251172"
---
# <a name="office-365-user-email-settings"></a><span data-ttu-id="d8d10-103">Office 365 用户电子邮件设置</span><span class="sxs-lookup"><span data-stu-id="d8d10-103">Office 365 user email settings</span></span>

<span data-ttu-id="d8d10-104">Office 365 组织的管理员可管理用户的电子邮件设置。</span><span class="sxs-lookup"><span data-stu-id="d8d10-104">As the admin of an Office 365 organization, there are email settings you can manage on your users.</span></span> <span data-ttu-id="d8d10-105">本文提供有关管理这些设置的信息。</span><span class="sxs-lookup"><span data-stu-id="d8d10-105">This article gives you information on managing these settings.</span></span>

## <a name="summary-of-email-settings"></a><span data-ttu-id="d8d10-106">电子邮件设置摘要</span><span class="sxs-lookup"><span data-stu-id="d8d10-106">Summary of email settings</span></span>

<span data-ttu-id="d8d10-107">下表将介绍可在 Office 365 中为用户更改的各种电子邮件设置。</span><span class="sxs-lookup"><span data-stu-id="d8d10-107">This table explains the various email settings you can change for a user in Office 365.</span></span>


|<span data-ttu-id="d8d10-108">邮件设置</span><span class="sxs-lookup"><span data-stu-id="d8d10-108">Mail setting</span></span>|<span data-ttu-id="d8d10-109">说明</span><span class="sxs-lookup"><span data-stu-id="d8d10-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d8d10-110">邮箱权限</span><span class="sxs-lookup"><span data-stu-id="d8d10-110">Mailbox permissions</span></span>| <span data-ttu-id="d8d10-111">通过“**阅读和管理**”可以设置用户是否有权阅读和管理他人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d8d10-111">**Read and manage** allows you to set whether people can read and manage other people's mailboxes.</span></span> <span data-ttu-id="d8d10-112">还可为用户设置“**发送方式**”和“**代表发送**”权限。</span><span class="sxs-lookup"><span data-stu-id="d8d10-112">You can also set **Send as** and **Send on behalf** permissions for a person.</span></span> <span data-ttu-id="d8d10-113">有关详细信息，请参阅[将邮箱权限授予 Office 365 中的另一用户 - 管理员帮助](../add-users/give-mailbox-permissions-to-another-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d8d10-113">Check out [Give mailbox permissions to another user in Office 365 - Admin Help](../add-users/give-mailbox-permissions-to-another-user.md) for more details.</span></span> |
|<span data-ttu-id="d8d10-114">电子邮件应用</span><span class="sxs-lookup"><span data-stu-id="d8d10-114">Email apps</span></span>| <span data-ttu-id="d8d10-115">通过“电子邮件应用”可以选择用户可用于访问其 Office 365 电子邮件的应用。</span><span class="sxs-lookup"><span data-stu-id="d8d10-115">Email apps allows you to choose the apps a user can use to access their Office 365 email.</span></span> |
|<span data-ttu-id="d8d10-116">在全局地址列表中显示</span><span class="sxs-lookup"><span data-stu-id="d8d10-116">Show in global address list</span></span>| <span data-ttu-id="d8d10-117">通过“在全局地址列表中显示”可以启用或禁用用户邮箱在组织地址列表中的可见性。</span><span class="sxs-lookup"><span data-stu-id="d8d10-117">Show in global address list allows you to enable or disable the visibility of the user's mailbox in the organization's address list.</span></span> |
|<span data-ttu-id="d8d10-118">电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="d8d10-118">Email forwarding</span></span>|<span data-ttu-id="d8d10-119">通过“电子邮件转发”可以为用户添加转发电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d8d10-119">Email forwarding allows you to add a forwarding email address to a user.</span></span> <span data-ttu-id="d8d10-120">如果用户有多个电子邮件地址，并且想要在其所有电子邮件地址中都收到电子邮件，你可能需要执行此设置。</span><span class="sxs-lookup"><span data-stu-id="d8d10-120">You might want to do this if the person has multiple email addresses and they want to receive emails at all their email addresses.</span></span> <span data-ttu-id="d8d10-121">有关详细信息，请参阅[在 Office 365 中配置电子邮件转发](configure-email-forwarding.md)。</span><span class="sxs-lookup"><span data-stu-id="d8d10-121">Check out [Configure email forwarding in Office 365](configure-email-forwarding.md) for more details.</span></span>|
|<span data-ttu-id="d8d10-122">自动答复</span><span class="sxs-lookup"><span data-stu-id="d8d10-122">Automatic replies</span></span>|<span data-ttu-id="d8d10-123">“自动答复”允许你设置在某人向用户的电子邮件地址发送电子邮件时进行自动答复。</span><span class="sxs-lookup"><span data-stu-id="d8d10-123">Automatic replies allows you to set an automatic reply when someone sends an email to the person's email address.</span></span> <span data-ttu-id="d8d10-124">如果员工离开了公司，而你想让电子邮件发件人知道这种情况，你可能需要执行此设置。</span><span class="sxs-lookup"><span data-stu-id="d8d10-124">You might want to do this if an employee leaves your company and you want to let the email sender know.</span></span>|
|<span data-ttu-id="d8d10-125">更多操作</span><span class="sxs-lookup"><span data-stu-id="d8d10-125">More actions</span></span>| <span data-ttu-id="d8d10-126">通过“**转换为共享邮箱**”可以将用户的邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="d8d10-126">**Convert to shared mailbox** allows you to convert the user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="d8d10-127">如果用户离开了你的组织，而你想将其邮箱数据保留一段时间，你可以执行此设置。</span><span class="sxs-lookup"><span data-stu-id="d8d10-127">You might do this if the person leaves your organization and you want to keep their mailbox data around for a while.</span></span> <span data-ttu-id="d8d10-128">请参阅[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)以及[打开和使用共享邮箱](https://support.office.com/article/open-and-use-a-shared-mailbox-in-outlook-d94a8e9e-21f1-4240-808b-de9c9c088afd)。</span><span class="sxs-lookup"><span data-stu-id="d8d10-128">Check out [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) and [Open and use a shared mailbox](https://support.office.com/article/open-and-use-a-shared-mailbox-in-outlook-d94a8e9e-21f1-4240-808b-de9c9c088afd).</span></span></br><span data-ttu-id="d8d10-129">通过“**编辑 Exchange 属性**”可以使用 Exchange 管理中心管理其他 Exchange Online 任务。</span><span class="sxs-lookup"><span data-stu-id="d8d10-129">**Edit Exchange properties** allows you to manage additional Exchange Online tasks using the Exchange admin center.</span></span> <span data-ttu-id="d8d10-130">请参阅[在 Exchange Online 中管理用户邮箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="d8d10-130">Read about [managing user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span>|