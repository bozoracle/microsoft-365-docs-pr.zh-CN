---
title: Microsoft 365 中的通信合规性（预览）
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: 了解 Microsoft 365 中的通信合规性
ms.openlocfilehash: 8c8e94209d2db575dd8338afa6f4c5c968033683
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633661"
---
# <a name="communication-compliance-in-microsoft-365-preview"></a><span data-ttu-id="7b961-103">Microsoft 365 中的通信合规性（预览）</span><span class="sxs-lookup"><span data-stu-id="7b961-103">Communication compliance in Microsoft 365 (preview)</span></span>

<span data-ttu-id="7b961-104">通信合规性是 Microsoft 365 中新的内幕风险解决方案集的一部分，可帮助您对组织中不适当的邮件进行检测、捕获和采取补救措施，从而帮助最大限度地减少通信风险。</span><span class="sxs-lookup"><span data-stu-id="7b961-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="7b961-105">通过预定义和自定义策略，可以扫描策略匹配的内部和外部通信，以便指定的审阅者可以对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="7b961-105">Pre-defined and custom policies allow you to scan internal and external communications for policy matches so they can be examined by designated reviewers.</span></span> <span data-ttu-id="7b961-106">审阅者可以调查组织中扫描的电子邮件、Microsoft 团队或第三方通信，并采取适当的补救措施以确保它们符合组织的邮件标准。</span><span class="sxs-lookup"><span data-stu-id="7b961-106">Reviewers can investigate scanned email, Microsoft Teams, or third-party communications in your organization and take appropriate remediation actions to make sure they're compliant with your organization's message standards.</span></span>

<span data-ttu-id="7b961-107">Microsoft 365 中的通信合规性策略可帮助您解决与合规性、内部和外部通信相关的许多新式难题，包括：</span><span class="sxs-lookup"><span data-stu-id="7b961-107">Communication compliance policies in Microsoft 365 help you overcome many modern challenges associated with compliance and internal and external communications, including:</span></span>

- <span data-ttu-id="7b961-108">扫描日益增长的通信信道类型</span><span class="sxs-lookup"><span data-stu-id="7b961-108">Scanning increasing types of communication channels</span></span>
- <span data-ttu-id="7b961-109">邮件数据量的增加</span><span class="sxs-lookup"><span data-stu-id="7b961-109">The increasing volume of message data</span></span>
- <span data-ttu-id="7b961-110">法规实施和罚款风险</span><span class="sxs-lookup"><span data-stu-id="7b961-110">Regulatory enforcement and the risk of fines</span></span>

<span data-ttu-id="7b961-111">在某些组织中，IT 支持与合规性管理组之间可能存在的职责分离。</span><span class="sxs-lookup"><span data-stu-id="7b961-111">In some organizations, there may be a separation of duties between IT support and the compliance management group.</span></span> <span data-ttu-id="7b961-112">Microsoft 365 支持通信合规性配置和扫描通信策略配置的分离。</span><span class="sxs-lookup"><span data-stu-id="7b961-112">Microsoft 365 supports the separation between communication compliance configuration and the configuration of policies for scanning communications.</span></span> <span data-ttu-id="7b961-113">例如，组织的 IT 组可能负责设置角色权限和组，以支持由组织的合规性团队配置和管理的通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="7b961-113">For example, the IT group for an organization may be responsible for setting up role permissions and groups to support communication compliance policies configured and managed by the organization's compliance team.</span></span>

## <a name="scenarios-for-communication-compliance"></a><span data-ttu-id="7b961-114">通信合规性方案</span><span class="sxs-lookup"><span data-stu-id="7b961-114">Scenarios for communication compliance</span></span>

<span data-ttu-id="7b961-115">通信合规性策略可协助在几个重要的合规性领域中查看组织中的邮件：</span><span class="sxs-lookup"><span data-stu-id="7b961-115">Communication compliance policies can assist with reviewing messages in your organization in several important compliance areas:</span></span>

- <span data-ttu-id="7b961-116">**公司策略**</span><span class="sxs-lookup"><span data-stu-id="7b961-116">**Corporate policies**</span></span>

    <span data-ttu-id="7b961-117">员工必须遵守其所有与业务相关的通信中的可接受使用、道德标准和其他公司政策。</span><span class="sxs-lookup"><span data-stu-id="7b961-117">Employees must comply with acceptable use, ethical standards, and other corporate policies in all their business-related communications.</span></span> <span data-ttu-id="7b961-118">通信合规性策略可以检测策略匹配，并帮助您采取纠正措施来帮助缓解这些类型的事件。</span><span class="sxs-lookup"><span data-stu-id="7b961-118">Communication compliance policies can detect policy matches and help you take corrective actions to help mitigate these types of incidents.</span></span> <span data-ttu-id="7b961-119">例如，您可以扫描组织中的员工通信，以查找潜在的人为资源问题，如骚扰或使用不当或攻击性的语言。</span><span class="sxs-lookup"><span data-stu-id="7b961-119">For example, you could scan employee communications in your organization for potential human resources concerns such as harassment or the use of inappropriate or offensive language.</span></span>

- <span data-ttu-id="7b961-120">**风险管理**</span><span class="sxs-lookup"><span data-stu-id="7b961-120">**Risk management**</span></span>

    <span data-ttu-id="7b961-121">组织负责在其基础结构和公司网络系统中分布的所有通信。</span><span class="sxs-lookup"><span data-stu-id="7b961-121">Organizations are responsible to all communications distributed throughout their infrastructure and corporate network systems.</span></span> <span data-ttu-id="7b961-122">使用通信监督策略来帮助确定和管理潜在的法律暴露和风险，可帮助最大限度地减少风险，然后才会损坏公司运营。</span><span class="sxs-lookup"><span data-stu-id="7b961-122">Using communications supervision policies to help identify and manage potential legal exposure and risk can help minimize risks before they can damage corporate operations.</span></span> <span data-ttu-id="7b961-123">例如，您可以扫描组织中的邮件，以获取有关机密项目的未经授权的通信，例如即将进行的收购、合并、收益披露、reorganizations 或领导团队更改。</span><span class="sxs-lookup"><span data-stu-id="7b961-123">For example, you could scan messages in your organization for unauthorized communications about confidential projects such as upcoming acquisitions, mergers, earnings disclosures, reorganizations, or leadership team changes.</span></span>

- <span data-ttu-id="7b961-124">**合规性**</span><span class="sxs-lookup"><span data-stu-id="7b961-124">**Regulatory compliance**</span></span>

    <span data-ttu-id="7b961-125">大多数组织必须符合其正常操作过程中的某些类型的法规遵从性标准。</span><span class="sxs-lookup"><span data-stu-id="7b961-125">Most organizations must comply with some type of regulatory compliance standards as part of their normal operating procedures.</span></span> <span data-ttu-id="7b961-126">这些法规通常要求组织为适合其行业的邮件服务实施某种类型的监督或监督过程。</span><span class="sxs-lookup"><span data-stu-id="7b961-126">These regulations often require organizations to implement some type of supervisory or oversight process for messaging that is appropriate for their industry.</span></span> <span data-ttu-id="7b961-127">金融行业规章颁发机构（FINRA）规则3110是一个很好的示例，它是组织实施监督过程以扫描员工通信以及它所参与的企业类型的一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="7b961-127">The Financial Industry Regulatory Authority (FINRA) Rule 3110 is a good example of a requirement for organizations to have supervisory procedures in place to scan employee communications and the types of businesses in which it engages.</span></span> <span data-ttu-id="7b961-128">另一个示例可能是查看组织中的经纪人通信以防止潜在的金钱 laundering、内幕交易、collusion 或 bribery 活动的需要。</span><span class="sxs-lookup"><span data-stu-id="7b961-128">Another example may be a need to review broker-dealer communications in your organization to safeguard against potential money laundering, insider trading, collusion, or bribery activities.</span></span> <span data-ttu-id="7b961-129">通过提供扫描和报告公司通信的过程，通信合规性策略可以帮助您的组织满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="7b961-129">Communication compliance policies can help your organization meet these requirements by providing a process to both scan and report on corporate communications.</span></span>

## <a name="new-enhancements"></a><span data-ttu-id="7b961-130">新的增强功能</span><span class="sxs-lookup"><span data-stu-id="7b961-130">New enhancements</span></span>

<span data-ttu-id="7b961-131">Microsoft 365 中的通信合规性建立在[Office 365 中的监督策略](supervision-policies.md)功能之上，具有以下几项新的增强功能：</span><span class="sxs-lookup"><span data-stu-id="7b961-131">Communication compliance in Microsoft 365 builds on the features of [Supervision policies in Office 365](supervision-policies.md) with several new enhancements:</span></span>

- <span data-ttu-id="7b961-132">智能可自定义模板</span><span class="sxs-lookup"><span data-stu-id="7b961-132">Intelligent customizable templates</span></span>
- <span data-ttu-id="7b961-133">灵活的补救工作流</span><span class="sxs-lookup"><span data-stu-id="7b961-133">Flexible remediation workflows</span></span>
- <span data-ttu-id="7b961-134">可操作的见解</span><span class="sxs-lookup"><span data-stu-id="7b961-134">Actionable insights</span></span>

![通信合规性主页](media/communication-compliance-home.png)

### <a name="intelligent-customizable-templates"></a><span data-ttu-id="7b961-136">智能可自定义模板</span><span class="sxs-lookup"><span data-stu-id="7b961-136">Intelligent customizable templates</span></span>

<span data-ttu-id="7b961-137">通过通信合规性的智能可自定义模板，您可以应用机器学习，以智能化检测组织中的通信冲突。</span><span class="sxs-lookup"><span data-stu-id="7b961-137">Intelligent customizable templates in communication compliance allow you to apply machine learning to intelligently detect communication violations in your organization.</span></span>

- <span data-ttu-id="7b961-138">**可自定义的预先配置的模板**：新的策略模板可帮助解决最常见的通信风险。</span><span class="sxs-lookup"><span data-stu-id="7b961-138">**Customizable pre-configured templates**: New policy templates help address the most common communications risks.</span></span> <span data-ttu-id="7b961-139">使用预定义的反骚扰和攻击性语言、敏感信息和法规遵从性模板，现在可以更快地创建初始策略和后续更新。</span><span class="sxs-lookup"><span data-stu-id="7b961-139">Initial policy creation and follow-on updating are now quicker with pre-defined anti-harassment and offensive language, sensitive information, and regulatory compliance templates.</span></span>
- <span data-ttu-id="7b961-140">**新机器学习支持**：内置威胁、骚扰和猥亵语言[分类](classifier-getting-started-with.md)程序有助于减少扫描邮件中的误报，并在调查和修正过程中保存审阅者时间。</span><span class="sxs-lookup"><span data-stu-id="7b961-140">**New machine learning support**: Built-in threat, harassment, and profanity [classifiers](classifier-getting-started-with.md) help reduce false positives in scanned messages, saving reviewers time during the investigation and remediation process.</span></span>
- <span data-ttu-id="7b961-141">**改进了条件生成器**：配置策略条件现已简化为策略向导中的单个集成体验，减少了如何对策略应用条件的混淆。</span><span class="sxs-lookup"><span data-stu-id="7b961-141">**Improved condition builder**: Configuring policy conditions is now streamlined into a single, integrated experience in the policy wizard, reducing confusion in how conditions are applied for policies.</span></span>

### <a name="flexible-remediation-workflows"></a><span data-ttu-id="7b961-142">灵活的补救工作流</span><span class="sxs-lookup"><span data-stu-id="7b961-142">Flexible remediation workflows</span></span>

<span data-ttu-id="7b961-143">利用内置的补救工作流，可以快速识别组织中具有策略匹配项的邮件并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="7b961-143">Built-in remediation workflows allow you to quickly identify and take action on messages with policy matches in your organization.</span></span> <span data-ttu-id="7b961-144">以下新功能提高了调查和补救活动的效率：</span><span class="sxs-lookup"><span data-stu-id="7b961-144">The following new features increase efficiency for investigation and remediation activities:</span></span>

- <span data-ttu-id="7b961-145">**灵活修正工作流**：新的修正工作流可帮助您快速对策略匹配采取措施，包括将邮件升级到其他审阅者的新选项以及向具有策略匹配的用户发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7b961-145">**Flexible remediation workflow**: New remediation workflow helps you quickly take action on policy matches, including new options to escalate messages to other reviewers and to send email notifications to users with policy matches.</span></span>
- <span data-ttu-id="7b961-146">**对话线程**：邮件现在以直观方式按原始邮件和所有关联的答复邮件进行分组，从而在调查和修正操作过程中获得更好的上下文。</span><span class="sxs-lookup"><span data-stu-id="7b961-146">**Conversation threading**: Messages are now visually grouped by original message and all associated reply messages, giving you better context during investigation and remediation actions.</span></span>
- <span data-ttu-id="7b961-147">**关键字突出显示**：术语匹配策略条件在邮件文本视图中突出显示，以帮助审阅者快速查找和修正策略通知。</span><span class="sxs-lookup"><span data-stu-id="7b961-147">**Keyword highlighting**: Terms matching policy conditions are highlighted in the message text view to help reviewers quickly locate and remediate policy alerts.</span></span>
- <span data-ttu-id="7b961-148">**确切的和接近的重复检测**：除了扫描匹配通信合规性策略的确切术语，临近的重复检测也会对以文字为依据的术语和消息进行分组，以帮助加快审阅过程。</span><span class="sxs-lookup"><span data-stu-id="7b961-148">**Exact and near duplicate detection**: In addition to scanning for exact terms matching communication compliance policies, near duplicate detection groups textually similar terms and messages together to help speed up your review process.</span></span>
- <span data-ttu-id="7b961-149">**新筛选器**：使用多个字段（包括发件人、收件人、日期、域等）的邮件筛选器更快地调查和修正策略警报。</span><span class="sxs-lookup"><span data-stu-id="7b961-149">**New filters**: Investigate and remediate policy alerts faster with message filters for several fields, including sender, recipient, date, domains, and many more.</span></span>
- <span data-ttu-id="7b961-150">**改进的邮件视图**：现在，使用新的邮件源、文本和批注视图，调查和修正操作的速度更快。</span><span class="sxs-lookup"><span data-stu-id="7b961-150">**Improved message views**: Investigation and remediation actions are now quicker with new message source, text, and annotation views.</span></span> <span data-ttu-id="7b961-151">现在可以查看邮件附件，以便在采取补救措施时提供完整的上下文。</span><span class="sxs-lookup"><span data-stu-id="7b961-151">Message attachments are now viewable to provide complete context when taking remediation actions.</span></span>
- <span data-ttu-id="7b961-152">**用户历史记录视图**：所有用户邮件修正活动（如过去的策略匹配通知和升级）的历史视图现在为审阅者提供了修正工作流过程中更多上下文的审阅者。</span><span class="sxs-lookup"><span data-stu-id="7b961-152">**User history view**: Historical view of all user message remediation activities, such as past notifications and escalations for policy matches, now provides reviewers with more context during the remediation workflow process.</span></span> <span data-ttu-id="7b961-153">对用户的策略匹配的首次或重复实例现已存档，可轻松查看。</span><span class="sxs-lookup"><span data-stu-id="7b961-153">First-time or repeat instances of policy matches for users are now archived and easily viewable.</span></span>

### <a name="actionable-insights"></a><span data-ttu-id="7b961-154">可操作的见解</span><span class="sxs-lookup"><span data-stu-id="7b961-154">Actionable insights</span></span>

<span data-ttu-id="7b961-155">新的用于通知、策略匹配、操作和趋势的交互仪表板可帮助您快速查看组织中的挂起和已解决通知的状态。</span><span class="sxs-lookup"><span data-stu-id="7b961-155">New interactive dashboards for alerts, policy matches, actions, and trends help you quickly view the status of pending and resolved alerts in your organization.</span></span>

- <span data-ttu-id="7b961-156">**主动预防性智能警报**：需要立即关注的策略匹配警报包括按严重性排序的新仪表板和发送给指定审阅者的新自动电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7b961-156">**Proactive intelligent alerts**: Alerts for policy matches requiring immediate attention include new dashboards for pending items sorted by severity and new automatic email notifications sent to designated reviewers.</span></span>
- <span data-ttu-id="7b961-157">**交互仪表板**：新仪表板显示策略匹配、挂起和解决的操作，以及用户和策略的趋势。</span><span class="sxs-lookup"><span data-stu-id="7b961-157">**Interactive dashboards**: New dashboards display policy matches, pending and resolved actions, and trends by users and policy.</span></span>
- <span data-ttu-id="7b961-158">**审核支持**：可以轻松地从 Microsoft 365 合规性中心导出策略和审查活动的完整日志，以帮助支持审核审阅请求。</span><span class="sxs-lookup"><span data-stu-id="7b961-158">**Auditing support**: A full log of policy and review activities is easily exported from the Microsoft 365 compliance center to help support audit review requests.</span></span>

## <a name="integration-with-microsoft-365-services"></a><span data-ttu-id="7b961-159">与 Microsoft 365 服务集成</span><span class="sxs-lookup"><span data-stu-id="7b961-159">Integration with Microsoft 365 services</span></span>

<span data-ttu-id="7b961-160">通信合规性策略跨多个通信通道扫描和捕获邮件，以帮助您快速查看和修正合规性问题：</span><span class="sxs-lookup"><span data-stu-id="7b961-160">Communication compliance policies scan and capture messages across several communication channels to help you quickly review and remediate compliance issues:</span></span>

- <span data-ttu-id="7b961-161">**Microsoft 团队**：针对公共和私有[microsoft 团队](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)频道和个人聊天的聊天通信和相关附件在通信合规性中支持作为独立频道源或其他 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="7b961-161">**Microsoft Teams**: Chat communications and associated attachments for public and private [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) channels and individual chats are supported in communication compliance as a standalone channel source or with other Microsoft 365 services.</span></span> <span data-ttu-id="7b961-162">现在，策略将自动扫描策略中定义的特定用户的所有 Microsoft 团队频道和团队，从而无需为 Microsoft 工作组工作分配保留单独的映射列表。</span><span class="sxs-lookup"><span data-stu-id="7b961-162">Policies now automatically scan all Microsoft Teams channels and teams for specific users defined in a policy, eliminating the need to keep a separate mapping list for Microsoft Teams assignments.</span></span>
- <span data-ttu-id="7b961-163">**Exchange online**：在 Microsoft 365 组织中的[exchange online](https://docs.microsoft.com/Exchange/exchange-online)上托管的所有邮箱都符合扫描条件。</span><span class="sxs-lookup"><span data-stu-id="7b961-163">**Exchange Online**: All mailboxes hosted on [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) in your Microsoft 365 organization are eligible for scanning.</span></span> <span data-ttu-id="7b961-164">与通信合规性策略条件匹配的电子邮件和附件可立即用于监视和监控报告。</span><span class="sxs-lookup"><span data-stu-id="7b961-164">Emails and attachments matching communication compliance policy conditions are instantly available for monitoring and in supervision reports.</span></span> <span data-ttu-id="7b961-165">Exchange Online 现在是一个可选的源通道，并且在通信合规性策略中不再需要。</span><span class="sxs-lookup"><span data-stu-id="7b961-165">Exchange Online is now an optional source channel and is no longer required in communication compliance policies.</span></span>
- <span data-ttu-id="7b961-166">**Skype For Business online**：通信合规性策略支持在[Skype for business Online](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)中扫描聊天通信和关联的附件。</span><span class="sxs-lookup"><span data-stu-id="7b961-166">**Skype for Business Online**: Communication compliance policies support scanning chat communications and associated attachments in [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online).</span></span>
- <span data-ttu-id="7b961-167">**第三方来源**：您可以从[第三方来源](archiving-third-party-data.md)扫描邮件，以获取在 Microsoft 365 组织中导入到邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="7b961-167">**Third-party sources**: You can scan messages from [third-party sources](archiving-third-party-data.md) for data imported into mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="7b961-168">通信合规性支持与几个流行平台（包括即时 Bloomberg、Facebook、Twitter 和其他平台）的连接。</span><span class="sxs-lookup"><span data-stu-id="7b961-168">Communication compliance supports connections to several popular platforms, including Instant Bloomberg, Facebook, Twitter, and others.</span></span>

<span data-ttu-id="7b961-169">若要了解有关通信合规性策略中的邮件传递通道支持的详细信息，请参阅[支持的通信类型](communication-compliance-feature-reference.md#supported-communication-types)。</span><span class="sxs-lookup"><span data-stu-id="7b961-169">To learn more about messaging channel support in communication compliance policies, see [supported communication types](communication-compliance-feature-reference.md#supported-communication-types).</span></span>

## <a name="workflow"></a><span data-ttu-id="7b961-170">工作流</span><span class="sxs-lookup"><span data-stu-id="7b961-170">Workflow</span></span>

<span data-ttu-id="7b961-171">通信合规性帮助您解决与遵守内部策略和法规遵从性要求相关的常见痛点。</span><span class="sxs-lookup"><span data-stu-id="7b961-171">Communication compliance helps you address common pain points associated with complying with internal policies and regulatory compliance requirements.</span></span> <span data-ttu-id="7b961-172">使用集中式策略模板和灵活的工作流，您可以使用可操作的见解快速解决检测到的合规性问题。</span><span class="sxs-lookup"><span data-stu-id="7b961-172">With focused policy templates and a flexible workflow, you can use actionable insights to quickly resolve detected compliance issues.</span></span>

<span data-ttu-id="7b961-173">通过 Microsoft 365 中的通信合规性确定和解决合规性问题，请使用以下工作流：</span><span class="sxs-lookup"><span data-stu-id="7b961-173">Identifying and resolving compliance issues with communication compliance in Microsoft 365 uses the following workflow:</span></span>

![通信合规性工作流](media/communication-compliance-workflow.png)

### <a name="configure"></a><span data-ttu-id="7b961-175">配置</span><span class="sxs-lookup"><span data-stu-id="7b961-175">Configure</span></span>

<span data-ttu-id="7b961-176">在此工作流步骤中，您可以确定合规性要求并配置适用的通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="7b961-176">In this workflow step, you identify your compliance requirements and configure applicable communication compliance policies.</span></span> <span data-ttu-id="7b961-177">策略模板是一种很好的方法，不仅可以快速配置新的符合性策略，还可以在要求发生变化时快速修改和更新策略。</span><span class="sxs-lookup"><span data-stu-id="7b961-177">Policy templates are a great way to not only quickly configure a new compliance policy, but to also quickly modify and update policies as your requirements change.</span></span> <span data-ttu-id="7b961-178">例如，在为组织中的所有用户配置策略之前，您可能需要为一小部分用户在通信中快速测试针对冒犯性语言和反骚扰的策略。</span><span class="sxs-lookup"><span data-stu-id="7b961-178">For example, you may want to quickly test a policy for offensive language and anti-harassment on communications for a small group of users before configuring a policy for all users in your organization.</span></span>

<span data-ttu-id="7b961-179">您可以从 Microsoft 365 合规性中心的以下策略模板中进行选择：</span><span class="sxs-lookup"><span data-stu-id="7b961-179">You can choose from the following policy templates in the Microsoft 365 compliance center:</span></span>

- <span data-ttu-id="7b961-180">**冒犯性语言和反骚扰**：使用此模板可以快速创建使用内置分类器的策略，以自动检测可能被视为滥用或攻击性的内容。</span><span class="sxs-lookup"><span data-stu-id="7b961-180">**Offensive language and anti-harassment**: Use this template to quickly create a policy that uses the built-in classifier to automatically detect content that may be considered abusive or offensive.</span></span>
- <span data-ttu-id="7b961-181">**敏感信息**：使用此模板创建用于扫描包含定义的敏感信息类型或关键字的通信的策略，以帮助确保重要数据不与不应访问的用户共享。</span><span class="sxs-lookup"><span data-stu-id="7b961-181">**Sensitive information**: Use this template to create a policy to scan communications containing defined sensitive information types or keywords to help make sure that important data isn't shared with people that shouldn't have access.</span></span>
- <span data-ttu-id="7b961-182">**法规遵从性**：使用此模板创建策略以扫描通信，以查找与法规标准相关联的标准财务术语的参考。</span><span class="sxs-lookup"><span data-stu-id="7b961-182">**Regulatory compliance**: Use this template to create a policy to scan communications for references to standard financial terms associated with regulatory standards.</span></span>
- <span data-ttu-id="7b961-183">**自定义策略**：使用此模板可配置特定通信通道、各个检测条件以及在组织中要查看的内容量。</span><span class="sxs-lookup"><span data-stu-id="7b961-183">**Custom policy**: Use this template to configure specific communication channels, individual detection conditions, and the amount of content to review for supervision in your organization.</span></span>

### <a name="investigate"></a><span data-ttu-id="7b961-184">调查</span><span class="sxs-lookup"><span data-stu-id="7b961-184">Investigate</span></span>

<span data-ttu-id="7b961-185">在此步骤中，您将更深入地了解检测到与通信合规性策略相匹配的问题。</span><span class="sxs-lookup"><span data-stu-id="7b961-185">In this step, you look deeper into the issues detected as matching your communication compliance policies.</span></span> <span data-ttu-id="7b961-186">此步骤包括 Microsoft 365 合规性中心中提供的以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b961-186">This step includes the following actions available in the Microsoft 365 compliance center:</span></span>

- <span data-ttu-id="7b961-187">**警报**：当邮件符合监督策略时，将自动生成警报。</span><span class="sxs-lookup"><span data-stu-id="7b961-187">**Alerts**: When a message matches a supervision policy, an alert is automatically generated.</span></span> <span data-ttu-id="7b961-188">对于每个警报，您都可以看到状态、严重性、检测到的时间，以及是否分配了事例以及其状态。</span><span class="sxs-lookup"><span data-stu-id="7b961-188">For each alert, you can see the status, the severity, the time detected, and if a case is assigned and its status.</span></span> <span data-ttu-id="7b961-189">新警报显示在通信合规性主页和 "**警报**" 页面上，并按严重性顺序列出。</span><span class="sxs-lookup"><span data-stu-id="7b961-189">New alerts are displayed on the communication compliance home page and the **Alerts** page and are listed in order of severity.</span></span>
- <span data-ttu-id="7b961-190">**问题管理**：对于每个通知，您都可以采取调查操作来帮助修正邮件中检测到的问题</span><span class="sxs-lookup"><span data-stu-id="7b961-190">**Issue management**: For each alert, you can take investigative actions to help remediate the issue detected in the message</span></span>
- <span data-ttu-id="7b961-191">**文档审阅**：在调查问题期间，您可以使用邮件的多个视图来帮助正确评估检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="7b961-191">**Document review**: During the investigation of an issue, you can use several views of the message to help properly evaluate the detected issue.</span></span> <span data-ttu-id="7b961-192">这些视图包括对话摘要、仅文本、已批注和通信对话的详细信息视图。</span><span class="sxs-lookup"><span data-stu-id="7b961-192">The views include a conversation summary, text-only, annotated, and detail views of the communication conversation.</span></span>
- <span data-ttu-id="7b961-193">查看**用户活动历史记录**：查看策略匹配的用户邮件活动和更正操作（如过去的通知和升级）的历史记录。</span><span class="sxs-lookup"><span data-stu-id="7b961-193">**Reviewing user activity history**: View the history of user message activities and remediation actions, such as past notifications and escalations, for policy matches.</span></span>
- <span data-ttu-id="7b961-194">**筛选器**：使用筛选器（如发件人、收件人、日期和主题）快速缩小要审阅的邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7b961-194">**Filters**: Use filters such as sender, recipient, date, and subject to quickly narrow down the message alerts that you want to review.</span></span>

### <a name="remediate"></a><span data-ttu-id="7b961-195">修正</span><span class="sxs-lookup"><span data-stu-id="7b961-195">Remediate</span></span>

<span data-ttu-id="7b961-196">下一步是使用以下选项修正已调查的通信合规性问题：</span><span class="sxs-lookup"><span data-stu-id="7b961-196">The next step is to remediate communication compliance issues you've investigated using the following options:</span></span>

- <span data-ttu-id="7b961-197">**解决**方法：查看问题后，可以通过解析警报进行修正。</span><span class="sxs-lookup"><span data-stu-id="7b961-197">**Resolve**: After reviewing an issue, you can remediate by resolving the alert.</span></span> <span data-ttu-id="7b961-198">解析警报会将其从待处理的警报队列中删除，并将操作保留为匹配策略的已解析队列中的条目。</span><span class="sxs-lookup"><span data-stu-id="7b961-198">Resolving an alert removes it from the pending alert queue, and the action is preserved as an entry in the Resolved queue for the matching policy.</span></span> <span data-ttu-id="7b961-199">在将警报标记为误报、向员工发送有关通知的通知或打开警报的新事例之后，将自动解决通知。</span><span class="sxs-lookup"><span data-stu-id="7b961-199">Alerts are automatically resolved after marking the alert as a false positive, sending a notice to an employee about the alert, or opening a new case for the alert.</span></span>
- <span data-ttu-id="7b961-200">**标记邮件**：作为问题解决的一部分，您可以将检测到的邮件标记为兼容性、不符合条件或可疑之处，因为它与组织的策略和标准相关。</span><span class="sxs-lookup"><span data-stu-id="7b961-200">**Tag a message**: As part of the resolution of an issue, you can tag the detected message as compliant, non-compliant, or as questionable as it relates to the policies and standards for your organization.</span></span> <span data-ttu-id="7b961-201">标记可帮助您微筛选策略警报以进行升级或作为其他内部审核流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b961-201">Tagging can help you micro-filter policy alerts for escalations or as part of other internal review processes.</span></span>
- <span data-ttu-id="7b961-202">**通知用户**：通常，用户意外或无意地违反通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="7b961-202">**Notify the user**: Often, users accidentally or inadvertently violate a communication compliance policy.</span></span> <span data-ttu-id="7b961-203">您可以使用通知功能向用户提供警告通知并解决问题。</span><span class="sxs-lookup"><span data-stu-id="7b961-203">You can use the notify feature to provide a warning notice to the user and to resolve the issue.</span></span>
- <span data-ttu-id="7b961-204">**升级到另一个审阅者**：有时，问题的最初审阅者需要从其他审阅者处进行输入，以帮助解决事件。</span><span class="sxs-lookup"><span data-stu-id="7b961-204">**Escalate to another reviewer**: Sometimes, the initial reviewer of an issue needs input from other reviewers to help resolve the incident.</span></span> <span data-ttu-id="7b961-205">您可以轻松地将邮件问题提升到组织其他区域中的审阅者，作为解决过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b961-205">You can easily escalate message issues to reviewers in other areas of your organization as part of the resolution process.</span></span>
- <span data-ttu-id="7b961-206">**标记为误报**：在符合性策略的匹配项中，错误地检测到邮件将偶尔遍历到审阅过程。</span><span class="sxs-lookup"><span data-stu-id="7b961-206">**Mark as a false positive**: Messages incorrectly detected as matches of compliance policies will occasionally slip through to the review process.</span></span> <span data-ttu-id="7b961-207">您可以将这些类型的警报标记为误报并自动解决问题。</span><span class="sxs-lookup"><span data-stu-id="7b961-207">You can mark these types of alerts as false positives and automatically resolve the issue.</span></span>

### <a name="monitor"></a><span data-ttu-id="7b961-208">监视</span><span class="sxs-lookup"><span data-stu-id="7b961-208">Monitor</span></span>

<span data-ttu-id="7b961-209">跟踪和管理由通信合规性策略标识的合规性问题跨整个工作流过程。</span><span class="sxs-lookup"><span data-stu-id="7b961-209">Keeping track and managing compliance issues identified by communication compliance policies spans the entire workflow process.</span></span> <span data-ttu-id="7b961-210">在生成警报并实施调查和修正操作后，现有策略可能需要审阅和更新，并且可能需要创建新策略。</span><span class="sxs-lookup"><span data-stu-id="7b961-210">As alerts are generated and investigation and remediation actions are implemented, existing policies may need review and updates, and new policies may need to be created.</span></span>

- <span data-ttu-id="7b961-211">**监视和报告**：使用在统一 Office 365 审核日志中记录的通信合规性仪表板、报告、导出日志和事件，以不断评估和改进您的合规性状况。</span><span class="sxs-lookup"><span data-stu-id="7b961-211">**Monitor and report**: Use communication compliance dashboards, reports, export logs, and events recorded in the unified Office 365 audit logs to continually evaluate and improve your compliance posture.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="7b961-212">准备好开始了吗？</span><span class="sxs-lookup"><span data-stu-id="7b961-212">Ready to get started?</span></span>

<span data-ttu-id="7b961-213">若要为 Microsoft 365 组织配置通信合规性，请参阅[configure communication 合规性 For microsoft 365 （预览）](communication-compliance-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="7b961-213">To configure communication compliance for your Microsoft 365 organization, see [Configure communication compliance for Microsoft 365 (preview)](communication-compliance-configure.md).</span></span>