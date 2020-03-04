---
title: 使用基于 Windows 的 DNS 为 Office 365 创建 DNS 记录
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: 了解如何验证您的域并为 Office 365 的基于 Windows 的 DNS 中的电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: ddea5cb95a7f2abef8b68b37de473f936ee08eb5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240965"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a><span data-ttu-id="4bac6-103">使用基于 Windows 的 DNS 为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="4bac6-103">Create DNS records for Office 365 using Windows-based DNS</span></span>

 <span data-ttu-id="4bac6-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="4bac6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="4bac6-105">如果使用基于 Windows 的 DNS 托管自己的 DNS 记录，请遵循本文中的步骤为电子邮件、Skype for Business Online 等设置记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4bac6-106">若要开始，您需要[在基于 Windows 的 dns 中查找 dns 记录](#find-your-dns-records-in-windows-based-dns)，以便您可以对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="4bac6-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="4bac6-107">此外，如果您计划将本地 Active Directory 与 Office 365 同步，请参阅[在本地 Active directory 中用作 UPN 的不可路由电子邮件地址](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="4bac6-107">Also, if you're planning to synchronize your on-premises Active Directory with Office 365, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="4bac6-108">添加 DNS 记录后出现邮件流或其他问题的问题，请参阅[在更改域名或 DNS 记录后解决问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4bac6-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="4bac6-109">在基于 Windows 的 DNS 中查找 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="4bac6-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="4bac6-110"><a name="BKMK_find_your_dns_1"></a>转到包含您的域的 DNS 记录的页面。</span><span class="sxs-lookup"><span data-stu-id="4bac6-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="4bac6-111">如果是在 Windows Server 2008 中工作，请转到 "**开始** > " "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="4bac6-112">如果使用的是 Windows Server 2012，请按 Windows 键和**r**键。</span><span class="sxs-lookup"><span data-stu-id="4bac6-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="4bac6-113">键入 " **Dnsmgmnt**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4bac6-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="4bac6-114">在 dns 管理器中，展开\*\* \<"\> \> DNS 服务器名称" 正向查找区域  \*\*"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="4bac6-115">选择域。</span><span class="sxs-lookup"><span data-stu-id="4bac6-115">Select your domain.</span></span> <span data-ttu-id="4bac6-116">现在已准备好创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="4bac6-117">添加 MX 记录</span><span class="sxs-lookup"><span data-stu-id="4bac6-117">Add MX record</span></span>
<span data-ttu-id="4bac6-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4bac6-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="4bac6-119">添加 MX 记录，以便您的域的电子邮件将发往 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4bac6-119">Add an MX record so email for your domain will come to Office 365.</span></span>
- <span data-ttu-id="4bac6-120">您添加的 MX 记录包括以下类似值（" **指向地址**"值）：\<MX token\>.mail.protection.outlook.com，其中，\<MX 令牌\> 是类似于 MSxxxxxxx 的值。</span><span class="sxs-lookup"><span data-stu-id="4bac6-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="4bac6-121">从 Office 365 的 "添加 DNS 记录" 页的 "Exchange Online" 部分的 "MX" 行中，复制 "磅到地址" 下方列出的值。</span><span class="sxs-lookup"><span data-stu-id="4bac6-121">From the MX row in the Exchange Online section of the Add DNS records page in Office 365, copy the value listed under Points to address.</span></span> <span data-ttu-id="4bac6-122">你将在此任务中创建的记录中使用此值。</span><span class="sxs-lookup"><span data-stu-id="4bac6-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="4bac6-123">在域的 "DNS 管理器" 页上，转到 "**操作** > **邮件交换器（MX）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="4bac6-124">若要在此域中查找此页面，请参阅[在基于 Windows 的 dns 中查找 DNS 记录](#find-your-dns-records-in-windows-based-dns)。</span><span class="sxs-lookup"><span data-stu-id="4bac6-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="4bac6-125">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="4bac6-126">主机名：</span><span class="sxs-lookup"><span data-stu-id="4bac6-126">Host Name:</span></span> 
    - <span data-ttu-id="4bac6-127">@Address：将 "磅" 粘贴到您刚刚从 Office 365 中复制的地址值。</span><span class="sxs-lookup"><span data-stu-id="4bac6-127">@Address: Paste the Points to address  value that you just copied from Office 365 here.</span></span>  
    - <span data-ttu-id="4bac6-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="4bac6-128">Pref:</span></span> 
- <span data-ttu-id="4bac6-129">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="4bac6-130">请删除任何已过时的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="4bac6-131">如果此域的任何旧 MX 记录将电子邮件路由到其他位置，则选中每个旧记录旁边的复选框，然后选择 "**删除** > **" 确定 "**。</span><span class="sxs-lookup"><span data-stu-id="4bac6-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="4bac6-132">添加 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="4bac6-132">Add CNAME records</span></span>
<span data-ttu-id="4bac6-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4bac6-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="4bac6-134">添加 Office 365 所需的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-134">Add the CNAME records that are required for Office 365.</span></span> <span data-ttu-id="4bac6-135">如果 Office 365 中列出了其他 CNAME 记录，则按照此处所示的相同常规步骤进行添加。</span><span class="sxs-lookup"><span data-stu-id="4bac6-135">If additional CNAME records are listed in Office 365, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4bac6-136">如果你有适用于 Office 365 的移动设备管理（MDM），则必须创建两个附加的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-136">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="4bac6-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4bac6-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="4bac6-138">（如果没有 MDM，则可以跳过此步骤。）</span><span class="sxs-lookup"><span data-stu-id="4bac6-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="4bac6-139">在域的 "DNS 管理器" 页上，转到 "**操作** > **CNAME （cname）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="4bac6-140">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="4bac6-141">主机名称：自动发现</span><span class="sxs-lookup"><span data-stu-id="4bac6-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="4bac6-142">类型：</span><span class="sxs-lookup"><span data-stu-id="4bac6-142">Type:</span></span> 
    - <span data-ttu-id="4bac6-143">Cname 地址： autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4bac6-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="4bac6-144">选择 " **O**K"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-144">Select **O**K.</span></span>

<span data-ttu-id="4bac6-145">添加 SIP CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="4bac6-146">在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="4bac6-147">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="4bac6-148">主机名： sip</span><span class="sxs-lookup"><span data-stu-id="4bac6-148">Host Name: sip</span></span>
    - <span data-ttu-id="4bac6-149">类型： CNAME</span><span class="sxs-lookup"><span data-stu-id="4bac6-149">Type: CNAME</span></span>
    - <span data-ttu-id="4bac6-150">地址： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4bac6-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="4bac6-151">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-151">Select **OK**.</span></span>

<span data-ttu-id="4bac6-152">添加 Skype for Business Online 自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="4bac6-153">在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="4bac6-154">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="4bac6-155">主机名： lyncdiscover。</span><span class="sxs-lookup"><span data-stu-id="4bac6-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="4bac6-156">类型： CNAME</span><span class="sxs-lookup"><span data-stu-id="4bac6-156">Type: CNAME</span></span>
    - <span data-ttu-id="4bac6-157">地址： webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4bac6-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="4bac6-158">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="4bac6-159">为适用于 Office 365 的移动设备管理 (MDM) 添加两个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="4bac6-159">Add two CNAME records for Mobile Device Management (MDM) for Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bac6-160">如果你有适用于 Office 365 的移动设备管理（MDM），则必须创建两个附加的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-160">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="4bac6-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4bac6-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="4bac6-162">> （如果没有 MDM，可以跳过此步骤。）</span><span class="sxs-lookup"><span data-stu-id="4bac6-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="4bac6-163">添加 MDM Enterpriseregistration CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="4bac6-164">在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="4bac6-165">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="4bac6-166">主机名： enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4bac6-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="4bac6-167">类型： CNAME</span><span class="sxs-lookup"><span data-stu-id="4bac6-167">Type: CNAME</span></span>
- <span data-ttu-id="4bac6-168">地址： enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4bac6-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="4bac6-169">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-169">Select **OK**.</span></span> 

<span data-ttu-id="4bac6-170">添加 MDM Enterpriseenrollment CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="4bac6-171">在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="4bac6-172">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="4bac6-173">主机名： enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4bac6-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="4bac6-174">类型： CNAME</span><span class="sxs-lookup"><span data-stu-id="4bac6-174">Type: CNAME</span></span>
    - <span data-ttu-id="4bac6-175">地址： enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4bac6-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="4bac6-176">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4bac6-177">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4bac6-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4bac6-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4bac6-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bac6-179">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="4bac6-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4bac6-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="4bac6-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4bac6-181">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4bac6-181">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4bac6-182">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-182">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="4bac6-183">为您的域添加 SPF TXT 记录以帮助防止垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="4bac6-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="4bac6-p111">您可能已在此记录的"TXT"值中拥有其他字符串（例如，营销电子邮件的字符串），这样没关系。请将那些字符串留在原位并添加此字符串，并在每个字符串两侧加上双引号以将它们隔开。</span><span class="sxs-lookup"><span data-stu-id="4bac6-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="4bac6-186">在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **文本（TXT）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="4bac6-187">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="4bac6-188">在某些版本的 Windows DNS 管理器中，可能已对域进行了设置，以便在创建 txt 记录时，主页名称默认为父域。</span><span class="sxs-lookup"><span data-stu-id="4bac6-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="4bac6-189">在这种情况下，添加 TXT 记录时，将主机名设置为空（没有值），而不是将其设置为 @ 或域名。</span><span class="sxs-lookup"><span data-stu-id="4bac6-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="4bac6-190">主机类型：@</span><span class="sxs-lookup"><span data-stu-id="4bac6-190">Host type: @</span></span>
-  <span data-ttu-id="4bac6-191">记录类型： TXT</span><span class="sxs-lookup"><span data-stu-id="4bac6-191">Record Type: TXT</span></span>
-  <span data-ttu-id="4bac6-192">Address： v = spf1 包括 include spf.protection.outlook.com-all</span><span class="sxs-lookup"><span data-stu-id="4bac6-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="4bac6-193">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="4bac6-194">添加 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="4bac6-194">Add SRV records</span></span>
<span data-ttu-id="4bac6-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4bac6-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="4bac6-196">添加 Office 365 所需的两个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-196">Add the two SRV records that are required for Office 365.</span></span>

<span data-ttu-id="4bac6-197">为 Skype for Business Online Web 会议添加 SIP SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="4bac6-198">在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **其他新记录**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="4bac6-199">在 "**资源记录类型**" 窗口中，选择 "**服务位置（SRV）**"，然后选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="4bac6-200">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="4bac6-201">服务： _sip</span><span class="sxs-lookup"><span data-stu-id="4bac6-201">Service: _sip</span></span>
    -  <span data-ttu-id="4bac6-202">协议： _tls</span><span class="sxs-lookup"><span data-stu-id="4bac6-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="4bac6-203">优先级： 100</span><span class="sxs-lookup"><span data-stu-id="4bac6-203">Priority: 100</span></span>
    -  <span data-ttu-id="4bac6-204">权重： 1</span><span class="sxs-lookup"><span data-stu-id="4bac6-204">Weight: 1</span></span>
    -  <span data-ttu-id="4bac6-205">端口： 443</span><span class="sxs-lookup"><span data-stu-id="4bac6-205">Port: 443</span></span>
    -  <span data-ttu-id="4bac6-206">目标（Hostname）： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4bac6-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="4bac6-207">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-207">Select **OK**.</span></span> 


<span data-ttu-id="4bac6-208">为 Skype for Business Online 联盟添加 SIP SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="4bac6-209">在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **其他新记录**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="4bac6-210">在 "**资源记录类型**" 窗口中，选择 "**服务位置（SRV）**"，然后选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="4bac6-211">在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：</span><span class="sxs-lookup"><span data-stu-id="4bac6-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="4bac6-212">服务： _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4bac6-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="4bac6-213">协议： _tcp</span><span class="sxs-lookup"><span data-stu-id="4bac6-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="4bac6-214">优先级： 100</span><span class="sxs-lookup"><span data-stu-id="4bac6-214">Priority: 100</span></span>
    -  <span data-ttu-id="4bac6-215">权重： 1</span><span class="sxs-lookup"><span data-stu-id="4bac6-215">Weight: 1</span></span>
    -  <span data-ttu-id="4bac6-216">端口： 5061</span><span class="sxs-lookup"><span data-stu-id="4bac6-216">Port: 5061</span></span>
    -  <span data-ttu-id="4bac6-217">目标（Hostname）： sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4bac6-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="4bac6-218">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4bac6-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="4bac6-219">添加记录以验证您拥有该域（如果尚未验证）</span><span class="sxs-lookup"><span data-stu-id="4bac6-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="4bac6-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4bac6-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4bac6-p113">添加 DNS 记录以设置您的 Office 365 服务之前，Office 365 必须确认您拥有正在添加的域。为此，请按照以下步骤添加记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-p113">Before you add the DNS records to set up your Office 365 services, Office 365 has to confirm that you own the domain you're adding. To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4bac6-223">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。</span><span class="sxs-lookup"><span data-stu-id="4bac6-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="4bac6-224">从 Office 365 收集信息。</span><span class="sxs-lookup"><span data-stu-id="4bac6-224">Gather information from Office 365.</span></span>  <br/> 
2. <span data-ttu-id="4bac6-225">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="4bac6-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="4bac6-226">在 "**域**" 页上，在要验证的域的 "**操作**" 列中，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="4bac6-227">在 "**将域添加到 Office 365** " 页上，选择 "**开始步骤 1**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-227">On the **Add a domain to Office 365** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="4bac6-228">在 "**确认您是否拥有**您的域" 页上的 "**请参阅有关使用此步骤执行此步骤的说明**" 下拉列表中，选择 "**常规说明**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="4bac6-229">从表中，复制"目标地址或指向的地址"值。</span><span class="sxs-lookup"><span data-stu-id="4bac6-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="4bac6-230">您将在下一步骤中需要它。</span><span class="sxs-lookup"><span data-stu-id="4bac6-230">You'll need it for the next step.</span></span> <span data-ttu-id="4bac6-231">建议您复制并粘贴此值，以确保所有空格保持正确。</span><span class="sxs-lookup"><span data-stu-id="4bac6-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="4bac6-232">添加 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="4bac6-233">在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **文本（TXT）**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="4bac6-234">在 "**新建资源记录**" 对话框中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="4bac6-235">在 "**新建资源记录**" 对话框的 "**自定义主机名称**" 区域中，请确保字段已设置为以下值。</span><span class="sxs-lookup"><span data-stu-id="4bac6-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="4bac6-236">在某些版本的 Windows DNS 管理器中，可能已对域进行了设置，以便在创建 txt 记录时，主页名称默认为父域。</span><span class="sxs-lookup"><span data-stu-id="4bac6-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="4bac6-237">在这种情况下，添加 TXT 记录时，将主机名设置为空（没有值），而不是将其设置为 @ 或域名。</span><span class="sxs-lookup"><span data-stu-id="4bac6-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="4bac6-238">主机名：@</span><span class="sxs-lookup"><span data-stu-id="4bac6-238">Host Name: @</span></span>
- <span data-ttu-id="4bac6-239">类型： TXT</span><span class="sxs-lookup"><span data-stu-id="4bac6-239">Type: TXT</span></span>
- <span data-ttu-id="4bac6-240">Address：将目标或指向您刚刚从 Office 365 中复制的地址值粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="4bac6-240">Address: Paste the Destination or Points to Address value that you just copied from Office 365 here.</span></span>  
- <span data-ttu-id="4bac6-241">选择 **"确定** > **完成**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="4bac6-242">在 Office 365 中验证您的域。</span><span class="sxs-lookup"><span data-stu-id="4bac6-242">Verify your domain in Office 365.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="4bac6-243">在执行此操作之前，请等待大约15分钟，以便您刚刚创建的记录可以通过 Internet 进行更新。</span><span class="sxs-lookup"><span data-stu-id="4bac6-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="4bac6-244">返回到 Office 365 并按照下面的步骤请求验证检查。</span><span class="sxs-lookup"><span data-stu-id="4bac6-244">Go back to Office 365 and follow the steps below to request a verification check.</span></span> <span data-ttu-id="4bac6-245">该检查将查找上一步中添加的 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="4bac6-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="4bac6-246">找到正确的 TXT 记录时，该域通过验证。</span><span class="sxs-lookup"><span data-stu-id="4bac6-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="4bac6-247">在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="4bac6-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="4bac6-248">在 "**域**" 页上，在要验证的域的 "**操作**" 列中，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="4bac6-249">在 "**确认你是否拥有域**" 页面上，选择 **"已完成，立即验证**"，然后在确认对话框中选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="4bac6-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="4bac6-p117">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4bac6-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="4bac6-253">在本地 Active Directory 中用作 UPN 的不可路由电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="4bac6-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="4bac6-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="4bac6-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="4bac6-255">如果计划使用 Office 365 同步本地 Active Directory，请确保 Active Directory 用户主体名称 (UPN) 后缀为有效域后缀，而不是不受支持的域后缀，如 @contoso.local。</span><span class="sxs-lookup"><span data-stu-id="4bac6-255">If you're planning to synchronize your on-premises Active Directory with Office 365, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="4bac6-256">如果需要更改 UPN 后缀，请参阅 how [to prepare a 不可路由的域以进行目录同步](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)。</span><span class="sxs-lookup"><span data-stu-id="4bac6-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="4bac6-p119">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4bac6-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  