---
title: 使用就绪分类器（预览）
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 提供了可用于在组织中标识和标记内容的计算机学习分类器的准备工作。 本主题介绍如何准备好使用类元的准备工作。
ms.openlocfilehash: 7e10bb94f84dd10a1ac22126106531d8ad309c47
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633851"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="f99e9-104">使用就绪分类器（预览）</span><span class="sxs-lookup"><span data-stu-id="f99e9-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="f99e9-105">Microsoft 已通过大量的示例数据集进行了培训和测试了大量分类程序，这有助于确定特定的内容类别。</span><span class="sxs-lookup"><span data-stu-id="f99e9-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="f99e9-106">请参阅[trainable 分类器的入门（预览）](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="f99e9-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="f99e9-107">默认情况下， `Ready to use`这些分类器显示在组中。</span><span class="sxs-lookup"><span data-stu-id="f99e9-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="f99e9-108">**冒犯性语言**：检测包含 profanities、slurs、taunts 和伪装的表达式的文本项（这是与更具冒犯性的术语具有相同意义的表达式）。</span><span class="sxs-lookup"><span data-stu-id="f99e9-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="f99e9-109">**恢复**：检测作为申请人个人、教育、专业资格、工作经验以及其他个人标识信息的文本帐户的项目。</span><span class="sxs-lookup"><span data-stu-id="f99e9-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="f99e9-110">**SourceCode**：检测包含一组用广泛使用的计算机编程语言编写的指令和语句的项。</span><span class="sxs-lookup"><span data-stu-id="f99e9-110">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="f99e9-111">**骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、民族、性别、色情方向、年龄、残疾。</span><span class="sxs-lookup"><span data-stu-id="f99e9-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="f99e9-112">**猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别。</span><span class="sxs-lookup"><span data-stu-id="f99e9-112">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="f99e9-113">**威胁**：检测与威胁相关的冒犯性语言文本项的特定类别，以提交暴力或对人员或财产造成物理伤害或损坏。</span><span class="sxs-lookup"><span data-stu-id="f99e9-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="f99e9-114">在使用准备就绪以在分类和标记工作流中使用分类器之前，应根据您认为适合类别的组织内容示例对其进行测试，以验证其分类预测是否符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="f99e9-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f99e9-115">请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本，但并不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="f99e9-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text and are not exhaustive or complete.</span></span> <span data-ttu-id="f99e9-116">此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类符的权利。</span><span class="sxs-lookup"><span data-stu-id="f99e9-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers at its discretion.</span></span> <span data-ttu-id="f99e9-117">虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不打算提供组织的唯一方法来监视或响应使用此类语言。</span><span class="sxs-lookup"><span data-stu-id="f99e9-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="f99e9-118">您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="f99e9-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal, and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="f99e9-119">如何准备和使用分类器准备就绪</span><span class="sxs-lookup"><span data-stu-id="f99e9-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="f99e9-120">收集您认为属于已准备好使用分类器的类别（正匹配）和您要测试的类别中不应包括的（负匹配）的 "可释放测试内容" 项。</span><span class="sxs-lookup"><span data-stu-id="f99e9-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f99e9-121">示例项目不能加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="f99e9-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="f99e9-122">创建专用的 SharePoint Online 文件夹;至少等待1小时，将文件夹添加到搜索索引中。</span><span class="sxs-lookup"><span data-stu-id="f99e9-122">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="f99e9-123">请记下文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="f99e9-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="f99e9-124">使用合规性管理员或安全管理员角色访问权限登录 microsoft 365 合规性中心，并打开**microsoft 365 合规性中心**或**microsoft 365 安全中心** > **记录管理（预览）** > "**标签策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f99e9-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="f99e9-125">选择`Auto-apply a label`。</span><span class="sxs-lookup"><span data-stu-id="f99e9-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="f99e9-126">选择`Choose a label to auto-apply`。</span><span class="sxs-lookup"><span data-stu-id="f99e9-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="f99e9-127">选择`Create new labels`并创建一个标签，以便在此测试中直接使用。</span><span class="sxs-lookup"><span data-stu-id="f99e9-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="f99e9-128">执行此操作时，请`Retention`将设置为 "关闭"。</span><span class="sxs-lookup"><span data-stu-id="f99e9-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="f99e9-129">您不希望启用任何保留或其他操作。</span><span class="sxs-lookup"><span data-stu-id="f99e9-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="f99e9-130">在这种情况下，您将使用保留标签，只是将其用作文本标签，而不会强制执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f99e9-130">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="f99e9-131">例如，您可以创建一个名为 "SourceCode 分类程序测试" 的保留标签，无操作，然后将该保留标签自动应用于将源代码分类器作为条件的内容。</span><span class="sxs-lookup"><span data-stu-id="f99e9-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="f99e9-132">若要了解有关创建保留标签的详细信息，请参阅[保留标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="f99e9-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="f99e9-133">依次`Auto-apply a label` `Choose a label to auto-apply`选择 "" 和 ""。</span><span class="sxs-lookup"><span data-stu-id="f99e9-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="f99e9-134">若要了解有关使用基于条件的自动应用标签的详细信息，请参阅[根据条件自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)。</span><span class="sxs-lookup"><span data-stu-id="f99e9-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="f99e9-135">从列表中选择您的测试标签， `Next`然后选择 ""。</span><span class="sxs-lookup"><span data-stu-id="f99e9-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="f99e9-136">选择`Apply label to content that matches a trainable classifier`。</span><span class="sxs-lookup"><span data-stu-id="f99e9-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![选择类元作为条件](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="f99e9-138">.</span><span class="sxs-lookup"><span data-stu-id="f99e9-138"></span></span>

10. <span data-ttu-id="f99e9-139">从列表中选择分类程序，在此示例中`Source Code`</span><span class="sxs-lookup"><span data-stu-id="f99e9-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="f99e9-140">对策略进行命名，例如 "源代码已准备好使用分类程序测试"。</span><span class="sxs-lookup"><span data-stu-id="f99e9-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="f99e9-141">选择`Let me choose specific locations`。</span><span class="sxs-lookup"><span data-stu-id="f99e9-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="f99e9-142">关闭除和选择`SharePoint sites` `Choose sites`之外的所有位置。</span><span class="sxs-lookup"><span data-stu-id="f99e9-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="f99e9-143">输入步骤2中的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="f99e9-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="f99e9-144">完成向导并选择`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="f99e9-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="f99e9-145">将测试项放入专用的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f99e9-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="f99e9-146">为应用标签留一个小时。</span><span class="sxs-lookup"><span data-stu-id="f99e9-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="f99e9-147">检查标签文档的属性以查看分类器是否包含并排除了您所需的测试内容。</span><span class="sxs-lookup"><span data-stu-id="f99e9-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="f99e9-148">查看标记的项目。</span><span class="sxs-lookup"><span data-stu-id="f99e9-148">Review the items that were labeled.</span></span>

20. <span data-ttu-id="f99e9-149">如果你已完成测试，请删除内容和标签策略。</span><span class="sxs-lookup"><span data-stu-id="f99e9-149">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="f99e9-150">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="f99e9-150">See also:</span></span>

- [<span data-ttu-id="f99e9-151">可训练分类器入门（预览）</span><span class="sxs-lookup"><span data-stu-id="f99e9-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="f99e9-152">保留标签概述</span><span class="sxs-lookup"><span data-stu-id="f99e9-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="f99e9-153">根据条件自动应用保留标签策略</span><span class="sxs-lookup"><span data-stu-id="f99e9-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)