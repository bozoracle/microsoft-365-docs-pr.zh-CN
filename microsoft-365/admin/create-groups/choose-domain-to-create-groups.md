---
title: 选择创建 Office 365 组时要使用的域
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: '了解如何在使用 PowerShell 配置电子邮件地址策略时选择要在创建 Office 365 组时使用的域。 '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238087"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="77687-103">选择创建 Office 365 组时要使用的域</span><span class="sxs-lookup"><span data-stu-id="77687-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="77687-p101">一些组织使用单独的电子邮件域，以区分不同的业务部分。可以指定用户创建 Office 365 组时应使用的域。</span><span class="sxs-lookup"><span data-stu-id="77687-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="77687-106">如果您的组织需要用户在企业的默认接受域以外的其他域中创建其组，则可以通过使用 PowerShell 配置电子邮件地址策略（EAPs）来允许这样做。</span><span class="sxs-lookup"><span data-stu-id="77687-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="77687-107">在运行 PowerShell cmdlet 之前，请下载并安装将允许您与 Office 365 组织交谈的模块。</span><span class="sxs-lookup"><span data-stu-id="77687-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization.</span></span> <span data-ttu-id="77687-108">请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785881)。</span><span class="sxs-lookup"><span data-stu-id="77687-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="77687-109">示例场景</span><span class="sxs-lookup"><span data-stu-id="77687-109">Example scenarios</span></span>

<span data-ttu-id="77687-110">假设您的企业的主域是 Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="77687-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="77687-111">但您的组织的默认接受域是 service.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="77687-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="77687-112">这意味着将在 service.contoso.com 中创建组（例如，jimsteam@service.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="77687-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="77687-113">假设您在组织中配置了子域。</span><span class="sxs-lookup"><span data-stu-id="77687-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="77687-114">您还希望在这些域中创建组：</span><span class="sxs-lookup"><span data-stu-id="77687-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="77687-115">students.contoso.com 学生版</span><span class="sxs-lookup"><span data-stu-id="77687-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="77687-116">教职员工成员的 faculty.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77687-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="77687-117">以下两种方案说明了如何实现此目的。</span><span class="sxs-lookup"><span data-stu-id="77687-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77687-118">当您拥有多个 EAPs 时，将按优先级顺序对它们进行评估。</span><span class="sxs-lookup"><span data-stu-id="77687-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="77687-119">值为1表示最高优先级。</span><span class="sxs-lookup"><span data-stu-id="77687-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="77687-120">EAP 匹配后，将不会评估任何其他 EAP，并且在该组上标记的地址按匹配的 EAP 进行。</span><span class="sxs-lookup"><span data-stu-id="77687-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="77687-121">> 如果没有 EAPs 匹配指定条件，则会在组织的默认接受域中设置组。</span><span class="sxs-lookup"><span data-stu-id="77687-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="77687-122">请查看在[Exchange Online 中管理接受的域](https://go.microsoft.com/fwlink/p/?LinkId=785428)，以了解有关如何添加接受域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="77687-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="77687-123">方案 1</span><span class="sxs-lookup"><span data-stu-id="77687-123">Scenario 1</span></span>

<span data-ttu-id="77687-124">下面的示例演示如何在 groups.contoso.com 域中预配组织中的所有 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="77687-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="77687-125">方案 2</span><span class="sxs-lookup"><span data-stu-id="77687-125">Scenario 2</span></span>

<span data-ttu-id="77687-126">假设您要控制在其中创建了哪些子域 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="77687-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="77687-127">你想要：</span><span class="sxs-lookup"><span data-stu-id="77687-127">You want:</span></span>
  
- <span data-ttu-id="77687-128">由 students.groups.contoso.com 域中的学生（将**部门**设置为**学生**的用户）创建的组。</span><span class="sxs-lookup"><span data-stu-id="77687-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="77687-129">请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="77687-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="77687-130">由教职员（在 "**部门**" 设置为 "教职员"**或 "电子邮件地址**" 的用户）在 faculty.groups.contoso.com 域中创建的组。</span><span class="sxs-lookup"><span data-stu-id="77687-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="77687-131">请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="77687-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="77687-132">Groups.contoso.com 域中的所有其他用户。</span><span class="sxs-lookup"><span data-stu-id="77687-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="77687-133">请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="77687-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="77687-134">更改电子邮件地址策略</span><span class="sxs-lookup"><span data-stu-id="77687-134">Change email address policies</span></span>

<span data-ttu-id="77687-135">若要更改现有 EAP 的优先级或电子邮件地址模板，请使用 Update-emailaddresspolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77687-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="77687-136">更改 EAP 对已设置的组没有影响。</span><span class="sxs-lookup"><span data-stu-id="77687-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="77687-137">删除电子邮件地址策略</span><span class="sxs-lookup"><span data-stu-id="77687-137">Delete email address policies</span></span>

<span data-ttu-id="77687-138">若要删除 EAP，请使用 Update-emailaddresspolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77687-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="77687-139">更改 EAP 对已设置的组没有影响。</span><span class="sxs-lookup"><span data-stu-id="77687-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="77687-140">混合要求</span><span class="sxs-lookup"><span data-stu-id="77687-140">Hybrid requirements</span></span>

<span data-ttu-id="77687-141">如果您的组织是在混合方案中配置的，请查看[使用本地 Exchange 混合配置 Office 365 组](https://go.microsoft.com/fwlink/p/?LinkId=785430)，以确保您的组织满足创建 Office 365 组的要求。</span><span class="sxs-lookup"><span data-stu-id="77687-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="77687-142">有关使用电子邮件地址策略组的其他信息：</span><span class="sxs-lookup"><span data-stu-id="77687-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="77687-143">还需要了解几个问题：</span><span class="sxs-lookup"><span data-stu-id="77687-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="77687-144">创建快速组的方式取决于您的组织中配置的 EAPs 的数量。</span><span class="sxs-lookup"><span data-stu-id="77687-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="77687-145">管理员和用户也可以在创建组时修改域。</span><span class="sxs-lookup"><span data-stu-id="77687-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="77687-146">用户组是使用已有的标准查询（用户属性）确定的。</span><span class="sxs-lookup"><span data-stu-id="77687-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="77687-147">对于受支持的可筛选 pproperties，请查看[-RecipientFilter 参数的可筛选属性](https://go.microsoft.com/fwlink/p/?LinkId=785918)。</span><span class="sxs-lookup"><span data-stu-id="77687-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties.</span></span> 
    
- <span data-ttu-id="77687-148">如果没有为组配置任何 EAPs，则选择 "创建组的默认接受域"。</span><span class="sxs-lookup"><span data-stu-id="77687-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="77687-149">如果删除接受域，则应首先更新 EAPs，否则组设置将受到影响。</span><span class="sxs-lookup"><span data-stu-id="77687-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="77687-150">可以为组织配置最大值为100的电子邮件地址策略。</span><span class="sxs-lookup"><span data-stu-id="77687-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="77687-151">相关文章</span><span class="sxs-lookup"><span data-stu-id="77687-151">Related articles</span></span>

[<span data-ttu-id="77687-152">在管理中心创建 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="77687-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)