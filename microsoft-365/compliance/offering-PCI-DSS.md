---
title: 支付卡行业 (PCI) 数据安全标准 (DSS)
description: Azure、SharePoint Online 和 OneDrive for Business 符合支付卡行业数据安全标准 Level 1 3.2 版。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 1b0e4ae933591f41c99a4b88d31eca6504322c92
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218691"
---
# <a name="compliance-offering-payment-card-industry-pci-data-security-standard-dss"></a><span data-ttu-id="9318a-104">合规性产品：支付卡行业 (PCI) 数据安全标准 (DSS)</span><span class="sxs-lookup"><span data-stu-id="9318a-104">Compliance offering: Payment Card Industry (PCI) Data Security Standard (DSS)</span></span>

## <a name="pci-dss-overview"></a><span data-ttu-id="9318a-105">PCI DSS 概述</span><span class="sxs-lookup"><span data-stu-id="9318a-105">PCI DSS overview</span></span>

<span data-ttu-id="9318a-106">支付卡行业 (PCI) 数据安全标准 (DSS) 是一种全球信息安全标准，旨在通过增强对信用卡数据的控制来预防欺诈。</span><span class="sxs-lookup"><span data-stu-id="9318a-106">The Payment Card Industry (PCI) Data Security Standards (DSS) is a global information security standard designed to prevent fraud through increased control of credit card data.</span></span> <span data-ttu-id="9318a-107">如果各种规模的组织接受五大信用卡品牌（Visa、MasterCard、American Express、Discover 和 Japan Credit Bureau (JCB)）的支付卡，则他们必须遵循 PCI DSS 标准。</span><span class="sxs-lookup"><span data-stu-id="9318a-107">Organizations of all sizes must follow PCI DSS if they accept payment cards from the five major credit card brands—Visa, MasterCard, American Express, Discover, and the Japan Credit Bureau (JCB).</span></span> <span data-ttu-id="9318a-108">任何存储、处理和传输付款持卡人数据的组织都必须符合 PCI DSS。</span><span class="sxs-lookup"><span data-stu-id="9318a-108">Compliance with PCI DSS is required for any organization that stores, processes, or transmits payment and cardholder data.</span></span>

## <a name="microsoft-and-pci-dss"></a><span data-ttu-id="9318a-109">Microsoft 和 PCI DSS</span><span class="sxs-lookup"><span data-stu-id="9318a-109">Microsoft and PCI DSS</span></span>

<span data-ttu-id="9318a-110">Microsoft 由经认可的合格安全性评估师 (QSA) 完成 PCI DSS 年度评估。</span><span class="sxs-lookup"><span data-stu-id="9318a-110">Microsoft completed an annual PCI DSS assessment using an approved Qualified Security Assessor (QSA).</span></span> <span data-ttu-id="9318a-111">审核员审查了 Microsoft Azure、Microsoft OneDrive for Business 和 Microsoft SharePoint Online 环境，其中包括验证基础结构、开发、操作、管理、支持和范围内服务。</span><span class="sxs-lookup"><span data-stu-id="9318a-111">The auditors reviewed Microsoft Azure, Microsoft OneDrive for Business, and Microsoft SharePoint Online  environments, which include validating the infrastructure, development, operations, management, support, and in-scope services.</span></span> <span data-ttu-id="9318a-112">PCI DSS 根据交易量指定了四个级别的合规性。</span><span class="sxs-lookup"><span data-stu-id="9318a-112">The PCI DSS designates four levels of compliance based on transaction volume.</span></span> <span data-ttu-id="9318a-113">Azure、OneDrive for Business 和 SharePoint Online 被认证为符合 PCI DSS 3.2 版的 Service Provider Level 1（成交量最高，每年超过 600 万）。</span><span class="sxs-lookup"><span data-stu-id="9318a-113">Azure, OneDrive for Business, and SharePoint Online are certified as compliant under PCI DSS version 3.2 at Service Provider Level 1 (the highest volume of transactions — more than 6 million a year).</span></span>

<span data-ttu-id="9318a-114">通过该评估，我们获得了可向客户提供的合规性证明 (AoC) 和 QSA 颁发的合规性报告 (RoC)。</span><span class="sxs-lookup"><span data-stu-id="9318a-114">The assessment results in an Attestation of Compliance (AoC), which is available to customers and Report on Compliance (RoC) issued by the QSA.</span></span> <span data-ttu-id="9318a-115">合规性的有效期开始于通过审核并收到评审员的 AoC，并于签署该 AoC 之日起一年后失效。</span><span class="sxs-lookup"><span data-stu-id="9318a-115">The effective period for compliance begins upon passing the audit and receiving the AoC from the assessor and ends one year from the date the AoC is signed.</span></span> 

<span data-ttu-id="9318a-116">希望开发持卡人环境或卡处理服务的客户可以在许多底层部分中使用这些验证，从而减少获取自己的 PCI DSS 认证的相关工作和成本。</span><span class="sxs-lookup"><span data-stu-id="9318a-116">Customers who want to develop a cardholder environment or card processing service can use these validations in many of the underlying portions, thereby reducing the associated effort and costs of getting their own PCI DSS certification.</span></span>

<span data-ttu-id="9318a-117">需要注意的重要一点是，明白 Azure、OneDrive for Business 和 SharePoint Online 的 PCI DSS 合规性状态不会自动转化成客户在这些平台上构建或托管的服务的 PCI DSS 认证。</span><span class="sxs-lookup"><span data-stu-id="9318a-117">It is important to understand that PCI DSS compliance status for Azure, OneDrive for Business, and SharePoint Online not automatically translate to PCI DSS certification for the services that customers build or host on these platforms.</span></span> <span data-ttu-id="9318a-118">客户负责确保他们自己符合 PCI DSS 要求。</span><span class="sxs-lookup"><span data-stu-id="9318a-118">Customers are responsible for ensuring that they achieve compliance with PCI DSS requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="9318a-119">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="9318a-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="9318a-120">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="9318a-120">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="9318a-121">云应用安全</span><span class="sxs-lookup"><span data-stu-id="9318a-121">Cloud App Security</span></span>
- <span data-ttu-id="9318a-122">Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="9318a-122">Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="9318a-123">Graph</span><span class="sxs-lookup"><span data-stu-id="9318a-123">Graph</span></span>
- <span data-ttu-id="9318a-124">Intune</span><span class="sxs-lookup"><span data-stu-id="9318a-124">Intune</span></span>
- <span data-ttu-id="9318a-125">PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="9318a-125">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="9318a-126">Power BI 云服务，无论是独立服务还是随 Office 365 品牌计划或套件提供的服务</span><span class="sxs-lookup"><span data-stu-id="9318a-126">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="9318a-127">OneDrive for Business 和 SharePoint Online（仅限美国）</span><span class="sxs-lookup"><span data-stu-id="9318a-127">OneDrive for Business and SharePoint Online (United States only)</span></span>

## <a name="audit-reports-and-certificates"></a><span data-ttu-id="9318a-128">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="9318a-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="9318a-129">Azure PCI DSS 合规性证明 (AoC)</span><span class="sxs-lookup"><span data-stu-id="9318a-129">Azure PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/azure-pci)
- [<span data-ttu-id="9318a-130">OneDrive for Business 和 SharePoint Online PCI DSS 合规性证明 (AoC)</span><span class="sxs-lookup"><span data-stu-id="9318a-130">OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a><span data-ttu-id="9318a-131">获取 Azure 上运行的 PCI DSS 解决方案</span><span class="sxs-lookup"><span data-stu-id="9318a-131">Get your PCI DSS solution running on Azure</span></span>

<span data-ttu-id="9318a-132">借助 Azure 安全性和合规性 PCI DSS 蓝图，在云中更快地构建和部署 PCI DSS 解决方案。</span><span class="sxs-lookup"><span data-stu-id="9318a-132">Build and deploy your PCI DSS solution in the cloud even faster with the Azure Security and Compliance PCI DSS Blueprint.</span></span> <span data-ttu-id="9318a-133">获取参考体系结构、部署指南、控制实现映射、自动化脚本等。</span><span class="sxs-lookup"><span data-stu-id="9318a-133">Get reference architectures, deployment guidance, control implementation mappings, automated scripts and more.</span></span> [<span data-ttu-id="9318a-134">开始使用 Azure PCI DSS 蓝图</span><span class="sxs-lookup"><span data-stu-id="9318a-134">Start using the Azure PCI DSS Blueprint</span></span>](https://aka.ms/pciblueprint)

## <a name="frequently-asked-questions"></a><span data-ttu-id="9318a-135">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="9318a-135">Frequently asked questions</span></span>

<span data-ttu-id="9318a-136">**为什么合规性证明 (AoC) 封面上写着“2018 年 6 月”？**</span><span class="sxs-lookup"><span data-stu-id="9318a-136">**Why does the Attestation of Compliance (AoC) cover page say “June 2018”?**</span></span>

<span data-ttu-id="9318a-137">封面上的 2018 年 6 月是 AoC 模板发布的日期。</span><span class="sxs-lookup"><span data-stu-id="9318a-137">The June 2018 date on the cover page is when the AoC template was published.</span></span> <span data-ttu-id="9318a-138">有关评估的日期，请参阅第 2 部分。</span><span class="sxs-lookup"><span data-stu-id="9318a-138">Refer to Section 2 for the date of the assessment.</span></span>

<span data-ttu-id="9318a-139">**为什么会有多个 Azure 合规性证明 (AoC)？**</span><span class="sxs-lookup"><span data-stu-id="9318a-139">**Why are there multiple Azure Attestations of Compliance (AoCs)?**</span></span>

<span data-ttu-id="9318a-140">Azure AoC 包具有对应于 Azure 公共、德国和政府云的 AoC。</span><span class="sxs-lookup"><span data-stu-id="9318a-140">The Azure AoC package has AoCs corresponding to Azure Public, Germany, and Government cloud.</span></span> <span data-ttu-id="9318a-141">客户应使用与其 Azure 环境对应的 AoC。</span><span class="sxs-lookup"><span data-stu-id="9318a-141">Customers should use the AoC that corresponds with their Azure environment.</span></span>  

<span data-ttu-id="9318a-142">**PA DSS 与 PCI DSS 之间有何关系？**</span><span class="sxs-lookup"><span data-stu-id="9318a-142">**What is the relationship between the PA DSS and PCI DSS?**</span></span>

<span data-ttu-id="9318a-143">支付应用程序数据安全标准 (PA DSS) 是一套符合 PCI DSS 的要求，它取代了 Visa 的支付应用程序最佳做法，并整合了其他主要发卡机构的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="9318a-143">The Payment Application Data Security Standard (PA DSS) is a set of requirements that comply with the PCI DSS, and replaces Visa’s Payment Application Best Practices, and consolidates the compliance requirements of the other primary card issuers.</span></span> <span data-ttu-id="9318a-144">PA DSS 帮助软件供应商开发第三方应用程序，以在卡授权或结算过程中存储、处理或传输持卡人支付数据。</span><span class="sxs-lookup"><span data-stu-id="9318a-144">The PA DSS helps software vendors develop third-party applications that store, process, or transmit cardholder payment data as part of a card authorization or settlement process.</span></span> <span data-ttu-id="9318a-145">零售商必须使用经 PA DSS 认证的应用程序，以有效取得 PCI DSS 合规性。</span><span class="sxs-lookup"><span data-stu-id="9318a-145">Retailers must use PA DSS certified applications to efficiently achieve their PCI DSS compliance.</span></span> <span data-ttu-id="9318a-146">PA DSS 不适用于 Azure。</span><span class="sxs-lookup"><span data-stu-id="9318a-146">The PA DSS does not apply to Azure.</span></span>

<span data-ttu-id="9318a-147">**什么是收单机构，Azure 是否使用收单机构？**</span><span class="sxs-lookup"><span data-stu-id="9318a-147">**What is an acquirer and does Azure use one?**</span></span>

<span data-ttu-id="9318a-148">收单机构是指处理支付卡事务的银行或其他实体。</span><span class="sxs-lookup"><span data-stu-id="9318a-148">An acquirer is a bank or other entity that processes payment card transactions.</span></span> <span data-ttu-id="9318a-149">Azure 不提供支付卡处理服务，因此不使用收单机构。</span><span class="sxs-lookup"><span data-stu-id="9318a-149">Azure does not offer payment card processing as a service and thus does not use an acquirer.</span></span>

<span data-ttu-id="9318a-150">**PCI DSS 适用于哪些组织和商家？**</span><span class="sxs-lookup"><span data-stu-id="9318a-150">**To what organizations and merchants does the PCI DSS apply?**</span></span>

<span data-ttu-id="9318a-151">PCI DSS 适用于任何接受、传输或存储持卡人数据的公司，不论规模或交易量如何。</span><span class="sxs-lookup"><span data-stu-id="9318a-151">PCI DSS applies to any company, no matter the size, or number of transactions, that accepts, transmits, or stores cardholder data.</span></span> <span data-ttu-id="9318a-152">也就是说，如果任何客户使用信用卡或借记卡向公司进行了支付，则会应用 PCI DSS 要求。</span><span class="sxs-lookup"><span data-stu-id="9318a-152">That is, if any customer ever pays a company using a credit or debit card, then the PCI DSS requirements apply.</span></span> <span data-ttu-id="9318a-153">根据过去 12 个月内总交易量，被确认为四个级别之一的公司。</span><span class="sxs-lookup"><span data-stu-id="9318a-153">Companies are validated at one of four levels based on the total transaction volume over a 12-month period.</span></span> <span data-ttu-id="9318a-154">Level 1 针对一年处理的交易量超过 600 万的公司；Level 2 针对 100 万到 600 万交易量；Level 3 针对 2 万到 100 万交易量；Level 4 针对低于 2 万交易量。</span><span class="sxs-lookup"><span data-stu-id="9318a-154">Level 1 is for companies that process over 6 million transactions a year; Level 2 for 1 million to 6 million transactions; Level 3 is for 20,000 to 1 million transactions; and Level 4 is for fewer than 20,000 transactions.</span></span>

<span data-ttu-id="9318a-155">**我的组织从何处着手开展针对部署在 Azure 上的解决方案的 PCI DSS 合规工作？**</span><span class="sxs-lookup"><span data-stu-id="9318a-155">**Where do I begin my organization’s PCI DSS compliance efforts for a solution deployed on Azure?**</span></span>

<span data-ttu-id="9318a-156">支付卡行业数据安全标准委员会提供的信息能够让您很好地了解具体的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="9318a-156">The information that the PCI Security Standards Council makes available is a good place to learn about specific compliance requirements.</span></span> <span data-ttu-id="9318a-157">该委员会针对商家及参与支付卡处理的人员发布了 [PCI DSS 快速参考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9318a-157">The council publishes the [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) for merchants and others involved in payment card processing.</span></span> <span data-ttu-id="9318a-158">该指南解释了 PCI DSS 如何帮助保护支付卡交易环境以及如何应用该标准。</span><span class="sxs-lookup"><span data-stu-id="9318a-158">The guide explains how the PCI DSS can help protect a payment card transaction environment and how to apply it.</span></span>

<span data-ttu-id="9318a-159">合规性涉及若干因素，包括评估未托管在 Azure 上的系统和流程。</span><span class="sxs-lookup"><span data-stu-id="9318a-159">Compliance involves several factors, including assessing the systems and processes not hosted on Azure.</span></span> <span data-ttu-id="9318a-160">根据所使用的 Azure 服务及它们在解决方案中用法，个别要求会有所变化。</span><span class="sxs-lookup"><span data-stu-id="9318a-160">Individual requirements vary based on which Azure services are used and how they are employed within the solution.</span></span>

<span data-ttu-id="9318a-161">**OneDrive for Business 和 SharePoint Online 是否有在美国境外实现 PCI DSS 合规性的计划？**</span><span class="sxs-lookup"><span data-stu-id="9318a-161">**Are there plans for OneDrive for Business and SharePoint Online to be PCI DSS-compliant outside of the United States?**</span></span>

<span data-ttu-id="9318a-162">目前，OneDrive for Business 和 SharePoint Online 仅在美国符合 PCI-DSS 要求。</span><span class="sxs-lookup"><span data-stu-id="9318a-162">Currently OneDrive for Business and SharePoint Online is PCI-DSS compliant only in the United States (US).</span></span> <span data-ttu-id="9318a-163">Microsoft 将评估美国以外地区的要求和时间表，并在将或如果有其他地区添加到路线图时提供更新。</span><span class="sxs-lookup"><span data-stu-id="9318a-163">Microsoft will evaluate the requirements and timelines for regions outside of US and provide updates when and if other regions are added to the roadmap.</span></span>

<span data-ttu-id="9318a-164">**OneDrive for Business 和 SharePoint Online 的范围内是什么？**</span><span class="sxs-lookup"><span data-stu-id="9318a-164">**What is in-scope for OneDrive for Business and SharePoint Online?**</span></span>

<span data-ttu-id="9318a-165">目前，只有上载到 OneDrive for Business 和 SharePoint Online 的文件和文档符合 PCI DSS。</span><span class="sxs-lookup"><span data-stu-id="9318a-165">Currently, only files and documents uploaded to OneDrive for Business and SharePoint Online will be complaint with PCI DSS.</span></span>

## <a name="resources"></a><span data-ttu-id="9318a-166">资源</span><span class="sxs-lookup"><span data-stu-id="9318a-166">Resources</span></span>

- [<span data-ttu-id="9318a-167">支付卡行业数据安全标准委员会</span><span class="sxs-lookup"><span data-stu-id="9318a-167">PCI Security Standards Council</span></span>](https://www.pcisecuritystandards.org/)
- [<span data-ttu-id="9318a-168">PCI 数据安全标准</span><span class="sxs-lookup"><span data-stu-id="9318a-168">PCI Data Security Standard (PCI DSS)</span></span>](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [<span data-ttu-id="9318a-169">Azure PCI DSS 3.2.1 责任矩阵</span><span class="sxs-lookup"><span data-stu-id="9318a-169">Azure PCI DSS 3.2.1 Responsibility Matrix</span></span>](https://aka.ms/pciresponsibilitymatrix)
- [<span data-ttu-id="9318a-170">PCI DSS 快速参考指南</span><span class="sxs-lookup"><span data-stu-id="9318a-170">PCI DSS Quick Reference Guide</span></span>](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [<span data-ttu-id="9318a-171">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="9318a-171">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="9318a-172">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="9318a-172">Download the offering backgrounder</span></span>

<span data-ttu-id="9318a-173">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="9318a-173">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="9318a-174">请下载 [PDF](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI_DSS_Compliance_Backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9318a-174">Download the [PDF](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI_DSS_Compliance_Backgrounder.pdf).</span></span>