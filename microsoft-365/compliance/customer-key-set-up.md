---
title: 设置适用于 Office 的客户密钥365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何为 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件设置适用于 Office 365 的客户密钥。
ms.openlocfilehash: a57fb5ee7eea1746a50ec0fb1e2c3e84495b4f2c
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804759"
---
# <a name="set-up-customer-key-for-office-365"></a><span data-ttu-id="c09c1-103">设置适用于 Office 的客户密钥365</span><span class="sxs-lookup"><span data-stu-id="c09c1-103">Set up Customer Key for Office 365</span></span>

<span data-ttu-id="c09c1-104">使用 "客户密钥"，可以控制组织的加密密钥，然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="c09c1-104">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="c09c1-105">换言之，客户密钥允许客户添加属于其密钥的加密层。</span><span class="sxs-lookup"><span data-stu-id="c09c1-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="c09c1-106">静态数据包含来自 Exchange Online 和 Skype for Business 的数据，这些数据存储在存储在 SharePoint Online 和 OneDrive for business 中的邮箱和文件中。</span><span class="sxs-lookup"><span data-stu-id="c09c1-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="c09c1-107">您必须先安装 Azure，然后才能使用适用于 Office 365 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="c09c1-108">本主题介绍了创建和配置所需 Azure 资源时需要遵循的步骤，然后提供在 Office 365 中设置客户密钥的步骤。</span><span class="sxs-lookup"><span data-stu-id="c09c1-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="c09c1-109">完成 Azure 安装后，确定要为组织中的邮箱和文件分配的策略，并因此确定哪些项。</span><span class="sxs-lookup"><span data-stu-id="c09c1-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="c09c1-110">未分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。</span><span class="sxs-lookup"><span data-stu-id="c09c1-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="c09c1-111">有关客户密钥的详细信息，或有关一般概述的详细信息，请参阅[Office 365 中的使用客户密钥的服务加密](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c09c1-112">强烈建议您遵循本主题中的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="c09c1-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="c09c1-113">这些信息称为**提示**和**重要**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="c09c1-114">通过 "客户密钥"，您可以控制其作用域与整个组织一样大的根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="c09c1-115">这意味着，使用这些密钥进行的错误可能会产生很大影响，并且可能会导致数据中断或无法挽回的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="c09c1-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="c09c1-116">设置客户密钥之前</span><span class="sxs-lookup"><span data-stu-id="c09c1-116">Before you set up Customer Key</span></span>

<span data-ttu-id="c09c1-117">在开始之前，请确保您有适合您的组织的许可。</span><span class="sxs-lookup"><span data-stu-id="c09c1-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="c09c1-118">Office 365 中的客户密钥在 Office 365 E5 或高级合规性 SKU 中提供。</span><span class="sxs-lookup"><span data-stu-id="c09c1-118">Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span> <span data-ttu-id="c09c1-119">若要了解本主题中的概念和过程，请参阅[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)文档。</span><span class="sxs-lookup"><span data-stu-id="c09c1-119">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="c09c1-120">此外，还应熟悉 Azure 中使用的术语（例如[租户](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))）。</span><span class="sxs-lookup"><span data-stu-id="c09c1-120">Also, become familiar with the terms used in Azure, for example, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).</span></span>

<span data-ttu-id="c09c1-121">FastTrack 仅用于收集用于注册客户密钥所需的租户和服务配置信息。</span><span class="sxs-lookup"><span data-stu-id="c09c1-121">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="c09c1-122">客户密钥提供通过 FastTrack 发布，以便您和我们的合作伙伴可以使用相同的方法提交所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c09c1-122">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="c09c1-123">FastTrack 还使您可以轻松地将提供的数据存档。</span><span class="sxs-lookup"><span data-stu-id="c09c1-123">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="c09c1-124">如果你需要文档之外的其他支持，请联系 Microsoft 咨询服务（MCS）、首要现场工程（PFE）或 Microsoft 合作伙伴以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="c09c1-124">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="c09c1-125">若要提供有关客户密钥的反馈（包括文档），请将你的想法、建议和观点发送到 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c09c1-125">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="c09c1-126">设置客户密钥的步骤概述</span><span class="sxs-lookup"><span data-stu-id="c09c1-126">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="c09c1-127">若要设置客户密钥，请按列出的顺序完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="c09c1-127">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="c09c1-128">本文的其余部分提供有关每个任务的详细说明，或链接到过程中每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c09c1-128">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="c09c1-129">**在 Azure 和 Microsoft FastTrack 中：**</span><span class="sxs-lookup"><span data-stu-id="c09c1-129">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="c09c1-130">你将通过远程连接到 Azure PowerShell 来完成大部分这些任务。</span><span class="sxs-lookup"><span data-stu-id="c09c1-130">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="c09c1-131">为获得最佳结果，请使用版本4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c09c1-131">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="c09c1-132">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="c09c1-132">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="c09c1-133">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="c09c1-133">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="c09c1-134">注册可能需要一到五个工作日的时间。</span><span class="sxs-lookup"><span data-stu-id="c09c1-134">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="c09c1-135">提交为激活 Office 365 的客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="c09c1-135">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="c09c1-136">创建了这两个新的 Azure 订阅后，您需要通过完成 Microsoft FastTrack 门户中承载的 web 表单来提交相应的客户密钥提供请求。</span><span class="sxs-lookup"><span data-stu-id="c09c1-136">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="c09c1-137">**FastTrack 团队不会向客户密钥提供帮助。Office 只是使用 FastTrack 门户来允许您提交表单并帮助我们跟踪客户密钥的相关优惠**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-137">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="c09c1-138">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="c09c1-138">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="c09c1-139">将权限分配给每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="c09c1-139">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="c09c1-140">启用然后确认密钥电子仓库上的软删除</span><span class="sxs-lookup"><span data-stu-id="c09c1-140">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="c09c1-141">通过创建或导入密钥将密钥添加到每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="c09c1-141">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="c09c1-142">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="c09c1-142">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="c09c1-143">备份 Azure 密钥存储库</span><span class="sxs-lookup"><span data-stu-id="c09c1-143">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="c09c1-144">验证 Azure Key Vault 配置设置</span><span class="sxs-lookup"><span data-stu-id="c09c1-144">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="c09c1-145">获取每个 Azure Key Vault 密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="c09c1-145">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="c09c1-146">**在 Office 365 中：**</span><span class="sxs-lookup"><span data-stu-id="c09c1-146">**In Office 365:**</span></span>
  
<span data-ttu-id="c09c1-147">Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="c09c1-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="c09c1-148">创建与 Exchange Online 和 Skype for Business 一起使用的数据加密策略（DEP）</span><span class="sxs-lookup"><span data-stu-id="c09c1-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="c09c1-149">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="c09c1-149">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="c09c1-150">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="c09c1-150">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="c09c1-151">SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="c09c1-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="c09c1-152">为每个 SharePoint Online 和 OneDrive for business 地域创建数据加密策略（DEP）</span><span class="sxs-lookup"><span data-stu-id="c09c1-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="c09c1-153">验证 SharePoint Online、OneDrive for Business 和团队文件的文件加密</span><span class="sxs-lookup"><span data-stu-id="c09c1-153">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="c09c1-154">在 Azure Key Vault 和 Microsoft FastTrack 中完成对客户密钥的任务</span><span class="sxs-lookup"><span data-stu-id="c09c1-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="c09c1-155">在 Azure Key Vault 中完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="c09c1-155">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="c09c1-156">您需要完成这些步骤，而不管您打算为 Exchange Online 和 Skype for business 或 SharePoint Online、OneDrive for Business 和团队文件设置客户密钥，还是 Office 365 中的所有受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="c09c1-156">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="c09c1-157">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="c09c1-157">Create two new Azure subscriptions</span></span>

<span data-ttu-id="c09c1-158">客户密钥需要两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="c09c1-158">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="c09c1-159">作为一种最佳做法，Microsoft 建议您创建新的 Azure 订阅以用于客户密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-159">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="c09c1-160">Azure Key Vault 密钥只能为同一 Azure Active Directory （AAD）租户中的应用程序授权，您必须使用用于将 DEPs 分配到的 Office 365 组织使用的相同 Azure AD 租户创建新订阅。</span><span class="sxs-lookup"><span data-stu-id="c09c1-160">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned.</span></span> <span data-ttu-id="c09c1-161">例如，在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="c09c1-161">For example, using your work or school account that has global administrator privileges in your Office 365 organization.</span></span> <span data-ttu-id="c09c1-162">有关详细步骤，请参阅[将 Azure 注册为组织](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-162">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c09c1-163">客户密钥需要每个数据加密策略（DEP）的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-163">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="c09c1-164">若要实现此目的，必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="c09c1-164">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="c09c1-165">作为一种最佳做法，Microsoft 建议您的组织的各个成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-165">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="c09c1-166">此外，这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-166">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="c09c1-167">这将保护您的组织，以防您在某个操作员意外、有意或恶意删除或以其他方式 mismanages 它们所负责的密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-167">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="c09c1-168">我们建议您设置新的 Azure 订阅，这些订阅仅用于管理 Azure Key Vault 资源，以便与客户密钥配合使用。</span><span class="sxs-lookup"><span data-stu-id="c09c1-168">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="c09c1-169">您可以为您的组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="c09c1-169">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="c09c1-170">按照这些最佳做法，可以最大限度地减少人为错误的影响，同时帮助管理由客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="c09c1-170">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="c09c1-171">提交为激活 Office 365 的客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="c09c1-171">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="c09c1-172">完成 Azure 步骤后，你需要在[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中提交服务请求。</span><span class="sxs-lookup"><span data-stu-id="c09c1-172">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="c09c1-173">通过 FastTrack web 门户提交请求后，Microsoft 将验证您提供的 Azure 密钥 Vault 配置数据和联系人信息。</span><span class="sxs-lookup"><span data-stu-id="c09c1-173">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="c09c1-174">您在 "产品" 窗体中所做的有关组织的授权监察官的选择对完成客户密钥注册至关重要且必需。</span><span class="sxs-lookup"><span data-stu-id="c09c1-174">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="c09c1-175">您在表单中选择的您组织的监察官将用于确保任何请求吊销的真实性，并销毁与客户密钥数据加密策略一起使用的所有密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-175">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="c09c1-176">您需要执行此步骤一次，激活 Exchange Online 和 Skype for business 覆盖的客户密钥，并再次激活适用于 SharePoint Online 和 OneDrive for business 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-176">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="c09c1-177">若要提交用于激活客户密钥的服务，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c09c1-177">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="c09c1-178">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户，登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-178">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="c09c1-179">登录后，请浏览到**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-179">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="c09c1-180">选择 "**服务**"，并查看当前提供的列表。</span><span class="sxs-lookup"><span data-stu-id="c09c1-180">Choose **Offers**, and review the list of current offers.</span></span>

4. <span data-ttu-id="c09c1-181">有关适用于你的优惠，请选择 "**了解详细信息**"：</span><span class="sxs-lookup"><span data-stu-id="c09c1-181">Choose **Learn More** for the offer that applies to you:</span></span>

   - <span data-ttu-id="c09c1-182">**Exchange Online 和 Skype For business：** 选择 "了解 Exchange 的**客户密钥**" 提供的**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-182">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span>

   - <span data-ttu-id="c09c1-183">**SharePoint Online、OneDrive For business 和团队文件：** 有关**详细信息**，请选择了解**SharePoint 和 OneDrive for Business 产品的客户密钥**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-183">**SharePoint Online, OneDrive for Business, and Teams files:** Choose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="c09c1-184">在 "**提供详细信息**" 页上，选择 "**创建请求**"。</span><span class="sxs-lookup"><span data-stu-id="c09c1-184">On the **Offer details** page, choose **Create Request**.</span></span>

6. <span data-ttu-id="c09c1-185">填写 "产品" 窗体上的所有适用详细信息和请求的信息。</span><span class="sxs-lookup"><span data-stu-id="c09c1-185">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="c09c1-186">特别注意您的组织中要授权的监察官，以批准永久和不可恢复的加密密钥和数据的销毁。</span><span class="sxs-lookup"><span data-stu-id="c09c1-186">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="c09c1-187">完成表单后，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="c09c1-187">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="c09c1-188">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="c09c1-188">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="c09c1-189">临时或永久丢失根加密密钥可能会非常中断，甚至会导致服务操作发生故障，并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="c09c1-189">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="c09c1-190">出于此原因，使用客户密钥的资源需要加强保护。</span><span class="sxs-lookup"><span data-stu-id="c09c1-190">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="c09c1-191">与客户密钥结合使用的所有 Azure 资源在默认配置之外提供保护机制。</span><span class="sxs-lookup"><span data-stu-id="c09c1-191">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="c09c1-192">可以通过阻止即时和不可撤销取消的方式对 Azure 订阅进行标记或注册。</span><span class="sxs-lookup"><span data-stu-id="c09c1-192">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="c09c1-193">这称为注册强制保留期。</span><span class="sxs-lookup"><span data-stu-id="c09c1-193">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="c09c1-194">为强制保留期注册 Azure 订阅所需的步骤需要与 Office 365 团队进行协作。</span><span class="sxs-lookup"><span data-stu-id="c09c1-194">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team.</span></span> <span data-ttu-id="c09c1-195">此过程可能需要一至五个工作日。</span><span class="sxs-lookup"><span data-stu-id="c09c1-195">This process can take from one to five business days.</span></span> <span data-ttu-id="c09c1-196">以前，这有时称为 "不取消"。</span><span class="sxs-lookup"><span data-stu-id="c09c1-196">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="c09c1-197">在联系 Office 365 团队之前，必须为每个用于客户密钥的 Azure 订阅执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="c09c1-197">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="c09c1-198">请确保已安装 Azure PowerShell Az 模块，然后再继续（https://docs.microsoft.com/powershell/azure/new-azureps-module-az。</span><span class="sxs-lookup"><span data-stu-id="c09c1-198">Please ensure that you have the Azure PowerShell Az module installed before proceeding (https://docs.microsoft.com/powershell/azure/new-azureps-module-az.</span></span>
  
1. <span data-ttu-id="c09c1-199">使用 Azure PowerShell 登录。</span><span class="sxs-lookup"><span data-stu-id="c09c1-199">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="c09c1-200">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-200">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c09c1-201">运行 AzProviderFeature cmdlet 以注册你的订阅，以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="c09c1-201">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="c09c1-202">对每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c09c1-202">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

3. <span data-ttu-id="c09c1-203">请与 Microsoft 联系以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="c09c1-203">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="c09c1-204">对于 SharePoint 和 OneDrive for Business 团队，请联系[spock@microsoft.com](mailto:spock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-204">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="c09c1-205">对于 Exchange Online 和 Skype for Business，请联系[exock@microsoft.com](mailto:exock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-205">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="c09c1-206">在您的电子邮件中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="c09c1-206">Include the following in your email:</span></span>

   <span data-ttu-id="c09c1-207">**Subject**： \<*租户的完全限定域名*的客户密钥\></span><span class="sxs-lookup"><span data-stu-id="c09c1-207">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="c09c1-208">**正文**：要为其完成强制保留期的订阅 id。</span><span class="sxs-lookup"><span data-stu-id="c09c1-208">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="c09c1-209">每个订阅的 AzProviderFeature 的输出。</span><span class="sxs-lookup"><span data-stu-id="c09c1-209">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="c09c1-210">完成此过程所需的服务级别协议（SLA）是在 Microsoft 经过通知（并验证）后，注册了你的订阅以使用强制保留期后，此过程的服务级别协议（SLA）就是5个工作日。</span><span class="sxs-lookup"><span data-stu-id="c09c1-210">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="c09c1-211">收到 Microsoft 注册已完成的通知后，通过运行 AzProviderFeature cmdlet 验证注册的状态，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c09c1-211">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature cmdlet as follows.</span></span> <span data-ttu-id="c09c1-212">对每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c09c1-212">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="c09c1-213">验证 AzProviderFeature cmdlet 中的**注册状态**属性是否返回**已注册**的值后，请运行以下命令来完成此过程。</span><span class="sxs-lookup"><span data-stu-id="c09c1-213">After verifying that the **Registration State** property from the Get-AzProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process.</span></span> <span data-ttu-id="c09c1-214">对每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c09c1-214">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace "Microsoft.KeyVault"
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="c09c1-215">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="c09c1-215">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="c09c1-216">创建密钥存储库的步骤在[开始使用 Azure Key vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)时进行了介绍，此步骤将指导您完成安装和启动 azure PowerShell，连接到 azure 订阅，创建资源组，以及在该资源组中创建密钥存储库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-216">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="c09c1-217">创建密钥存储库时，必须选择 SKU：标准版或高级存储库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-217">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="c09c1-218">标准 SKU 允许 Azure Key Vault 密钥受软件保护-没有硬件安全模块（HSM）密钥保护-并且 Premium SKU 允许使用 Hsm 来保护关键保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-218">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="c09c1-219">客户密钥接受使用任何 SKU 的密钥电子仓库，尽管 Microsoft 强烈建议您仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="c09c1-219">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="c09c1-220">无论是哪种类型的键的运算开销都是一样的，因此，每个受 HSM 保护的密钥的成本的唯一区别是每个月的成本。</span><span class="sxs-lookup"><span data-stu-id="c09c1-220">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="c09c1-221">有关详细信息，请参阅[主要保管库定价](https://azure.microsoft.com/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-221">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c09c1-222">对生产数据使用 Premium SKU 密钥电子仓库和受 HSM 保护的密钥，并且仅使用标准 SKU 密钥电子仓库和密钥进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="c09c1-222">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="c09c1-223">对于每个将使用客户密钥的 Office 365 服务，请在您创建的两个 Azure 订阅中的每个中创建一个密钥存储库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-223">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="c09c1-224">例如，仅针对 Exchange Online 和 Skype for business 或 SharePoint Online 和 OneDrive for Business，你将仅创建一对电子仓库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-224">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="c09c1-225">若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥，您将创建两对主要电子仓库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-225">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="c09c1-226">对密钥库使用命名约定，以反映将与保管库关联的数据加密策略的预期用途。</span><span class="sxs-lookup"><span data-stu-id="c09c1-226">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="c09c1-227">请参阅下面的 "最佳实践" 部分，了解命名约定建议。</span><span class="sxs-lookup"><span data-stu-id="c09c1-227">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="c09c1-228">为每个数据加密策略创建一组单独的、成对的电子仓库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-228">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="c09c1-229">对于 Exchange Online，当您将策略分配给邮箱时，会选择数据加密策略的范围。</span><span class="sxs-lookup"><span data-stu-id="c09c1-229">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="c09c1-230">一个邮箱只能分配一个策略，并且最多可以创建50个策略。</span><span class="sxs-lookup"><span data-stu-id="c09c1-230">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="c09c1-231">对于 SharePoint Online，策略的范围是组织内的所有数据（地理_位置或地理_位置）。</span><span class="sxs-lookup"><span data-stu-id="c09c1-231">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="c09c1-232">创建密钥存储库还需要创建 Azure 资源组，因为密钥存储库需要存储容量（尽管非常小）和密钥存储库日志记录（如果启用）也会生成存储的数据。</span><span class="sxs-lookup"><span data-stu-id="c09c1-232">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="c09c1-233">作为一种最佳做法，Microsoft 建议使用单独的管理员来管理每个资源组，并将管理与将管理所有相关客户密钥资源的一组管理员相一致。</span><span class="sxs-lookup"><span data-stu-id="c09c1-233">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c09c1-234">若要最大限度地提高可用性，关键电子仓库应位于与 Office 365 服务接近的区域。</span><span class="sxs-lookup"><span data-stu-id="c09c1-234">To maximize availability, your key vaults should be in regions close to your Office 365 service.</span></span> <span data-ttu-id="c09c1-235">例如，如果您的 Exchange Online 组织在北美，请将您的密钥电子仓库放在北美。</span><span class="sxs-lookup"><span data-stu-id="c09c1-235">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="c09c1-236">如果你的 Exchange Online 组织在欧洲，请将你的密钥电子仓库放在欧洲。</span><span class="sxs-lookup"><span data-stu-id="c09c1-236">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="c09c1-237">对密钥存储库使用公用前缀，并包含密钥保管库和密钥的使用和作用域的缩写（例如，对于将在北美使用电子仓库的 Contoso SharePoint 服务，可能的姓名对是 Contoso-O365SP-VaultA1，Contoso-O365SP-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="c09c1-237">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="c09c1-238">保管库名称在 Azure 中是全局唯一的字符串，因此，如果所需名称已由其他 Azure 客户声明，则可能需要尝试其他名称的变体。</span><span class="sxs-lookup"><span data-stu-id="c09c1-238">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="c09c1-239">从7月2017电子仓库名称无法更改，因此最佳做法是为设置编写计划，并使用第二个人验证是否正确执行了计划。</span><span class="sxs-lookup"><span data-stu-id="c09c1-239">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="c09c1-240">如果可能，请在非配对区域中创建您的电子仓库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-240">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="c09c1-241">配对的 Azure 区域在服务故障域之间提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="c09c1-241">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="c09c1-242">因此，可以将区域对视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="c09c1-242">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="c09c1-243">这意味着，放置在一个区域中的 Azure 资源将自动获得配对区域的容错能力。</span><span class="sxs-lookup"><span data-stu-id="c09c1-243">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="c09c1-244">出于此原因，在区域为成对的数据加密策略中使用的两个存储库的区域选择区域意味着仅有两个可用性区域处于使用状态。</span><span class="sxs-lookup"><span data-stu-id="c09c1-244">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="c09c1-245">大多数地理位置仅有两个区域，因此尚不能选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="c09c1-245">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="c09c1-246">如果可能，请为用于数据加密策略的两个电子仓库选择两个非配对区域。</span><span class="sxs-lookup"><span data-stu-id="c09c1-246">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="c09c1-247">这从总共四个可用区域获益。</span><span class="sxs-lookup"><span data-stu-id="c09c1-247">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="c09c1-248">有关详细信息，请参阅[业务连续性和灾难恢复（BCDR）：](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)当前区域对列表的 Azure 配对区域。</span><span class="sxs-lookup"><span data-stu-id="c09c1-248">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="c09c1-249">将权限分配给每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="c09c1-249">Assign permissions to each key vault</span></span>

<span data-ttu-id="c09c1-250">对于每个密钥存储库，您将需要为客户密钥定义三组不同的权限，具体取决于您的实现。</span><span class="sxs-lookup"><span data-stu-id="c09c1-250">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="c09c1-251">例如，您需要为以下各项定义一组权限：</span><span class="sxs-lookup"><span data-stu-id="c09c1-251">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="c09c1-252">将对您的组织执行关键电子仓库的日常管理的**主要保管库管理员**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-252">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="c09c1-253">这些任务包括备份、创建、获取、导入、列出和还原。</span><span class="sxs-lookup"><span data-stu-id="c09c1-253">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c09c1-254">分配给主要保管库管理员的权限集不包含删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="c09c1-254">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="c09c1-255">这是有意和重要的做法。</span><span class="sxs-lookup"><span data-stu-id="c09c1-255">This is intentional and an important practice.</span></span> <span data-ttu-id="c09c1-256">通常情况下，删除加密密钥不会完成，因为这样做会永久破坏数据。</span><span class="sxs-lookup"><span data-stu-id="c09c1-256">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="c09c1-257">作为一种最佳做法，默认情况下不要向主要保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="c09c1-257">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="c09c1-258">相反，请为重要的保管库参与者预留此权限，并在清楚了解结果的情况下，仅在短期内将其分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="c09c1-258">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="c09c1-259">若要将这些权限分配给 Office 365 组织中的用户，请使用 Azure PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="c09c1-259">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="c09c1-260">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-260">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="c09c1-261">运行 AzKeyVaultAccessPolicy cmdlet 以分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="c09c1-261">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="c09c1-262">例如：</span><span class="sxs-lookup"><span data-stu-id="c09c1-262">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="c09c1-263">可以更改 Azure 密钥存储库本身权限的**主要保管库参与者**。</span><span class="sxs-lookup"><span data-stu-id="c09c1-263">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="c09c1-264">您需要更改这些权限，因为员工离开或加入团队，或者在极少数情况下，主要保管库管理员合法需要删除或还原密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="c09c1-264">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="c09c1-265">需要在密钥保管库中向此组密钥 vault 参与者授予**参与者**角色。</span><span class="sxs-lookup"><span data-stu-id="c09c1-265">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="c09c1-266">您可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="c09c1-266">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="c09c1-267">有关详细步骤，请参阅[使用基于角色的访问控制管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-267">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="c09c1-268">创建订阅的管理员将隐式拥有此访问权限，以及将其他管理员分配给参与者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="c09c1-268">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="c09c1-269">如果打算将客户密钥用于 Exchange Online 和 Skype for business，则需要向 Office 365 授予权限，以代表 Exchange Online 和 Skype for business 使用密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-269">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="c09c1-270">同样，如果您打算将客户密钥与 SharePoint Online 和 OneDrive for business 结合使用，则需要添加 Office 365 的权限，以代表 SharePoint Online 和 OneDrive for business 使用密钥存储库。</span><span class="sxs-lookup"><span data-stu-id="c09c1-270">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="c09c1-271">若要向 Office 365 授予权限，请使用以下语法运行**AzKeyVaultAccessPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c09c1-271">To give permission to Office 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="c09c1-272">其中：</span><span class="sxs-lookup"><span data-stu-id="c09c1-272">Where:</span></span>

    - <span data-ttu-id="c09c1-273">*保管库名称*是您创建的密钥存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="c09c1-273">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="c09c1-274">对于 Exchange Online 和 Skype for Business，请将*Office 365 appID*替换为`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="c09c1-274">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="c09c1-275">对于 SharePoint Online、OneDrive for Business 和团队文件，请将*Office 365 appID*替换为`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="c09c1-275">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="c09c1-276">示例：设置 Exchange Online 和 Skype for business 的权限：</span><span class="sxs-lookup"><span data-stu-id="c09c1-276">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="c09c1-277">示例：设置 SharePoint Online、OneDrive for Business 和团队文件的权限：</span><span class="sxs-lookup"><span data-stu-id="c09c1-277">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="c09c1-278">启用然后确认密钥电子仓库上的软删除</span><span class="sxs-lookup"><span data-stu-id="c09c1-278">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="c09c1-279">如果可以快速恢复密钥，则由于意外或恶意删除的密钥而遇到的扩展服务故障的可能性较小。</span><span class="sxs-lookup"><span data-stu-id="c09c1-279">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="c09c1-280">您需要先启用此配置（称为 "软删除"），然后才能在 "客户密钥" 中使用密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-280">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="c09c1-281">启用软删除允许您在删除90天内恢复密钥或电子仓库，而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="c09c1-281">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="c09c1-282">若要在密钥保管库上启用软删除，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c09c1-282">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="c09c1-283">使用 Windows Powershell 登录到你的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="c09c1-283">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="c09c1-284">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-284">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c09c1-285">运行[AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c09c1-285">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="c09c1-286">在此示例中，*保管库名称*是要为其启用软删除的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="c09c1-286">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="c09c1-287">通过运行**AzKeyVault** cmdlet，确认已为密钥存储库配置了软删除。</span><span class="sxs-lookup"><span data-stu-id="c09c1-287">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="c09c1-288">如果为密钥存储库正确配置了软删除，则 "_已启用软删除_" 属性将返回值**True**：</span><span class="sxs-lookup"><span data-stu-id="c09c1-288">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="c09c1-289">通过创建或导入密钥将密钥添加到每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="c09c1-289">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="c09c1-290">有两种方法可以将密钥添加到 Azure Key Vault;可以直接在密钥保管库中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-290">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="c09c1-291">直接在 "密钥存储库" 中创建密钥是不太复杂的方法，而导入密钥提供了对如何生成密钥的总体控制。</span><span class="sxs-lookup"><span data-stu-id="c09c1-291">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="c09c1-292">若要直接在密钥保管库中创建密钥，请运行[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-292">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="c09c1-293">其中：</span><span class="sxs-lookup"><span data-stu-id="c09c1-293">Where:</span></span>

- <span data-ttu-id="c09c1-294">*保管库名称*是要在其中创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="c09c1-294">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="c09c1-295">*键名称*是要赋予新键的名称。</span><span class="sxs-lookup"><span data-stu-id="c09c1-295">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="c09c1-296">使用上面的密钥库的命名约定命名键。</span><span class="sxs-lookup"><span data-stu-id="c09c1-296">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="c09c1-297">这样一来，在仅显示密钥名称的工具中，字符串是自我描述的。</span><span class="sxs-lookup"><span data-stu-id="c09c1-297">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="c09c1-298">如果打算使用 HSM 保护密钥，请确保将**HSM**指定为_Destination_参数的值，否则指定 "**软件**"。</span><span class="sxs-lookup"><span data-stu-id="c09c1-298">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="c09c1-299">For example,</span><span class="sxs-lookup"><span data-stu-id="c09c1-299">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="c09c1-300">若要将密钥直接导入到密钥存储库中，您需要具有 Thales nShield 硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="c09c1-300">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="c09c1-301">某些组织首选使用此方法来建立其密钥的 provenance，此方法还提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="c09c1-301">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="c09c1-302">用于导入的工具集包括来自 Thales 的证明，用于加密所生成密钥的密钥交换密钥（KEK）不可导出，并在 Thales 制造的正版 HSM 中生成。</span><span class="sxs-lookup"><span data-stu-id="c09c1-302">The tool set used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>

- <span data-ttu-id="c09c1-303">工具集包括 Thales 中的证明，该认证来自 Azure Key Vault 安全世界也是在由 Thales 生产的正版 HSM 上生成的。</span><span class="sxs-lookup"><span data-stu-id="c09c1-303">The tool set includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="c09c1-304">此认证向你证明 Microsoft 也在使用正版 Thales 硬件。</span><span class="sxs-lookup"><span data-stu-id="c09c1-304">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>

<span data-ttu-id="c09c1-305">检查安全组以确定是否需要上述 attestations。</span><span class="sxs-lookup"><span data-stu-id="c09c1-305">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="c09c1-306">有关在本地创建密钥并将其导入到密钥保管库的详细步骤，请参阅 how [to 为 Azure Key vault 生成和传输受 HSM 保护的密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-306">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="c09c1-307">使用 Azure 说明在每个密钥存储库中创建密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-307">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="c09c1-308">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="c09c1-308">Check the recovery level of your keys</span></span>

<span data-ttu-id="c09c1-309">Office 365 要求 Azure Key Vault 订阅设置为 "不取消"，并且客户密钥使用的密钥启用了软删除。</span><span class="sxs-lookup"><span data-stu-id="c09c1-309">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="c09c1-310">你可以通过查看密钥上的恢复级别来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="c09c1-310">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="c09c1-311">若要检查注册表项的恢复级别，请在 Azure PowerShell 中运行 AzKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-311">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="c09c1-312">如果_恢复级别_属性返回的值不是**可恢复 + ProtectedSubscription**的值，则需要查看本主题，并确保已按照所有步骤将订阅放在 "不要取消" 列表中，并且已在每个密钥保管库上启用软删除。</span><span class="sxs-lookup"><span data-stu-id="c09c1-312">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="c09c1-313">备份 Azure 密钥存储库</span><span class="sxs-lookup"><span data-stu-id="c09c1-313">Back up Azure Key Vault</span></span>

<span data-ttu-id="c09c1-314">立即完成创建或对某个键的任何更改，执行备份并存储联机和脱机的备份副本。</span><span class="sxs-lookup"><span data-stu-id="c09c1-314">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="c09c1-315">脱机副本不应连接到任何网络，例如在物理安全或商业存储设施中。</span><span class="sxs-lookup"><span data-stu-id="c09c1-315">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="c09c1-316">至少应将备份的一个副本存储在灾难发生时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="c09c1-316">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="c09c1-317">备份 blob 是恢复密钥材料的唯一方法（应永久销毁密钥保管库密钥），或以其他方式呈现为不可操作。</span><span class="sxs-lookup"><span data-stu-id="c09c1-317">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="c09c1-318">Azure Key Vault 外部的密钥和已导入到 Azure Key Vault 的密钥不能作为备份，因为客户密钥使用密钥所需的元数据在外部密钥中不存在。</span><span class="sxs-lookup"><span data-stu-id="c09c1-318">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="c09c1-319">只有从 Azure 密钥存储库中获取的备份才能用于使用客户密钥的还原操作。</span><span class="sxs-lookup"><span data-stu-id="c09c1-319">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="c09c1-320">因此，在上载或创建密钥时，应创建 Azure 密钥存储库的备份，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="c09c1-320">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="c09c1-321">若要创建 Azure Key Vault 密钥的备份，请运行[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-321">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="c09c1-322">确保输出文件使用后缀`.backup`。</span><span class="sxs-lookup"><span data-stu-id="c09c1-322">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="c09c1-323">此 cmdlet 生成的输出文件已加密，不能在 Azure 密钥保管库外部使用。</span><span class="sxs-lookup"><span data-stu-id="c09c1-323">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="c09c1-324">只能将备份还原到从中获取备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="c09c1-324">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="c09c1-325">对于输出文件，选择您的电子仓库名称和密钥名称的组合。</span><span class="sxs-lookup"><span data-stu-id="c09c1-325">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="c09c1-326">这将使文件名自我描述。</span><span class="sxs-lookup"><span data-stu-id="c09c1-326">This will make the file name self-describing.</span></span> <span data-ttu-id="c09c1-327">它还将确保备份文件名称不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="c09c1-327">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="c09c1-328">例如：</span><span class="sxs-lookup"><span data-stu-id="c09c1-328">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="c09c1-329">验证 Azure Key Vault 配置设置</span><span class="sxs-lookup"><span data-stu-id="c09c1-329">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="c09c1-330">在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="c09c1-330">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="c09c1-331">特别是，如果您使用步骤设置了除本主题中所述的密钥和电子仓库之外的密钥和电子仓库，则应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。</span><span class="sxs-lookup"><span data-stu-id="c09c1-331">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="c09c1-332">若要验证您的密钥是否启用了 get、wrapKey 和 unwrapKey 操作，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c09c1-332">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="c09c1-333">运行[AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-333">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="c09c1-334">在 "输出" 中，根据需要查找访问策略和 Exchange Online 标识（GUID）或 SharePoint Online 标识（GUID）。</span><span class="sxs-lookup"><span data-stu-id="c09c1-334">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="c09c1-335">所有三个权限都必须显示在 "键的权限" 下。</span><span class="sxs-lookup"><span data-stu-id="c09c1-335">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="c09c1-336">如果访问策略配置不正确，请运行 AzKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-336">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="c09c1-337">例如，对于 Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="c09c1-337">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="c09c1-338">例如，对于 SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="c09c1-338">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="c09c1-339">若要验证没有为你的密钥设置到期日期，请运行[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-339">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="c09c1-340">已过期的密钥不能由客户密钥使用，尝试使用过期密钥的操作将会失败，并且可能会导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="c09c1-340">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="c09c1-341">强烈建议使用与客户密钥一起使用的密钥不具有过期日期。</span><span class="sxs-lookup"><span data-stu-id="c09c1-341">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="c09c1-342">过期日期一旦设置，便无法删除，但可以更改为不同的日期。</span><span class="sxs-lookup"><span data-stu-id="c09c1-342">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="c09c1-343">如果必须使用具有过期日期设置的密钥，请将 "过期" 值更改为 "12/31/9999"。</span><span class="sxs-lookup"><span data-stu-id="c09c1-343">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="c09c1-344">过期日期设置为12/31/9999 之外的密钥将不会通过 Office 365 验证。</span><span class="sxs-lookup"><span data-stu-id="c09c1-344">Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="c09c1-345">若要更改已设置为12/31/9999 以外的任何其他值的过期日期，请运行[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-345">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="c09c1-346">不要在与客户密钥结合使用的加密密钥上设置到期日期。</span><span class="sxs-lookup"><span data-stu-id="c09c1-346">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="c09c1-347">获取每个 Azure Key Vault 密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="c09c1-347">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="c09c1-348">完成 Azure 中的所有步骤以设置密钥存储库并添加密钥后，运行以下命令以获取每个密钥存储库中的密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="c09c1-348">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="c09c1-349">在稍后创建和分配每个 DEP 时，需要使用这些 Uri，将此信息保存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="c09c1-349">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="c09c1-350">请务必为每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="c09c1-350">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="c09c1-351">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="c09c1-351">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="c09c1-352">Office 365：设置 Exchange Online 和 Skype for business 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c09c1-352">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="c09c1-353">在开始之前，请确保您已完成设置 Azure Key Vault 所需的任务。</span><span class="sxs-lookup"><span data-stu-id="c09c1-353">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="c09c1-354">有关信息，请参阅[Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-354">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="c09c1-355">若要设置 Exchange Online 和 Skype for business 的客户密钥，你将需要通过 Windows PowerShell 远程连接到 Exchange Online 来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c09c1-355">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="c09c1-356">创建与 Exchange Online 和 Skype for Business 一起使用的数据加密策略（DEP）</span><span class="sxs-lookup"><span data-stu-id="c09c1-356">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="c09c1-357">一个 DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="c09c1-357">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="c09c1-358">您在 Office 365 中向邮箱分配了一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="c09c1-358">You assign a DEP to a mailbox in Office 365.</span></span> <span data-ttu-id="c09c1-359">然后，Office 365 将使用在策略中标识的密钥来加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="c09c1-359">Office 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="c09c1-360">若要创建 DEP，您需要之前获取的主要保管库 Uri。</span><span class="sxs-lookup"><span data-stu-id="c09c1-360">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="c09c1-361">有关说明，请参阅[获取每个 Azure Key Vault 密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key) 。</span><span class="sxs-lookup"><span data-stu-id="c09c1-361">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="c09c1-362">还!</span><span class="sxs-lookup"><span data-stu-id="c09c1-362">Remember!</span></span> <span data-ttu-id="c09c1-363">创建 DEP 时，请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-363">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="c09c1-364">确保这些项位于两个单独的 Azure 区域中，以确保地域冗余。</span><span class="sxs-lookup"><span data-stu-id="c09c1-364">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="c09c1-365">若要创建 DEP，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c09c1-365">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="c09c1-366">在您的本地计算机上，使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户，通过打开 Windows PowerShell 并运行以下命令[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="c09c1-366">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) by opening Windows PowerShell and running the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="c09c1-367">在 "Windows PowerShell 凭据请求" 对话框中，输入你的工作或学校帐户信息，单击 **"确定**"，然后输入以下命令。</span><span class="sxs-lookup"><span data-stu-id="c09c1-367">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="c09c1-368">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c09c1-368">Run the following command.</span></span>

   ```powershell
   Import-PSSession $Session
   ```

4. <span data-ttu-id="c09c1-369">若要创建 DEP，请通过键入以下命令来使用 DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c09c1-369">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="c09c1-370">其中：</span><span class="sxs-lookup"><span data-stu-id="c09c1-370">Where:</span></span>

   - <span data-ttu-id="c09c1-371">*PolicyName*是要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="c09c1-371">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="c09c1-372">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="c09c1-372">Names cannot contain spaces.</span></span> <span data-ttu-id="c09c1-373">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="c09c1-373">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="c09c1-374">*策略说明*是一种用户友好的策略说明，可帮助您记住该策略的用途。</span><span class="sxs-lookup"><span data-stu-id="c09c1-374">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="c09c1-375">您可以在说明中包含空格。</span><span class="sxs-lookup"><span data-stu-id="c09c1-375">You can include spaces in the description.</span></span> <span data-ttu-id="c09c1-376">例如，"适用于美国的邮箱的根键及其区域"。</span><span class="sxs-lookup"><span data-stu-id="c09c1-376">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="c09c1-377">*KeyVaultURI1*是策略中的第一个项的 URI。</span><span class="sxs-lookup"><span data-stu-id="c09c1-377">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="c09c1-378">例如，https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="c09c1-378">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span>

   - <span data-ttu-id="c09c1-379">*KeyVaultURI2*是策略中的第二个项的 URI。</span><span class="sxs-lookup"><span data-stu-id="c09c1-379">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="c09c1-380">例如，https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。</span><span class="sxs-lookup"><span data-stu-id="c09c1-380">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="c09c1-381">用逗号和空格分隔两个 Uri。</span><span class="sxs-lookup"><span data-stu-id="c09c1-381">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="c09c1-382">示例：</span><span class="sxs-lookup"><span data-stu-id="c09c1-382">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="c09c1-383">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="c09c1-383">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="c09c1-384">使用 "设置邮箱" cmdlet 将 DEP 分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="c09c1-384">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="c09c1-385">一旦分配了策略，Office 365 就可以使用 DEP 中指定的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="c09c1-385">Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="c09c1-386">其中*MailboxIdParameter*指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="c09c1-386">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="c09c1-387">有关设置邮箱 cmdlet 的详细信息，请参阅[set-邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-387">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="c09c1-388">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="c09c1-388">Validate mailbox encryption</span></span>

<span data-ttu-id="c09c1-389">对邮箱加密可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="c09c1-389">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="c09c1-390">首次分配策略时，该邮箱还必须完全从一个数据库移动到另一个数据库，然后服务才能对邮箱加密。</span><span class="sxs-lookup"><span data-stu-id="c09c1-390">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="c09c1-391">建议您在更改 DEP 或首次将 DEP 分配到邮箱之后，先等待72小时，再尝试验证加密。</span><span class="sxs-lookup"><span data-stu-id="c09c1-391">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="c09c1-392">使用 Get-mailboxstatistics cmdlet 可以确定邮箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="c09c1-392">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="c09c1-393">如果邮箱已加密，则 IsEncrypted 属性返回**true** ，如果邮箱未加密，则返回**false**值。</span><span class="sxs-lookup"><span data-stu-id="c09c1-393">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="c09c1-394">完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="c09c1-394">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="c09c1-395">如果邮箱在您分配 DEP 的时间之后没有加密过，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="c09c1-395">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c09c1-396">Office 365：为 SharePoint Online、OneDrive for Business 和团队文件设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="c09c1-396">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c09c1-397">在开始之前，请确保您已完成设置 Azure Key Vault 所需的任务。</span><span class="sxs-lookup"><span data-stu-id="c09c1-397">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="c09c1-398">有关信息，请参阅[Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-398">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="c09c1-399">若要为 SharePoint Online、OneDrive for Business 和团队文件设置客户密钥，您将需要通过使用 Windows PowerShell 远程连接到 SharePoint Online 来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c09c1-399">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="c09c1-400">为每个 SharePoint Online 和 OneDrive for business 地域创建数据加密策略（DEP）</span><span class="sxs-lookup"><span data-stu-id="c09c1-400">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="c09c1-401">将 DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="c09c1-401">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="c09c1-402">您将 DEP 应用于一个地理位置（也称为地理位置）中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="c09c1-402">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="c09c1-403">如果使用 Office 365 的多地理位置功能，可以为每个地理位置创建一个 DEP，以便每个地区使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-403">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="c09c1-404">如果您不使用多地理位置，则可以在 Office 365 组织中创建一个 DEP，以便与 SharePoint Online、OneDrive for Business 和团队文件一起使用。</span><span class="sxs-lookup"><span data-stu-id="c09c1-404">If you are not using multi-geo, you can create one DEP in your Office 365 organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="c09c1-405">Office 365 使用在 DEP 中标识的密钥来加密该地理位置中的数据。</span><span class="sxs-lookup"><span data-stu-id="c09c1-405">Office 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="c09c1-406">若要创建 DEP，您需要之前获取的主要保管库 Uri。</span><span class="sxs-lookup"><span data-stu-id="c09c1-406">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="c09c1-407">有关说明，请参阅[获取每个 Azure Key Vault 密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key) 。</span><span class="sxs-lookup"><span data-stu-id="c09c1-407">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="c09c1-408">还!</span><span class="sxs-lookup"><span data-stu-id="c09c1-408">Remember!</span></span> <span data-ttu-id="c09c1-409">创建 DEP 时，请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="c09c1-409">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="c09c1-410">确保这些项位于两个单独的 Azure 区域中，以确保地域冗余。</span><span class="sxs-lookup"><span data-stu-id="c09c1-410">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="c09c1-411">若要创建 DEP，您需要使用 Windows PowerShell 远程连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="c09c1-411">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="c09c1-412">在您的本地计算机上，使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户，[连接到 SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="c09c1-412">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="c09c1-413">在 Microsoft SharePoint Online 命令行管理程序中，运行 SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c09c1-413">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="c09c1-414">注册 DEP 时，会开始对 geo 中的数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="c09c1-414">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="c09c1-415">这可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="c09c1-415">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="c09c1-416">验证文件加密</span><span class="sxs-lookup"><span data-stu-id="c09c1-416">Validate file encryption</span></span>

 <span data-ttu-id="c09c1-417">若要验证 SharePoint Online、OneDrive for Business 和团队文件的加密，请[连接到 Sharepoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)，然后使用 SPODataEncryptionPolicy cmdlet 检查租户的状态。</span><span class="sxs-lookup"><span data-stu-id="c09c1-417">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="c09c1-418">如果启用了客户密钥加密且所有站点中的所有文件均已加密，则_State_属性将返回一个**注册**值。</span><span class="sxs-lookup"><span data-stu-id="c09c1-418">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="c09c1-419">如果仍在进行加密，则此 cmdlet 提供有关已完成的网站百分比的信息。</span><span class="sxs-lookup"><span data-stu-id="c09c1-419">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c09c1-420">相关文章</span><span class="sxs-lookup"><span data-stu-id="c09c1-420">Related articles</span></span>

- [<span data-ttu-id="c09c1-421">使用 Office 365 的客户密钥进行服务加密</span><span class="sxs-lookup"><span data-stu-id="c09c1-421">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c09c1-422">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c09c1-422">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c09c1-423">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c09c1-423">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c09c1-424">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c09c1-424">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="c09c1-425">Office 365 服务加密</span><span class="sxs-lookup"><span data-stu-id="c09c1-425">Office 365 Service Encryption</span></span>](office-365-service-encryption.md)