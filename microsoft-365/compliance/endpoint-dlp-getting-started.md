---
title: Microsoft 365 终结点数据丢失防护（预览）入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 设置 Microsoft 365 终结点数据丢失防护，以监视文件活动并将针对这些文件的保护措施实施到终结点。
ms.openlocfilehash: 08e2bd43b4337087b401244b7dc4cf80a26aaf06
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131666"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a>终结点数据丢失防护（预览）入门

Microsoft 终结点数据丢失防护（终结点 DLP）是 Microsoft 365 数据丢失防护 (DLP) 功能套件的一部分，可用于发现和保护 Microsoft 365 服务中的敏感项目。 有关 Microsoft 所有 DLP 产品/服务的更多信息，请参阅[数据丢失防护概述](data-loss-prevention-policies.md)。 若要了解有关终结点 DLP 的详细信息，请参阅[了解终结点数据丢失防护（预览）](endpoint-dlp-learn-about.md)

通过 Microsoft 终结点 DLP，你可以监视 Windows 10 设备并检测何时使用和共享敏感项目。 这为你提供了所需的可见性和控制力，以确保正确使用和保护它们，并帮助防止可能危害它们的危险行为。

## <a name="before-you-begin"></a>准备工作

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

在开始使用终结点 DLP 之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何加载项。 若要访问和使用终结点 DLP 功能，必须具有这些订阅或加载项中的一个。

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 合规
- Microsoft 365 A5 合规
- Microsoft 365 E5 信息保护和治理
- Microsoft 365 A5 信息保护和治理

### <a name="permissions"></a>权限

若要启用设备管理，你使用的帐户必须是以下任何一个角色的成员：

- 全局管理员
- 安全管理员
- 合规性管理员

如果要使用自定义帐户查看设备管理设置，该帐户必须具有以下角色之一：

- 全局管理员
- 合规性管理员
- 合规性数据管理员
- 全局读取者

如果要使用自定义帐户访问载入/载出页面，该帐户必须具有以下角色之一：

- 全局管理员
- 合规性管理员

如果要使用自定义帐户打开/关闭设备监视，该帐户必须具有以下角色之一：

- 全局管理员
- 合规性管理员

可在[活动资源管理器](data-classification-activity-explorer.md)中查看终结点 DLP 中的数据。 有四个角色可向活动资源管理器授予权限，用于访问数据的帐户必须是其中任何一个的成员。

- 全局管理员
- 合规性管理员
- 安全管理员
- 合规性数据管理员

### <a name="prepare-your-endpoints"></a>准备终结点

确保你计划部署终结点 DLP 的 Windows 10 设备满足这些要求。

1. 必须运行 Windows 10 内部版本 1809 或更高版本。
2. 所有设备必须[已加入 Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) 或已加入混合 Azure AD。
3. 在终结点设备上安装 Microsoft Chromium Edge 浏览器，以对上传到云活动执行策略操作。 请参见[下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。

## <a name="onboarding-devices-into-device-management"></a>将设备载入设备管理

 必须先启用设备监视功能并载入终结点，然后才能监视和保护设备上的敏感项目。 这两项操作都在 Microsoft 365 合规门户中完成。

当你想载入尚未载入的设备时，你需要下载适当的脚本并将其部署到那些设备上。 按照[载入设备程序](endpoint-dlp-getting-started.md#onboarding-devices)进行操作。

已载入到 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) 的设备将显示在“托管设备”列表中。 请按照“[与设备载入到 Microsoft Defender for Endpoint 的过程](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint)”进行操作。

### <a name="onboarding-devices"></a>载入设备

在此部署方案中，你将载入尚未载入的设备，并且只想监视和保护敏感项目，防止 Windows 10 设备上发生意外共享。

1. 打开“[Microsoft 合规中心](https://compliance.microsoft.com)”。
2. 打开合规中心设置页面，然后选择“**载入设备**”。 

   ![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > 设备载入通常需要大约 60 秒才能启用，请先等待 30 分钟，然后再与 Microsoft 支持人员接洽。

3. 选择“**设备管理**”，以打开“**设备**”列表。 在载入设备之前，此列表将为空。
4. 选择“**载入**”以开始载入流程。
5. 从“**部署方法**”列表中选择要部署到这些额外设备的方式，然后**下载程序包**。

   ![部署方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. 按照[适用于 Windows 10 计算机的载入工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的相应程序进行操作。 此链接会将你定位到登录页面，你可以在其中访问与在步骤 5 中选择的部署程序包相匹配的 Microsoft Defender for Endpoint 过程：
    - 使用组策略载入 Windows 10 计算机
    - 使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 计算机
    - 使用移动设备管理工具载入 Windows 10 计算机
    - 使用本地脚本载入 Windows 10 计算机
    - 载入非持久性虚拟桌面基础结构 (VDI) 计算机。

完成操作并启用终结点后，它应该在设备列表中可见，并且还应开始向活动资源管理器报告审核活动日志。

> [!NOTE]
> 此体验根据许可证强制实施。 如果没有所需的许可证，数据将不可见或不可访问。

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>与设备载入到 Microsoft Defender for Endpoint

在此方案中，已经部署了 Microsoft Defender for Endpoint，并且在其中报告了终结点。 所有这些终结点都将显示在托管设备列表中。 可通过使用[载入设备程序](endpoint-dlp-getting-started.md#onboarding-devices)将新设备继续载入到终结点 DLP 中，以扩展覆盖范围。

1. 打开“[Microsoft 合规中心](https://compliance.microsoft.com)”。
2. 打开合规中心设置页面，然后选择“**启用设备监视**”。
3. 选择“**设备管理**”，以打开“**设备**”列表。 你应该会看到已经向 Microsoft Defender for Endpoint 报告的设备列表。 ![设备管理](../media/endpoint-dlp-getting-started-2-device-management.png)
4. 如果需要载入附加设备，请选择“**载入**”。
5. 从“**部署方法**”列表中选择要部署到这些额外设备的方式，然后**下载程序包**。
6. 按照[适用于 Windows 10 计算机的载入工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的相应程序进行操作。 此链接会将你定位到登录页面，你可以在其中访问与在步骤 5 中选择的部署程序包相匹配的 Microsoft Defender for Endpoint 过程：
    - 使用组策略载入 Windows 10 计算机
    - 使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 计算机
    - 使用移动设备管理工具载入 Windows 10 计算机
    - 使用本地脚本载入 Windows 10 计算机
    - 载入非持久性虚拟桌面基础结构 (VDI) 计算机。

完成操作并载入终结点后，它应该在“**设备**”表下可见，并且还应开始向**活动资源管理器**报告审核日志。

> [!NOTE]
>此体验根据许可证强制实施。 如果没有所需的许可证，数据将不可见或不可访问。

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>在活动资源管理器中查看终结点 DLP 数据

1. 在 Microsoft 365 合规中心中打开域的“[数据分类页面](https://compliance.microsoft.com/dataclassification?viewid=overview)”，然后选择“活动资源管理器”。
2. 请参考[活动资源管理器入门](data-classification-activity-explorer.md)中的程序，以访问和筛选终结点设备的所有数据。

![终结点设备的活动资源管理器筛选器](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>后续步骤
现在，你已载入设备，并且可以在“活动资源管理器”中查看活动数据，那么就可以继续下一步，在其中创建保护敏感项目的 DLP 策略。

- [使用终结点数据丢失防护（预览）](endpoint-dlp-using.md)

## <a name="see-also"></a>另请参阅

- [了解终结点数据丢失防护（预览）](endpoint-dlp-learn-about.md)
- [使用终结点数据丢失防护（预览）](endpoint-dlp-using.md)
- [数据丢失防护概述](data-loss-prevention-policies.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 设备的装载工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [已加入 Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
