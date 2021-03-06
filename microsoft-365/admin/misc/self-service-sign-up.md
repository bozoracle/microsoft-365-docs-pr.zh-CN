---
title: 在组织中使用自助式注册
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: 了解 Microsoft 365 自助注册和可用自助服务程序，如 Microsoft Power Apps、Microsoft Flow 和 Dynamics 365 for 金融。
ms.openlocfilehash: 8e8ed80cc24e3c6ec0a4a9d408d202495de52adb
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324476"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>在组织中使用自助式注册

自助注册使组织中的用户能够更轻松地注册来自 Microsoft 的联机服务。 我们将此注册过程称为 "自助注册"，因为用户可以注册以使用订阅付费的服务，也可以使用免费服务，而无需让您代表自己执行操作。
  
## <a name="how-self-service-sign-up-works"></a>自助服务注册的工作原理

以下示例介绍如何对学校进行自我注册。 同一过程适用于在其租户中启用了自助式程序的任何组织。
  
1. 学生和教职员成员具有学校电子邮件地址，指示它们与你的机构相关联。 例如，电子邮件地址 jakob@uw.edu 可能指示位于华盛顿大学的学生。
2. 学生和教职员转到 [我们的网站](https://go.microsoft.com/fwlink/p/?LinkId=536628)，并使用其电子邮件地址注册您的组织提供的服务，例如，Microsoft 365 Apps for enterprise。 他们还可以注册以获取我们提供的其他免费服务。
3. 我们验证其电子邮件地址，然后可以立即开始使用 Microsoft 365、Power BI 或其他服务。
4. 作为企业管理员，你可以通过在 Microsoft 365 管理中心的 " **许可** " 页上选择 "订阅" 来查看谁注册了订阅。 这样一来，你可以看到租户中的服务存在新的或无法识别的许可证。 若要控制用户是否可以注册自助服务订阅，请将 [Set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell Cmdlet 与 **AllowAdHocSubscriptions** 参数一起使用。 有关详细信息，请参阅 [如何控制自助服务设置？](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>可用的自助服务程序

以下是当前可用的自助服务程序。 在添加新程序时，将更新此列表。
  
|||||
|:-----|:-----|:-----|:-----|
|**程序** <br/> |**说明** <br/> |**其他信息** <br/> |自助注册的网站 * * * * <br/> |
|Office 365 A1 * * * * <br/> |任何学生或教师都可以使用学校电子邮件地址注册免费的 Office 365，并获取适用于 web 的 Office 应用、1 TB 的 OneDrive 云存储空间、团队和项目网站的 SharePoint Online。  <br/> |[Office 365 教育版技术常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 教育版](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |符合条件的学生和教师可以注册 Office 365 A1 Plus，其中包括上文提到的所有内容以及适用于企业的 Microsoft 365 应用程序。 适用于企业的 Microsoft 365 应用程序是生产力软件，包括 Word、PowerPoint、Excel、Outlook、OneNote、Publisher、Access 和 Skype for Business 等安装在台式计算机或便携式计算机上的软件。  <br/> |[Office 365 教育版技术常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 教育版](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI 使用户能够以直观的新方式可视化数据、共享发现和进行协作。 <br/> 如果你的组织已订阅，你可能还会看到 "Power BI Pro 个人用户试用" 的许可证，它为用户提供了对高级功能的有限、免费访问权限。  <br/> |[组织中的 Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**权限管理服务 (RMS)** <br/> |适用于个人的 RMS 是组织中的用户的免费自助订阅，这些订阅已经发送了受 Azure 权限管理 (Azure RMS) 保护的敏感文件，但其 IT 部门尚未实现 Azure 权限管理 (Azure RMS) 或 Active Directory 权限管理服务 (AD RMS) 。  <br/> |[适用于个人和 Azure 权限管理的 RMS](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft 权限管理门户](https://portal.azure.com/) ，以便您可以检查是否可以打开给定的受权限保护的文档。  <br/> |
|**Microsoft Power Apps** <br/> |在 PowerApps 中，可以通过运行您创建的应用程序或其他人创建并与您共享的应用程序来管理组织数据。 在手机等移动设备上运行的应用程序，也可以通过打开 Dynamics 365 在浏览器中运行这些应用程序。 您可以创建无限多个应用程序-所有这些都不学习 c # 等编程语言。  <br/> |[为 PowerApps 注册自助服务](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**适用于财务的 Dynamics 365** <br/> |为中小型企业获取完整的业务和财务管理解决方案。 Dynamics 365 for 金融使排序、销售、开票和报告变得更加轻松—从第一天开始。  <br/> |[适用于财务的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[适用于财务的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**适用于操作的 Microsoft Dynamics 365** <br/> |提高开展业务的速度。 Dynamics 365 for Operations 中的完整 ERP 工具提供了全球可扩展性和数字智能，可帮助你在你的步调中发展。  <br/> |[适用于操作的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[适用于操作的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource 是基于 Microsoft 云平台构建的软件即服务业务应用程序的目标。 AppSource 功能可扩展 Microsoft 产品（如 Azure、Dynamics 365、Office 365 和 Power BI）功能的数百个应用、加载项和内容包。  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft 合作伙伴激励** <br/> |Microsoft 合作伙伴网络提供了三种类型的成员身份。 每种类型都提供了一系列优势来帮助您的业务增长。 在实现目标时，请在适合您的独特需求的级别加入该计划，以了解更多好处，并在网络中与我们和其他合作伙伴建立关系。  <br/> |[Microsoft 合作伙伴激励](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft 合作伙伴激励](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center 是通过 Microsoft 产品和服务协议 (MPSA) 进行购买的客户的门户。 <br/> |[快速入门：注册 Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft 批量许可证服务中心** <br/> |Microsoft 批量许可证服务中心显示在企业、选择、教育 (校园或学校) 、开放价值、开放许可证和 ISV 版税协议中购买的许可证。  <br/> |[VLSC 培训和资源](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft 教育版** <br/> |通过使用 Minecraft 作为学习的平台，教师可以鼓励和鼓舞每个学生以实现更多，并 ignite 为学习提供热情。 加入一社区教师学习，了解如何使用 Minecraft 解锁学生潜力。  <br/> |[Minecraft 教育版](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft 教育版](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |在组织中上载并共享视频，以改进通信、参与和学习。  <br/> |[注册 &amp; 第0天的体验](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |电力自动化是一种产品，可帮助您在收藏的应用程序和服务之间设置自动工作流，以同步文件、获取通知、收集数据等。  <br/> |[注册并登录以实现自动完成功能](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |使用高级虚拟代理，团队可以使用无需数据科学家或开发人员，轻松创建功能强大的 bot，而无需使用引导式无代码图形界面。 电源虚拟代理解决了当今行业中的 bot 组装中的许多主要问题。 它消除了行业专家和构建 bot 的开发团队之间的缺口，以及识别问题和更新机器人以解决问题的团队之间的持续时间延迟。  <br/> |[许可和访问详细信息](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[注册 Power Virtual 代理](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) 企业到企业 (B2B) 协作允许您邀请外部用户 (或 "来宾用户" ) 使用您付费的 Azure AD 服务。 某些功能是免费的，但对于任何付费的 Azure AD 功能，你可以在你的租户中为员工或非来宾用户拥有的每个 Azure AD 版本许可证邀请最高5个来宾用户。 <br/> |[适用于 Azure AD B2B 协作注册的自助服务](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |