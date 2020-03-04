---
title: 更改名称服务器以将 Office 365 设置为 1&1 IONOS
f1.keywords:
- NOCSH
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 了解如何设置由世纪互联运营的 Office 365 以管理 DNS 记录，当 1&1 Internet 是 DNS 托管提供商时。
ms.openlocfilehash: 3678d5372b9edd8e9333ad78862694b450abe53a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352563"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a><span data-ttu-id="b716c-103">更改名称服务器以将 Office 365 设置为 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="b716c-103">Change nameservers to set up Office 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="b716c-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="b716c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b716c-105">如果希望 Office 365 管理 Office 365 DNS 记录，请按以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="b716c-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="b716c-106">（如果愿意，您可以[在 1&1 IONOS 管理所有的 Office 365 DNS 记录](create-dns-records-at-1-1-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="b716c-106">(If you prefer, you can [manage all your Office 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b716c-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="b716c-107">Add a TXT record for verification</span></span>


<span data-ttu-id="b716c-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="b716c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b716c-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="b716c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b716c-112">请按下列步骤操作或[观看视频（从 0:42 开始）](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b716c-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b716c-113">若要开始，请转到域页面 1&1 IONOS 通过[此链接](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)。</span><span class="sxs-lookup"><span data-stu-id="b716c-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="b716c-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b716c-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="b716c-115">在 **"我的域**" 下，选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b716c-116">在 "**域中心**" 页上，找到要更新的域;然后，选择该域的 **"面板"** （ **v**）控件。</span><span class="sxs-lookup"><span data-stu-id="b716c-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b716c-117">在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b716c-118">在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="b716c-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b716c-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="b716c-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b716c-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b716c-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="b716c-121">**Type**</span></span> <br/> |<span data-ttu-id="b716c-122">**前缀**</span><span class="sxs-lookup"><span data-stu-id="b716c-122">**Prefix**</span></span> <br/> |<span data-ttu-id="b716c-123">**名称值**</span><span class="sxs-lookup"><span data-stu-id="b716c-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="b716c-124">TXT</span><span class="sxs-lookup"><span data-stu-id="b716c-124">TXT</span></span>  <br/> |<span data-ttu-id="b716c-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="b716c-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b716c-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b716c-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="b716c-127">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="b716c-127">**Note**: This is an example.</span></span> <span data-ttu-id="b716c-128">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="b716c-128">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="b716c-129">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="b716c-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="b716c-130">选择 "**保存**"，然后重新**保存**。</span><span class="sxs-lookup"><span data-stu-id="b716c-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="b716c-131">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="b716c-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="b716c-132">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="b716c-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b716c-133">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="b716c-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b716c-134">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="b716c-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b716c-135">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="b716c-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b716c-136">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="b716c-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b716c-137">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="b716c-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b716c-138">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="b716c-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b716c-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b716c-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b716c-140">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="b716c-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b716c-141">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b716c-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b716c-142">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="b716c-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b716c-p107">要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="b716c-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b716c-p108">将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。例如，在你进行此更改之后，发送到你的域（例如 rob@ *your_domain*  .com）的所有电子邮件都将开始传送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b716c-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
<span data-ttu-id="b716c-p109">准备好更改 NS 记录以便 Office 365 可以设置域了吗？请按下列步骤操作或[观看视频（从 2:47 开始）](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b716c-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="b716c-150">下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="b716c-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="b716c-151">> 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="b716c-152">若要开始，请使用[此链接](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)转到域页面 1&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="b716c-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="b716c-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b716c-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="b716c-154">在 **"我的域**" 下，选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b716c-155">在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="b716c-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b716c-156">在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b716c-157">在" **名称服务器设置**"部分中，选择" **其他名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="b716c-158">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="b716c-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="b716c-159">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：</span><span class="sxs-lookup"><span data-stu-id="b716c-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="b716c-160">如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="b716c-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="b716c-161">如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="b716c-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b716c-162">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="b716c-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="b716c-163">在" **名称服务器 1**"框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="b716c-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b716c-164">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="b716c-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="b716c-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![在 "名称服务器 1" 框中输入值](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="b716c-167">在" **其他名称服务器**"下拉列表中，选择" **我的辅助名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="b716c-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="b716c-169">在" **名称服务器 2、3 和 4**"框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="b716c-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b716c-170">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="b716c-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="b716c-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b716c-172">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="b716c-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="b716c-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b716c-174">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="b716c-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="b716c-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="b716c-176">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b716c-176">Select **Save**.</span></span>
    
    ![在 "名称服务器设置" 页上选择 "保存"](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="b716c-178">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="b716c-178">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![在 "编辑 DNS 设置" 对话框中选择 "保存"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="b716c-p112">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="b716c-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b716c-182">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="b716c-182">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="b716c-p113">*仅*  当具有这四个  *正确*  的名称服务器以外的现有名称服务器时，执行以下步骤。（即，  *仅*  删除名称  *不是* **ns1.bdm.microsoftonline.com** 、 **ns2.bdm.microsoftonline.com** 、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的任何当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="b716c-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="b716c-185">如果" **名称服务器**"框中已列有名称服务器，通过选择每一项，然后按键盘上的 **Delete** 键，将其删除。</span><span class="sxs-lookup"><span data-stu-id="b716c-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="b716c-187">在" **名称服务器 1、2、3 和 4**"框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="b716c-187">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b716c-188">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="b716c-188">**Name server 1**</span></span> <br/> |<span data-ttu-id="b716c-189">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-189">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b716c-190">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="b716c-190">**Name server 2**</span></span> <br/> |<span data-ttu-id="b716c-191">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-191">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b716c-192">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="b716c-192">**Name server 3**</span></span> <br/> |<span data-ttu-id="b716c-193">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-193">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b716c-194">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="b716c-194">**Name server 4**</span></span> <br/> |<span data-ttu-id="b716c-195">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b716c-195">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![输入名称服务器值](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="b716c-197">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b716c-197">Select **Save**.</span></span>
    
    ![在 "名称服务器设置" 页上选择 "保存"](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="b716c-199">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="b716c-199">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![在 "编辑 DNS 设置" 对话框中选择 "保存"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="b716c-p114">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="b716c-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

