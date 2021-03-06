---
title: EOP 设置的示例脚本-多租户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解如何使用 PowerShell 将配置设置应用到您在 Microsoft Exchange Online Protection (EOP) 中的租户。
ms.openlocfilehash: 6e33ceb6a9daa88bfefd4ec08ac9f2a9f34a942f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198675"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>将 EOP 设置应用到多个租户的示例脚本

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


以下示例脚本允许管理多个租户（公司）的 Microsoft Exchange Online Protection (EOP) 管理员使用 Windows PowerShell 将配置设置应用到租户。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>在多个租户上运行脚本或 cmdlet

1. 使用 Excel 等应用程序创建 .csv 文件（例如，c:\scripts\inputfile.csv）：

2. 在 .csv 文件中，指定两个列名称：UserName 和 Cmdlet。

3. 对于 .csv 文件中的每一行，在 UserName 列中添加租户的管理员名称，在 Cmdlet 列中添加对该租户运行的 cmdlet。例如，使用 admin@contoso.com 和 Get-AcceptedDomain。

4. 将 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 脚本复制到记事本中，然后将该文件保存到易于查找的位置 (例如，c：\scripts) 。

5. 使用以下语法运行此脚本：

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   下面是一个示例：

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 每个租户都将登录到，脚本将运行。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
