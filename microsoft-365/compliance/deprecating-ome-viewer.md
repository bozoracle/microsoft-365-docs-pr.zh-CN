---
title: 弃用邮件加密查看器应用程序
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 邮件加密（OME）查看器应用已从2018中的 Android 和 Apple 存储中删除。
ms.openlocfilehash: 9aca6fa2c0e9b276b666ffa187e3d18f061e7224
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817861"
---
# <a name="deprecating-message-encryption-viewer-app"></a>弃用邮件加密查看器应用程序

在2018年8月15日，我们从 Android 和 Apple 商店中删除了 Office 365 邮件加密（OME）查看器移动应用。 Office 365 邮件加密查看器移动应用程序需要阅读使用 Apple 和 Android 手机上的早期版本的 OME 加密的电子邮件和附件。 除了删除 OME Viewer 应用程序，我们不会对早期版本的 OME 进行任何其他更改。
  
## <a name="changes-from-august-2018"></a>2018年8月的更改

为2017年9月宣布，我们发布了[Office 365 邮件加密](https://aka.ms/ome2017)的新版本，以便用户可以向组织内外的任何人发送加密和受保护的邮件，而不需要移动应用。 从那时起，我们添加了其他功能：
  
- [仅加密模板](https://aka.ms/encryptonly)

- [用于解密附件的控件](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
进行此更改后，用户将不再能够从8月1日开始下载 Office 365 邮件加密查看器移动应用。 因此，邮件收件人可能无法读取在某些 Android 和 Apple 移动设备上使用 OME 的早期版本加密的邮件。 但是，他们仍可以在个人计算机上读取这些邮件（通过桌面浏览器）。 已下载应用程序的用户将继续能够使用它。
  
## <a name="why-this-change-was-made"></a>为什么要进行此更改

新版本的 OME 不再需要移动应用读取受保护的电子邮件和附件。 使用新 OME 功能的客户可以在 Outlook mobile 中查看受保护的邮件，而非客户可以在浏览器中查看受保护的邮件。
  
要求用户下载移动应用是客户查看受保护邮件的另一个障碍。 新的 Office 365 邮件加密功能可提供更好的移动体验。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>我仍然可以使用以前版本的 Office 365 邮件加密

早期版本的 Office 365 邮件加密目前不会被弃用。但是，我们对 Office 365 邮件加密的新版本进行了重要的增强，这使得加密和权限保护对任何设备的敏感数据更加简单，包括用户能够直接在 Outlook 中阅读受保护的邮件（桌面、移动和 web）。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>需要执行哪些操作才能为此更改做准备

如果您的组织当前向需要 OME 查看器应用程序的收件人发送了加密附件，则应更新您的文档和培训资源。
  
我们建议您更新现有的 Exchange 邮件流规则，以使用当前版本的 OME，以便您的组织可以利用新的和改进的功能。 一旦设置了新的 OME 功能，收件人就不需要 OME 查看器应用来在移动设备上阅读加密的邮件。
  
Microsoft 建议您制定一个计划，尽快移动到新的 OME 功能，因为它对您的组织合理。 有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 如果您想要详细了解新功能的工作方式，请参阅[Office 365 邮件加密](ome.md)。
  

