---
title: 更改用户名和电子邮件地址
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: '了解全局管理员可以如何更改用户的电子邮件地址和显示名称。 '
ms.openlocfilehash: fedc1532bfec246392180d386a6960dbb08bd137
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079709"
---
# <a name="change-a-user-name-and-email-address"></a>更改用户名和电子邮件地址

例如，若用户结婚和更改姓氏，则可能需要更改该用户的电子邮件地址和显示名称。

请观看有关更改用户电子邮件地址的简短视频。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="change-a-users-email-address"></a>更改用户的电子邮件地址

必须是[全局管理员](about-admin-roles.md)才能执行这些步骤。 

::: moniker range="o365-worldwide"
 
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 选择用户的姓名，然后在“**帐户**”选项卡上选择“**管理用户名**”。
    
3. 在第一个框中，键入新电子邮件地址的第一部分。 如果已将自己的域添加到 Microsoft 365，请使用下拉列表为新电子邮件别名选择域。 

4. 选择“**保存更改**”。

   
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 在第一个框中，键入新电子邮件地址的第一部分。 如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。

4. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 在第一个框中，键入新电子邮件地址的第一部分。 如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。

4. 选择“**保存**”。

::: moniker-end

**重要提示**：如果收到错误消息，请参阅[处理错误消息](#resolve-error-messages)。

## <a name="set-the-primary-email-address"></a>设置主要电子邮件地址

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 选择用户的姓名，然后在“**帐户**”选项卡上选择“**管理电子邮件别名**”。

3. 对于要为该用户设置为主要电子邮件地址的地址，选择“**设置为主要电子邮件地址**”。 
    
    **重要提示**：如果是从 GoDaddy 或提供管理控制台的另一合作伙伴服处购买的 Microsoft 365，则不会看到“设为主要别名”选项。请改为登录到 GoDaddy/合作伙伴的管理控制台，设置主要别名。 
    
    此外，只有全局管理员才能看到此选项。如果没有看到此选项，则表明你不具有更改用户名称和主要电子邮件地址的权限。
  
4. 你会看到一个大的黄色警告，提示你将更改用户的登录信息。 依次选择“**保存**”和“**关闭**”。
    
5. 为用户提供以下信息：
 
  - 此更改可能需要一些时间。
  
  - 新的用户名。登录 Microsoft 365 时需要此用户名。
    
  - 如果用户使用的是 Skype for Business Online，他们必须重新安排其组织召开的所有 Skype for Business Online 会议并告知其外部联系人以更新联系人信息。

  - 如果他们使用的是 OneDrive，则此位置的 URL 已更改。 如果他们的 OneDrive 中有 OneNote 笔记本，则可能需要在 OneNote 中关闭后再重新打开笔记本。 如果他们在 OneDrive 中具有共享文件，则指向这些文件的链接可能不起作用，这种情况下，用户可以重新共享。    
  
  - 如果还更改了密码，系统将提示他们在移动设备上输入新密码，否则将不会同步。
  
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 对于要为该用户设置为主要电子邮件地址的地址，选择“**设置为主要电子邮件地址**”。 
    
    **重要提示**：如果是从 GoDaddy 或提供管理控制台的另一合作伙伴服处购买的 Microsoft 365，则不会看到“设为主要别名”选项。请改为登录到 GoDaddy/合作伙伴的管理控制台，设置主要别名。 
    
    此外，只有全局管理员才能看到此选项。如果没有看到此选项，则表明你不具有更改用户名称和主要电子邮件地址的权限。
  
4. 你会看到一个大的黄色警告，提示你将更改用户的登录信息。 依次选择“**保存**”和“**关闭**”。
    
5. 告知用户以下信息：
 
  - 此更改可能需要一些时间才会生效。
  
  - 他们的新用户名是什么。登录 Microsoft 365 时需要此用户名。
    
  - 如果用户使用 Skype for Business Online，需告知用户重新安排其组织召开的所有 Skype for Business Online 会议并通知其需要告知外部联系人以更新旧联系人信息。

  - 如果他们使用的是 OneDrive，请告诉他们此位置的 URL 已更改。 如果他们的 OneDrive 中有 OneNote 笔记本，可能需要在 OneNote 中关闭并重新打开笔记本。 如果他们具有 OneDrive 中的共享文件，则指向这些文件的链接可能不起作用，这种情况下，用户可以重新共享。    
  
  - 如果还更改了密码，需告知用户系统将提示他们在移动设备上输入新密码，否则将不会同步。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 对于要为该用户设置为主要电子邮件地址的地址，选择“**设置为主要电子邮件地址**”。 
    
    **重要提示**：如果是从 GoDaddy 或提供管理控制台的另一合作伙伴服处购买的 Microsoft 365，则不会看到“设为主要别名”选项。请改为登录到 GoDaddy/合作伙伴的管理控制台，设置主要别名。 
    
    此外，只有全局管理员才能看到此选项。如果没有看到此选项，则表明你不具有更改用户名称和主要电子邮件地址的权限。
  
4. 你会看到一个大的黄色警告，提示你将更改用户的登录信息。 依次选择“**保存**”和“**关闭**”。
    
5. 告知用户以下信息：
 
  - 此更改可能需要一些时间才会生效。
  
  - 他们的新用户名是什么。登录 Microsoft 365 时需要此用户名。
    
  - 如果用户使用 Skype for Business Online，需告知用户重新安排其组织召开的所有 Skype for Business Online 会议并通知其需要告知外部联系人以更新旧联系人信息。

  - 如果他们使用的是 OneDrive，请告诉他们此位置的 URL 已更改。 如果他们的 OneDrive 中有 OneNote 笔记本，可能需要在 OneNote 中关闭并重新打开笔记本。 如果他们具有 OneDrive 中的共享文件，则指向这些文件的链接可能不起作用，这种情况下，用户可以重新共享。    
  
  - 如果还更改了密码，需告知用户系统将提示他们在移动设备上输入新密码，否则将不会同步。

::: moniker-end
  
## <a name="change-a-users-display-name"></a>更改用户的显示名称

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择用户的姓名，然后在“**帐户**”选项卡上选择“**管理联系人信息**”。

3. 在“**显示名称**”框中，键入该用户的新名称，然后选择“**保存**”。

    如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”，请参阅[处理错误消息](#resolve-error-messages)。

此更改最多可能需要 24 小时才会在所有服务中生效。更改生效后，用户需要使用更新后的用户名登录 Outlook、Skype for Business 和 SharePoint。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择该用户。 在浮出窗格中的“**联系人信息**”旁，选择“**编辑**”。

3. 在“**显示名称**”框中，键入该用户的新名称，然后选择“**保存**”。

    如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”，请参阅[处理错误消息](#resolve-error-messages)。

此更改最多可能需要 24 小时才会在所有服务中生效。更改生效后，用户需要使用更新后的用户名登录 Outlook、Skype for Business 和 SharePoint，因此请务必将更改告知用户。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择该用户。 在浮出窗格中的“**联系人信息**”旁，选择“**编辑**”。

3. 在“**显示名称**”框中，键入该用户的新名称，然后选择“**保存**”。

    如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”，请参阅[处理错误消息](#resolve-error-messages)。

此更改最多可能需要 24 小时才会在所有服务中生效。更改生效后，用户需要使用更新后的用户名登录 Outlook、Skype for Business 和 SharePoint，因此请务必将更改告知用户。

::: moniker-end

## <a name="resolve-error-messages"></a>解决错误消息

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>“找不到与参数名称‘EmailAddresses’匹配的参数”

如果收到错误消息：“**找不到与参数名称 EmailAddresses 匹配的参数**”，则表明完成租户或自定义域设置（如果最近添加了一个）所需的时间会更长。设置过程最多需要 4 个小时才能完成。稍等片刻，待设置过程完成后重试。如果问题仍然存在，请致电[支持人员](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)，让他们为你执行完全同步。
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>“很抱歉，无法编辑该用户。 请查看用户信息，请查看用户信息并重试”

如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”， 这意味着你不是全局管理员，不具有更改用户名的权限。 找到企业中的全局管理员，请他们进行更改。


## <a name="what-to-do-with-old-email-addresses"></a>对旧电子邮件地址的处理

用户先前的主要电子邮件地址将作为其他电子邮件地址保留。**强烈建议不要删除旧电子邮件地址。**
  
某些人可能会继续向该用户的旧电子邮件地址发送电子邮件，删除此地址可能导致 NDR 故障。Microsoft 会自动将邮件路由到新地址。此外，不要重复使用旧的 SMTP 电子邮件地址和将其应用到新帐户。这也会导致 NDR 故障或传递到计划外的邮箱。
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>用户的脱机通讯簿未与全局地址列表同步怎么办？

如果用户使用的是 Exchange Online，或其帐户与组织的本地 Exchange 环境链接，则在你尝试更改用户名和电子邮件地址时可能会看到以下错误：“此用户已与你的本地 Active Directory 同步。某些详细信息仅可通过本地 Active Directory 进行编辑。”
  
这是由 Microsoft 联机电子邮件路由地址 (MOERA) 引起的。MOERA 通过 Active Directory 中的用户 _userPrincipalName_ 属性进行构造，其在初始同步期间自动分配到云帐户，且创建后不可在 Microsoft 365 中修改或删除。随后，可在 Active Directory 中更改用户名，但这不会更改 MOERA，并且可能会在全局地址列表中显示新更改的名称方面遇到问题。 
  
若要修复此问题，请使用 Microsoft 365 管理员凭据登录到[用于 PowerShell 的 Azure Active Directory 模块]( https://go.microsoft.com/fwlink/?LinkId=823193)， 然后使用以下语法： 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> 这会更改用户的 **userPrincipalName** 属性，不会影响其 Microsoft 联机电子邮件路由地址 (MOERA) 电子邮件地址。 但是，最佳做法是使用户的登录 UPN 与其主要 SMTP 地址相匹配。 
  
若要了解如何使用 Windows Server 2003 及更早版本在 Active Directory 中更改用户的用户名，请参阅[重命名用户帐户](https://go.microsoft.com/fwlink/?LinkId=809091)。
  
## <a name="related-articles"></a>相关文章

[管理员：重置一个或多个用户的密码](reset-passwords.md)
  
[为用户添加另一个电子邮件地址](../email/add-another-email-alias-for-a-user.md)
