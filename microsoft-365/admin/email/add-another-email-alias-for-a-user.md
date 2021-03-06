---
title: 添加用户的其他电子邮件别名
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何将多个电子邮件地址（称为 "电子邮件别名"）与 Microsoft 365 商业版帐户相关联。 '
ms.openlocfilehash: 030d8022a8503f6b383d03b0dd97720f66d8f2f6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080011"
---
# <a name="add-another-email-alias-for-a-user"></a>为用户添加另一个电子邮件别名

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end
  
本文适用于具有业务订阅的 Microsoft 365 管理员。 不适用于家庭用户。
  
Microsoft 365 中的主电子邮件地址通常是创建帐户时分配给用户的电子邮件地址。 当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。 他们还可以有多个电子邮件地址与他们的 Microsoft 365 商业版帐户关联。 其他地址称为别名。 
  
例如，假设 Jenna 具有电子邮件地址 jenna@contosoco.com，但她还希望在 jen@contosoco.com 中接收电子邮件，因为某些人会按该名称引用她。 您可以为她创建别名，以便这两个电子邮件地址都转到 Jenna 的收件箱。
<br><br>  
  
最多可为一个用户创建 400 个别名。 无需其他费用或许可证。
  
> [!Tip]
> 如果您希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建一个共享邮箱。 若要了解详细信息，请参阅[创建共享邮箱](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>向用户添加电子邮件别名
<a name="AddEmailPreview"> </a>

您必须具有[管理员权限](../add-users/about-admin-roles.md)才能执行此操作。 

  
::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在 "**活动用户**" 页上，选择 "用户 >**管理电子邮件别名**。 如果没有为用户分配许可证，则不会看到此选项。 
    
3. 选择 " **+ 添加别名**"，然后输入用户的新别名。   
    
    > [!Important] 
    > 如果您收到错误消息 "**找不到与参数名匹配的参数" EmailAddresses**"，这意味着完成对租户的设置或自定义域（如果您最近添加了一个）会花一些时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
    
  
    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅[add a domain To Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 
  
     
5. 完成后，请选择 "**保存更改**"。
    
6. 等待24小时，以在整个 Microsoft 365 中填充新别名。
    
    用户现在将拥有一个主地址和一个别名。 例如，发送到陶湘 Hoffman 的主要地址、Eliza@NodPublishers.com 和她的别名 Sales@NodPublishers.com 的所有邮件都将转到陶湘的 "收件箱"。
    
  
7. **当用户回复时，"*发件*人" 地址将成为她的主要电子邮件别名。** 例如，假设向 Sales@NodPublishers.com 发送了一封邮件，并且该邮件到达陶湘的收件箱中。 陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。 
    
    
2. 在" **活动用户**"页面上，选择要编辑的用户名。

3. 在 "**用户名/电子邮件别名**" 旁边，选择 "**编辑**"。

    > [!Important] 
    > 如果您收到错误消息 "**找不到与参数名匹配的参数" EmailAddresses**"，这意味着完成对租户的设置或自定义域（如果您最近添加了一个）会花一些时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。

4. 在 "**别名**" 下的文本框中，键入新电子邮件别名的第一部分。 如果您向 Microsoft 365 添加了自己的域，则可以使用下拉列表选择新电子邮件别名的域。 然后，选择“**添加**”。

    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅[add a domain To Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 

5. 完成后，选择“**保存**”。

6. 等待24小时，以在整个 Microsoft 365 中填充新别名。 
    
    用户现在将拥有一个主地址和一个别名。 例如，发送到陶湘 Hoffman 的主要地址、Eliza@NodPublishers.com 和她的别名 Sales@NodPublishers.com 的所有邮件都将转到陶湘的 "收件箱"。
    
  
7. **当用户回复时，"*发件*人" 地址将成为她的主要电子邮件别名。** 例如，假设向 Sales@NodPublishers.com 发送了一封邮件，并且该邮件到达陶湘的收件箱中。 陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

    
2. 在" **活动用户**"页面上，选择要编辑的用户名。

3. 在 "**用户名/电子邮件别名**" 旁边，选择 "**编辑**"。

    > [!Important] 
    > 如果您收到错误消息 "**找不到与参数名匹配的参数" EmailAddresses**"，这意味着完成对租户的设置或自定义域（如果您最近添加了一个）会花一些时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。

4. 在 "**别名**" 下的文本框中，键入新电子邮件别名的第一部分。 如果您向 Microsoft 365 添加了自己的域，则可以使用下拉列表选择新电子邮件别名的域。 然后，选择“**添加**”。

    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅[add a domain To Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 

5. 完成后，选择“**保存**”。

6. 等待24小时，以在整个 Microsoft 365 中填充新别名。 
    
    用户现在将拥有一个主地址和一个别名。 例如，发送到陶湘 Hoffman 的主要地址、Eliza@NodPublishers.com 和她的别名 Sales@NodPublishers.com 的所有邮件都将转到陶湘的 "收件箱"。
    
  
7. **当用户回复时，"*发件*人" 地址将成为她的主要电子邮件别名。** 例如，假设向 Sales@NodPublishers.com 发送了一封邮件，并且该邮件到达陶湘的收件箱中。 陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>您是否收到 "找不到与参数名称 EmailAddresses 匹配的参数？"


如果您收到错误消息 "**找不到与参数名称 EmailAddresses 匹配的参数**"，这意味着完成设置租户或自定义域（如果最近添加了一个）会花一些时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>是否从 GoDaddy 或另一合作伙伴处购买订阅？


如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。
  
## <a name="related-articles"></a>相关文章

[从不同的地址发送电子邮件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[更改用户名和电子邮件地址](../add-users/change-a-user-name-and-email-address.md)
  

