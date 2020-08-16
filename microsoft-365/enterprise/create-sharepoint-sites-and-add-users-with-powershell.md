---
title: 使用 PowerShell 创建 SharePoint Online 网站并添加用户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 摘要：使用 PowerShell 创建新的 SharePoint Online 网站，然后将用户和组添加到这些网站。
ms.openlocfilehash: 4c4edbd68343f0eaf3a25a8c60a2af1e83b058b6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687741"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="e3319-103">使用 PowerShell 创建 SharePoint Online 网站并添加用户</span><span class="sxs-lookup"><span data-stu-id="e3319-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="e3319-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="e3319-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e3319-105">当您使用 PowerShell for Microsoft 365 创建 SharePoint Online 网站并添加用户时，您可以在 Microsoft 365 管理中心内快速和重复执行任务快得多。</span><span class="sxs-lookup"><span data-stu-id="e3319-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e3319-106">您还可以执行不能在 Microsoft 365 管理中心中执行的任务。</span><span class="sxs-lookup"><span data-stu-id="e3319-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="e3319-107">连接到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e3319-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="e3319-108">本主题中的过程要求您连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="e3319-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="e3319-109">有关说明，请参阅 [连接到 SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="e3319-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="e3319-110">步骤1：使用 PowerShell 创建新的网站集</span><span class="sxs-lookup"><span data-stu-id="e3319-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="e3319-111">使用提供的示例代码和记事本创建多个使用 PowerShell 的网站和一个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e3319-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="e3319-112">在此步骤中，你将使用你自己的网站和租户特定信息替换括号中显示的占位符信息。</span><span class="sxs-lookup"><span data-stu-id="e3319-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="e3319-113">此过程允许您创建一个文件，并运行使用该文件的单个 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="e3319-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="e3319-114">这使得所采取的操作具有可重复性和可移植性，并可以减少许多（如果不是全部）因向 SharePoint Online 命令行管理程序键入长命令而导致的错误。</span><span class="sxs-lookup"><span data-stu-id="e3319-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="e3319-115">此步骤包括两个部分。</span><span class="sxs-lookup"><span data-stu-id="e3319-115">There are two parts to this procedure.</span></span> <span data-ttu-id="e3319-116">首先，创建一个 .csv 文件，然后使用 PowerShell 引用该 .csv 文件，该文件将使用其内容来创建网站。</span><span class="sxs-lookup"><span data-stu-id="e3319-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="e3319-117">PowerShell cmdlet 导入 .csv 文件，并将其管道传递到在大括号中将文件的第一行读取为列标题的循环。</span><span class="sxs-lookup"><span data-stu-id="e3319-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="e3319-118">然后，PowerShell cmdlet 将循环访问其余记录，为每个记录创建一个新的网站集，并根据列标题分配网站集的属性。</span><span class="sxs-lookup"><span data-stu-id="e3319-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="e3319-119">创建 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="e3319-119">Create a .csv file</span></span>

1. <span data-ttu-id="e3319-120">打开记事本，然后向其中粘贴以下文本块：</span><span class="sxs-lookup"><span data-stu-id="e3319-120">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="e3319-121">其中 *租户* 是你的租户的名称， *所有者* 是你要向其授予主网站集管理员角色的租户上的用户用户名。</span><span class="sxs-lookup"><span data-stu-id="e3319-121">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="e3319-122"> (在使用记事本以更快批量替换时，可以按 Ctrl + H。 ) </span><span class="sxs-lookup"><span data-stu-id="e3319-122">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="e3319-123">将文件以 **SiteCollections.csv**的形式保存在桌面上。</span><span class="sxs-lookup"><span data-stu-id="e3319-123">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="e3319-124">在使用此程序或任何其他 .csv 或 Windows PowerShell 脚本文件之前，最好确保没有多余的或非打印的字符。</span><span class="sxs-lookup"><span data-stu-id="e3319-124">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="e3319-125">在 Word 中打开该文件，在功能区单击“段落”图标以显示非打印字符。</span><span class="sxs-lookup"><span data-stu-id="e3319-125">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="e3319-126">应该没有多余的非打印字符。</span><span class="sxs-lookup"><span data-stu-id="e3319-126">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="e3319-127">例如，除了文件末尾的最后一个段落标记之外，应该没有其他任何段落标记。</span><span class="sxs-lookup"><span data-stu-id="e3319-127">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="e3319-128">运行 Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="e3319-128">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="e3319-129">在 Windows PowerShell 提示符处，键入或复制并粘贴以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="e3319-129">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="e3319-130">其中， *MyAlias* 等于您的用户别名。</span><span class="sxs-lookup"><span data-stu-id="e3319-130">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="e3319-p106">等待 Windows PowerShell 提示符重新出现。可能需要一两分钟。</span><span class="sxs-lookup"><span data-stu-id="e3319-p106">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="e3319-133">在 Windows PowerShell 提示符处键入或复制并粘贴以下 cmdlet，然后按 Enter 键：</span><span class="sxs-lookup"><span data-stu-id="e3319-133">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="e3319-134">请注意列表中的新网站集。</span><span class="sxs-lookup"><span data-stu-id="e3319-134">Note the new site collections in the list.</span></span> <span data-ttu-id="e3319-135">使用我们的示例 CSV 文件，可以看到以下网站集： **TeamSite01**、 **Blog01**、 **Project01**和 **Community01**</span><span class="sxs-lookup"><span data-stu-id="e3319-135">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="e3319-136">就是这样。</span><span class="sxs-lookup"><span data-stu-id="e3319-136">That’s it.</span></span> <span data-ttu-id="e3319-137">您已使用创建的 .csv 文件和一个 Windows PowerShell 命令创建了多个网站集。</span><span class="sxs-lookup"><span data-stu-id="e3319-137">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="e3319-138">现在，可以创建用户并将其分配给这些网站。</span><span class="sxs-lookup"><span data-stu-id="e3319-138">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="e3319-139">步骤 2：添加用户和组</span><span class="sxs-lookup"><span data-stu-id="e3319-139">Step 2: Add users and groups</span></span>

<span data-ttu-id="e3319-p109">现在，您将创建用户并将其添加到网站集组中。然后，您将使用 .csv 文件批量上载新的组和用户。</span><span class="sxs-lookup"><span data-stu-id="e3319-p109">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="e3319-142">以下过程将继续使用示例网站 TeamSite01、Blog01、Project01 和 Community01。</span><span class="sxs-lookup"><span data-stu-id="e3319-142">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="e3319-143">创建 .csv 和 .ps1 文件</span><span class="sxs-lookup"><span data-stu-id="e3319-143">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="e3319-144">打开记事本，然后向其中粘贴以下文本块：</span><span class="sxs-lookup"><span data-stu-id="e3319-144">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="e3319-145">其中 *租户* 等于你的租户名称。</span><span class="sxs-lookup"><span data-stu-id="e3319-145">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="e3319-146">将文件以 **GroupsAndPermissions.csv**的形式保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="e3319-146">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="e3319-147">打开记事本的新实例，然后向其中粘贴以下文本块：</span><span class="sxs-lookup"><span data-stu-id="e3319-147">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="e3319-148">其中 *租户* 等于租户名称， *用户名* 等于现有用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="e3319-148">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="e3319-149">将文件以 **Users.csv**的形式保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="e3319-149">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="e3319-150">打开记事本的新实例，然后向其中粘贴以下文本块：</span><span class="sxs-lookup"><span data-stu-id="e3319-150">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="e3319-151">其中，MyAlias 等于当前登录的用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="e3319-151">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="e3319-152">将文件以 **UsersAndGroups.ps1**的形式保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="e3319-152">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="e3319-153">这是一个简单的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="e3319-153">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="e3319-154">现在，您可以运行 UsersAndGroup.ps1 脚本以向多个网站集中添加用户和组。</span><span class="sxs-lookup"><span data-stu-id="e3319-154">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="e3319-155">运行 UsersAndGroups.ps1 脚本</span><span class="sxs-lookup"><span data-stu-id="e3319-155">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="e3319-156">返回到 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="e3319-156">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="e3319-157">在 Windows PowerShell 提示符下键入或复制并粘贴以下行，然后按 Enter 键：</span><span class="sxs-lookup"><span data-stu-id="e3319-157">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="e3319-158">在确认提示符处，按 " **Y**"。</span><span class="sxs-lookup"><span data-stu-id="e3319-158">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="e3319-159">在 Windows PowerShell 提示符下键入或复制并粘贴以下内容，然后按 Enter 键：</span><span class="sxs-lookup"><span data-stu-id="e3319-159">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="e3319-160">其中， *MyAlias* 等于您的用户名。</span><span class="sxs-lookup"><span data-stu-id="e3319-160">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="e3319-p111">在继续之前，请等待提示符返回。首先，您将看到这些组在创建时的样子。然后，您将看到添加用户后的重复组列表。</span><span class="sxs-lookup"><span data-stu-id="e3319-p111">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3319-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3319-164">See also</span></span>

[<span data-ttu-id="e3319-165">连接到 SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3319-165">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="e3319-166">使用 PowerShell 管理 SharePoint Online 网站用户组</span><span class="sxs-lookup"><span data-stu-id="e3319-166">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="e3319-167">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3319-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e3319-168">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="e3319-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
