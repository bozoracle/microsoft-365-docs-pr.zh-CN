---
title: 启用 Microsoft 365 使用情况分析
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 了解如何使用 Power BI 中的 Microsoft 365 使用情况分析模板应用来开始收集租户的数据。
ms.openlocfilehash: 249fadce15ca2e4c979d6e1930ff0d14ccd9bc08
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42355003"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="3005f-103">启用 Microsoft 365 使用情况分析</span><span class="sxs-lookup"><span data-stu-id="3005f-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="3005f-104">Microsoft 365 美国政府社区也提供 microsoft 365 的使用情况分析。</span><span class="sxs-lookup"><span data-stu-id="3005f-104">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="3005f-105">启用 Microsoft 365 使用情况分析的步骤</span><span class="sxs-lookup"><span data-stu-id="3005f-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="3005f-106">若要开始使用 Microsoft 365 使用情况分析，您必须先使数据在 Microsoft 365 管理中心中可用，然后在 Power BI 中启动模板应用。</span><span class="sxs-lookup"><span data-stu-id="3005f-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="3005f-107">获取 Power BI</span><span class="sxs-lookup"><span data-stu-id="3005f-107">Get Power BI</span></span>

<span data-ttu-id="3005f-108">如果你尚不具有 Power BI，则可以[注册 POWER Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="3005f-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="3005f-109">选择 "**免费试用**" 注册试用版，或**立即购买**以获取 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="3005f-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="3005f-110">也可展开" **产品**"，购买某一版 Power BI。</span><span class="sxs-lookup"><span data-stu-id="3005f-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="3005f-111">您需要使用 Power BI Pro 许可证来安装、自定义和分发模板应用程序。</span><span class="sxs-lookup"><span data-stu-id="3005f-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="3005f-112">有关详细信息，请参阅[先决条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="3005f-112">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="3005f-113">你需要使用 Power BI Pro 许可证来共享你的内容，以及你将其与之共享的人员，或者内容需要位于[高级容量](https://docs.microsoft.com/power-bi/service-premium-what-is)的工作区中。</span><span class="sxs-lookup"><span data-stu-id="3005f-113">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="3005f-114">启用模板应用程序</span><span class="sxs-lookup"><span data-stu-id="3005f-114">Enable the template app</span></span>

<span data-ttu-id="3005f-115">若要启用模板应用程序，您必须是**全局管理员**、**报告读者**、 **Exchange 管理员**、 **Skype for business 管理员**或**SharePoint 管理员**。</span><span class="sxs-lookup"><span data-stu-id="3005f-115">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="3005f-116">有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3005f-116">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="3005f-117">在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。</span><span class="sxs-lookup"><span data-stu-id="3005f-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="3005f-118">在 "**使用情况**" 页上，找到 " **Microsoft 365 使用情况分析**卡"，然后选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="3005f-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="3005f-119">在打开的 "报告" 面板中，设置 "将**数据提供给 Microsoft 365 使用情况分析以供 Power BI** **保存** **"** \> 。</span><span class="sxs-lookup"><span data-stu-id="3005f-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="3005f-120">这将启动数据收集过程，并将在2到48小时内完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="3005f-120">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="3005f-121">数据收集完成后，"**转到 POWER BI** " 按钮将处于启用状态（不再为灰色）。</span><span class="sxs-lookup"><span data-stu-id="3005f-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="3005f-122">启动模板应用程序</span><span class="sxs-lookup"><span data-stu-id="3005f-122">Initiate the template app</span></span>

<span data-ttu-id="3005f-123">若要启动模板应用程序，您必须是**全局管理员**、**报告读者**、 **Exchange 管理员**、 **Skype for business 管理员**或**SharePoint 管理员**。</span><span class="sxs-lookup"><span data-stu-id="3005f-123">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="3005f-124">复制租户 Id，然后选择 "**转到 POWER BI**"。</span><span class="sxs-lookup"><span data-stu-id="3005f-124">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="3005f-125">转到 Power BI 后，请进行登录。</span><span class="sxs-lookup"><span data-stu-id="3005f-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="3005f-126">选择 "应用-从导航菜单 >获取应用程序"。</span><span class="sxs-lookup"><span data-stu-id="3005f-126">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="3005f-127">在 "**应用程序**" 选项卡中，在 "搜索" 框中键入 microsoft 365，然后选择 " **microsoft 365 使用率分析** \> **现在获取它**"。</span><span class="sxs-lookup"><span data-stu-id="3005f-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="3005f-128">[![选择 "立即获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="3005f-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="3005f-129">安装应用程序后。</span><span class="sxs-lookup"><span data-stu-id="3005f-129">Once the app is installed.</span></span> <span data-ttu-id="3005f-130">单击磁贴以打开它。</span><span class="sxs-lookup"><span data-stu-id="3005f-130">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="3005f-131">单击 "**浏览应用**程序" 以查看包含示例数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3005f-131">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="3005f-132">单击 "**连接**" 将应用程序连接到您的组织的数据。</span><span class="sxs-lookup"><span data-stu-id="3005f-132">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="3005f-133">**单击 "连接"** 后，在 "**连接到 Microsoft 365 使用情况分析**" 屏幕上键入您在步骤（1）中\>复制的 "租户 Id" （**下一**步）。</span><span class="sxs-lookup"><span data-stu-id="3005f-133">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="3005f-134">在下一个屏幕上，选择 " **oAuth2** " 作为**身份验证方法** \> **登录**。</span><span class="sxs-lookup"><span data-stu-id="3005f-134">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="3005f-135">如果选择任何其他身份验证方法，则与模板应用程序的连接将失败。</span><span class="sxs-lookup"><span data-stu-id="3005f-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="3005f-137">模板应用程序实例化后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中提供。</span><span class="sxs-lookup"><span data-stu-id="3005f-137">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="3005f-138">仪表板的初始加载将需要2到30分钟时间。</span><span class="sxs-lookup"><span data-stu-id="3005f-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="3005f-139">租户级别聚合将在所有报告中可用。</span><span class="sxs-lookup"><span data-stu-id="3005f-139">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="3005f-140">**用户级别的详细信息仅在选择 "日历" 月的第一天或第15天后才会变为可用**。</span><span class="sxs-lookup"><span data-stu-id="3005f-140">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="3005f-141">这将影响 "用户活动" 下的所有报告（有关如何查看和使用这些报告的提示，请参阅[在 Microsoft 365 使用情况分析中导航和利用报告](navigate-and-utilize-reports.md)）。</span><span class="sxs-lookup"><span data-stu-id="3005f-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="3005f-142">使收集的数据匿名</span><span class="sxs-lookup"><span data-stu-id="3005f-142">Make the collected data anonymous</span></span>

<span data-ttu-id="3005f-143">若要使收集的所有报表数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="3005f-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="3005f-144">这将在报告中和模板应用程序中隐藏可识别信息，如用户、组和网站名称。</span><span class="sxs-lookup"><span data-stu-id="3005f-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="3005f-145">在管理中心中，转到 "**设置** \> "**设置**，在 "**服务**" 选项卡下，选择 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="3005f-145">In the admin center, go to the **Settings** \> **Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="3005f-146">选择 "**报告**"，然后选择 "**显示匿名标识符**"。</span><span class="sxs-lookup"><span data-stu-id="3005f-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="3005f-147">此设置既可应用于使用情况报告，也可应用于模板应用。</span><span class="sxs-lookup"><span data-stu-id="3005f-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="3005f-148">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="3005f-148">Select **Save changes**.</span></span>