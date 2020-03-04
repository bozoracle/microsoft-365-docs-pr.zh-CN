---
title: 在 Yahoo! Small Business 处为 Office 365 创建 DNS 记录
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
ms.assetid: 034bd7bc-b098-4c4d-8a93-4d74ff24532a
description: 了解如何验证你的域并为电子邮件、Skype for Business Online 和 Yahoo！中的其他服务设置 DNS 记录 适用于 Office 365 的小型企业版。
ms.openlocfilehash: c178afeb309fba9515e01155a43d5e6b97d1136f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362637"
---
# <a name="create-dns-records-at-yahoo-small-business-for-office-365"></a><span data-ttu-id="f11e3-105">在 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f11e3-105">Create DNS records at Yahoo!</span></span> <span data-ttu-id="f11e3-106">Small Business 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f11e3-106">Small Business for Office 365</span></span>

 <span data-ttu-id="f11e3-107">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="f11e3-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f11e3-p104">如果 Yahoo!Small Business 之前一直充当的是 DNS 托管提供者，请注意它现已更名为 Aabaco Small Business。</span><span class="sxs-lookup"><span data-stu-id="f11e3-p104">If Yahoo! Small Business has been your DNS hosting provider, you should be aware that your provider is now Aabaco Small Business.</span></span>
  
<span data-ttu-id="f11e3-110">按照本文中的步骤操作，在 Aabaco 处创建一个帐户，可在 Aabaco 更改 DNS 并续订一个或多个域。</span><span class="sxs-lookup"><span data-stu-id="f11e3-110">Follow the steps in this article to create an account at Aabaco, where you can make DNS changes and renew your domain or domains.</span></span>
  
<span data-ttu-id="f11e3-111">您必须先创建 Aabaco 帐户，然后才能[创建 DNS 记录](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="f11e3-111">You must create your Aabaco account before you can [create DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

  
## <a name="create-an-aabaco-small-business-account"></a><span data-ttu-id="f11e3-112">创建 Aabaco Small Business 帐户</span><span class="sxs-lookup"><span data-stu-id="f11e3-112">Create an Aabaco Small Business account</span></span>

1. <span data-ttu-id="f11e3-113">若要开始，请使用[此链接](https://www.luminate.com/services/)转到 Aabaco 上的 "域" 页面，然后选择 "**设置 Aabaco 小型企业帐户**"。</span><span class="sxs-lookup"><span data-stu-id="f11e3-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select **Setup your Aabaco Small Business account**.</span></span>
    
    ![选择 "设置你的 Aabaco 小型企业帐户"](../../media/d708f272-d42f-40a1-9aaf-d05d8cfd55cf.png)
  
2. <span data-ttu-id="f11e3-115">提供 Yahoo！</span><span class="sxs-lookup"><span data-stu-id="f11e3-115">Provide your Yahoo!</span></span> <span data-ttu-id="f11e3-116">小型企业**电子邮件/YAHOO ID**，然后选择 "**我不是机器人**"。</span><span class="sxs-lookup"><span data-stu-id="f11e3-116">Small Business **Email/Yahoo ID**, and then select **I'm not a robot**.</span></span>
    
    ![Select I am not a robot](../../media/ded4b5dd-4e04-4baa-ae31-8426b5799151.png)
  
3. <span data-ttu-id="f11e3-118">选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="f11e3-118">Select **Get started**.</span></span>
    
    ![选择 "开始"](../../media/6674707d-c222-4f0d-bec4-229d39ab2499.png)
  
4. <span data-ttu-id="f11e3-p106">登录到 Yahoo!Small Business 电子邮件帐户，然后从 Aabaco Small Business 打开新的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f11e3-p106">Sign in to your Yahoo! Small Business email account and open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f11e3-122">如有必要，可在" **收到的邮件**"页面上选择" **重新发送电子邮件链接**"，重新发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f11e3-122">Resend the message, if necessary, by choosing the **resend the email link** on the **You've got mail** page.</span></span> 
  
    ![The You've got mail page](../../media/2e02fc30-6cca-40d6-bb64-131a41b4a369.png)
  
5. <span data-ttu-id="f11e3-124">在 "Aabaco**确认您的电子邮件地址以继续安装**电子邮件" 中，选择 "**确认电子**邮件"。</span><span class="sxs-lookup"><span data-stu-id="f11e3-124">In the Aabaco **Confirm your email address to continue setup** email message, select **Confirm email**.</span></span>
    
    ![选择确认电子邮件](../../media/eb5f5526-6f90-4a10-83a7-5249a1ebd562.png)
  
6. <span data-ttu-id="f11e3-126">在" **选择密码**"页面上，键入或复制粘贴要用于 Aabaco 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="f11e3-126">On the **Choose your password** page, type or copy and paste the password that you want to use for your Aabaco account.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f11e3-p107">可使用 Yahoo! Small Business 帐户所用的相同密码。</span><span class="sxs-lookup"><span data-stu-id="f11e3-p107">You can use the same password that you used with your Yahoo! Small Business account.</span></span> 
  
    ![The Choose your password page](../../media/cc592345-72d1-4a41-9410-a1f3345cfd1d.png)
  
7. <span data-ttu-id="f11e3-130">选择 **"我同意条款和条件**"，然后选择 "**创建密码**"。</span><span class="sxs-lookup"><span data-stu-id="f11e3-130">Select **I agree to the terms and conditions**, and then select **Create password**.</span></span>
    
    ![选择 "创建密码"](../../media/434aa6a3-076e-4abf-a9cf-31145786e819.png)
  
8. <span data-ttu-id="f11e3-p108">登录到 Yahoo!Small Business 电子邮件帐户，然后从 Aabaco Small Business 打开新的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f11e3-p108">Sign in to your Yahoo! Small Business email account, and then open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f11e3-p109">如有必要，可在" **即将完成!**"页面上选择" **重新发送电子邮件链接**"，重新发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f11e3-p109">Resend the message, if necessary, by choosing the **resend the email link** on the **You're almost done!** page.</span></span> 
  
    ![The You're almost done page](../../media/1a4142a3-e140-48a8-9c80-aa126ff08179.png)
  
9. <span data-ttu-id="f11e3-137">在 Aabaco 中，**您几乎已有**电子邮件消息，请选择 **"激活我的帐户**"。</span><span class="sxs-lookup"><span data-stu-id="f11e3-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span></span>
    
    ![选择 "激活我的帐户"](../../media/e76d5edc-d8ba-4d8d-872d-d916716c3618.png)
  
10. <span data-ttu-id="f11e3-139">登录到 Aabaco Small Business 帐户。</span><span class="sxs-lookup"><span data-stu-id="f11e3-139">Sign in to your Aabaco Small Business account.</span></span>
    
    ![The sign-in page for Aabaco Small Business](../../media/4ef3cfc3-26da-4e03-932b-9346ef217848.png)
  
<span data-ttu-id="f11e3-141">现已创建 Aabaco 帐户，即可[在 Aabaco Small Business for Office 365 中创建 DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="f11e3-141">Now that you have created your Aabaco account, you can [Create DNS records at Aabaco Small Business for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  