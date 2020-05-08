---
title: 设置你的 Microsoft 威胁防护试用实验室环境
description: 访问 Microsoft 365 安全中心，然后设置你的 Microsoft 威胁防护试用实验室环境
keywords: Microsoft 威胁防护试用版安装程序，请尝试 Microsoft 威胁防护，Microsoft 威胁防护评估实验室安装程序
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049611"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>设置你的 Microsoft 威胁防护试用实验室环境 

**适用于：**
- Microsoft 威胁防护 


创建 Microsoft 威胁 Protection 试用实验室环境并部署它的过程分为三个阶段：

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="准备 Microsoft 威胁防护评估实验室" />
      <br/>第1阶段：准备</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="设置你的 Microsoft 威胁防护评估实验室" />
      <br/>阶段2：安装程序</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
为 Microsoft 威胁防护试用实验室环境配置每个 Microsoft 威胁防护支柱，并将终结点集成在一起" />
      <br/>第3阶段： Configure & 板载</a><br>
</td>


  </tr>
</table>

你当前处于 "设置" 阶段。 执行最初的步骤来访问 Microsoft 365 安全中心，然后设置你的试用实验室环境。

注册 Office 365 或 Azure Active Directory 订阅，以生成可用于注册 Microsoft 365 E5 许可证的*onmicrosoft.com*租户。 

>[!NOTE]
>如果已有 Office 365 或 Azure Active Directory 订阅，则可以跳过 Office 365 E5 试用版租户创建步骤。

在此阶段中，将指导您执行以下操作：
- 创建 Office 365 E5 试用租户
- 启用 Microsoft 365 试用订阅


## <a name="create-an-office-365-e5-trial-tenant"></a>创建 Office 365 E5 试用租户
>[!NOTE]
>如果已有 Office 365 或 Azure Active Directory 订阅，则可以跳过 Office 365 E5 试用版租户创建步骤。

1. 转到[Office 365 E5 产品门户](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)，并选择 "**免费试用版**"。
![图像 of_page](../../media/mtp-eval-9.png) <br>
  
2. 通过输入您的电子邮件地址（个人或公司）完成试用注册。 单击 "**设置帐户**"。
![图像 of_page](../../media/mtp-eval-10.png) <br> 

3. 填写你的名字、姓氏、商务电话号码、公司名称、公司规模和国家或地区。  
<br>![图像 of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>您在此处设置的国家或地区决定了您的 Office 365 将托管的数据中心区域。
  
4. 选择您的验证首选项：通过短信或 call。 单击 "**发送验证代码**"。 
![图像 of_page](../../media/mtp-eval-12.png) <br>

5. 为租户设置自定义域名称，然后单击 "**下一步**"。
<br>![图像 of_page](../../media/mtp-eval-13.png) <br>
 
6. 设置将成为租户的全局管理员的第一个标识。 填写 "**名称**" 和 "**密码**"。 单击 "**注册**"。
![图像 of_page](../../media/mtp-eval-14.png) <br>
c
7. 单击 "**转到设置**" 以完成 Office 365 E5 试用租户设置。
<br>![图像 of_page](../../media/mtp-eval-15.png) <br>

8. 将企业域连接到 Office 365 租户。 Optional选择 "**连接您已拥有的域**"，并键入您的域名。 单击“**下一步**”。
<br>![图像 of_page](../../media/mtp-eval-16.png) <br>
 
9. 您将需要添加 TXT 或 MX 记录以验证域所有权。 将 TXT 或 MX 记录添加到域后，选择 "**验证**"。
<br>![图像 of_page](../../media/mtp-eval-17.png) <br>
 
10. Optional为你的租户创建更多用户帐户。 您可以通过单击 "**下一步**" 跳过此步骤。
![图像 of_page](../../media/mtp-eval-18.png) <br>
 
11. Optional下载 Office 应用。 单击 "**下一步**" 跳过此步骤。 
<br>![图像 of_page](../../media/mtp-eval-19.png) <br>

12. Optional迁移电子邮件。 同样，您可以跳过此步骤。
<br>![图像 of_page](../../media/mtp-eval-20.png) <br>
 
13. 选择 "在线服务"。 选择 " **Exchange** " 并单击 "**下一步**"。 
<br>![图像 of_page](../../media/mtp-eval-21.png) <br>

14. 向您的域中添加 MX、CNAME 和 TXT 记录。 完成后，选择 "**验证**"。
<br>![图像 of_page](../../media/mtp-eval-22.png) <br>
 
15. 恭喜，你已完成 Office 365 租户的预配。
<br>![图像 of_page](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>启用 Microsoft 365 试用订阅

>[!NOTE]
>注册试用版将提供25个用户许可证用于一个月。 有关详细信息，请参阅[试用或购买 M365 订阅](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1)。

1. 从[Microsoft 365 管理中心](https://admin.microsoft.com/)，单击 "**帐单**"，然后导航到 "**购买服务**"。

2. 选择 " **Microsoft 365 E5** "，然后单击 "**开始免费试用**"。 
![图像 of_page](../../media/mtp-eval-24.png) <br>

3. 选择您的验证首选项：通过短信或 call。 确定后，请输入电话号码，选择 "**文本**" 或 "**呼叫我**"，具体取决于你的选择。
![图像 of_page](../../media/mtp-eval-25.png) <br>
 
4. 输入验证代码，然后单击 "**开始免费试用**"。 
<br>![图像 of_page](../../media/mtp-eval-26.png) <br>

5. 单击 "**立即试用**" 以确认你的 Microsoft 365 E5 试用版。
<br>![图像 of_page](../../media/mtp-eval-27.png) <br>
 
6. 转到**Microsoft 365 管理中心** > **用户** > **活动用户**。 选择您的用户帐户，选择 "**管理产品许可证**"，然后将来自 Office 365 e5 的许可证交换为**Microsoft 365 e5**。 单击“**保存**”。
![图像 of_page](../../media/mtp-eval-28.png) <br>
 
7. 再次选择全局管理员帐户，然后单击 "**管理用户名**"。
<br>![图像 of_page](../../media/mtp-eval-29.png) <br>

8. Optional将域从*onmicrosoft.com*更改为您自己的域，具体取决于您在前面步骤中选择的内容。 单击“**保存更改**”。
<br>![图像 of_page](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>后续步骤
||||：-------|：-----| config-onboard （.png） <br>[第3阶段：配置 & 板载](config-mtpeval.md)|为 Microsoft 威胁防护试用实验室环境配置每个 Microsoft 威胁防护支柱，并将终结点集成在一起。