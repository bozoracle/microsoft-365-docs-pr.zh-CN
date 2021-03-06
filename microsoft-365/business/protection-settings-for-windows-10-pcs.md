---
title: 编辑或创建 Windows 10 电脑的设备保护设置
f1.keywords:
- NOCSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 了解 Microsoft 365 for business 中适用于 Windows 10 设备的安全设置。
ms.openlocfilehash: bd992113403c7134fb32bc6cced5bf216843241b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289147"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>编辑或创建 Windows 10 电脑的设备保护设置

本文适用于 Microsoft 365 商业高级版。

设置 "设置" 页面上的 "设置默认 Windows 保护设置" 后，可以添加适用于所有用户或一组用户的新的 "Windows 保护" 设置。 您还可以编辑已创建的任何文件。

## <a name="create-protection-settings-for-windows-10-devices"></a>为 Windows 10 设备创建保护设置

观看有关如何使用 Microsoft 365 商业高级版保护 Windows 10 设备的视频：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。 
2. 在左侧导航中，选择 " **设备** \> **策略**" " \> **添加**"。
3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
4. 在" **策略类型**"下，选择" **Windows 10 设备配置**"。
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. 有关详细信息，请参阅 [可用设置](#available-settings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.
7. 最后，选择" **完成**"以保存该策略，并将其分配到设备。 

## <a name="edit-windows-10-protection-settings"></a>编辑 Windows 10 保护设置
 
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。     
2. 在左侧导航中，选择 " **设备** \> **策略** "。
1. 选择现有的 Windows 设备策略，然后进行 **编辑**。
1. 选择要更改的设置旁边的 " **编辑** "，然后单击 " **保存**"。

## <a name="available-settings"></a>可用设置

所有设置均默认为" **开启**"状态。 可使用以下设置：
  
有关详细信息，请参阅 [Microsoft 365 Premium 中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。 
  
|||
|:-----|:-----|
|Setting  <br/> |说明  <br/> |
|使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁  <br/> |需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。  <br/> |
|帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁  <br/> |在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。  <br/> |
|使用减少设备攻击面的规则  <br/> |启用此规则后，攻击面减少有助于阻止通常被恶意软件用来感染设备的操作和应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。请参阅[减少攻击面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)以了解详细信息。  <br/> |
|保护文件夹免受勒索软件等威胁  <br/> |此设置使用受控文件夹访问来保护公司数据免受可疑或恶意应用（如勒索软件）的修改。 无法在受保护的文件夹中更改这些类型的应用。 仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。 请参阅 [使用受控制文件夹的访问保护文件夹](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) 以了解详细信息。  <br/> |
|防止网络访问 Internet 上的潜在恶意内容  <br/> |使用此设置可阻止出站用户与可承载网络钓鱼诈骗、入侵或其他恶意内容的低信誉 Internet 位置的连接。 仅当 Windows Defender 防病毒设置为 **打开**时，此设置才可用。 有关详细信息，请参阅 [保护网络](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。  <br/> |
|使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问  <br/> |Bitlocker 通过加密计算机硬盘来保护数据，在计算机丢失或被盗时防止数据泄露。 有关详细信息，请参阅 [BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)。  <br/> |
|允许用户从 Microsoft Store 下载应用  <br/> |允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  <br/> |
|允许用户访问 Cortana  <br/> |Cortana 非常有用！ Cortana 可以为你打开或关闭设置、提供说明，并确保你的约会时间已过，因此，默认情况下将此设置保持为 **打开** 。  <br/> |
|允许用户接收来自 Microsoft 的 Windows 提示和广告  <br/> |Windows 提示非常方便，可在新功能发布时为用户提供指导。  <br/> |
|让 Windows 10 设备自动保持最新状态  <br/> |确保 Windows 10 设备会自动接收最新的更新。  <br/> |
|在空闲此时长后关闭设备屏幕  <br/> |确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。  <br/> |
