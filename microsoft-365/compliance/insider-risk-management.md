---
title: 内幕风险管理
description: 了解如何使用 Microsoft 365 中的内幕风险管理帮助最大限度地减少组织中的风险。
keywords: Microsoft 365，内幕风险，风险管理，合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0da96fe4148ffc30ac8e2f7854157675786cd321
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582871"
---
# <a name="insider-risk-management-in-microsoft-365-preview"></a><span data-ttu-id="4429a-104">Microsoft 365 中的内幕风险管理（预览）</span><span class="sxs-lookup"><span data-stu-id="4429a-104">Insider risk management in Microsoft 365 (preview)</span></span>

<span data-ttu-id="4429a-105">内幕风险管理是 Microsoft 365 中的一个内部风险解决方案，它通过使您能够检测、调查和对组织中的危险活动采取措施来帮助最大限度地减少内部风险。</span><span class="sxs-lookup"><span data-stu-id="4429a-105">Insider risk management is an internal risk solution in Microsoft 365 that helps minimize internal risks by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span> <span data-ttu-id="4429a-106">自定义策略允许您检测组织中的恶意和意外风险活动并采取措施，包括在需要时向其他 Microsoft 365 调查解决方案升级案例。</span><span class="sxs-lookup"><span data-stu-id="4429a-106">Custom policies allow you to detect and take action on malicious and inadvertent risk activities in your organization, including escalating cases to other Microsoft 365 investigation solutions if needed.</span></span> <span data-ttu-id="4429a-107">组织中的风险分析师可以快速采取适当的措施，以确保用户符合组织的合规性标准。</span><span class="sxs-lookup"><span data-stu-id="4429a-107">Risk analysts in your organization can quickly take appropriate actions to make sure users are compliant with your organization's compliance standards.</span></span>

<span data-ttu-id="4429a-108">观看以下视频，了解内幕风险管理如何帮助您的组织防止、检测和包含风险，同时确定组织价值、文化和员工体验的优先级：</span><span class="sxs-lookup"><span data-stu-id="4429a-108">Watch the video below to learn how insider risk management can help your organization prevent, detect, and contain risks while prioritizing your organization values, culture, and employee experience:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a><span data-ttu-id="4429a-109">新式风险痛点</span><span class="sxs-lookup"><span data-stu-id="4429a-109">Modern risk pain points</span></span>

<span data-ttu-id="4429a-110">管理和最大限度地减少组织中的风险从了解新式工作区中发现的风险类型开始。</span><span class="sxs-lookup"><span data-stu-id="4429a-110">Managing and minimizing risk in your organization starts with understanding the types of risks found in the modern workplace.</span></span> <span data-ttu-id="4429a-111">某些风险由外部事件和因素驱动，并在直接控制范围内。</span><span class="sxs-lookup"><span data-stu-id="4429a-111">Some risks are driven by external events and factors and are outside direct control.</span></span> <span data-ttu-id="4429a-112">其他风险由可以消除并避免的内部事件和员工活动驱动。</span><span class="sxs-lookup"><span data-stu-id="4429a-112">Other risks are driven by internal events and employee activities that can be eliminated and avoided.</span></span> <span data-ttu-id="4429a-113">有些示例是来自员工和经理的非法、不正当、未授权或不道德行为和操作的风险。</span><span class="sxs-lookup"><span data-stu-id="4429a-113">Some examples are risks from illegal, inappropriate, unauthorized, or unethical behavior and actions by employees and managers.</span></span> <span data-ttu-id="4429a-114">这些行为包括员工的多种内部风险：</span><span class="sxs-lookup"><span data-stu-id="4429a-114">These behaviors include a broad range of internal risks from employees:</span></span>

- <span data-ttu-id="4429a-115">敏感数据泄露和数据外泄</span><span class="sxs-lookup"><span data-stu-id="4429a-115">Leaks of sensitive data and data spillage</span></span>
- <span data-ttu-id="4429a-116">违反机密性</span><span class="sxs-lookup"><span data-stu-id="4429a-116">Confidentiality violations</span></span>
- <span data-ttu-id="4429a-117">知识财产（IP）盗窃</span><span class="sxs-lookup"><span data-stu-id="4429a-117">Intellectual property (IP) theft</span></span>
- <span data-ttu-id="4429a-118">防</span><span class="sxs-lookup"><span data-stu-id="4429a-118">Fraud</span></span>
- <span data-ttu-id="4429a-119">内幕交易</span><span class="sxs-lookup"><span data-stu-id="4429a-119">Insider trading</span></span>
- <span data-ttu-id="4429a-120">法规遵从性冲突</span><span class="sxs-lookup"><span data-stu-id="4429a-120">Regulatory compliance violations</span></span>

<span data-ttu-id="4429a-121">新式工作区中的员工有权在各种各样的平台和服务中创建、管理和共享数据。</span><span class="sxs-lookup"><span data-stu-id="4429a-121">Employees in the modern workplace have access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="4429a-122">在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围的风险，同时还能满足员工隐私标准。</span><span class="sxs-lookup"><span data-stu-id="4429a-122">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting employee privacy standards.</span></span>

<span data-ttu-id="4429a-123">Microsoft 365 中的内幕风险管理使用全面的服务和第三方指示器来帮助您快速确定、会审并对风险活动采取措施。</span><span class="sxs-lookup"><span data-stu-id="4429a-123">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and take action on risk activity.</span></span> <span data-ttu-id="4429a-124">通过使用 Office 365 和 Microsoft Graph 中的日志，内幕风险管理允许您定义特定策略以标识风险指示器。</span><span class="sxs-lookup"><span data-stu-id="4429a-124">By using logs from Office 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators.</span></span> <span data-ttu-id="4429a-125">通过这些策略，您可以确定危险活动并采取措施来缓解这些风险。</span><span class="sxs-lookup"><span data-stu-id="4429a-125">These policies allow you to identify risky activities and to take action to mitigate these risks.</span></span>

<span data-ttu-id="4429a-126">内幕风险管理的中心围绕以下原则：</span><span class="sxs-lookup"><span data-stu-id="4429a-126">Insider risk management is centered around the following principles:</span></span>

- <span data-ttu-id="4429a-127">**透明度**：根据设计隐私体系结构，平衡员工隐私和组织风险。</span><span class="sxs-lookup"><span data-stu-id="4429a-127">**Transparency**: Balance employee privacy versus organization risk with privacy-by-design architecture.</span></span>
- <span data-ttu-id="4429a-128">**可配置**：基于行业、地理位置和业务组的可配置策略。</span><span class="sxs-lookup"><span data-stu-id="4429a-128">**Configurable**: Configurable policies based on industry, geographical, and business groups.</span></span>
- <span data-ttu-id="4429a-129">**集成**：跨 Microsoft 365 合规性解决方案的集成工作流。</span><span class="sxs-lookup"><span data-stu-id="4429a-129">**Integrated**: Integrated workflow across Microsoft 365 compliance solutions.</span></span>
- <span data-ttu-id="4429a-130">可**操作**：提供有关启用员工通知、数据调查和员工调查的见解。</span><span class="sxs-lookup"><span data-stu-id="4429a-130">**Actionable**: Provides insights to enable employee notifications, data investigations, and employee investigations.</span></span>

## <a name="workflow"></a><span data-ttu-id="4429a-131">工作流</span><span class="sxs-lookup"><span data-stu-id="4429a-131">Workflow</span></span>

<span data-ttu-id="4429a-132">内幕风险管理可帮助您确定、调查和采取措施来解决组织中的内部风险。</span><span class="sxs-lookup"><span data-stu-id="4429a-132">Insider risk management helps you identify, investigate, and take action to address internal risks in your organization.</span></span> <span data-ttu-id="4429a-133">使用集中式策略模板、跨 Microsoft 365 服务的全面活动信号和灵活的工作流，您可以使用可操作的见解快速识别和解决有风险的行为。</span><span class="sxs-lookup"><span data-stu-id="4429a-133">With focused policy templates, comprehensive activity signaling across the Microsoft 365 service, and a flexible workflow, you can use actionable insights to quickly identify and resolve risky behavior.</span></span>

<span data-ttu-id="4429a-134">使用以下工作流确定和解决 Microsoft 365 中的内幕风险管理的内部风险活动和合规性问题：</span><span class="sxs-lookup"><span data-stu-id="4429a-134">Identifying and resolving internal risk activities and compliance issues with insider risk management in Microsoft 365 uses the following workflow:</span></span>

![内幕风险管理工作流](media/insider-risk-workflow.png)

### <a name="policies"></a><span data-ttu-id="4429a-136">策略</span><span class="sxs-lookup"><span data-stu-id="4429a-136">Policies</span></span>

<span data-ttu-id="4429a-137">内幕风险管理策略是使用预定义的模板和策略条件（定义在 Microsoft 365 功能区域中检查哪些风险指示器）创建的。</span><span class="sxs-lookup"><span data-stu-id="4429a-137">Insider risk management policies are created using pre-defined templates and policy conditions that define what risk indicators are examined in Microsoft 365 feature areas.</span></span> <span data-ttu-id="4429a-138">这些条件包括指示器用于通知、策略中包含的用户、确定优先顺序的服务以及监视时间段。</span><span class="sxs-lookup"><span data-stu-id="4429a-138">These conditions include how indicators are used for alerts, what users are included in the policy, which services are prioritized, and the monitoring time period.</span></span>

<span data-ttu-id="4429a-139">您可以从以下[策略模板](insider-risk-management-policies.md#policy-templates)中进行选择，以便快速开始使用 "内幕风险管理"：</span><span class="sxs-lookup"><span data-stu-id="4429a-139">You can select from the following [policy templates](insider-risk-management-policies.md#policy-templates) to quickly get started with insider risk management:</span></span>

- <span data-ttu-id="4429a-140">脱离员工数据失窃</span><span class="sxs-lookup"><span data-stu-id="4429a-140">Departing employee data theft</span></span>
- <span data-ttu-id="4429a-141">数据泄露</span><span class="sxs-lookup"><span data-stu-id="4429a-141">Data leaks</span></span>
- <span data-ttu-id="4429a-142">通信中的冒犯性语言</span><span class="sxs-lookup"><span data-stu-id="4429a-142">Offensive language in communication</span></span>

<span data-ttu-id="4429a-143">有关详细信息，请参阅[内幕风险管理策略](insider-risk-management-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4429a-143">For more information, see [Insider risk management policies](insider-risk-management-policies.md).</span></span>

![内幕风险管理策略仪表板](media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a><span data-ttu-id="4429a-145">警报</span><span class="sxs-lookup"><span data-stu-id="4429a-145">Alerts</span></span>

<span data-ttu-id="4429a-146">警报由符合策略条件并显示在 "**通知" 仪表板**中的风险指示器自动生成。</span><span class="sxs-lookup"><span data-stu-id="4429a-146">Alerts are automatically generated by risk indicators that match policy conditions and are displayed in the **Alerts dashboard**.</span></span> <span data-ttu-id="4429a-147">通过此仪表板，可以快速查看需要查看的所有警报、一段时间内打开的警报以及组织的警报统计信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-147">This dashboard enables a quick view of all alerts needing review, open alerts over time, and alert statistics for your organization.</span></span> <span data-ttu-id="4429a-148">将显示所有策略警报，其中包含相关信息，以帮助您快速识别现有通知的当前状态和需要采取操作的新警报：</span><span class="sxs-lookup"><span data-stu-id="4429a-148">All policy alerts are displayed with associated information to help you quickly identify the current status of existing alerts and new alerts that need action:</span></span>

- <span data-ttu-id="4429a-149">状态</span><span class="sxs-lookup"><span data-stu-id="4429a-149">Status</span></span>
- <span data-ttu-id="4429a-150">严重性</span><span class="sxs-lookup"><span data-stu-id="4429a-150">Severity</span></span>
- <span data-ttu-id="4429a-151">检测时间</span><span class="sxs-lookup"><span data-stu-id="4429a-151">Time detected</span></span>
- <span data-ttu-id="4429a-152">情况</span><span class="sxs-lookup"><span data-stu-id="4429a-152">Case</span></span>
- <span data-ttu-id="4429a-153">案例状态</span><span class="sxs-lookup"><span data-stu-id="4429a-153">Case status</span></span>

<span data-ttu-id="4429a-154">有关详细信息，请参阅[内幕风险管理警报](insider-risk-management-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="4429a-154">For more information, see [Insider risk management alerts](insider-risk-management-alerts.md).</span></span>

![内幕风险管理警报仪表板](media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a><span data-ttu-id="4429a-156">诊断</span><span class="sxs-lookup"><span data-stu-id="4429a-156">Triage</span></span>

<span data-ttu-id="4429a-157">需要调查的新活动会自动生成为其分配了 "*需要审阅*" 状态的警报。</span><span class="sxs-lookup"><span data-stu-id="4429a-157">New activities that need investigation automatically generate alerts that are assigned a *Needs review* status.</span></span> <span data-ttu-id="4429a-158">审阅者可以快速识别这些通知并滚动到每个通知进行评估和会审。</span><span class="sxs-lookup"><span data-stu-id="4429a-158">Reviewers can quickly identify these alerts and scroll through each to evaluate and triage.</span></span> 

<span data-ttu-id="4429a-159">通过打开新事例、将警报分配给现有事例或消除警报来解决警报。</span><span class="sxs-lookup"><span data-stu-id="4429a-159">Alerts are resolved by opening a new case, assigning the alert to an existing case, or dismissing the alert.</span></span> <span data-ttu-id="4429a-160">使用警报筛选器，可以轻松地根据状态、严重性或时间来识别警报。</span><span class="sxs-lookup"><span data-stu-id="4429a-160">Using alert filters, it's easy to quickly identify alerts by status, severity, or time detected.</span></span> <span data-ttu-id="4429a-161">作为会审过程的一部分，审阅者可以查看策略匹配的警报详细信息、查看与匹配项关联的用户活动、查看警报的严重性并查看用户配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-161">As part of the triage process, reviewers can view alert details for the policy match, view user activity associated with the match, see the severity of the alert, and review user profile information.</span></span>

![内幕风险管理会审](media/insider-risk-triage.png)

### <a name="investigate"></a><span data-ttu-id="4429a-163">调查</span><span class="sxs-lookup"><span data-stu-id="4429a-163">Investigate</span></span>

<span data-ttu-id="4429a-164">为需要深入审查和调查策略匹配周围的详细信息和情况的警报创建案例。</span><span class="sxs-lookup"><span data-stu-id="4429a-164">Cases are created for alerts that require deeper review and investigation of the details and circumstances around the policy match.</span></span> <span data-ttu-id="4429a-165">**事例仪表板**提供了所有活动案例的详细视图、一段时间内的开放事例以及贵组织的案例统计信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-165">The **Case dashboard** provides an all-up view of all active cases, open cases over time, and case statistics for your organization.</span></span> <span data-ttu-id="4429a-166">审阅者可以按状态、打开案例的日期以及上次更新事例的日期来快速筛选案例。</span><span class="sxs-lookup"><span data-stu-id="4429a-166">Reviewers can quickly filter cases by status, the date the case was opened, and the date the case was last updated.</span></span>

<span data-ttu-id="4429a-167">在事例仪表板上选择一个事例将打开调查和审阅的案例。</span><span class="sxs-lookup"><span data-stu-id="4429a-167">Selecting a case on the case dashboard opens the case for investigation and review.</span></span> <span data-ttu-id="4429a-168">这一步是内幕风险管理工作流的核心。</span><span class="sxs-lookup"><span data-stu-id="4429a-168">This step is the heart of the insider risk management workflow.</span></span> <span data-ttu-id="4429a-169">此区域是风险活动指标、策略条件、警报详细信息和员工详细信息合成到审阅者的集成视图中的地方。</span><span class="sxs-lookup"><span data-stu-id="4429a-169">This area is where risk activity indicators, policy conditions, alerts details, and employee details are synthesized into an integrated view for reviewers.</span></span> <span data-ttu-id="4429a-170">此区域中的主要调查工具是：</span><span class="sxs-lookup"><span data-stu-id="4429a-170">The primary investigation tools in this area are:</span></span>

- <span data-ttu-id="4429a-171">**用户活动**：用户活动将自动显示在交互式图表中，该图表按时间和当前或过去风险活动的风险级别绘制风险活动。</span><span class="sxs-lookup"><span data-stu-id="4429a-171">**User activity**: User activity is automatically displayed in an interactive chart that plots risk activities over time and by risk level for current or past risk activities.</span></span> <span data-ttu-id="4429a-172">审阅者可以快速筛选和查看员工的整个风险历史记录，并深入了解具体活动以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-172">Reviewers can quickly filter and view the entire risk history for the employee and drill into specific activities for more details.</span></span>
- <span data-ttu-id="4429a-173">**内容资源管理器**：与警报风险活动相关联的所有数据文件和电子邮件都将自动捕获并显示在内容资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="4429a-173">**Content explorer**: All data files and email messages associated with alert risk activities are automatically captured and displayed in the content explorer.</span></span> <span data-ttu-id="4429a-174">审阅者可以按数据源、文件类型、标记、对话以及其他许多属性来筛选和查看文件和邮件。</span><span class="sxs-lookup"><span data-stu-id="4429a-174">Reviewers can filter and view files and messages by data source, file type, tags, conversation, and many more attributes.</span></span>
- <span data-ttu-id="4429a-175">**案例备注**：审阅者在 "事例注释" 部分中提供了有关案例的注释。</span><span class="sxs-lookup"><span data-stu-id="4429a-175">**Case notes**: Reviewers provide notes for a case in the Case Notes section.</span></span> <span data-ttu-id="4429a-176">此列表合并了一个中心视图中的所有笔记，并包含审阅者和提交的日期信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-176">This list consolidates all notes in a central view and include reviewer and date submitted information.</span></span>

<span data-ttu-id="4429a-177">有关详细信息，请参阅[内幕风险管理案例](insider-risk-management-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="4429a-177">For more information, see [Insider risk management cases](insider-risk-management-cases.md).</span></span>

![内幕风险管理调查](media/insider-risk-investigate.png)

### <a name="action"></a><span data-ttu-id="4429a-179">Action</span><span class="sxs-lookup"><span data-stu-id="4429a-179">Action</span></span>

<span data-ttu-id="4429a-180">在调查事例之后，审阅者可以快速采取措施解决案例或与组织中的其他风险承担者进行协作。</span><span class="sxs-lookup"><span data-stu-id="4429a-180">After cases are investigated, reviewers can quickly take action to resolve the case or collaborate with other risk stakeholders in your organization.</span></span> <span data-ttu-id="4429a-181">当员工意外或无意地违反策略条件时，可以向员工发送一个简单的提醒通知，您可以为您的组织配置通知模板。</span><span class="sxs-lookup"><span data-stu-id="4429a-181">When employees accidentally or inadvertently violate policy conditions, a simple reminder notice can be sent to the employee from notice templates you can configure for your organization.</span></span> <span data-ttu-id="4429a-182">这些通知可用作简单的提醒，也可指导员工进行复习培训或指导，以帮助防止将来出现风险的行为。</span><span class="sxs-lookup"><span data-stu-id="4429a-182">These notices may serve as simple reminders or may direct the employee to refresher training or guidance to help prevent future risky behavior.</span></span> <span data-ttu-id="4429a-183">有关详细信息，请参阅[内幕风险管理通知模板](insider-risk-management-notices.md)。</span><span class="sxs-lookup"><span data-stu-id="4429a-183">For more information, see [Insider risk management notice templates](insider-risk-management-notices.md).</span></span>

<span data-ttu-id="4429a-184">在最严重的情况下，您可能需要与组织中的其他审阅人共享内幕风险管理案例信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-184">In the most serious situations, you may need to share the insider risk management case information with other reviewers in your organization.</span></span> <span data-ttu-id="4429a-185">内幕风险管理与其他 Microsoft 365 合规性功能紧密集成，可帮助您进行端到端风险解决方案。</span><span class="sxs-lookup"><span data-stu-id="4429a-185">Insider risk management is tightly integrated with other Microsoft 365 compliance features to help you with end-to-end risk resolution.</span></span> <span data-ttu-id="4429a-186">升级案例以使您能够将案例的数据和管理转移到 Microsoft 365 中的高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="4429a-186">Escalating a case for investigation allows you to transfer data and management of the case to Advanced eDiscovery in Microsoft 365.</span></span> <span data-ttu-id="4429a-187">高级电子数据展示提供了端到端工作流，以保留、收集、查看、分析和导出对组织内部和外部调查做出响应的内容。</span><span class="sxs-lookup"><span data-stu-id="4429a-187">Advanced eDiscovery provides an end-to-end workflow to preserve, collect, review, analyze, and export content that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="4429a-188">它允许法律团队管理整个法律封存通知工作流。</span><span class="sxs-lookup"><span data-stu-id="4429a-188">It allows legal teams to manage the entire legal hold notification workflow.</span></span> <span data-ttu-id="4429a-189">若要了解有关高级电子数据展示事例的详细信息，请参阅[Microsoft 365 中的高级电子数据展示概述](overview-ediscovery-20.md)。</span><span class="sxs-lookup"><span data-stu-id="4429a-189">To learn more about Advanced eDiscovery cases, see [Overview of Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).</span></span>

## <a name="scenarios"></a><span data-ttu-id="4429a-190">方案</span><span class="sxs-lookup"><span data-stu-id="4429a-190">Scenarios</span></span>

<span data-ttu-id="4429a-191">内幕风险管理可帮助您在以下几个常见方案中检测、调查和采取措施来缓解组织中的内部风险：</span><span class="sxs-lookup"><span data-stu-id="4429a-191">Insider risk management can help you detect, investigate, and take action to mitigate internal risks in your organization in several common scenarios:</span></span>

### <a name="data-theft-by-departing-employee"></a><span data-ttu-id="4429a-192">通过脱离员工进行数据窃取</span><span class="sxs-lookup"><span data-stu-id="4429a-192">Data theft by departing employee</span></span>

<span data-ttu-id="4429a-193">当员工离开组织（自愿或作为终止的结果）时，通常会对公司、客户和员工数据存在风险带来合法的关注。</span><span class="sxs-lookup"><span data-stu-id="4429a-193">When employees leave an organization, either voluntarily or as the result of termination, there is often legitimate concerns that company, customer, and employee data are at risk.</span></span> <span data-ttu-id="4429a-194">员工可能 innocently 认为项目数据并非专有，或者他们可能会尝试将公司数据用于个人利益，并违反公司政策和法律标准。</span><span class="sxs-lookup"><span data-stu-id="4429a-194">Employees may innocently assume that project data isn't proprietary or they may be tempted to take company data for personal gain and in violation of company policy and legal standards.</span></span> <span data-ttu-id="4429a-195">使用[传出员工数据失窃](insider-risk-management-policies.md#policy-templates)策略模板的内幕风险管理策略可自动检测通常与此类型的盗窃相关联的活动。</span><span class="sxs-lookup"><span data-stu-id="4429a-195">Insider risk management policies that use the [Departing employee data theft](insider-risk-management-policies.md#policy-templates) policy template automatically detect activities typically associated with this type of theft.</span></span> <span data-ttu-id="4429a-196">使用此策略，您将自动收到与传出员工失窃相关的可疑活动的警报，以便您可以采取适当的调查操作。</span><span class="sxs-lookup"><span data-stu-id="4429a-196">With this policy, you'll automatically receive alerts for suspicious activities associated with departing employees theft so you can take appropriate investigative actions.</span></span> <span data-ttu-id="4429a-197">为您的组织配置[Microsoft 365 HR 连接器](import-hr-data.md)是此策略模板所必需的。</span><span class="sxs-lookup"><span data-stu-id="4429a-197">Configuring a [Microsoft 365 HR Connector](import-hr-data.md) for your organization is required for this policy template.</span></span>

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a><span data-ttu-id="4429a-198">敏感或机密信息的有意或无意泄露</span><span class="sxs-lookup"><span data-stu-id="4429a-198">Intentional or unintentional leak of sensitive or confidential information</span></span>

<span data-ttu-id="4429a-199">在大多数情况下，员工最好先尝试其正确处理敏感或机密信息。</span><span class="sxs-lookup"><span data-stu-id="4429a-199">In most cases, employees try their best to properly handle sensitive or confidential information.</span></span> <span data-ttu-id="4429a-200">但有时员工会导致错误，并且信息会在您的组织外部意外共享或违反您的信息保护策略。</span><span class="sxs-lookup"><span data-stu-id="4429a-200">But occasionally employees make mistakes and information is accidentally shared outside your organization or in violation of your information protection policies.</span></span> <span data-ttu-id="4429a-201">有时，员工可能会有意泄露或共享敏感和机密信息，以实现恶意目的和潜在的个人利益。</span><span class="sxs-lookup"><span data-stu-id="4429a-201">Sometimes employees may intentionally leak or share sensitive and confidential information with malicious intent and for potential personal gain.</span></span> <span data-ttu-id="4429a-202">使用[数据泄露](insider-risk-management-policies.md#policy-templates)策略模板创建的内幕风险管理策略将自动检测通常与共享敏感信息或机密信息相关的活动。</span><span class="sxs-lookup"><span data-stu-id="4429a-202">Insider risk management policies created using the [Data leaks](insider-risk-management-policies.md#policy-templates) policy template automatically detect activities typically associated with sharing sensitive or confidential information.</span></span> <span data-ttu-id="4429a-203">对于此策略模板，至少需要为您的组织配置一个 Microsoft 365[数据丢失保护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="4429a-203">Configuring at least one Microsoft 365 [Data Loss Protection (DLP) policy](create-test-tune-dlp-policy.md) for your organization is required for this policy template.</span></span>

### <a name="actions-and-behaviors-that-violate-corporate-policies"></a><span data-ttu-id="4429a-204">违反企业策略的操作和行为</span><span class="sxs-lookup"><span data-stu-id="4429a-204">Actions and behaviors that violate corporate policies</span></span>

<span data-ttu-id="4429a-205">员工对员工的通信通常是意外或恶意违反公司策略的来源。</span><span class="sxs-lookup"><span data-stu-id="4429a-205">Employee-to-employee communications are often a source of inadvertent or malicious violations of corporate policies.</span></span> <span data-ttu-id="4429a-206">这些冲突可能包括员工之间的冒犯性语言、威胁和网络威胁。</span><span class="sxs-lookup"><span data-stu-id="4429a-206">These violations can include offensive language, threats, and cyber-bullying between employees.</span></span> <span data-ttu-id="4429a-207">此类型的活动可分配给恶意工作环境，并可能导致对员工和更大的组织的法律活动。</span><span class="sxs-lookup"><span data-stu-id="4429a-207">This type of activity contributes to a hostile work environment and can result in legal actions against both employees and the larger organization.</span></span> <span data-ttu-id="4429a-208">内幕风险管理使用新的内置 Microsoft 365 分类器和[电子邮件](insider-risk-management-policies.md#policy-templates)策略模板中的冒犯性语言。</span><span class="sxs-lookup"><span data-stu-id="4429a-208">Insider risk management uses new built-in Microsoft 365 classifiers and the [Offensive language in email](insider-risk-management-policies.md#policy-templates) policy template.</span></span> <span data-ttu-id="4429a-209">通过这些分类器和模板，可以快速配置策略，以自动检测并提醒您此类行为。</span><span class="sxs-lookup"><span data-stu-id="4429a-209">These classifiers and templates enable the quick configuration of a policy to automatically detect and alert you of this kind of behavior.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="4429a-210">准备好开始了吗？</span><span class="sxs-lookup"><span data-stu-id="4429a-210">Ready to get started?</span></span>

<span data-ttu-id="4429a-211">准备好为你的组织配置内幕风险管理吗？</span><span class="sxs-lookup"><span data-stu-id="4429a-211">Ready to configure insider risk management for your organization?</span></span> <span data-ttu-id="4429a-212">请参阅 "[内幕风险管理入门](insider-risk-management-configure.md)"，配置先决条件、创建策略并开始接收通知。</span><span class="sxs-lookup"><span data-stu-id="4429a-212">See [Get started with insider risk management](insider-risk-management-configure.md) to configure prerequisites, create policies, and start receiving alerts.</span></span>