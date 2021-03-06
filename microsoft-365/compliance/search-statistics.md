---
title: 搜索统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 搜索统计信息是验证搜索结果并在 "搜索详细信息" 弹出页面上的 "状态" 下显示的有效方式。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 24de99cf0a7ae21b5966811b988c93d64abd5148
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286088"
---
# <a name="search-statistics-in-data-investigations-preview"></a>"数据调查" 中的搜索统计信息 (预览) 

在调查数据事件时，验证搜索结果的有效方法是查看有关搜索结果的统计信息，以确保它们符合您的预期。 当搜索运行完毕时，将在 "搜索详细信息" 弹出页面上的 " **状态** " 下显示以下高级统计信息：

![在 "搜索详细信息" 弹出页面上搜索 statisics](../media/SearchDetailsFlyout.png)

- 与搜索条件匹配的项目的估计数量和大小。

- 部分已编制索引的项目的数量和大小 (也称为未编制索引的项目) ，这些 *项目* 不可搜索，但在搜索中包含的内容位置中找到。

- 已搜索的邮箱和网站的数量。

若要查看更多详细统计信息，请单击 "搜索详细信息" 弹出页面上的 "**统计** 在 " **搜索统计信息** " 页上，您可以查看搜索摘要、包含与搜索结果匹配的项目的顶部位置以及有关搜索查询的详细统计信息。

![搜索统计信息下拉列表](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a>摘要

在 **摘要** 视图中，可以看到按位置类型划分的搜索结果 (例如，位置包括 Exchange 邮箱和 SharePoint 网站) 。 将为每个位置类型显示以下信息：

- 包含符合搜索条件的项目的位置数。

- 与搜索条件匹配的每个位置类型中的项目总数。

- 与搜索条件匹配的每个位置类型中的项目的总大小。

## <a name="top-locations"></a>顶部位置

在 " **顶部位置** " 视图中，您将看到与搜索条件匹配项最多的各个内容位置。 对于每个内容位置，将显示以下信息：

- 位置的名称;邮箱的电子邮件地址和 SharePoint 网站的 URL

- 位置类型

- 与搜索条件匹配的项目数

- 与搜索条件匹配的所有项目的总大小。

## <a name="queries"></a>Queries

在 " **查询** " 视图中，可以查看搜索查询每个组件的详细统计信息。 如果您在搜索查询中使用关键字列表，则可以在 " **查询** " 视图中查看增强的统计信息，以显示与每个关键字或关键字短语匹配的项目数。 这可帮助您快速确定查询的哪些部分是最 (的，并且) 效率最少。 

**查询**视图中显示以下信息：

 - **位置类型** -行中显示的统计信息的内容位置类型。

- **Part** -此列将显示以下值之一： **Primary** 或 **关键字**。 **主要** 是指该行显示整个查询的统计信息; **关键字** 表示行中的统计信息是查询组件之一。

- **条件** -行引用的搜索查询的实际查询组件。 如果 **Part** 列中的值 **为主**，则显示整个搜索查询的统计信息;如果值为 **关键字**，则显示在 **查询** 列中显示的查询组件的统计信息。 例如，如果使用了关键字列表，则会显示其中一个关键字的统计信息。

  下面是有关 " **查询** " 列中显示的统计信息的一些其他事项：
  
  - 当您在邮箱 (中搜索所有内容时，如果未指定任何关键字) ，实际查询 ** (大小 >= 0) ** 以便返回所有项目
  
  - 当您搜索 SharePoint 和 OneDrive 网站时，将在搜索查询中添加以下两个组件：
    
    **NOT IsExternalContent： 1** -排除本地 SharePoint 组织中的任何内容
    
    **NOT isOneNotePage： 1** -这将排除所有 OneNote 文件，因为这些文件是与搜索查询相匹配的任何文档的重复项。

- **搜索中的位置** 包含行中显示的部分/条件与搜索查询匹配的项目的内容位置数。 请注意，如果存档邮箱包含与搜索条件匹配的项目，则会将其计为一个单独的位置。

- **Items** -与行中显示的部件/条件的搜索条件匹配的项目总数。

- **Size** -与行中显示的 part/condition 的搜索条件匹配的项目总数。

