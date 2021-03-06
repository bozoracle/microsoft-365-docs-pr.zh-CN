---
title: 配置具有三层保护的 Teams
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-overview
- m365solution-securecollab
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 保护 Microsoft Teams 中文件的配置建议。
ms.openlocfilehash: aea542d92e981e286062fc07b7e559b5f36427d4
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307723"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>配置具有三层保护的 Teams

本系列中的文章为如何在 Microsoft Teams 中配置团队及其关联 SharePoint 网站以实现通过轻松协作权衡安全性的文件保护提供了相关建议。

本文定义了四个不同的配置，首先介绍的是具有最开放的共享策略的公共团队。 每个额外配置均表示有意义的保护设置，对 Teams 中存储的文件的访问和协作限定为一组相关团队成员。 

本文中的配置符合 Microsoft 针对数据、标识和设备的三层保护的建议：

- 基线保护

- 敏感保护

- 高度敏感保护

有关这些保护层以及针对每层建议的功能的详细信息，请参阅[面向企业架构师的 Microsoft 云图解](https://docs.microsoft.com/microsoft-365/solutions/cloud-architecture-models)。


## <a name="three-tiers-at-a-glance"></a>三个层级概览

下表总结了各层的配置。 使用这些配置作为起点建议并调整网站配置，以满足组织的需求。 可能不需要每一层。

||基准（公共）|基准（专用）|敏感|高度敏感|
|:-----|:-----|:-----|:-----|:-----|
|专用或公用团队|公开|Private|Private|Private|
|谁可以访问？|组织中的每个人（包括 B2B 用户）。|仅限团队成员。 其他人可以请求访问关联的网站。|仅限团队成员。|仅限团队成员。|
|专用频道|所有者和成员可以创建专用频道|所有者和成员可以创建专用频道|仅所有者可创建专用频道|仅所有者可创建专用频道|
|网站级别来宾访问|**新来宾和现有来宾**（默认值）。|**新来宾和现有来宾**（默认值）。|**新来宾和现有来宾** 或 **仅组织中的人员** 取决于团队需求。|**新来宾和现有来宾** 或 **仅组织中的人员** 取决于团队需求。|
|网站共享设置|**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。|**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。|**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。|**仅网站所有者可以共享文件、文件夹和网站**。<br>访问请求**关闭**。|
|网站级别未托管设备的访问|**从桌面版应用程序、移动应用程序和 web 完全访问**（默认值）。|**从桌面版应用程序、移动应用程序和 web 完全访问**（默认值）。|**允许限制性的 web 访问**。|**阻止访问**。|
|默认共享链接类型|**仅组织内部人员**|**仅组织内部人员**|**特定人员**|**现有访问权限者**|
|敏感度标签|无|无|敏感度标签用于对团队进行分类并控制来宾共享和未托管设备访问。|敏感度标签用于对团队进行分类并控制来宾共享和未托管设备访问。 还可在文件上使用标签对文件进行加密。|

[具有安全隔离的团队](secure-teams-security-isolation.md)是高度敏感选项的变体，为一个团队使用唯一敏感度标签，从而提供更高的安全性。 可以使用此标签来加密文件，只有该团队成员才能读取它们。

基线保护同时公共和私人团队。 组织中的任何人均可发现和访问公共团队。 只有团队成员可以发现和访问私人团队。 这两种配置都将共享 SharePoint 网站的共享限制为团队所有者，以帮助进行权限管理。

敏感和高度敏感保护团队是私有团队，在该团队中对关联站点的共享和访问请求受到限制，并且敏感度标签用于设置有关来宾共享、设备访问和内容加密策略。

## <a name="sensitivity-labels"></a>敏感度标签

敏感层和高度敏感层使用敏感度标签来帮助保护团队和其文件。 为实现这些层，必须启用[用于保护 Microsoft Teams、Office 365 和 SharePoint 网站中内容的敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

虽然基线层不需要敏感度标签，但请考虑创建“常规”标签，然后要求标记所有团队。 这将有助于确保用户在创建团队时就敏感度做出有意识的选择。 如果计划部署敏感或高度敏感层，建议创建一个“常规”标签，该标签可用于基线团队和不敏感的文件。

如果不熟悉敏感度标签，建议阅读[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels)以开始使用。 

如果已经在组织中推出了敏感度标签，请考虑敏感和高度敏感层中所使用的标签如何与整体标签策略配合使用。 

## <a name="sharing-the-sharepoint-site"></a>共享 SharePoint 网站

每个团队都有存储文档的关联 SharePoint 网站。 （这是团队渠道中的“**文件**”选项卡。）SharePoint 网站保留自己的权限管理，但关联到团队权限。 团队所有者被包含为网站所有者，而团队成员被包含为关联网站中的站点成员。

生成的权限允许：

- 团队所有者管理网站，并对网站内容拥有完全控制权。
- 团队成员在网站上创建和编辑文件。 

默认情况下，团队所有者和成员可以与团队外部的人员共享网站本身，而无需将其实际添加到团队中。 建议不要使用此方法，因为这会让用户管理变得复杂，并可能会导致非团队成员的人员能够在团队拥有者不知情的情况下存取团队文件。 为了防止这种情况，从基线保护级别开始，我们建议仅允许所有者直接共享站点。

尽管团队没有只读权限选项，但 SharePoint 网站有此权限。 如果你的合作伙伴组利益干系人能够查看团队文件但是不能编辑，考虑直接将其添加至具有“读取”权限的 SharePoint 网站。

## <a name="sharing-files-and-folders"></a>共享文件和文件夹

默认情况下，团队所有者和成员都可以与团队外部的人员共享文件和文件夹。 如果允许来宾共享，则其中可能包括组织外部人员。 在所有三个层中，我们都会更新默认共享链接类型，有助于避免意外的过度共享。 在高度敏感层中，我们仅将这种共享限制为团队所有者。

## <a name="guest-sharing"></a>来宾共享

如果需要与组织外部人员进行协作，建议配置 [SharePoint 和 OneDrive 与 Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) 集成，以获得最佳的共享和管理体验。

默认情况下，团队来宾共享处于关闭状态，但 Office 365 组（存储团队成员资格）和 SharePoint 的共享处于打开状态。 我们在基线层中启用 Teams共享，如果需要，可以使用敏感度标签在敏感层和高度敏感层中将其关闭。

敏感度标签仅影响团队的来宾共享。 关联 SharePoint 网站的来宾共享设置是单独控制的，我们协调敏感层和高度敏感层的设置。

在高度敏感层，我们将敏感度标签配置为加密应用标签的文件。 如果需要来宾访问这些文件，必须在创建标签时必须授予他们权限。

如果需要与组织外部的人员进行协作，强烈建议基线层和敏感层或高度敏感层启用来宾共享。 相比将文件作为附件发送到电子邮件中，Microsoft 365 的来宾共享功能提供了更为安全和可管理的共享体验。 用户使用不受管制的消费产品与合法的外部合作者共享时，还降低了影子 IT 的风险。

请参阅以下参考材料，为组织创建安全高效的来宾共享环境：

- [有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)
- [在与组织外人员共享文件时限制意外公开信息](share-limit-accidental-exposure.md)
- [创建安全的来宾共享环境](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>非托管设备的访问

对于敏感层和高度敏感层，我们使用敏感度标签限制对 SharePoint 内容的访问。 Azure AD 条件访问提供很多用于确定用户如何访问 Microsoft 365 的选项，包括基于位置、风险、设备合规性和其他因素的限制。 建议阅读[什么是条件访问？](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)，并考虑哪些其他策略可能适用于你的组织。

## <a name="next-step"></a>后续步骤

首先[配置基线保护级别](configure-teams-baseline-protection.md)。 如果需要，可在基线上添加[敏感保护](configure-teams-sensitive-protection.md)和[高度敏感保护](configure-teams-highly-sensitive-protection.md)。

## <a name="see-also"></a>另请参阅

[Microsoft Teams 中的安全性和合规性](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[安全与合规中心警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
