---
title: 无限制存档概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自动扩展存档，该存档为 Exchange Online 邮箱提供无限制的存档存储。
ms.openlocfilehash: f2d9e645badd98ea9a1d14dec22e291c8ad7de63
ms.sourcegitcommit: 416a4b87bfd7e5aff80194b59b2776f054aa8eb5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44534914"
---
# <a name="overview-of-unlimited-archiving"></a>无限制存档概述

在 Office 365 中，存档邮箱为用户提供额外的邮箱存储空间。 启用用户的存档邮箱后，最多可有 100 GB 的附加存储空间。 过去，当达到 100 GB 的存储配额时，组织必须与 Microsoft 联系以请求存档邮箱的额外存储空间。 这就不再是这样。

Microsoft 365 中的无限制存档功能（称为*自动扩展存档*）在存档邮箱中提供了额外的存储空间。 当达到存档邮箱中的存储配额时，Microsoft 365 会自动增加存档的大小，这意味着用户将不会用尽邮箱存储空间，并且管理员不必为存档邮箱请求额外的存储空间。

有关启用自动扩展存档的分步说明，请参阅[启用无限制存档](enable-unlimited-archiving.md)。

> [!NOTE]
> 自动扩展存档还支持共享邮箱。 若要为共享邮箱启用存档，需要具有 Exchange Online 存档许可证的 Exchange Online 计划2许可证或 Exchange Online 计划1许可证。

## <a name="how-auto-expanding-archiving-works"></a>自动扩展存档的工作方式

如前所述，在启用用户的存档邮箱时，会创建额外的邮箱存储空间。 启用自动扩展存档后，Microsoft 365 将定期检查存档邮箱的大小。 当存档邮箱接近其存储限制时，Microsoft 365 会自动为存档创建额外的存储空间。 如果用户在此额外的存储空间中耗尽，Microsoft 365 将为用户的存档增加更多的存储空间。 此过程会自动发生，这意味着管理员无需请求额外存档存储或管理自动扩展存档。

以下是此过程的快速概述。

![自动扩展存档过程概述](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 对用户邮箱或共享邮箱启用存档。 将创建一个具有 100 GB 存储空间的存档邮箱，并将存档邮箱的警告配额设置为 90 GB。

2. 管理员可自动展开邮箱的存档。 当存档邮箱（包括 "可恢复的项目" 文件夹）达到 90 GB 时，它将转换为自动扩展存档，而 Microsoft 365 将向存档添加存储空间。 最多可能需要30天的时间来设置额外的存储空间。

   > [!NOTE]
   > 如果将邮箱置于保留或分配到保留策略，则在启用自动扩展存档时，存档邮箱的存储配额将增加到 110 GB。 同样，存档警告配额增加到 100 GB。

3. Microsoft 365 会在必要时自动添加更多的存储空间。

> [!IMPORTANT]
> 仅对用于单个用户（或共享邮箱）的邮箱支持自动扩展存档，该邮箱的增长率不超过每日的 1 GB。 用户的存档邮箱只供该用户使用。 不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱。 Microsoft 保留在用户的存档邮箱用于存储其他用户的存档数据的情况下或在不恰当使用的其他情况下，拒绝无限存档的权利。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>移动到其他存档存储空间的内容是什么？

为了高效地使用自动扩展存档存储，文件夹可能会移动。 Microsoft 365 确定在向存档中添加额外存储时哪些文件夹会移动。 有时移动文件夹时，会自动创建一个或多个子文件夹，并将原始文件夹中的项目分发到这些文件夹，以促进移动过程。 在 Outlook 中查看文件夹列表的存档部分时，这些子文件夹将显示在原始文件夹下。  Microsoft 365 用于命名这些子文件夹的命名约定是** \<folder name\> _yyyy （在 mmm dd，Yyyy h_mm 创建）**，其中：

- **yyyy**是接收文件夹中邮件的年份。

- **mmm dd，yyyy h_m**是 Office 365 创建子文件夹的日期和时间，以 UTC 格式为单位，基于用户的时区和 Outlook 中的区域设置。

下面的屏幕截图显示在邮件移动到自动展开的存档之前和之后的文件夹列表。

 **添加额外的存储之前**

![预配自动扩展存档之前的存档邮箱的文件夹列表](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **添加额外的存储后**

![预配自动扩展存档后存档邮箱的文件夹列表](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 如前所述，Microsoft 365 将项目移至子文件夹（并使用上述命名约定对其进行命名），以帮助将内容分发到辅助存档。 但将项目移动到子文件夹可能并非总是如此。 有时可能会将整个文件夹移动到辅助存档中。 在这种情况下，文件夹将保留其原始名称。  在 Outlook 的文件夹列表中，该文件夹已移动到辅助存档中并不明显。

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>用于访问自动扩展存档中的项目的 Outlook 要求

若要访问存储在自动扩展的存档中的邮件，用户必须使用以下 Outlook 客户端之一：

- Outlook 2016 或 Outlook 2019 for Windows

- Outlook 网页版

- Outlook 2016 或 Outlook 2019 for Mac

以下是在使用 Outlook 或 web 上的 Outlook 访问存储在自动扩展的存档中的邮件时需要考虑的一些事项。

- 您可以访问存档邮箱中的任何文件夹，包括已移动到自动扩展存储区域的文件夹。

- 搜索自动扩展存档仅在内部人员构建16.0.12716.10000 时才在 Outlook 桌面上提供。 Outlook for web 中提供了搜索功能。 与联机存档类似，您可以仅通过搜索文件夹本身来搜索已移动到其他存储区域的项目。 这意味着，您必须在文件夹列表中选择 "存档" 文件夹，以选择**当前文件夹**选项作为搜索范围。 同样，如果自动扩展存储区域中的文件夹包含子文件夹，则必须单独搜索每个子文件夹。

- Outlook 中的项目计数和可读/未读的计数（在 Outlook 和 web 上的 outlook 中）在自动展开的存档中可能不准确。

- 您可以删除子文件夹中指向自动扩展存储区域的项目，但不能删除该文件夹本身。

- 无法使用 "恢复已删除邮件" 功能恢复从自动扩展的存储区域中删除的项目。

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>自动扩展存档和其他合规性功能

本节介绍了自动扩展存档与其他合规性和数据管理功能之间的功能。

- **电子数据展示：** 当您使用电子数据展示工具（如内容搜索或就地电子数据展示）时，还会搜索自动扩展存档中的其他存储区域。

- **保留：** 将邮箱置于保留状态时，使用诸如 Exchange Online 中的诉讼保留或电子数据展示事例保留和合规性中心中的保留策略等工具，位于自动扩展存档中的内容也会置于保留状态。

- **邮件记录管理（MRM）：** 如果使用 Exchange Online 中的 MRM 删除策略以永久删除过期的邮箱项目，则也会删除位于自动展开的存档中的已过期项目。

- **导入服务：** 您可以使用 Office 365 导入服务将 PST 文件导入到用户的自动扩展存档中。 你可以将 PST 文件中的最大为 100 GB 的数据导入用户的存档邮箱。

## <a name="more-information"></a>详细信息

有关自动扩展存档的更多技术详细信息，请参阅[Microsoft 365：自动扩展存档常见问题解答](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。
