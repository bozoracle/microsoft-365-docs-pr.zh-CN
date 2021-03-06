---
title: "\"管理中心\" 中的 Microsoft 365 报表-邮箱使用情况"
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: 了解如何获取邮箱使用情况报告，以了解用户使用用户邮箱的活动。
ms.openlocfilehash: 0b0c57bda813e1600866513df86b7c973dcdffdc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949128"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>"管理中心" 中的 Microsoft 365 报表-邮箱使用情况

**邮箱使用情况报告**根据电子邮件发送、阅读、创建约会、发送会议、接受会议、谢绝会议和取消会议活动，提供具有用户邮箱和活动级别的用户的信息。 它还显示每个用户邮箱占用了多少存储空间以及其中多少用户即将达到存储配额。 
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>如何访问邮箱使用情况报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 " **选择报告** " 下拉下，选择 " **Exchange** \> **邮箱使用情况**"。
  
## <a name="interpret-the-mailbox-usage-report"></a>解读邮箱使用情况报告

可查看" **邮箱**"、" **存储**"和" **配额**"图表，了解组织的" **邮箱使用情况**"。 
  
|Item|说明|
|:-----|:-----|
|1.  <br/> |可查看" **邮箱使用情况**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，则该表将显示从当前日期起的最长28天的数据 (并不是生成报告的日期) 。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |邮箱图表显示组织中的用户邮箱总数以及在报告周期内的任意指定日期处于活动状态的用户邮箱总数。 如果用户邮箱具有电子邮件发送、阅读、创建约会、发送会议、接受会议、谢绝会议和取消会议活动，则会将该邮箱视为活动用户。  <br/> |
|4.  <br/> |" **存储**"图表显示组织中使用的存储量。 存储图表不包括存档邮箱。 有关自动扩展存档的详细信息，请参阅 [Microsoft 365 中的无限制存档概述](https://docs.microsoft.com/microsoft-365/compliance/unlimited-archiving)。<br/> |
|5.  <br/> | " **配额**"图表显示每个配额类别中用户邮箱的数量。有以下 4 种配额类别：  <br/>  良好 - 其使用的存储低于问题警告配额的用户数量。  <br/>  警告 - 其使用的存储等于或高于问题警告配额但低于禁止发送配额的用户数量  <br/>  无法发送 - 其使用的存储等于或高于禁止发送配额但低于禁止发送/接收配额的用户数量  <br/>  无法发送/接收 - 其使用的存储等于或高于禁止发送/接收配额的用户数量  <br/> |
|6.  <br/> | 在" **邮箱**"图表上，Y 轴表示用户邮箱计数。  <br/>  在" **存储**"图表上，Y 轴表示组织中用户邮箱正在使用的存储量。  <br/>  在" **配额**"图表上，Y 轴表示每个存储配额中用户邮箱的数量。  <br/>  "邮箱"和"存储"图表上的 X 轴都表示此特定报表的所选日期范围。  <br/>  "配额"图表上的 X 轴表示配额类别。  <br/> |
|7.  <br/> |您可以通过选择图例中的项目来筛选所见图表。  <br/> |
|8.  <br/> | 下表详细显示每个用户级别的邮箱使用情况。可向表格添加其他列。  <br/> " **用户名**"是用户的电子邮件地址。  <br/> " **显示名称**"是用户的全名。  <br/> " **已删除邮箱**"是指当前处于"已删除"状态的邮箱，但其在报告的部分报告周期内处于活动状态。  <br/> " **删除日期**"是指删除邮箱的日期。  <br/> " **创建日期**"是指创建邮箱的日期。  <br/> " **上次活动日期**"是指邮箱的电子邮件发送或阅读活动日期。  <br/> " **项计数**"是指邮箱中项的总数。  <br/> " **使用的存储(MB)**"是指使用的存储总量。  <br/> **已删除项目计数** 指邮箱中已删除邮件的总数。 <br/> **已删除项目大小 (MB) ** 是指邮箱中所有已删除邮件的总大小。 <br/> " **问题警告配额(MB)**"是指即将达到存储配额时，邮箱所有者会收到警告的存储空间上限。  <br/> " **禁止发送配额(MB)**"是指邮箱无法再发送电子邮件时的存储空间上限。  <br/> " **禁止发送接收配额(MB)**"是指邮箱无法再发送或接收电子邮件时的存储空间上限。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请参阅[Microsoft 365 管理中心的活动报告](activity-reports.md)中的 "报告" 部分的 "**隐藏用户详细信息**"。  <br/> |
|9.  <br/> |您还可以通过选择 " **导出** " 链接将报告数据导出到 Excel .csv 文件中。  <br/> |
|||
   

