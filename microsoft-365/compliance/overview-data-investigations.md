---
title: Microsoft 365 中的数据调查 (预览) 概述
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
ms.assetid: ''
ms.custom:
- seo-marvel-mar2020
description: 在本文中，您将了解在 Microsoft 365 中的 "数据调查" (预览) 工具。 数据调查工具可帮助您评估和修正数据外泄。
ms.openlocfilehash: 21241ad36278bc75a8363b9aeefeaf4caec783b5
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285988"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 中的数据调查 (预览) 概述

当包含机密、敏感或恶意内容的文档发布到不受信任的环境中时，将发生数据溢出。 检测到数据溢出时，很重要的一点是，快速包含环境、评估外泄的大小和位置、检查周围的用户活动，然后从服务中删除溢出的数据。 通过使用新的数据调查 (preview) 工具，您可以在 Office 365 中搜索敏感、恶意或误放的数据，调查所发生的情况，并采取适当的措施修正外泄。  

本文介绍了如何使用新的数据调查 (preview) 工具中的功能来解决 Data 外泄方案。

## <a name="permissions"></a>权限

若要访问和进行数据调查，您需要是数据调查员角色组的成员。 有关详细信息，请参阅 [为数据调查分配权限](data-investigations-permissions.md)。

## <a name="data-investigations-preview-workflow"></a> (预览) 工作流的数据调查 

以下各节介绍了在 "数据调查" 中的内置工作流 (预览) 的每个步骤。 下面的屏幕截图显示了名为 "*高风险：财务文档泄露*" 的调查的 "**主页**" 选项卡。 

![数据调查工具中的工作流](../media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>搜索敏感、恶意或误放的数据

使用 " **搜索** " 选项卡可创建搜索以查找要修正的数据的 Microsoft 365。 您可以创建和运行基于查询的搜索，以确定设置的电子邮件消息和文档中可能包含溢出的数据，然后将它们作为证据收集以供审阅和分析。 此外，还可以使用搜索工具预览示例文档，并查看可帮助您优化和改进搜索结果的搜索统计信息。 一旦您认为搜索结果包含与调查相关的所有数据，您就可以将搜索结果添加到证据集，以进一步查看、影响评估，并根据需要采取补救措施。 有关详细信息，请参阅 [在调查中搜索数据](search-for-data.md)。

## <a name="review-and-investigate-evidence"></a>查看和调查证据

使用 " **证据** " 选项卡可调查从 live service 中收集的数据，在此示例中为 Office 365。 证据集中的数据是您收集的搜索结果的快照。 以证据的形式添加搜索结果时，将触发进程以提取文件、元数据和文本。 完成此过程后，数据调查工具会生成所有数据的新索引，并将其添加到证据集。 对于任何对时间敏感的调查，这使您可以通过删除位于 live service) 中的原始内容位置 (的数据来快速包含环境，同时调查您在隔离环境中收集的证据。 收集证据后，可以运行更多查询以根据时间范围、文件类型、数据所有者和其他类型的条件来缩小数据的范围。 例如，通过使用作者、发件人和收件人条件，您可以快速识别包含在数据溢出中的用户，以及是否有任何溢出的数据与组织外部的人员共享。

您还可以对所收集的证据运行高级分析。 这可为您提供常规主题，并通过电子邮件线索、完全重复的重复项以及临近的重复项来组织证据以促进您的调查。 您可以查看提取的文本视图中的文档或本机文件格式的文档，并使用调查结果对其进行标记。 有关详细信息，请参阅：

  - [查看证据中的数据](review-data-in-evidence.md)

  - [运行分析功能，加快调查](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>管理感兴趣的人员

使用 " **感兴趣的人员** " 选项卡可以在调查证据时添加和管理已标识为要关注的人员的人员。 当您添加感兴趣的人时，将标识并映射他们的数据源（如其邮箱和 OneDrive 帐户）。 然后，可以通过仅搜索这些人员的内容位置来限定搜索范围。 在按感兴趣的人员确定范围时，搜索会更高效且准确，因为该工具 reprocesses 任何未编制索引的数据（如图像或不受支持的文件类型）。 在 " **感兴趣的人员** " 选项卡上，您还可以查看和搜索这些人员的审核日志活动，以进一步帮助您进行调查。 您可以在整个调查中添加更多感兴趣的人。 有关详细信息，请参阅 [管理感兴趣的人员调查](manage-people-of-interest.md)。

## <a name="indexing-the-data-of-people-of-interest"></a>为感兴趣的人员的数据编制索引

如果向调查中添加感兴趣的人，则会重新对用户数据源中的任何部分已编制索引的项目进行索引。 此过程称为 " *高级索引*"。 高级索引 reprocesses 数据（如图像和不受支持的文件类型），以便在运行搜索以收集用于调查的数据时能够完全发现这些数据。 使用 " **处理** " 选项卡监视高级索引的状态，并修复使用称为 " *错误修正*" 的过程可能发生的任何处理错误。 有关详细信息，请参阅 [处理调查数据时的错误修正](error-remediation.md)。

## <a name="exporting-data"></a>导出数据

如果要导出数据，请使用 " **导出** " 选项卡管理导出作业并从证据集下载数据。 在导出证据时，会将数据上载到 Azure 存储位置，然后可将其下载到本地计算机。 在 " **导出** " 选项卡上，您可以获取 Azure 存储位置 URL 和存储评估密钥，这两个都是下载导出的数据所必需的。 有关详细信息，请参阅 [从调查中导出数据](export-data.md)。

## <a name="managing-jobs"></a>管理作业

使用 " **作业** " 选项卡监视与调查相关的任务的长时间运行的进程。 这包括用于运行搜索、将数据添加到证据集、重建数据索引和导出证据的作业。 例如，您可以在 " **搜索** " 选项卡上创建包含许多数据源的搜索。 此搜索过程的状态将显示在 " **作业** " 选项卡上。有关详细信息，请参阅 [在数据调查中管理作业](manage-jobs.md)。

## <a name="configuring-investigation-settings"></a>配置调查设置

使用 " **设置** " 选项卡配置调查范围设置。 这包括将成员添加到调查中、关闭或删除调查，以及配置搜索和分析行为。
