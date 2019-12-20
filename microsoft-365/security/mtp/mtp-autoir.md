---
title: Microsoft 威胁防护中的自动调查和响应
description: 简要了解 Microsoft 威胁防护中的自动调查和响应功能
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ea3201838e625969a239aee4339e0de605d95c55
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808607"
---
# <a name="automated-investigation-and-response-air-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的自动调查和响应 (AIR)

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="your-virtual-analyst"></a>你的虚拟分析师

触发安全警报后，安全运营团队将负责调查这些警报并采取措施以保护你的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 

想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。 这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。 这种情况听起来像科幻小说？绝不是！ 这种虚拟分析师是 Microsoft 威胁防护套件的一部分，它的名称是“自动调查和响应”** (AIR)。

AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。 借助 AIR，可以减少处理调查和修正活动的成本，并充分利用威胁防护套件。 AIR 通过以下方式为安全运营团队提供帮助：

1.  确定是否需要针对威胁执行操作；
2.  执行（或建议执行）任何必要的修正操作；
3.  确定应进行哪些其他调查；以及
4.  根据需要对其他警报重复此过程。

## <a name="the-automated-investigation-process"></a>自动调查流程

**警报** > **事件** > **自动调查** > **裁定** > **修正操作**

在较高级别，触发的警报会创建事件，这可以启动自动调查。 该调查可能会导致执行一项或多项修正操作。 在 Microsoft 威胁防护中，每次自动调查都会将 Azure 高级威胁防护 (Azure ATP)、Microsoft Defender 高级威胁防护 (Microsoft Defender ATP) 和 Office 365 高级威胁防护 (Office 365 ATP) 之间的信号相关联，如下表所示： 

|实体 |威胁防护服务  |
|---------|---------|
|设备（也称为终结点）     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件内容（邮箱中的文件和邮件）     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |


每次调查都会针对调查的每条证据生成裁定（*恶意*、*可疑*或*干净*）。 根据威胁的类型和最终裁定结果，自动执行修正操作，或者在组织的安全运营团队批准后执行修正操作。 "[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。 

> [!NOTE]
> 并非每个警报都会触发自动调查，也不是每个调查都会导致自动修正操作；这一切都取决于你的组织配置 AIR 的方式。 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的 AIR 要求

| | |
|--|--|
|订阅要求 |- 已启用标识和威胁防护的 Microsoft 365 E5 或 Microsoft 365 E3<br/>- 请参阅 [Microsoft 365 计划](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)|
|网络要求 |- 已启用 [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)<br/>- 已配置 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS)<br/>- [与 Azure ATP 集成的 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 计算机要求 |- 已安装 Windows 10 版本 1709 或更高版本（请参阅 [Windows 10 发行信息](https://docs.microsoft.com/windows/release-information/)）<br/>- 已配置 [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- 已配置 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|权限 |- 若要*配置* AIR，必须在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配****“全局管理员”或“安全管理员”**** 角色。<br/><br/>- 若要*使用* AIR 功能，请参阅[操作中心任务所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="next-steps"></a>后续步骤

- [批准或拒绝与自动调查和响应相关的操作](mtp-autoir-actions.md)
- [详细了解操作中心](mtp-action-center.md)