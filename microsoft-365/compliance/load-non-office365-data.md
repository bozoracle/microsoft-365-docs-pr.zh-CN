---
title: 将非 Microsoft 365 数据加载到证据中
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
description: 了解如何使用非 Office 365 内容导入功能将非 Office 365 文档上载到数据调查中的证据中。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: b6d8c2f65a1fa3a43fa2ac4bf3821cc6c1fac514
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285368"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>将非 Microsoft 365 数据加载到证据中

并非所有可能需要在数据调查中进行分析的文档都将位于 Microsoft 365 中。 使用非 Microsoft 365 内容导入功能，可以将不在 Microsoft 365 中的文档上传到证据，以便可以在数据调查中分析这些文档。

## <a name="requirements-to-upload-non-office-365-content"></a>上载非 Office 365 内容的要求

使用此过程中所述的上传非 Microsoft 365 功能时，需要具备以下条件：

- Microsoft 365 或 Office 365 E5 订阅。

- 将上载其非 Microsoft 365 内容的所有感兴趣的人都必须具有相应的 E5 或 E5 附加许可证。

- 现有电子数据展示事例。

- 将上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中，文件夹的名称 *alias@domainname*的格式。 *Alias@domainname*必须是用户的别名和域。 您可以将所有 *alias@domainname* 文件夹收集到一个根文件夹中。 根文件夹只能包含 *alias@domainname* 文件夹，根文件夹中必须没有松散文件。

- 一种帐户，既可以是电子数据展示管理器，也可以是安装在可访问非 Microsoft 365 内容文件夹结构的计算机上的电子数据展示管理员 Microsoft Azure 存储工具。

- 安装 AzCopy，可以从 [AzCopy 开始使用](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>将非 Microsoft 365 内容上传到数据调查

1. 打开 **数据调查** 并转到调查，以将非 Microsoft 365 数据上载到。  单击 " **证据** " 选项卡，然后选择您希望将数据加载到的证据集。  如果尚未创建证据集，现在可以执行此操作。  最后，单击 " **管理证据** "，然后查看 "数据" 部分中的 " **上载** "

2. 单击 " **上载文件** " 按钮以启动 "非 Microsoft 365 数据导入向导"。

![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 向导中的第一步是为要上载的文件准备一个安全的 Azure blob。  准备完成后，单击 " **下一步：上传文件** " 按钮。

![准备非 Microsoft 365 数据导入](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在 " **上载文件** " 步骤中，指定 **文件位置的路径**，这是您计划导入的非 Microsoft 365 数据所在的位置。  设置正确的位置可确保正确更新 AzCopy 命令。

> [!NOTE]
> 如果尚未安装 AzCopy，可以从以下位置执行此操作： https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. 通过单击 " **复制到剪贴板** " 链接复制预定义命令。 启动 windows 命令提示符，粘贴命令并按 enter。  将在下一步中将文件上载到安全 Azure blob 存储。

![上载非 Microsoft 365 数据导入的文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![使用 AzCopy 导入非 Microsoft 365 数据](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最后，返回到安全 & 合规性，然后单击 " **下一步：处理文件** " 按钮。  这将启动已上载文件的处理、文本提取和索引。  您可以在此处或在 " **作业** " 选项卡中跟踪处理进度。 完成后，新文件就会出现在证据集中。  处理完成后，可以关闭向导。

![非 Microsoft 365 导入过程文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

