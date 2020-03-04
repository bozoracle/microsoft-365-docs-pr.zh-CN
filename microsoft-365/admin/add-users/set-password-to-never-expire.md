---
title: 将个人用户密码设置为永不过期
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 了解如何使用 Windows PowerShell 将某些个人用户密码设置为永不过期。
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238141"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="7f8e9-103">将个人用户密码设置为永不过期</span><span class="sxs-lookup"><span data-stu-id="7f8e9-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="7f8e9-104">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="7f8e9-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="7f8e9-105">在 "管理中心" 中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全 & 隐私</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="7f8e9-106">选择 "**密码策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="7f8e9-107">如果密码设置为永不过期，请将切换设置为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="7f8e9-108">您将获得用于指定密码过期前的天数的选项。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-108">You'll get the option to specify the number of days until passwords expire.</span></span> 


## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="7f8e9-109">为单个用户设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="7f8e9-109">Set the password expiration policy for individual users</span></span> 

<span data-ttu-id="7f8e9-110">Microsoft 云服务的全局管理员可以使用 Windows PowerShell 的 Microsoft Azure AD 模块将密码设置为对特定用户不过期。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="7f8e9-111">您还可以使用 Windows PowerShell cmdlet 删除永不过期的配置，或查看设置为永不过期的用户密码。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span> 

<span data-ttu-id="7f8e9-112">本指南适用于其他提供商，如 Intune 和 Office 365，后者还依赖 Azure AD 进行标识和目录服务。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="7f8e9-113">密码过期是策略中唯一可以更改的部分。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="7f8e9-114">只能将未通过目录同步同步的用户帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="7f8e9-115">有关目录同步的详细信息，请参阅[CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>


### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="7f8e9-116">如何检查密码的过期策略</span><span class="sxs-lookup"><span data-stu-id="7f8e9-116">How to check the expiration policy for a password</span></span>

* <span data-ttu-id="7f8e9-117">运行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-117">Run one of the following commands:</span></span>

   * <span data-ttu-id="7f8e9-118">若要查看是否将单个用户的密码设置为永不过期，请使用 UPN （例如， *user@contoso.onmicrosoft.com*）或要检查的用户的用户 ID 运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-118">To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
<span data-ttu-id="7f8e9-119">示例：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-119">Example:</span></span>
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * <span data-ttu-id="7f8e9-120">若要查看所有用户的 "**密码永不过期**" 设置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span> 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* <span data-ttu-id="7f8e9-121">若要使用名为**ReportPasswordNeverExpires**的当前用户的桌面上的 Html 中的所有用户获取报告，PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="7f8e9-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* <span data-ttu-id="7f8e9-122">使用名为**ReportPasswordNeverExpires**的当前用户的桌面上的 PasswordNeverExpires 中的所有用户获取报告</span><span class="sxs-lookup"><span data-stu-id="7f8e9-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a><span data-ttu-id="7f8e9-123">将密码设置为过期</span><span class="sxs-lookup"><span data-stu-id="7f8e9-123">Set a password to expire</span></span>

<span data-ttu-id="7f8e9-124">运行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-124">Run one of the following commands:</span></span>

   * <span data-ttu-id="7f8e9-125">若要设置一个用户的密码以使密码过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * <span data-ttu-id="7f8e9-126">若要将组织中所有用户的密码设置为过期，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="7f8e9-127">将密码设置为永不过期</span><span class="sxs-lookup"><span data-stu-id="7f8e9-127">Set a password to never expire</span></span>

<span data-ttu-id="7f8e9-128">运行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-128">Run one of the following commands:</span></span>

   * <span data-ttu-id="7f8e9-129">若要将一个用户的密码设置为永不过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span> 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * <span data-ttu-id="7f8e9-130">若要将组织中所有用户的密码设置为永不过期，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8e9-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span> 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > <span data-ttu-id="7f8e9-131">密码根据属性`-PasswordPolicies DisablePasswordExpiration`设置为 "仍存在`pwdLastSet`年龄"。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="7f8e9-132">如果将用户密码设置为永不过期，然后设置为 90 + 天，则密码将过期。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="7f8e9-133">根据`pwdLastSet`属性，如果将过期时间更改为`-PasswordPolicies None`，则所有`pwdLastSet`早于90天的密码都需要用户在下次登录时更改。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="7f8e9-134">此更改可能会影响大量用户。</span><span class="sxs-lookup"><span data-stu-id="7f8e9-134">This change can affect a large number of users.</span></span> 