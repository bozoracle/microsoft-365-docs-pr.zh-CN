---
title: 启用要由 Microsoft 365 for business 管理的加入域的 Windows 10 设备
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 了解如何启用 Microsoft 365 以仅在几个步骤中保护本地的 Active Directory 加入 Windows 10 设备。
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560835"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>启用要由 Microsoft 365 商业高级版管理的加入域的 Windows 10 设备

如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业高级版设置为保护您的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。
若要设置此保护，可以实现**混合 AZURE AD 加入的设备**。 这些设备将加入本地 Active Directory 和 Azure Active Directory。

本视频介绍了有关如何针对最常见方案对此进行设置的步骤，在下面的步骤中也将对此进行详细介绍。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>在开始之前，请确保完成以下步骤：
- 使用 Azure AD Connect 将用户同步到 Azure AD。
- 完成 Azure AD Connect 组织单位 (OU) sync。
- 确保您要同步的所有域用户都具有到 Microsoft 365 商业高级版的许可证。

有关步骤，请参阅[将域用户同步到 Microsoft](manage-domain-users.md) 。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 在 Intune 中验证 MDM 证书颁发机构

转到[终结点管理器](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)，在 Microsoft Intune 页上，选择 "**设备注册**"，然后在 "**概述**" 页上，确保**MDM 颁发机构**是**Intune**。

- 如果**mdm 机构**为 "**无**"，请单击**mdm 机构**将其设置为**Intune**。
- 如果**mdm 机构**是**Microsoft office 365**，请转到 "**设备**  >  **注册设备**"，并使用右侧的 "**添加 mdm 颁发机构**" 对话框添加**Intune MDM**颁发机构 (仅当**MDM 机构**设置为 "Microsoft Office 365" 时，"**添加 mdm 颁发**机构" 对话框才可用) 。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 验证 Azure AD 是否已启用加入计算机

- 转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，选择 "azure Active **directory** "，如果 azure active Directory 在 "**管理中心**" 列表中) 不可见，请选择 "azure active Directory (选择" 全部显示 "。 
- 在**Azure Active directory 管理中心**中，转到 " **azure active directory** "，选择 "**设备**"，然后选择 "**设备设置**"。
- 验证**用户是否可以将设备加入 AZURE AD**已启用 
    1. 若要启用所有用户，请设置为**all**。
    2. 若要启用特定用户，请将设置为 "已**选择**" 以启用特定用户组。
        - 将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。
        - 选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 验证 Azure AD 是否已启用 MDM

- 转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，选择 "选择**终结点 Managemen**t" (选择 "如果**终结点管理器**不可见，则**显示所有**内容") 
- 在**Microsoft 终结点管理器管理中心**，转到 "**设备**  >  **windows**  >  **windows 注册**  >  **自动注册**"。
- 验证 MDM 用户作用域是否已启用。

    1. 若要注册所有计算机，设置为**all** ，以便在用户向 Windows 添加工作帐户时自动注册加入 Azure AD 和新计算机的所有用户计算机。
    2. 设置为**Some**以注册特定用户组的计算机。
        -  将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。
        -  选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。

## <a name="4-create-the-required-resources"></a>4. 创建所需的资源 

通过使用在[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模块中找到的[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet，执行[配置混合 Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)所需的任务已得到简化。 调用此 cmdlet 时，它将创建并配置所需的服务连接点和组策略。

您可以通过从 PowerShell 实例中调用以下命令来安装此模块：

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> 建议在运行 Azure AD Connect 的 Windows 服务器上安装此模块。

若要创建所需的服务连接点和组策略，您将调用[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet。 执行此任务时，将需要 Microsoft 365 商业高级全局管理员凭据。 准备好创建资源时，请调用以下命令：

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

第一个命令将与 Microsoft 云建立连接，当系统提示时，请指定 Microsoft 365 Business Premium 全局管理员凭据。

## <a name="5-link-the-group-policy"></a>5. 链接组策略

1. 在组策略管理控制台 (GPMC) 中，右键单击要将策略链接到的位置，然后从上下文菜单中选择 "*链接现有 GPO ...* "。
2. 选择在上述步骤中创建的策略，然后单击 **"确定"**。

## <a name="get-the-latest-administrative-templates"></a>获取最新的管理模板

如果您没有看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**，可能是因为您没有为 Windows 10 版本1803、版本1809或版本1903安装 ADMX。 若要解决此问题，请执行以下步骤 (注意：最新的 MDM 在向后兼容) ：

1.  下载： [Windows 10 的管理模板 ( admx) 可能会2019更新 (1903) ](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。
2.  在主域控制器 (PDC) 上安装程序包。
3.  根据文件夹的版本进行导航： **C:\Program Files (x86) \Microsoft Group Policy\Windows 10 可能 2019 Update (1903) v3**。
4.  将上述路径中的 "**策略定义**" 文件夹重命名为**PolicyDefinitions**。
5.  将**PolicyDefinitions**文件夹复制到**C:\Windows\SYSVOL\domain\Policies**。 
    -   如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。
6.  重新启动主域控制器，以使策略可用。 此过程也适用于将来的任何版本。

此时，您应该能够看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**。
