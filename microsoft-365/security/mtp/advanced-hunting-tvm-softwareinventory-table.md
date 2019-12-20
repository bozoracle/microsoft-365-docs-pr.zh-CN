---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventoryVulnerabilities 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventoryVulnerabilities 表中，了解设备的软件清单及其漏洞。
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, 威胁和漏洞管理, TVM, 设备管理, 软件, 清单, 漏洞, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6aca41e46af8ba94f87e7ee91059c3d11a4fbe9e
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808627"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高级搜寻架构中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表包含设备上软件的[威胁和漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)清单以及这些软件产品中的任何已知漏洞。 此表还包括操作系统信息、CVE ID 和漏洞严重性信息。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `OSPlatform` | string | 计算机上运行的操作系统平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `OSVersion` | string | 计算机上运行的操作系统版本 |
| `OSArchitecture` | string | 计算机上运行的操作系统的体系结构 |
| `SoftwareVendor` | string | 基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别 |
| `SoftwareName` | string | 软件产品的名称 |
| `SoftwareVersion` | string | 软件产品版本号 |
| `CveId` | string | 通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符 |
| `VulnerabilitySeverityLevel` | string | 基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别 |



## <a name="related-topics"></a>相关主题

- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [威胁和漏洞管理概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)