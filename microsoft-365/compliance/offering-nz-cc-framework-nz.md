---
title: 新西兰政府云计算安全性和隐私注意事项
description: Microsoft 新西兰解决在新西兰云计算框架中发布的问题。
keywords: Microsoft 365，合规性，产品选项
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: eb14bbe784685fb79ba09f28bc9ca12216b24d57
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690178"
---
# <a name="compliance-offering-new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="f8ba5-104">合规性服务：新西兰政府云计算安全和隐私注意事项</span><span class="sxs-lookup"><span data-stu-id="f8ba5-104">Compliance offering: New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="f8ba5-105">新西兰政府云计算安全性和隐私概述</span><span class="sxs-lookup"><span data-stu-id="f8ba5-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="f8ba5-106">在10月2015，新的新西兰政府认可了一个已修订的全政府 ICT 策略，该战略将 reaffirmed 其 "云优先" 策略，在整个公共部门中使用信息技术。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its “cloud first” policy on using information technology across the public sector.</span></span> <span data-ttu-id="f8ba5-107">修订后的策略保留在 NZ 政府首席信息官（GCIO）的授权下开发和实施的 "云计算风险和保证框架"。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-107">The revised strategy retains the “Cloud Computing Risk and Assurance Framework” that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="f8ba5-108">政府要求所有新西兰状态服务机构在评估和使用云服务时在此框架内工作。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="f8ba5-109">"云计算要求" 概述了在采用云服务时必须执行的操作，以及政府的云策略的历史记录概述。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-109">“Requirements for Cloud Computing” outlines what agencies must do when adopting cloud services along with an overview of the history of the government’s cloud policy.</span></span>

<span data-ttu-id="f8ba5-110">为了协助新西兰政府机构在实施一致和强健的关注潜在云解决方案方面的努力，GCIO 已发布了 "云计算：信息安全和隐私注意事项" （"云计算 ISPC"）。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published “Cloud Computing: Information Security and Privacy Considerations” (the “Cloud Computing ISPC”).</span></span> <span data-ttu-id="f8ba5-111">本文档包含100多个问题，重点关注数据主权、隐私、安全性、治理、机密性、数据完整性、可用性以及事件响应和管理。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="f8ba5-112">请注意，"云计算 IPSC" 未定义云服务提供商必须向其演示正式合规性的新西兰政府标准。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-112">Note that “Cloud Computing IPSC” does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="f8ba5-113">但是，在文档中设置的许多问题都是指了解云服务提供商如何遵守各种相关标准的重要性。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="f8ba5-114">Microsoft 和新西兰政府云计算安全性和隐私注意事项</span><span class="sxs-lookup"><span data-stu-id="f8ba5-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="f8ba5-115">为了帮助代理执行对 Microsoft 企业云服务的分析和评估，Microsoft 新西兰生成了一系列文档，显示其企业云服务如何解决 "云计算 ISPC" 中设置的问题的方法将它们链接到 Microsoft 云服务认证所针对的标准。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced a series of documents showing how its enterprise cloud services address the questions set out in the “Cloud Computing ISPC” by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="f8ba5-116">这些认证是 Microsoft 如何确保公共和私有部门客户在设计、构建和运行云服务以有效缓解隐私和安全风险和解决数据主权问题方面的核心。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="f8ba5-117">了解 Microsoft 云上的 NZ CC Framework 的优势：[下载 NZ cc framework backgrounder](https://aka.ms/nzcc-framework-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="f8ba5-117">Learn about the benefits of NZ CC Framework on the Microsoft Cloud: [Download the NZ CC framework backgrounder](https://aka.ms/nzcc-framework-backgrounder)</span></span>

<span data-ttu-id="f8ba5-118">了解如何通过我们的 Azure 安全性和合规性蓝图加快你的新西兰 CC 框架部署：[将 Azure 响应下载到 NZ CC framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span><span class="sxs-lookup"><span data-stu-id="f8ba5-118">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="f8ba5-119">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="f8ba5-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="f8ba5-120">Azure 和 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="f8ba5-120">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="f8ba5-121">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f8ba5-121">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="f8ba5-122">Intune</span><span class="sxs-lookup"><span data-stu-id="f8ba5-122">Intune</span></span>
- <span data-ttu-id="f8ba5-123">Power BI 云服务作为独立服务或包含在 Office 365 品牌计划或套件中</span><span class="sxs-lookup"><span data-stu-id="f8ba5-123">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="f8ba5-124">Office 365</span><span class="sxs-lookup"><span data-stu-id="f8ba5-124">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="f8ba5-125">Exchange Online、SharePoint Online 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-125">Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="f8ba5-126">Microsoft NZ 已与 GCIO 团队合作开发用于集成 Exchange Online 和 SEEMail 的参考体系结构。白皮书[Office 365： SEEMail 集成和参考体系结构](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)中所述</span><span class="sxs-lookup"><span data-stu-id="f8ba5-126">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail described in the white paper [Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f8ba5-127">常见问题</span><span class="sxs-lookup"><span data-stu-id="f8ba5-127">Frequently asked questions</span></span>

<span data-ttu-id="f8ba5-128">**框架适用于哪些人？**</span><span class="sxs-lookup"><span data-stu-id="f8ba5-128">**To whom does the framework apply?**</span></span>

<span data-ttu-id="f8ba5-129">GCIO 要求（公共和非公共服务部门、20地区健康委员会和七个 Crown 实体）下的组织必须在决定使用云服务时遵守框架。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-129">Organizations that fall under the GCIO mandate — the public and non-public service departments, the 20 district health boards, and seven Crown entities — must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="f8ba5-130">**我的机构是否可以在我们的 ICT 系统的认证过程中使用 Microsoft 对此框架的响应？**</span><span class="sxs-lookup"><span data-stu-id="f8ba5-130">**Can my agency use Microsoft’s responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="f8ba5-131">如果您的代理商需要在新西兰[信息安全手册](https://go.microsoft.com/fwlink/p/?linkid=2099496)中实施其 ICT 系统的认证和资格鉴定，那么您可以在分析过程中使用这些响应。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-131">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="f8ba5-132">资源</span><span class="sxs-lookup"><span data-stu-id="f8ba5-132">Resources</span></span>

- [<span data-ttu-id="f8ba5-133">近海托管 Office 生产力服务的安全要求： Office 365 的符合性指南</span><span class="sxs-lookup"><span data-stu-id="f8ba5-133">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="f8ba5-134">Microsoft Azure 在新西兰安全性和隐私要求的环境中合规性</span><span class="sxs-lookup"><span data-stu-id="f8ba5-134">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="f8ba5-135">新西兰政府 ICT 策略2015</span><span class="sxs-lookup"><span data-stu-id="f8ba5-135">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="f8ba5-136">对云计算的新西兰政府要求</span><span class="sxs-lookup"><span data-stu-id="f8ba5-136">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="f8ba5-137">云计算：信息安全和隐私注意事项（ISPC）</span><span class="sxs-lookup"><span data-stu-id="f8ba5-137">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://aka.ms/NZ-Cloud-Computing-Considerations)
- [<span data-ttu-id="f8ba5-138">Microsoft Online Services 条款</span><span class="sxs-lookup"><span data-stu-id="f8ba5-138">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- <span data-ttu-id="f8ba5-139">[Office 365： SEEMail 集成和参考体系结构](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)（有关云服务采用的其他 Microsoft NZ 指南）</span><span class="sxs-lookup"><span data-stu-id="f8ba5-139">[Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (additional Microsoft NZ guidance on cloud service adoption)</span></span>
- [<span data-ttu-id="f8ba5-140">Microsoft 信任中心的合规性</span><span class="sxs-lookup"><span data-stu-id="f8ba5-140">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="f8ba5-141">Microsoft 对 "云计算 IPSC" 的响应</span><span class="sxs-lookup"><span data-stu-id="f8ba5-141">Microsoft responses to “Cloud Computing IPSC”</span></span>

- [<span data-ttu-id="f8ba5-142">Azure</span><span class="sxs-lookup"><span data-stu-id="f8ba5-142">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="f8ba5-143">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f8ba5-143">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="f8ba5-144">Intune</span><span class="sxs-lookup"><span data-stu-id="f8ba5-144">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="f8ba5-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="f8ba5-145">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="f8ba5-146">Power BI</span><span class="sxs-lookup"><span data-stu-id="f8ba5-146">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="f8ba5-147">下载产品 backgrounder</span><span class="sxs-lookup"><span data-stu-id="f8ba5-147">Download the offering backgrounder</span></span>

<span data-ttu-id="f8ba5-148">是否需要此产品的 backgrounder 文档？</span><span class="sxs-lookup"><span data-stu-id="f8ba5-148">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="f8ba5-149">下载[PDF](https://download.microsoft.com/download/6/6/4/664E4B6F-15C6-421E-8F74-3FA468587A47/NZ_CC_Compliance_Backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-149">Download the [PDF](https://download.microsoft.com/download/6/6/4/664E4B6F-15C6-421E-8F74-3FA468587A47/NZ_CC_Compliance_Backgrounder.pdf).</span></span>