---
title: 安全与合规中心内的消息跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用安全 & 合规性中心中的邮件跟踪来查明邮件发生了什么情况。
ms.openlocfilehash: 1e9f5e21655e55f711997defcb7ace0319ff4be6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197533"
---
# <a name="message-trace-in-the-security--compliance-center"></a>安全与合规中心内的消息跟踪

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="message-trace-features"></a>邮件跟踪功能

Security & 合规中心中的邮件跟踪在通过 Exchange Online 组织传递的电子邮件中遵循这些电子邮件。 您可以确定服务是否已接收、拒绝、推迟或发送邮件。 它还显示邮件在到达其最终状态之前对邮件执行的操作。

Security & 合规性中心中的邮件跟踪功能在 Exchange 管理中心 (EAC) 中提供的原始邮件跟踪改进。 您可以使用邮件跟踪中的信息来有效地回答有关邮件发生的问题、解决邮件流问题以及验证策略更改的用户问题。

> [!NOTE]
>
> - 若要执行邮件跟踪，您必须是 "组织管理"、"合规性管理" 或 "技术支持" 角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
>
> - 结果中显示的最大邮件数取决于所选的报告类型 (有关详细信息) ，请参阅 [选择报告类型](#choose-report-type) 部分。 Exchange Online PowerShell 或独立 EOP PowerShell 中的 [start-historicalsearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet 将返回结果中的所有邮件。

## <a name="open-message-trace"></a>打开邮件跟踪

1. 在上打开安全 & 合规性中心 <https://protection.office.com> 。

2. 展开 " **邮件流**"，然后选择 " **邮件跟踪**"。

## <a name="message-trace-page"></a>邮件跟踪页

从这里，可以通过单击 " **启动跟踪** " 按钮来启动新的默认跟踪。 这将在最近两天内搜索所有发件人和收件人的所有邮件。 或者，您可以使用可用查询类别中的一个存储查询，也可以按自己的方式运行这些查询，也可以将它们用作自己的查询的起始点：

- **默认查询**： Microsoft 365 提供的内置查询。

- **自定义查询**：组织在组织中保存以供将来使用的查询。

- 自动**保存的查询**：最近十个最近运行的查询。 通过此列表，可以轻松地从中断的位置开始选择。

此外，在此页面上也是一个 **可下载的报告** 部分，其中包含已提交的请求以及报告本身（如果有）可供下载。

## <a name="options-for-a-new-message-trace"></a>新邮件跟踪选项

### <a name="filter-by-senders-and-recipients"></a>按发件人和收件人进行筛选

默认值为 **所有发件人** 和 **所有收件人**，但您可以使用下列字段筛选结果：

- **由以下人员**：单击此字段可选择组织中的一个或多个发件人。 您还可以开始键入名称，列表中的项目将按您键入的内容进行筛选，这与搜索页面的行为方式非常相似。

- 对于**以下人员**：在此字段中单击以选择组织中的一个或多个收件人。

> [!NOTE]
> 您还可以键入外部发件人和收件人的电子邮件地址。 支持通配符 (例如， `*@contoso.com`) ，但不能同时在同一字段中使用多个通配符条目。 <br/><br/> 可以粘贴多个发件人或收件人列表，由分号 (`;`) 分隔。 空格 (`\s`) ，回车将返回 (`\r`) 或下一行 (`\n`) 。

### <a name="time-range"></a>时间范围

默认值为 **2 天**，但您可以指定最长为90天的日期/时间范围。 使用日期/时间范围时，请考虑以下问题：

- 默认情况下，使用时间行在 **滑块** 视图中选择时间范围。 您只能选择显示的日期或时间设置。 如果尝试选择 "介于" 值，则会将 "开始/结束" 气泡对齐到最接近的显示设置。

  ![安全 & 合规性中心内的新邮件跟踪中的滑块时间范围](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  不过，您还可以切换到 **自定义** 视图，在其中可以指定 **开始日期** 和 **结束日期** 值 (包括次数) ，还可以为日期/时间范围选择 **时区** 。 请注意， **时区** 设置适用于您的查询输入和查询结果。

  ![安全 & 合规性中心的新邮件跟踪中的自定义时间范围](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  对于10天或更少，结果将立即作为 **摘要** 报告提供。 如果指定的时间范围稍微大于10天，则结果将延迟，因为它们仅可用作可下载的 CSV 文件 ( **增强的摘要** 或 **扩展** 的报告) 。

  有关不同报告类型的详细信息，请参阅本主题中的 [选择报告类型](#choose-report-type) 部分。

  **注意**：已使用存档的邮件跟踪数据准备好了增强的摘要和扩展报告，并且在报告可供下载前最多可能需要几个小时的时间。 根据其他管理员同时提交报告请求的数量，您还可能会注意到，在处理排队请求之前，会先延迟一段时间。

- 在 **滑块** 视图中保存查询保存相对时间范围 (例如，从今天开始3天) 。 在 **自定义** 视图中保存查询会保存绝对日期/时间范围 (例如，2018-05-06 13:00 到 2018-05-08 18:00) 。

### <a name="more-search-options"></a>更多搜索选项

#### <a name="delivery-status"></a>传递状态

您可以保留 **所有** 选定的默认值，也可以选择下列值之一来筛选结果：

- 已**传递**：邮件已成功传递到预期的目标。

- **挂起**：正在尝试或重新尝试传递邮件。

- 已**展开**：通讯组收件人在传递给组中的单个成员之前展开。

- **失败**：邮件未送达。

- 已**隔离**：邮件被隔离 (为垃圾邮件、批量邮件或网络钓鱼) 。 有关详细信息，请参阅 [EOP 中隔离的电子邮件](quarantine-email-messages.md)。

- **筛选为垃圾**邮件：邮件已被识别为垃圾邮件，已被拒绝或阻止 (不隔离) 。

- **获取状态：** Microsoft 365 最近收到了邮件，但其他状态数据仍不可用。 请在几分钟后回来查看。

**注意**：**作为垃圾邮件****挂起、** **隔离**和筛选的值仅适用于少于10天的搜索。 此外，实际和报告的传递状态之间可能有5到10分钟的延迟。

#### <a name="message-id"></a>邮件 ID

这是 internet 邮件 ID (也称为 "客户端 ID") ，在邮件头的 " **邮件 ID：** 头" 字段中找到。 用户可为您提供此值来调查特定邮件。

该值在邮件生存期内是常量。 对于在 Microsoft 365 或 Exchange 中创建的邮件，值的格式为 `<GUID@ServerFQDN>` ，包括尖括号 (\< \>) 。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。 其他邮件系统可能使用不同的语法或值。 此值应是唯一的，但并不是所有的电子邮件系统都严格遵守此要求。 如果 **邮件 ID：** 标头字段不存在或对于来自外部源的传入邮件为空，则分配一个任意值。

使用 **邮件 ID** 筛选结果时，请务必包含完整的字符串，包括任何尖括号。

#### <a name="direction"></a>Direction

您可以保留 **所有** 选中的默认值，也可以选择 " **入站** (发送到组织中的收件人的邮件) 或从组织中的用户发送的 **出站** (邮件) 以筛选结果。

#### <a name="original-client-ip-address"></a>原始客户端 IP 地址

您可以通过客户端 IP 地址对结果进行文件管理，以调查发送大量垃圾邮件或恶意软件的受攻击的计算机。 虽然邮件可能看起来来自多个发件人，但很可能是同一台计算机正在生成所有邮件。

**注意**：客户端 IP 地址信息仅在10天内可用，并且仅在 **增强的摘要** 或 **扩展** 报告中可用 (可下载的 CSV 文件) 。

### <a name="choose-report-type"></a>选择报告类型

可用的报告类型包括：

- **摘要**：如果时间范围少于10天，且不需要其他筛选选项，则为可用。 搜索结果几乎会在您单击 " **搜索**" 之后立即可用。 该报告最大返回20000个结果。

- **增强的摘要** 或 **扩展**：这些报告仅可用作可下载的 CSV 文件，并且需要一个或多个以下筛选选项，而不考虑时间范围： **由这些人员**、 **这些**人员或 **邮件 ID**。 您可以对发件人或收件人使用通配符 (例如， \* @contoso .com) 。 增强的摘要报告将返回最高为50000的结果。 扩展报告将返回最大为1000的结果。

**注意**：

- 增强的摘要和扩展报告使用存档的邮件跟踪数据进行准备，并且在报告可供下载前可能需要几个小时的时间。 根据其他管理员同时提交报告请求的数量，您可能还会注意到，在开始处理排队的请求之前会有一段延迟时间。

- 虽然可以为任何日期/时间范围选择增强的摘要或扩展报告，但存档数据的最后四个小时通常对这两种类型的报告都不可用。

单击 " **下一步**" 时，将显示一个摘要页，其中列出了所选的筛选选项、报表的唯一 (可编辑) 标题，以及在邮件跟踪完成 (也可编辑的情况下接收通知的电子邮件地址，并且必须在组织的接受域之一) 中。 单击 " **准备报告** " 以提交邮件跟踪。 在 "主 **邮件跟踪** " 页面上，您可以在 **可下载报告** 部分中看到报告的状态。

有关不同报告类型中返回的信息的详细信息，请参阅下一节。

## <a name="message-trace-results"></a>邮件跟踪结果

不同的报告类型返回不同级别的信息。 以下各节介绍了不同报告中提供的信息。

### <a name="summary-report-output"></a>摘要报告输出

运行邮件跟踪后，将列出结果，并按降序排序日期/时间 (最近的第一个) 。

![安全 & 合规中心中的邮件跟踪摘要报告结果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

摘要报告包含以下信息：

- **日期**：服务收到邮件的日期和时间（使用配置的 UTC 时区）。

- **发件人**：发件人 (*别名* @ *域*) 的电子邮件地址。

- **收件人**：收件人或收件人的电子邮件地址。 对于发送给多个收件人的邮件，每个收件人有一行。 如果收件人是通讯组、动态通讯组或启用邮件的安全组，则该组将成为第一个收件人，然后组中的每个成员都在单独的行中。

- **Subject**：邮件 " **Subject：** " 字段的前256个字符。

- **状态**：这些值将在 " [传递状态](#delivery-status) " 一节中进行介绍。

默认情况下，加载第一个250结果并随时可用。 向下滚动时，将在加载下一批结果时略有暂停。 除滚动之外，您可以单击 " **全部加载** " 以加载最多为10000的所有结果。

您可以单击列标题，按该列中的值以升序或降序对结果进行排序。

您可以单击 " **筛选结果** " 按一个或多个列筛选结果。

您可以通过单击 " **导出结果** " 选择一个或多个行，然后选择 " **导出所有结果**"、" **导出加载结果**" 或 " **导出选定**项"，导出结果。

#### <a name="find-related-records-for-this-message"></a>查找此邮件的相关记录

相关邮件记录是共享同一邮件 ID 的记录。 请记住，即使在两个人之间发送的单个邮件也可以生成多个记录。 当邮件受通讯组展开、转发、邮件流 (规则（也称为传输规则) 等）的影响时，会增加记录数。

选中行的复选框后，可以通过单击显示的 " **查找相关** " 按钮，或选择 " **更多选项**" 来查找 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **此邮件) 的相关记录** ，从而查找邮件的相关记录。

有关邮件 ID 的详细信息，请参阅本主题前面的邮件 ID 一节。

#### <a name="message-trace-details"></a>邮件跟踪详细信息

在摘要报告输出中，可以使用以下任一方法来查看有关邮件的详细信息：

- 选择行 (单击除复选框之外的行中的任意位置) 。

- 选中该行的复选框，然后单击 " **更多选项**" 查看详细 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **信息**。

   ![在摘要报告邮件跟踪中双击行后的详细信息将导致安全 & 合规性中心](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

邮件跟踪详细信息包含摘要报告中不存在的以下附加信息：

- **邮件事件**：本节包含的分类可帮助对邮件所需的操作进行分类。 您可能遇到**的一些更有趣的事件**是：

  - **接收**：服务收到邮件。

  - **发送**：邮件是由服务发送的。

  - **失败**：邮件传递失败。

  - **传递**：邮件已传递到邮箱。

  - **Expand**：邮件被发送到展开的通讯组。

  - **传输**：由于内容转换、邮件收件人限制或代理，收件人被移动到分支邮件。

  - **Defer**：邮件传递被推迟，稍后可能重试。

  - **已解决**：邮件已重定向到基于 Active Directory 查找的新收件人地址。 当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。

  注意：

  - 成功传递的无事件邮件将在邮件跟踪中生成多个 **事件** 条目。

  - 此列表不应详尽。 有关更多事件的说明，请参阅 [邮件跟踪日志中的事件类型](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。 请注意，此链接是 Exchange Server (本地 Exchange) 主题。

- **详细信息**：本节包含以下详细信息：

  - **邮件 id**：此值在本主题前面的 [邮件 id](#message-id) 部分中进行了描述。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

  - **邮件大小**

  - **发件人 ip**：发送邮件的计算机的 ip 地址。 对于从 Exchange Online 发送的出站邮件，该值是空值。

  - **目标 ip**：服务尝试传递邮件的 ip 地址或地址。 如果邮件有多个收件人，则会显示这些收件人。 对于发送到 Exchange Online 的入站邮件，该值是空值。

### <a name="enhanced-summary-reports"></a>增强的摘要报告

可用 (已完成) 增强的摘要报告可在开始邮件跟踪的 **可下载报告** 部分中找到。 报告中提供了以下信息：

- **origin_timestamp** <sup>*</sup> ：服务最初接收邮件时使用配置的 UTC 时区的日期和时间。

- **sender_address**：发件人的电子邮件地址 (*别名* @ *域*) 。

- **Recipient_status**：将邮件传递给收件人的状态。 如果邮件发送给多个收件人，则它将显示所有收件人以及每个收件人的相应状态，格式为： \<*email address*\> ## \<*status*\> 。 例如：

  - **# #Receive，Send** 表示该邮件由服务接收，并发送到预定的目标。

  - **# #Receive，Fail** 表示邮件已由服务接收，但传递到目标目标失败。

  - **# #Receive，提供** 表示邮件已由服务接收，并已传递到收件人的邮箱。

- **message_subject**：邮件的 " **subject** " 字段的前256个字符。

- **total_bytes**：邮件的大小（以字节为单位），包括附件。

- **message_id**：此值在本主题前面的 [邮件 id](#message-id) 部分中进行了描述。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

- **network_message_id**：在由于分叉或通讯组扩展而可能创建的邮件的所有副本中保持的唯一邮件 id 值。 示例值为 `1341ac7b13fb42ab4d4408cf7f55890f` 。

- **original_client_ip**：发件人客户端的 ip 地址。

- **方向**性：指示是否已将邮件发送到组织的入站 (1) ，或者是否从您的组织发送出站 (2) 。

- **connector_id**：源或目标连接器的名称。 有关 Exchange Online 连接器的详细信息，请参阅 [在 Office 365 中使用连接器配置邮件流](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

- **delivery_priority** <sup>*</sup> ：邮件是以**高**、**低**还是**普通**优先级发送。

<sup>*</sup>这些属性仅在增强的摘要报告中可用。

### <a name="extended-reports"></a>扩展报告

可用 (已完成) 在邮件跟踪开头的 **可下载报告** 部分中提供了扩展报告。 实际上，来自增强的摘要报告的所有信息都可以在扩展报告 (中使用，但 **origin_timestamp** 和 **delivery_priority**) 除外。 以下附加信息仅适用于扩展报告：

- **client_ip**：提交邮件的电子邮件服务器或邮件客户端的 ip 地址。

- **client_hostname**：提交邮件的电子邮件服务器或邮件客户端的主机名或 FQDN。

- **server_ip**：源或目标服务器的 ip 地址。

- **server_hostname**：目标服务器的主机名或 FQDN。

- **source_context**：与 **源** 字段相关联的额外信息。 例如：

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **源**：负责事件的 Exchange Online 组件。 例如：

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**：这些值对应于在 "[查找此邮件的相关记录](#find-related-records-for-this-message)" 一节中介绍的**消息事件**值。

- **internal_message_id**：由当前正在处理邮件的 Exchange Online 服务器分配的邮件标识符。

- **recipient_address**：邮件收件人的电子邮件地址。 多个电子邮件地址通过分号字符 (;) 分隔。

- **recipient_count**：邮件中的总收件人数。

- **related_recipient_address**：与 `EXPAND` 、 `REDIRECT` 和事件一起用 `RESOLVE` 来显示与邮件相关联的其他收件人电子邮件地址。

- **参考**：此字段包含特定事件类型的其他信息。 例如：

  - **DSN**：包含报告链接，如果在此事件的后面生成 dsn，则它是关联的传递状态通知 (（也称为 "dsn"、"未送达" 报告、"NDR" 或 "退回邮件"）的 **message_id** 值) 。 如果这是 DSN 邮件，则此字段包含为其生成 DSN 的原始邮件的 **message_id** 值。

  - **EXPAND**：包含相关邮件的 **related_recipient_address** 值。

  - **RECEIVE**：如果邮件是由其他进程生成的，则可能包含相关邮件的 **message_id** 值 (例如，收件箱规则) 。

  - **SEND**：包含任何 DSN 邮件的 **internal_message_id** 值。

  - **传输**：包含正在分叉的邮件的 **internal_message_id** 值 (例如，通过内容转换、邮件收件人限制或代理) 。

  - **MAILBOXRULE**：包含导致收件箱规则生成出站邮件的入站邮件的 **internal_message_id** 值。

    对于其他类型的事件，此字段通常为空。

- **return_path**：发送邮件的 " **邮件发件** 人" 命令指定的返回电子邮件地址。 虽然此字段永远不为空，但它可以有表示为的 null 发件人地址值 `<>` 。

- **message_info**：有关邮件的其他信息。 例如：

  - 的消息起始日期-时间（UTC） `DELIVER` 和 `SEND` 事件。 源日期-时间是邮件第一次进入 Exchange Online 组织的时间。 UTC 日期-时间以 ISO 8601 日期-时间格式表示： `yyyy-mm-ddThh:mm:ss.fffZ` ，其中 `yyyy` = year， `mm` = month， `dd` = day， `T` 表示时间部分的开始， `hh` = 小时， `mm` = 分钟， `ss` = second， `fff` = 秒的小数， `Z` 表示 `Zulu` ，这是表示 UTC 的另一种方法。

  - 身份验证错误。 例如，您可能会看到值和身份验证 `11a` 错误发生时使用的身份验证类型。

- **tenant_id**：一个表示 Exchange Online 组织的 GUID 值 (例如， `39238e87-b5ab-4ef6-a559-af54c6b07b42`) 。

- **original_server_ip**：原始服务器的 ip 地址。

- **custom_data**：包含与特定事件类型相关的数据。 有关详细信息，请参阅以下各节。

#### <a name="custom_data-values"></a>custom_data 值

**custom_data** `AGENTINFO` 各种 Exchange Online 代理使用事件的 custom_data 字段来记录消息处理详细信息。 以下各节中介绍了一些更有趣的代理。

#### <a name="spam-filter-agent"></a>垃圾邮件筛选器代理

以**custom_data** `S:SFA` 来自垃圾邮件筛选器代理的开头的 custom_data 值。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`SFV=NSPM`|邮件被标记为非垃圾邮件并发送给预期收件人。|
|`SFV=SPM`|邮件被反垃圾邮件筛选标记为垃圾邮件 (也称为内容筛选) 。|
|`SFV=BLK`|跳过筛选但阻止邮件，因为它是由已阻止发件人发送。|
|`SFV=SKS`|在反垃圾邮件筛选处理之前，邮件被标记为垃圾邮件。 这包括符合以下邮件流程规则条件（也称为传输规则）的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。|
|`SCL=<number>`|有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。|
|`PCL=<number>`|邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](spam-confidence-levels.md)中介绍 SCL 值的方式对这些值做出解释。  |
|`DI=SB`|已阻止邮件发件人。|
|`DI=SQ`|邮件已隔离。|
|`DI=SD`|邮件已删除。|
|`DI=SJ`|邮件已发送至收件人的"垃圾邮件"文件夹。|
|`DI=SN`|邮件已通过正常出站传送池路由。|
|`DI=SO`|邮件已通过高风险传送池路由。 有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。|
|`SFS=[a]|SFS=[b]`|说明匹配此垃圾邮件规则。|
|`IPV=CAL`|邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。|
|`H=<EHLOstring>`|连接电子邮件服务器的 HELO 或 EHLO 字符串。|
|`PTR=<ReverseDNS>`|发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。|
|

针对以下垃圾邮件筛选出的邮件的示例 **custom_data** 值，如下所示：

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>恶意软件筛选器代理

以其开头的 **custom_data** 值 `S:AMA` 来自恶意软件筛选器代理。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`AMA=SUM|v=1|` 或 `AMA=EV|v=1`|已确定此邮件包含恶意软件。 `SUM` 指示任意数量的引擎可能检测到恶意软件。 `EV` 指示特定引擎检测到恶意软件。 引擎检测到恶意软件后，将触发后续操作。|
|`Action=r`|邮件已被替换。|
|`Action=p`|邮件已被忽略。|
|`Action=d`|邮件已被延迟。|
|`Action=s`|邮件已删除。|
|`Action=st`|邮件已被忽略。|
|`Action=sy`|邮件已被忽略。|
|`Action=ni`|邮件已被拒绝。|
|`Action=ne`|邮件已被拒绝。|
|`Action=b`|邮件已被阻止。|
|`Name=<malware>`|已检测到的恶意软件的名称。|
|`File=<filename>`|恶意软件中包含的文件名称。|
|

包含恶意软件的邮件的 **custom_data** 值示例如下所示：

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>传输规则代理

开头的 **custom_data** 值 `S:TRA` 来自邮件流规则的传输规则代理 (也称为传输规则) 。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`ETR|ruleId=<guid>`|匹配的规则 ID。|
|`St=<datetime>`|发生规则匹配时的日期和时间（以 UTC 为单位）。|
|`Action=<ActionDefinition>`|应用的操作。 有关可用操作的列表，请参阅 [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|`Mode=<Mode>`|规则模式。 有效值为：<ul><li>**强制**：将强制实施对规则的所有操作。</li><li>**使用策略提示进行测试：**：将发送所有策略提示操作，但不会对其他强制操作执行操作。</li><li>**不使用策略提示进行测试**：将在日志文件中列出操作，但不会以任何方式通知发件人，并且不会对强制性操作进行处理。</li></ul>|
|

与邮件流规则的条件相匹配的邮件的示例 **custom_data** 值如下所示：

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
