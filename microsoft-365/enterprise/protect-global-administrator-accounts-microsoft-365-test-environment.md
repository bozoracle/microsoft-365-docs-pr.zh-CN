---
title: 保护 Microsoft 365 企业版测试环境中的全局管理员帐户
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用这些步骤来保护 Microsoft 365 企业版测试环境中的全局管理员帐户。
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695178"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>保护 Microsoft 365 企业版测试环境中的全局管理员帐户

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

您可以通过确保您的管理员帐户尽可能安全，来阻止组织的数字攻击。 本文介绍如何使用 Azure Active Directory (Azure AD) 条件访问策略来保护全局管理员帐户。

在 Microsoft 365 企业版测试环境中保护全局管理员帐户有两个阶段：

1.  创建适用于企业级测试环境的 Microsoft 365。
2.  保护您的专用全局管理员帐户。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果只想使用最低要求以轻型方式测试全局管理员帐户保护，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试全局管理员帐户保护，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试全局管理员帐户保护不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 的目录同步。 此处提供它作为选项，以便您可以测试全局管理员帐户保护并在代表典型组织的环境中进行实验。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>阶段2：配置条件访问策略

首先，创建一个新的用户帐户作为专用全局管理员。

1. 在单独的选项卡上，打开 [Microsoft 365 管理中心](https://admin.microsoft.com/)。
2. 单击 " **用户 > 活动用户**"，然后单击 " **添加用户**"。
3. 在 "**添加用户**" 窗格中，在 "**名字"、"****显示名称**" 和 "**用户名**" 中键入**DedicatedAdmin** 。
4. 单击 " **密码**"，单击 " **让我创建密码**"，然后键入一个强密码。 将此新帐户的密码记录在安全位置。
5. 单击“**下一步**”。
6. 在 " **分配产品许可证** " 窗格中，选择 " **Microsoft 365 E5**"，然后单击 " **下一步**"。
7. 在 " **可选设置** " 窗格中，单击 " **角色**"，然后选择 "管理中心" " **访问** 和 **全局管理员**"。单击 " **下一步**"。
8. 在 " **即将完成** " 窗格中，单击 " **完成添加**"，然后单击 " **关闭**"。

接下来，创建一个名为 "GlobalAdmins" 的新组，并向其添加 DedicatedAdmin 帐户。

1. 在 " **Microsoft 365 管理中心** " 选项卡上，单击左侧导航栏中的 " **组** "，然后单击 " **组**"。
2. 单击 " **添加组**"。
3. 在 " **选择组类型** " 窗格中，选择 " **安全性**"，然后单击 " **下一步**"。
4. 在 " **设置基础知识"** 窗格中，单击 " **创建组**"，然后单击 " **关闭**"。
5. 在 " **查看并完成添加组** 窗格" 中，键入 **GlobalAdmins**，然后单击 " **下一步**"。
7. 在组列表中，单击 " **GlobalAdmins** " 组。
8. 在 " **GlobalAdmins** " 窗格中，单击 " **成员**"，然后单击 " **查看所有和管理成员**"。
9. 在 **GlobalAdmins** 窗格中，单击 " **添加成员**"，选择 " **DedicatedAdmin** " 帐户和全局管理员帐户，然后单击 " **保存" > 关闭 > "关闭**"。

接下来，创建条件访问策略以要求对全局管理员帐户进行多因素身份验证，并在登录风险为 "中" 或 "高" 时拒绝身份验证。

第一个策略要求所有全局管理员帐户使用 MFA。

1. 在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。
2. 单击 " **Azure Active Directory > Security > 条件访问**。
3. 在 " **条件访问–策略** " 窗格中，单击 " **基准策略：要求对管理员的 MFA (preview) **。
4. 在 " **基准策略** " 窗格中，单击 " **立即使用策略" > 保存**。

当登录风险为 "中" 或 "高" 时，第二个策略将阻止对全局管理员帐户进行身份验证。

1. 在 " **条件访问–策略** " 窗格中，单击 " **新建策略**"。
2. 在 "**新建**" 窗格中，在 "**名称**" 中键入**全局管理员**。
3. 在 " **工作分配** " 部分，单击 " **用户和组**"。
4. 在 "**用户和组**" 窗格的 "**包含**" 选项卡上，单击 "选择用户和组" **> 用户和组**"。 >" 选择 "。
5. 在 **选择** 窗格中，单击 " **GlobalAdmins** " 组，然后单击 " **选择 > 完成**"。
6. 在 " **工作分配** " 部分，单击 " **条件**"。
7. 在 "**条件**" 窗格中，单击 "**登录风险**"，对 **"配置**" 单击 **"是"** ，单击 "**高**" 和 "**中**"，然后单击 "**选择**并**完成**"。
8. 在**新**窗格的 "**访问控制**" 部分，单击 "**授予**"。
9. 在 " **授予** " 窗格中，单击 " **阻止访问**"，然后单击 " **选择**"。
10. 在 " **新建** " 窗格中，单击 **"** **启用策略**"，然后单击 " **创建**"。
11. 关闭 " **Azure 门户** " 和 " **Microsoft 365 管理中心** " 选项卡。

若要测试第一个策略，请注销并使用 DedicatedAdmin 帐户登录。 系统会提示您配置 MFA。 这说明正在应用第一个策略。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
