---
title: "已知问题 EDI 和 AS2 状态报告 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d755dca-a4b6-44be-bc45-88c0b17685a0
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691a10671c4c8ff5f2ff77065455c100784ddd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-edi-and-as2-status-reporting"></a>已知问题 EDI 和 AS2 状态报告
本主题介绍与 EDI 状态报告在 BizTalk Server 中的已知的问题。  
  
## <a name="batch-status-reporting-data-may-not-be-updated-if-the-batch-orchestration-is-stopped-outside-of-the-partner-agreement-manager"></a>在合作伙伴协议管理器之外停止批处理业务流程可能无法更新批处理状态报告数据  
 通过参与方“EDI 属性”对话框的“批处理”页可停用批处理业务流程实例。 如果以此方式停用批处理业务流程，BizTalk Server 将更新该批处理的状态报告数据。 但是，如果以其他方式停止批处理业务流程（例如，从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台“组概述”页中的其中一个查询页停止业务流程），则可能无法更新状态报告数据，并且批处理状态报告可能过期。 例如，即使已停用批处理业务流程实例，状态报告也可能指示批处理仍处于活动状态。  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-edi-status-reporting-has-been-enabled"></a>启用 EDI 状态报告功能后需要重新启动 BizTalk 服务  
 **症状**  
  
 已启用 EDI 状态报告功能，但未生成 EDI 状态报告。  
  
 **可能的原因**  
  
 激活或停用 EDI 状态报告功能后，需要重新启动 BizTalk 服务，以使更改生效。 如果在解决方案中使用了 AS2EdiReceive 或 AS2EdiSend 管道，则需要重新启动 BizTalk 服务和 IIS 服务，以使更改生效。  
  
 **解决方法**  
  
 重新启动 BizTalk 服务（在“计算机管理”对话框中）。 如果你的解决方案中正在使用 AS2EdiReceive 管道或 AS2EdiSend 管道，请重新启动 IIS Admin service (使用*iisreset*命令)，以及。  
  
> [!NOTE]
>  启用 AS2 状态报告功能后无需重新启动 BizTalk 服务或 IIS 管理服务。  
  
## <a name="the-status-report-will-display-9999-for-the-year-when-the-as2-message-date-time-in-the-message-is-a-null-value"></a>当消息中的 AS2 消息日期时间为空值时，状态报告的年份将显示“9999”  
 如果传入 AS2 消息中的“AS2 消息日期时间”字段设置为 Null，那么在 AS2 状态报告中，该消息的“AS2 消息日期时间”字段中的年份将显示为值“9999”。  
  
 如果传入 AS2 消息中的“AS2 消息日期时间”字段无法解析（如 Mon, 21 May 2007 10:08:28 NZST），那么在 AS2 状态报告中，该消息的“AS2 消息日期时间”字段将设置为当前时间。  
  
## <a name="status-reporting-is-still-configured-after-bam-tools-have-been-uninstalled"></a>卸载 BAM 工具后仍配置有状态报告功能  
 要安装 EDI 状态报告功能，您必须安装 BAM 工具。 但是，如果已卸载 BAM 工具，则仍配置有状态报告功能。 这是设计的结果。  
  
 删除 BAM 工具后，无法再通过用户界面搜索状态报告表。 但是，如果已启用状态报告功能，BizTalk Server 仍将在状态报告表中创建记录。  
  
## <a name="only-one-edi-interchange-will-be-correlated-to-an-as2-message-in-the-status-report-ui"></a>状态报告 UI 中只有一个 EDI 交换与 AS2 消息关联  
 如果一则 AS2 消息包含多个 EDI 交换，并且您尝试显示 AS2 消息中多个 EDI 交换的状态，那么交换/ACK 状态报告中将只显示最后一个 EDI 交换。 此外， **EDI 交换控制否**AS2/MDN 状态报告中的字段将仅显示最后一个的交换控制编号。 （该交换控制编号将 AS2 消息与其 EDI 交换负载关联起来。）  
  
 AS2 消息中所有 EDI 交换的数据都保存在状态报告数据库中。 你可以在交换/ACK 状态报表采用的 AS2 消息中显示所有的交换，如果**控件 ID 等于所有**子句是状态报表查询。 这还可能显示不属于 AS2 消息的其他交换；但是，通过查看其他字段（如“发送方”、“接收方”和“交换日期时间”），您可以确定 AS2 消息中有哪些 EDI 交换。  
  
## <a name="removing-the-bam-tools-from-a-group-will-prevent-you-from-viewing-edi-or-as2-status-reports"></a>从组中删除 BAM 工具将阻止您查看 EDI 或 AS2 状态报告  
 如果从组中删除 BAM 工具，尝试查看 EDI 或 AS2 状态报告将导致错误。 出现一个此类错误表示未找到 bts_GetBatchStatusRecords 存储过程。 如果在尝试查看 EDI 或 AS2 状态报告时出现错误，请验证 EDI 和 AS2 的组、运行时和 BAM 工具的配置是否正确。  
  
 如果取消配置 BAM 工具（而不是仅删除），则可以避免此问题。 如果取消配置 BAM 工具，系统将提示您取消配置 EDI/AS2 相关功能。 如果删除 BAM 工具，则不会提示您执行此操作。  
  
## <a name="status-reporting-will-not-work-after-an-upgrade-if-the-bam-tools-are-not-configured"></a>升级后，如果未配置 BAM 工具，状态报告功能将不工作  
 要使 EDI 和 AS2 状态报告功能工作，必须配置 BAM 工具。 如果您将 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 的安装升级到后续版本，并且在升级过程中未配置 BAM 工具，则已升级的安装上的 EDI/AS2 状态报告功能将无法正确地发挥作用。  
  
 如果你想要使用状态报告在升级到 BizTalk Server 之后，，请确保在执行升级之前，配置了 BAM 工具。  
  
 如果在执行升级后状态报告功能不工作，请在升级日志中确定在升级之前是否配置了 BAM 工具。 如果没有，你可以配置 BAM 工具，并随后部署内的 EdiStatusReportingActivityDefs.xml 文件中包含的 BusinessMessageJournal BAM 活动*\<驱动器\>*: files\microsoftBizTalk Server。  
  
## <a name="disabling-transaction-set-storage-affects-an-activated-batch-but-enabling-storage-does-not"></a>禁用事务集存储会影响激活的批处理，但启用存储则不会产生任何影响  
 如果在批处理业务流程处于激活状态时禁用事务集存储，更改将立即生效。 BizTalk Server 将在启用存储的情况下存储批处理的事务集，但不会在禁用存储后存储事务集。 您可以禁用事务集存储，方法是：在“EDI 属性”对话框的“常规”窗格中清除“存储事务集/负载以用于报告”属性。  
  
 但是，如果在禁用事务集存储的情况下激活批处理业务流程实例，然后再启用该存储，则不会为创建的批处理存储任何事务集。  
  
## <a name="unicode-as2-messages-will-not-be-displayed-completely-in-text-wire-format"></a>无法以文本传输格式完全显示 UNICODE AS2 消息  
 如果 BizTalk Server 处理的 AS2 消息或 MDN 是以 UNICODE 格式编码的，并且您尝试以文本传输格式查看该消息，BizTalk Server 将无法完全显示该消息。 出现此情况的原因是 UNICODE 格式的“00”字节被解释为流的末尾。 但是，如果以二进制传输格式查看该消息，BizTalk Server 将完全显示该消息。  
  
 当在“AS2 属性”对话框的“常规”窗格中激活 AS2 消息的状态报告功能，且在“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”窗格或“作为 AS2 消息发送方的参与方”窗格中启用入站或出站 AS2 或 MDN 消息的存储时，将出现此问题。  
  
## <a name="enabling-as2-status-reporting-and-send-port-body-tracking-simultaneously-may-cause-an-error"></a>同时启用 AS2 状态报告功能和发送端口正文跟踪可能导致错误  
 如果启用 AS2 状态报告和发送端口正文跟踪同时，以下错误可能会显示在事件查看器:"消息传递引擎时遇到错误删除一个或多个消息。" 在以下情况中将出现此问题：发送端口是具有 AS2Send 和 AS2Receive 管道的静态要求响应 AS2 发送端口， 并且已启用下列属性：  
  
-   “AS2 属性”对话框的“常规”窗格中的“激活 AS2 报告”属性。  
  
-   “AS2 属性”对话框的“作为 AS2 消息接收方的参与方”窗格中的“将编码后的出站 AS2 消息存储在不可否认数据库中”。  
  
-   “发送端口属性”对话框的“跟踪”窗格中的“端口处理后请求消息”属性。  
  
 此问题的解决办法是清除“将编码后的出站 AS2 消息存储在不可否认数据库中”属性或“端口处理后请求消息”属性。 建议您禁用“端口处理后请求消息”，以使 AS2 跟踪捕获正文信息以及 AS2 状态报告中的其他信息。  
  
## <a name="edi-and-as2-message-context-properties-are-not-available-after-upgrading-to-biztalk-2009"></a>EDI 和 AS2 消息上下文属性在升级到 BizTalk 2009 后不可用  
 升级到 BizTalk Server 后，没有上下文属性显示在状态报告的任何收到升级发生之前的 EDI 或 AS2 消息。  升级后收到的消息将正确显示上下文属性。  
  
 EDI 和 AS2 上下文属性集合没有作为消息的一部分存储在之前版本的 BizTalk Server 中，并且在升级后不可用。 升级到 BizTalk Server 中，上下文属性将存储为消息的一部分的 AS2 之后但是 EDI 上下文属性不是。  
  
## <a name="interchange-date-for-received-documents-may-display-the-wrong-year-in-status-reports"></a>已接收文档的交换日期可能在状态报告中显示错误的年份  
 如果接收到的文档中 YYMMDD 格式指定日期，BizTalk Server 将使用以下逻辑来确定的年份值：  
  
-   如果 YY 大于或等于 75，则年份将显示为 19YY。  
  
-   如果 YY 小于 75，则年份将显示为 20YY。  
  
 例如，如果传入消息的 ISA09 的值包含 991113，则状态报告会将日期显示为 11/13/1999。  
  
## <a name="error-message-may-be-displayed-as-a-string-of-question-marks"></a>错误消息可能会显示为一个问号字符串。  
 在 BizTalk Server 本地化版本中，如果错误消息显示为一个问号字符串，您需要根据操作系统语言更改系统区域，才能获取所需的错误消息。 更改系统区域设置的详细信息，请参阅[更改系统区域设置](http://windows.microsoft.com/en-IN/windows-vista/Change-the-system-locale)。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)