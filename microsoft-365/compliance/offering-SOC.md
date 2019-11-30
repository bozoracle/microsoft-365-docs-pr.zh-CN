---
title: Service Organization Controls (SOC)
description: Microsoft 云服务符合 Service Organization Controls 操作安全标准。
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
ms.openlocfilehash: c773d2e4f69b415745e0a327e497ce26ed62c223
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218671"
---
# <a name="compliance-offering-service-organization-controls-soc"></a><span data-ttu-id="7d97a-104">合规性产品/服务：Service Organization Controls (SOC)</span><span class="sxs-lookup"><span data-stu-id="7d97a-104">Compliance offering: Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="7d97a-105">SOC 1、2 和 3 报告概述</span><span class="sxs-lookup"><span data-stu-id="7d97a-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="7d97a-106">企业越来越多地将基本功能（例如数据存储和应用程序的访问权）外包给云服务提供商 (CSP) 和其他服务组织。</span><span class="sxs-lookup"><span data-stu-id="7d97a-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="7d97a-107">为此，美国注册会计师协会 (AICPA) 开发出了 Service Organization Controls (SOC) 框架，这是一种用于保护云中存储和处理的信息机密性和隐私性的控制措施标准。</span><span class="sxs-lookup"><span data-stu-id="7d97a-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="7d97a-108">该标准符合 International Standard on Assurance Engagements (ISAE)，后者是一种针对国际服务组织的报告标准。</span><span class="sxs-lookup"><span data-stu-id="7d97a-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="7d97a-109">基于 SOC 框架的服务审核分为两类：SOC 1 和 SOC 2，适用于范围内 Microsoft 云服务。</span><span class="sxs-lookup"><span data-stu-id="7d97a-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="7d97a-110">SOC 1 审核针对审计财务报表的 CPA 事务所，可评估 CSP 内部控制措施的有效性，这些内部控制措施会影响使用提供商云服务的客户的财务报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP’s internal controls that affect the financial reports of a customer using the provider’s cloud services.</span></span> <span data-ttu-id="7d97a-111">《鉴证业务准则公告》(SSAE 18) 和《鉴证业务国际准则</span><span class="sxs-lookup"><span data-stu-id="7d97a-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="7d97a-112">第 3402 号》(ISAE 3402) 是进行审核的标准，也是 SOC 1 报告的基础。</span><span class="sxs-lookup"><span data-stu-id="7d97a-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="7d97a-113">SOC 2 审核基于 AICPA Trust Service Principles and Criteria 来衡量 CSP 系统的有效性。</span><span class="sxs-lookup"><span data-stu-id="7d97a-113">A SOC 2 audit gauges the effectiveness of a CSP’s system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="7d97a-114">Attest Engagement under Attestation Standards (AT) 条例 101 是 SOC 2 和 SOC 3 报告的基础。</span><span class="sxs-lookup"><span data-stu-id="7d97a-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="7d97a-115">在 SOC 1 或 SOC 2 审核结尾部分，服务审核员会在 SOC 1 Type 2 或 SOC 2 Type 2 报告中提供评价意见，用于描述 CSP 系统并评估 CSP 对其控制措施描述的公平性。</span><span class="sxs-lookup"><span data-stu-id="7d97a-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP’s system and assesses the fairness of the CSP’s description of its controls.</span></span> <span data-ttu-id="7d97a-116">该结论还会评估 CSP 控制措施是否设计得当、在指定日期是否正常运行，以及在指定时间段内是否有效运行。</span><span class="sxs-lookup"><span data-stu-id="7d97a-116">It also evaluates whether the CSP’s controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="7d97a-117">审核员还可以创建 SOC 3 报告（SOC 2 Type 2 审核报告的简化版），该报告适用于想要保证 CSP 控制措施但又不需要完整的 SOC 2 报告的用户。</span><span class="sxs-lookup"><span data-stu-id="7d97a-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP’s controls but don’t need a full SOC 2 report.</span></span> <span data-ttu-id="7d97a-118">只有在 CSP 的 SOC 2 审核意见为不合格时，才能授予 SOC 3 报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="7d97a-119">Microsoft 和 SOC 1、2 和 3 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="7d97a-120">独立的第三方审核员会根据 SOC 报告框架对 Microsoft 涵盖的云服务进行审核，至少每年一次。</span><span class="sxs-lookup"><span data-stu-id="7d97a-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="7d97a-121">Microsoft 云服务的审核涵盖有关数据安全性、可用性、处理完整性和机密性的控制措施（如果每个服务的范围内信任原则适用）。</span><span class="sxs-lookup"><span data-stu-id="7d97a-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="7d97a-122">Microsoft 已获得 SOC 1 Type 2、SOC 2 Type 2 和 SOC 3 报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="7d97a-123">通常，SOC 1 和 SOC 2 报告仅供与 Microsoft 签署了保密协议的客户使用；SOC 3 报告是公开提供的。</span><span class="sxs-lookup"><span data-stu-id="7d97a-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

<span data-ttu-id="7d97a-124">在 Microsoft 云上了解 SOC 1、2、3 的优势：[下载 SOC 1 和 SOC 2 Type 2 报告背景信息](https://aka.ms/soc_backgrounder)</span><span class="sxs-lookup"><span data-stu-id="7d97a-124">Learn about the benefits of SOC 1, 2, 3 on the Microsoft Cloud: [Download the SOC 1 and SOC 2 type 2 reports backgrounder](https://aka.ms/soc_backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="7d97a-125">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="7d97a-125">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="7d97a-126">SOC 1 和 SOC 2 覆盖的服务</span><span class="sxs-lookup"><span data-stu-id="7d97a-126">Covered services for SOC 1 and SOC 2</span></span>

- <span data-ttu-id="7d97a-127">Azure、Azure 政府和 Azure 德国[详细列表](https://aka.ms/AzureCompliance)</span><span class="sxs-lookup"><span data-stu-id="7d97a-127">Azure, Azure Government, and Azure Germany [detailed list](https://aka.ms/AzureCompliance)</span></span>
- <span data-ttu-id="7d97a-128">云应用安全</span><span class="sxs-lookup"><span data-stu-id="7d97a-128">Cloud App Security</span></span>
- <span data-ttu-id="7d97a-129">Dynamics 365 和 Dynamics 365 美国政府版[详细列表](https://aka.ms/d365-compliance-list)</span><span class="sxs-lookup"><span data-stu-id="7d97a-129">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="7d97a-130">Graph</span><span class="sxs-lookup"><span data-stu-id="7d97a-130">Graph</span></span>
- <span data-ttu-id="7d97a-131">Intune</span><span class="sxs-lookup"><span data-stu-id="7d97a-131">Intune</span></span>
- <span data-ttu-id="7d97a-132">Microsoft Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="7d97a-132">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="7d97a-133">Office 365、Office 365 美国政府版和 Office 365 美国政府国防版[详细列表](https://go.microsoft.com/fwlink/p/?LinkID=2077751)；Yammer 已完成 SOC 1 Type 1 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-133">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense [detailed list](https://go.microsoft.com/fwlink/p/?LinkID=2077751); Yammer has achieved a SOC 1 Type 1 report</span></span>
- <span data-ttu-id="7d97a-134">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="7d97a-134">Office 365 Germany</span></span>
- <span data-ttu-id="7d97a-135">PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="7d97a-135">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="7d97a-136">Power BI 云服务，作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="7d97a-136">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="7d97a-137">Stream</span><span class="sxs-lookup"><span data-stu-id="7d97a-137">Stream</span></span>
- <span data-ttu-id="7d97a-138">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7d97a-138">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="7d97a-139">SOC 3 涵盖的服务</span><span class="sxs-lookup"><span data-stu-id="7d97a-139">Covered services for SOC 3</span></span>

- <span data-ttu-id="7d97a-140">Azure、Azure 政府和 Azure 德国[详细列表](https://aka.ms/AzureCompliance)</span><span class="sxs-lookup"><span data-stu-id="7d97a-140">Azure, Azure Government, and Azure Germany [detailed list](https://aka.ms/AzureCompliance)</span></span>
- <span data-ttu-id="7d97a-141">云应用安全</span><span class="sxs-lookup"><span data-stu-id="7d97a-141">Cloud App Security</span></span>
- <span data-ttu-id="7d97a-142">Graph</span><span class="sxs-lookup"><span data-stu-id="7d97a-142">Graph</span></span>
- <span data-ttu-id="7d97a-143">Intune</span><span class="sxs-lookup"><span data-stu-id="7d97a-143">Intune</span></span>
- <span data-ttu-id="7d97a-144">Microsoft Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="7d97a-144">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="7d97a-145">PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="7d97a-145">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="7d97a-146">Power BI</span><span class="sxs-lookup"><span data-stu-id="7d97a-146">Power BI</span></span>
- <span data-ttu-id="7d97a-147">Stream</span><span class="sxs-lookup"><span data-stu-id="7d97a-147">Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="7d97a-148">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="7d97a-148">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="7d97a-149">审核周期</span><span class="sxs-lookup"><span data-stu-id="7d97a-149">Audit cycle</span></span>

<span data-ttu-id="7d97a-150">Microsoft 云服务会根据 SOC 1（SSAE18，ISAE 3402）和 SOC 2（AT 条例 101）标准每年至少进行一次审核。</span><span class="sxs-lookup"><span data-stu-id="7d97a-150">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402) and SOC 2 (AT Section 101) standards.</span></span>

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a><span data-ttu-id="7d97a-151">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream 和 Microsoft 数据中心</span><span class="sxs-lookup"><span data-stu-id="7d97a-151">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="7d97a-152">Azure 和 Azure 政府的 SOC 1 Type 2 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-152">Azure and Azure Government SOC 1 Type 2 Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [<span data-ttu-id="7d97a-153">Azure 和 Azure 政府的 SOC 2 Type 2 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-153">Azure and Azure Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="7d97a-154">Azure 和 Azure 政府的 SOC 3 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-154">Azure and Azure Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a><span data-ttu-id="7d97a-155">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7d97a-155">Dynamics 365</span></span>

- [<span data-ttu-id="7d97a-156">Dynamics 365 SOC 1 Type 2 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-156">Dynamics 365 SOC 2 Type 2 Report & Bridge Letter</span></span>](https://aka.ms/Dynamics365SOC1AuditReport)
- [<span data-ttu-id="7d97a-157">Dynamics 365 SOC 2 AT 101 Type II 审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-157">Dynamics 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Dynamics365SOC2AuditReport)
- [<span data-ttu-id="7d97a-158">请参阅 Bridge Letter 和其他审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-158">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

#### <a name="office-365"></a><span data-ttu-id="7d97a-159">Office 365</span><span class="sxs-lookup"><span data-stu-id="7d97a-159">Office 365</span></span>

- [<span data-ttu-id="7d97a-160">Office 365 SOC 1 SSAE 16 Type II 审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-160">Office 365 SOC 1 SSAE 16 Type II Audit Report</span></span>](https://aka.ms/office365soc1auditreport)
- [<span data-ttu-id="7d97a-161">Office 365 SOC 2 AT 101 Type II 审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-161">Office 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Office365SOC2AuditReport)
- [<span data-ttu-id="7d97a-162">Office 365 客户密码箱 SOC 1 SSAE 16 审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-162">Office 365 Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="7d97a-163">Yammer SOC 2 AT 101 Type II 审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-163">Yammer SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/YammerSOC2AuditReport)
- [<span data-ttu-id="7d97a-164">Yammer SOC 2 AT 101 Type I 审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-164">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="7d97a-165">请参阅 Bridge Letter 和其他审核报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-165">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="7d97a-166">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="7d97a-166">Frequently asked questions</span></span>

<span data-ttu-id="7d97a-167">**如何获得 SOC 报告的副本？**</span><span class="sxs-lookup"><span data-stu-id="7d97a-167">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="7d97a-168">使用这些报告，您的审核员可以将 Microsoft 商务云服务结果与你自己的法律和法规要求相比较。</span><span class="sxs-lookup"><span data-stu-id="7d97a-168">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="7d97a-169">可通过[服务信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)查看所有 SOC 报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-169">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="7d97a-170">无法访问[服务信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)的 Azure DevOps 服务客户可以向 [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) 发送电子邮件来获取其 SOC 1 和 SOC 2 报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-170">Azure DevOps Service customers that can’t access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="7d97a-171">此电子邮件仅用于请求 Azure DevOps SOC 报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-171">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="7d97a-172">**Azure SOC 报告多久发布一次？**</span><span class="sxs-lookup"><span data-stu-id="7d97a-172">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="7d97a-173">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream 和 Microsoft 数据中心的 SOC 报告基于滚动的 12 个月运行窗口（审计期）每个季度发布一份新报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-173">SOC reports for Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued quarterly.</span></span> <span data-ttu-id="7d97a-174">通过 SOC 报告，增加的审核频率可提供更及时的审核期覆盖范围，与 Bridge Letter 相比，外部审核员可以提供更大的保证。</span><span class="sxs-lookup"><span data-stu-id="7d97a-174">The increased audit frequency provides a more timely audit period coverage through a SOC report, which provides greater assurance by an external auditor when compared to a bridge letter.</span></span> <span data-ttu-id="7d97a-175">客户可从服务信任门户[下载](https://aka.ms/stp)最新报告。</span><span class="sxs-lookup"><span data-stu-id="7d97a-175">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="7d97a-176">**是否需要对 Microsoft 数据中心执行我自己的审核流程？**</span><span class="sxs-lookup"><span data-stu-id="7d97a-176">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="7d97a-177">否。</span><span class="sxs-lookup"><span data-stu-id="7d97a-177">No.</span></span> <span data-ttu-id="7d97a-178">Microsoft 会与客户共享独立的审核报告与认证，以便客户能够检验 Microsoft 是否符合自己的安全承诺。</span><span class="sxs-lookup"><span data-stu-id="7d97a-178">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="7d97a-179">**能否在我自己组织的认证过程中使用 Microsoft 的合规性认证？**</span><span class="sxs-lookup"><span data-stu-id="7d97a-179">**Can I use Microsoft’s compliance in my organization’s certification process?**</span></span>

<span data-ttu-id="7d97a-180">是。</span><span class="sxs-lookup"><span data-stu-id="7d97a-180">Yes.</span></span> <span data-ttu-id="7d97a-181">当您将应用程序和数据迁移到所覆盖的 Microsoft 云服务时，您可以把 Microsoft 所持有的审核与认证作为构建基础。</span><span class="sxs-lookup"><span data-stu-id="7d97a-181">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="7d97a-182">独立报告可证实 Microsoft 已实施用于维护您数据的安全性和隐私的控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="7d97a-182">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="7d97a-183">**从何处着手开展我自己组织的合规工作？**</span><span class="sxs-lookup"><span data-stu-id="7d97a-183">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="7d97a-184">[面向服务组织的 SOC 工具套件](https://aka.ms/soc-toolkit)对了解 SOC 报告过程和推动组织利用这些报告是非常有用的资源。</span><span class="sxs-lookup"><span data-stu-id="7d97a-184">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization’s use of them.</span></span>

## <a name="resources"></a><span data-ttu-id="7d97a-185">资源</span><span class="sxs-lookup"><span data-stu-id="7d97a-185">Resources</span></span>

 - [<span data-ttu-id="7d97a-186">使用 Microsoft 云服务更好地保护你的数据</span><span class="sxs-lookup"><span data-stu-id="7d97a-186">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
 - [<span data-ttu-id="7d97a-187">Service Organization Control (SOC) 报告</span><span class="sxs-lookup"><span data-stu-id="7d97a-187">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
 - [<span data-ttu-id="7d97a-188">SSAE 16 审核标准</span><span class="sxs-lookup"><span data-stu-id="7d97a-188">SSAE 16 Auditing Standard</span></span>](https://www.ssae-16.com/)
 - [<span data-ttu-id="7d97a-189">ISAE 3402 标准</span><span class="sxs-lookup"><span data-stu-id="7d97a-189">ISAE 3402 Standard</span></span>](https://isae3402.com/)
 - [<span data-ttu-id="7d97a-190">Microsoft 公共控制中心合规性框架</span><span class="sxs-lookup"><span data-stu-id="7d97a-190">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
 - [<span data-ttu-id="7d97a-191">Microsoft 联机服务条款</span><span class="sxs-lookup"><span data-stu-id="7d97a-191">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
 - [<span data-ttu-id="7d97a-192">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="7d97a-192">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
 - [<span data-ttu-id="7d97a-193">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="7d97a-193">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="7d97a-194">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="7d97a-194">Download the offering backgrounder</span></span>

<span data-ttu-id="7d97a-195">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="7d97a-195">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="7d97a-196">请下载 [PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf)。</span><span class="sxs-lookup"><span data-stu-id="7d97a-196">Download the [PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf).</span></span>