---
title: 使用敏感度标签保护团队中的文件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：应用敏感度标签，保护高度机密团队中的文件。
ms.openlocfilehash: f52b864087d22e14bb3e9bfe1eb38d088f6f981a
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925742"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="f9280-103">使用敏感度标签保护团队中的文件</span><span class="sxs-lookup"><span data-stu-id="f9280-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="f9280-104">与可由任何人应用于任何文件的高度管控数据敏感度标签不同，高度机密团队需要其自己的标签或子标签，以使分配的文件：</span><span class="sxs-lookup"><span data-stu-id="f9280-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="f9280-105">单独加密。</span><span class="sxs-lookup"><span data-stu-id="f9280-105">Are individually encrypted.</span></span>
- <span data-ttu-id="f9280-106">包含自定义权限，以便只有团队成员能打开文件。</span><span class="sxs-lookup"><span data-stu-id="f9280-106">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="f9280-107">若要以这种方式为团队的底层 SharePoint 网站中存储的文件实现更高的安全级别，必须配置一个自定义的敏感度标签，以用作其自身标签，或作为高度管控数据的常规标签的子标签。</span><span class="sxs-lookup"><span data-stu-id="f9280-107">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="f9280-108">只有团队成员可在其标签列表中看到自定义标签或子标签。</span><span class="sxs-lookup"><span data-stu-id="f9280-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="f9280-109">如果需要将少量标签应用于全局和各个私人团队，请使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="f9280-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="f9280-110">如果你拥有大量标签，或者希望在高度管控标签下整理高度机密团队的标签，请使用敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="f9280-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="f9280-111">按照[这些说明](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)，使用以下设置配置单独的标签或子标签：</span><span class="sxs-lookup"><span data-stu-id="f9280-111">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="f9280-112">标签或子标签名称包含团队名称</span><span class="sxs-lookup"><span data-stu-id="f9280-112">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="f9280-113">启用加密</span><span class="sxs-lookup"><span data-stu-id="f9280-113">Encryption is enabled</span></span>
- <span data-ttu-id="f9280-114">团队的 Office 365 组有共同创作权限</span><span class="sxs-lookup"><span data-stu-id="f9280-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="f9280-115">创建后，为用户发布新的标签或子标签，用户可在将文件上传到团队之前或文件存储在团队中之后，将其应用到文件。</span><span class="sxs-lookup"><span data-stu-id="f9280-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="f9280-116">下面是高度机密团队的配置，该配置将敏感度标签用于文件加密和权限。</span><span class="sxs-lookup"><span data-stu-id="f9280-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![面向公共团队的基准级别保护。](../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="f9280-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9280-118">See Also</span></span>

[<span data-ttu-id="f9280-119">保护 Microsoft Teams 中的文件</span><span class="sxs-lookup"><span data-stu-id="f9280-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="f9280-120">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="f9280-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)