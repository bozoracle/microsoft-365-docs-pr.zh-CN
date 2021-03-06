---
title: 为 Microsoft 365 企业版测试环境自动化许可和组成员身份
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685554"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>为 Microsoft 365 企业版测试环境自动化许可和组成员身份

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。 动态组成员身份根据用户帐户属性（如部门或国家/地区）添加或删除组中的成员。 本文将逐步引导您在 Microsoft 365 企业版测试环境中进行演示。

在 Microsoft 365 企业版测试环境中设置自动许可和动态组成员身份有两个阶段：

1. 创建适用于企业级测试环境的 Microsoft 365。
2. 配置和测试动态组成员身份和自动许可。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果只想使用最低要求以轻型方式测试自动许可和组成员身份，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试自动授权和组成员身份，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>第2阶段：配置和测试动态组成员身份和自动许可

首先，创建一个新的 Sales 组并添加一个动态组成员身份规则，以便将部门设置为 "销售" 的用户帐户自动添加到 "销售" 组中。

1. 使用 Internet 浏览器的专用实例，使用 Microsoft 365 E5 测试实验室订阅的全局管理员帐户登录 [microsoft 365 管理中心](https://admin.microsoft.com) 。
2. 在浏览器的一个单独的选项卡上，转到 Azure 门户处 [https://portal.azure.com](https://portal.azure.com) 。
3. 在 Azure 门户中，在搜索框中键入 **组** ，然后单击 " **组**"。
4. 在 " **所有组** " 窗格中，单击 " **新建组**"。
5. 在 " **组类型**" 中，选择 " **Microsoft 365**"。
6. 在 " **组名称**" 中，键入 **Sales**。
7. 在 " **成员身份类型**" 中，选择 " **动态用户**"。
8. 单击 " **动态用户成员**"。
9. 在 " **动态成员身份规则** " 窗格中： 
   - 选择 " **部门** " 属性。
   - 选择 " **等于** " 运算符。
   - 键入**值**中的**销售额**。
10. 单击“保存”****。
11. 单击“**创建**”。

接下来，配置 "销售" 组，以便自动向成员分配 Microsoft 365 E5 许可证。

1. 单击 " **销售** " 组，然后单击 " **许可证**"。
2. 在 " **更新许可证分配** " 窗格中，选择 " **Microsoft 365 E5**"，然后单击 " **保存**"。
3. 关闭浏览器中的 Azure 门户选项卡。

接下来，在用户4帐户上测试动态组成员身份和自动许可。 

1. 在浏览器中的 " **Microsoft Office 主页** " 选项卡上，单击 " **管理**"。
2. 在 " **Microsoft 365 管理中心** " 选项卡上，单击 " **活动用户**"。
3. 在 " **活动用户** " 页上，单击 " **用户 4** " 帐户。
4. 在 "**用户 4** " 窗格中，单击 "**产品许可证**" 的 "**编辑**"。
5. 在 " **产品许可证** " 窗格上，禁用 **Microsoft 365 E5** 许可证，然后单击 " **保存" > "关闭**"。
6. 在 "User 4" 帐户的 "属性" 中，确认未分配任何产品许可证，并且没有组成员身份。
7. 单击**Edit** "编辑**联系人信息**"。
8. 在 " **编辑联系人信息** " 窗格中，单击 " **联系人信息**"。
9. 在 " **部门** " 字段中，键入 **Sales**，然后单击 " **保存" > "关闭**"。
10. 等待几分钟，然后定期单击 "用户 4" 帐户窗格右上角的 "刷新" 图标。 

您应该会看到以下内容：

- 更新了**Sales**组的**组成员身份**属性。
- 使用**Microsoft 365 E5**许可证更新的 "**产品许可证**" 属性。

请参阅以下文章以在生产环境中部署动态组成员身份和自动许可：

- 链接 TBD
- 链接 TBD

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
