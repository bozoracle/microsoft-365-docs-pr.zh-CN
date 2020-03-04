---
title: 使用 Amazon Web Services (AWS) 更改名称服务器以设置 Office 365
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: '了解如何设置 Office 365 以管理 Amazon Web 服务（AWS）上的 DNS 记录。 '
ms.openlocfilehash: 9500522478c22277c57772ef64b4d0a4b87e8c44
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352483"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="052b5-103">使用 Amazon Web Services (AWS) 更改名称服务器以设置 Office 365</span><span class="sxs-lookup"><span data-stu-id="052b5-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="052b5-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="052b5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="052b5-p101">如果希望 Office 365 管理你的 Office 365 DNS 记录，请按照以下说明操作。 （如果愿意，你可以[在 AWS 中管理所有 Office 365 DNS 记录](create-dns-records-at-aws.md)。）</span><span class="sxs-lookup"><span data-stu-id="052b5-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="052b5-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="052b5-107">Add a TXT record for verification</span></span>

<span data-ttu-id="052b5-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="052b5-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="052b5-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="052b5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="052b5-p104">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="052b5-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="052b5-114">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="052b5-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="052b5-115">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="052b5-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="052b5-116">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="052b5-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="052b5-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="052b5-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="052b5-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="052b5-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="052b5-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="052b5-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="052b5-121">**名称**</span><span class="sxs-lookup"><span data-stu-id="052b5-121">**Name**</span></span> <br/> |<span data-ttu-id="052b5-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="052b5-122">**Type**</span></span> <br/> |<span data-ttu-id="052b5-123">**别名**</span><span class="sxs-lookup"><span data-stu-id="052b5-123">**Alias**</span></span> <br/> |<span data-ttu-id="052b5-124">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="052b5-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="052b5-125">**值**</span><span class="sxs-lookup"><span data-stu-id="052b5-125">**Value**</span></span> <br/> |<span data-ttu-id="052b5-126">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="052b5-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="052b5-127">（将此字段留空）</span><span class="sxs-lookup"><span data-stu-id="052b5-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="052b5-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="052b5-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="052b5-129">否</span><span class="sxs-lookup"><span data-stu-id="052b5-129">No</span></span>  <br/> |<span data-ttu-id="052b5-130">300</span><span class="sxs-lookup"><span data-stu-id="052b5-130">300</span></span>  <br/> |<span data-ttu-id="052b5-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="052b5-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="052b5-132">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="052b5-132">**Note:** This is an example.</span></span> <span data-ttu-id="052b5-133">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="052b5-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="052b5-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="052b5-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="052b5-135">简单</span><span class="sxs-lookup"><span data-stu-id="052b5-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="052b5-136">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="052b5-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="052b5-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="052b5-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="052b5-138">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="052b5-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="052b5-139">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="052b5-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="052b5-140">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="052b5-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="052b5-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="052b5-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="052b5-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="052b5-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="052b5-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="052b5-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="052b5-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="052b5-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="052b5-145">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="052b5-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="052b5-146">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="052b5-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="052b5-147">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="052b5-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="052b5-p108">要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="052b5-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="052b5-p109">将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。例如，在你进行此更改之后，发送到你的域（例如 rob@ *your_domain*  .com）的所有电子邮件都将开始传送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="052b5-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="052b5-153">下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="052b5-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="052b5-154">> 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="052b5-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="052b5-155">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="052b5-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="052b5-156">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="052b5-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="052b5-157">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="052b5-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="052b5-158">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="052b5-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="052b5-159">选择" **名称服务器**"记录集。</span><span class="sxs-lookup"><span data-stu-id="052b5-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="052b5-161">在" **值**"框中的" **NS - 名称服务器**"记录集中，通过将它们全部选中并按键盘上的 **Delete** 键来删除所有名称服务器。</span><span class="sxs-lookup"><span data-stu-id="052b5-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="052b5-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="052b5-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="052b5-163">（也就是说，仅删除任何*未*命名为**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="052b5-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="052b5-165">在 " **TTL （秒）：** " 区域中，选择**1H** （1小时）。</span><span class="sxs-lookup"><span data-stu-id="052b5-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![选择1H 一小时](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="052b5-167">仍在" **NS - 名称服务器**"记录集的" **值**"框中，键入或复制粘贴下表" **第一行**"的值，然后按键盘上的 **Enter** 键，键入或复制粘贴" **下一行**"的值。</span><span class="sxs-lookup"><span data-stu-id="052b5-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="052b5-168">每个名称服务器值 *必须*  位于" **值** "框中其自己单独的行上，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="052b5-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="052b5-169">**第一行**</span><span class="sxs-lookup"><span data-stu-id="052b5-169">**First line**</span></span> <br/> |<span data-ttu-id="052b5-170">ns1.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="052b5-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="052b5-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="052b5-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="052b5-172">**第二行**</span><span class="sxs-lookup"><span data-stu-id="052b5-172">**Second line**</span></span> <br/> |<span data-ttu-id="052b5-173">ns2.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="052b5-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="052b5-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="052b5-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="052b5-175">**第三行**</span><span class="sxs-lookup"><span data-stu-id="052b5-175">**Third line**</span></span> <br/> |<span data-ttu-id="052b5-176">ns3.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="052b5-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="052b5-177">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="052b5-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="052b5-178">**第四行**</span><span class="sxs-lookup"><span data-stu-id="052b5-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="052b5-179">ns4.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="052b5-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="052b5-180">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="052b5-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![在 "值" 框中键入或粘贴第一行值](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="052b5-182">选择 "**保存记录集**"。</span><span class="sxs-lookup"><span data-stu-id="052b5-182">Select **Save Record Set**.</span></span>
    
    ![选择 "保存记录集"](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="052b5-p113">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="052b5-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 