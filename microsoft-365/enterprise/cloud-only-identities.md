---
title: Microsoft 365 仅限云身份标识
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 介绍如何在 Microsoft 365 订阅使用仅云标识时创建用户和组。
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327923"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365 仅限云身份标识

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

对于仅限云身份，你的所有用户、组和联系人都存储在 Microsoft 365 订阅 (Azure AD) 租户的 Azure Active Directory 中。 下面是仅限云身份的基本组件。
 
![仅限云标识的基本组件](../media/about-microsoft-365-identity/cloud-only-identity.png)

可以通过多种方式对组织中的用户及其用户帐户进行分类。 例如，一些是员工，且具有永久状态。 有些是具有临时状态的供应商、承包商或合作伙伴。 有些外部用户没有用户帐户，但仍必须被授予对特定服务和资源的访问权限，以支持交互和协作。 例如：

- 租户帐户表示组织中许可访问云服务的用户。

- 企业到企业 (B2B) 帐户表示组织外部邀请加入协作的用户。

对组织中的用户类型进行分组。 分组是什么？ 例如，您可以将用户按高级功能或目标分组到您的组织。

此外，可以将某些云服务与组织外部没有任何用户帐户的用户共享，而且你还需要标识这些用户组。

您可以使用 Azure AD 中的组来实现多种目的，从而简化云环境的管理。 例如，使用 Azure AD 组，您可以执行以下操作：

- 使用基于组的许可将 Microsoft 365 的许可证立即分配给您的用户帐户，然后在将其添加为成员时自动。
- 根据用户帐户属性（如部门名称）动态地向特定组添加用户帐户。
- 自动为用户预配软件 (SaaS) 应用程序，并使用多重身份验证 (MFA) 和其他条件访问策略来保护对这些应用程序的访问。
- 为 SharePoint Online 团队网站设置权限和访问权限级别。

## <a name="next-steps-for-cloud-only-identity"></a>仅限云标识的后续步骤

- [管理用户帐户](manage-microsoft-365-accounts.md)
- [向用户帐户分配许可证](assign-licenses-to-user-accounts.md)
- [管理组和组成员身份](manage-microsoft-365-groups.md)
- [管理用户帐户密码](manage-microsoft-365-passwords.md)
