---
title: "使用 EDI 批处理的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 510ac82b-8a02-4135-87b7-0a5f288f5317
caps.latest.revision: "38"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e550a80cf8a7bbd6ae5e2b214c57d15427f919f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-batching"></a>EDI 批处理的已知问题
本主题介绍了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中批处理的已知问题。  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a>即使子文档批注设置为“是”，也不会执行子文档拆分  
 **症状**  
  
 即使在该交换 HIPAA 架构 subdocument_creation_break 批注已设置为"是"。 不 HIPAA 交换拆分为子文档  
  
 **可能的原因**  
  
-   入站的批处理的发送方的选项设置为"保留交换"。 在这种情况下，即使已将 HIPAA 架构中的 subdocument_creation_break 批注设置为“是”，HIPAA 文档也不会拆分为子文档。  
  
-   Subdocument_break 批注已设置为"是"，但 subdocument_creation_break 批注未设置为"是"。  
  
 **解决方法**  
  
-   在**验证和确认生成设置**页**EDI 属性**的发送方的对话框中设置**入站批处理**选项属性任一**将交换拆分为事务集-出错时暂停事务集**或**将交换拆分为事务集-出错时暂停交换**。  
  
-   HIPAA 文档将不拆分为子文档除非 subdocument_creation_break 批注设置为"是"。  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a>如果在批处理业务流程处于激活状态时更改批配置设置，批处理验证可能会失败  
 如果在批处理业务流程处理批的过程中更改批的配置设置，则新配置设置不会应用于该批。 这会导致发送管道中产生验证错误。  
  
 这些设置位于“EDI 属性”对话框的“批处理”页。  
  
 要解决此问题，请重新启动与批处理业务流程关联的主机实例。 这会导致立即应用批配置设置。  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a>BatchControlMessageRecvLoc 接收位置只能在 32 位计算机或带有 WOW 环境的 64 位计算机上运行  
 SQL 适配器只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。 因此，安装程序安装的使用 SQL 适配器的 BatchControlMessageRecvLoc 接收位置将只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。 此接收位置是批处理所必需的。  
  
 如果在 64 位计算机上的 WOW 下运行 BatchControlMessageRecvLoc 接收位置，则应在其他主机中运行批处理业务流程。 如果运行批处理业务流程的主机与运行接收位置的主机相同，则该批处理业务流程也将在 WOW 下运行，这样您将失去在 64 位计算机上运行所具有的优势。  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a>意外发送端口可以提取批处理  
 当批处理业务流程发布时将交换时，这样还有助于提升两个属性： ToBeBatched = False 和 DestinationPartyName = \< *PartyName*>。 订阅以上任意一个或两个属性的发送端口都可以提取这些批处理交换。 请确保配置发送端口的筛选器，使该发送端口仅提取应提取的批处理交换。  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a>批元素计数大于批处理所需的事务集数目时可能不会提示批处理的发布  
 如果批处理的发布条件基于每组或每个交换的事务集数目，即使批元素计数大于发布批处理所需的事务集数目，也可能不会发布此批处理。 当启用确认并将批处理筛选条件设置为向批处理添加此确认时，则可能出现此问题。 在这种情况下，组（或交换）中的批元素数目将大于每组（或交换）的事务集数目。 在上述情况中，如果每组（或每个交换）的事务集数目小于发布批处理所需的数目，则不会发布批处理；但同时，批元素数目可能大于发布批处理所需的事务集数目。  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a>单击“开始”后未保存任何批元素  
 **症状**  
  
 当**启动**被单击在方的批处理页中，任何消息为收集批处理。  
  
 **可能的原因**  
  
 从该处的日期时间**启动**被单击早于中输入的日期时间**激活**部分。 因此，业务流程实例已激活，但为批处理收集任何消息。 有关详细信息，请参阅[配置传出批处理](../core/configuring-an-outgoing-batch.md)。  
  
 **解决方法**  
  
 单击**停止**遇到此问题的批处理配置的批处理页中。 设置**激活**为**立即开始**或早于当前时间中，输入日期时间，然后单击**启动**。 当提示你重置**启动**从 datetime 到当前时间中，单击**确定**。 此时 BizTalk Server 将开始为批处理收集消息。  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a>EDIFACT 批处理中的字节数可能取决于使用的字符集  
 一些字符在某些 EDIFACT 字符集中可能是双字节字符，而在其他 EDIFACT 字符集中则可能是单字节字符。 鉴于以上原因，在您根据交换中的字符数设置批的发布条件时，相应交换中的字节数可能会因使用的字符集而不同。  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a>在批处理的信封中，必须以编码形式表示字符“<”和“&”  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持以下字符以其文本形式时创建的批处理的 EDI 交换的信封字段:"<"和"&"。  
  
 如果在传出批处理交换的信封字段中按原义使用上述任一字符，当 EdiSend 管道用于序列化交换时可能会导致消息挂起。  
  
 如果需要在批处理的信封字段中使用上述字符之一，以 BizTalk 管理员身份配置信封字段时，您可以使用下表中已编码的相应值：  
  
|字符|编码|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 如果使用上述编码格式之一，当 BizTalk Server 验证字段是否满足在 BizTalk Server 管理控制台的合作伙伴协议管理器 (PAM) 屏幕中的长度限制时，以该编码格式表示的每个字符都将计为一个单独字符。 例如，即使的编码"&lt;"将表示单个字符"\<"中批处理的 EDI 交换中，BizTalk Server 将此算作四个字符的特定字段的长度限制进行验证时. 此问题仅适用于 PAM，而不适用于 EDI 组装器。  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a>执行升级批处理业务流程期间出现异常  
 **症状**  
  
 当使用在传入文档中设置 EDI.DestinationPartyId 属性的自定义管道组件时，您可能会接收到应用程序事件日志中的错误，指出执行升级批处理业务流程期间发生了异常。  
  
 **可能的原因**  
  
 如果 ErrorMessage ="找不到批"，此错误指示升级批处理业务流程无法即可成功辨别传入文档的批。  
  
 **解决方法**  
  
 升级批处理业务流程使用 EDI.DestinationPartyId 来查找参与方名称。 然后，业务流程构造一个使用方名称，EDI 的字符串。EncodingType 和字符串"Default"，然后查找与批处理名称匹配某个批配置。 如果任何批配置不存在具有此名称，此错误记录到应用程序事件日志和业务流程实例处于挂起状态。  
  
> [!NOTE]
>  例如，如果当事方名称为 Contoso 和 EDI。EncodingType X12，业务流程将查找名为 ContosoX12Default 一批。  
  
 若要解决此问题，请确保一批存在具有此名称的将与升级批处理业务流程所构造的字符串匹配。  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a>使用 EDI 标记的消息。ToBeBatched = True 和 EDI。DestinationParties 都将被挂起  
 **症状**  
  
 当使用自定义管道组件将标记的批处理通过设置 EDI 消息。ToBeBatched = True 和 EDI。列表的 DestinationParties 方 Id，将用路由失败指出没有任何订户挂起消息。  
  
 **可能的原因**  
  
 在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时应处理一条消息，则会将 EDI 设置通过多个批处理配置。DestinationParties 属性设置为一个空格分隔的当事方 Id 的列表。 路由业务流程订阅具有 EDI.ToBeBatched = True 和 EDI.DestinationParties 属性的消息，会使用包含在 EDI.DestinationParties 属性中的参与方 ID 列表为每个 ID 创建消息，然后将消息传递到批处理业务流程。  通过使用方确定批处理因为每个方配置可能只有一个批配置，已使用 ID。  
  
 在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，每一方可以有多个批处理配置，因此不再不足以仅显示 pary ID 用于确定要使用的批处理配置。  若要指示多个批处理配置必须处理一条消息，消息必须 EDI。BatchIDs 属性设置为一个空格分隔的批处理消息应发送到的 Id 的列表。  
  
> [!NOTE]
>  处理标记且只有一个的邮件时方使用 EDI 的 ID。DestinationPartyId 属性升级批处理业务流程将处理该消息。 有关详细信息，请参阅[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
 **解决方法**  
  
 升级自定义管道组件，以便其设置 EDI.BatchIDs 属性，而非 EDI.DestinationParties。  特定的批处理的批处理 ID 可以找到 EDI 属性的批处理设置页上，为各参与方。  
  
> [!NOTE]
>  如果 BatchMarker 管道组件用来标记的消息的批处理不会出现此问题。  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a>批次筛选器刷新超时是硬编码为十五分钟  
 在修改批筛选器条件时，它将需要 15 分钟才能使更改生效。 此刷新时间间隔不能修改。 若要使筛选器立即生效，请重新启动 BizTalk Server 主机进程。  
  
## <a name="the-routingorchestration-suspends-after-reporting-an-uncaught-exception"></a>RoutingOrchestration 挂起报告未捕获的异常后  
 **症状**  
  
 应用程序事件日志中从 XLANG/秒开始，Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService 失败，因为未捕获时处理针对多个批处理配置的文档，你都可能会收到错误异常。  
  
 **可能的原因**  
  
 当 RoutingOrchestration 尝试将消息发送到 BatchingOrchestration 并且 BatchingOrchestration 实例不会启动，可以出现此错误。  
  
 **解决方法**  
  
 确保在提交要批处理的文档之前正在运行 BatchingOrchestration 实例。  
  
## <a name="many-active-batches-may-cause-the-biztalkmsgboxdb-logfile-to-grow-large"></a>许多活动的批处理数可能会导致变大 BizTalkMsgBoxDb 日志文件  
 **症状**  
  
 在开始几个批处理后，你可能注意到 BizTalk 消息框数据库 (BizTalkMsgBoxDb) 的事务日志已增加到较大的大小。  
  
 **可能的原因**  
  
 如果你有大量的批处理入门释放条件导致批次版本 （例如，计划以释放每分钟一批） 之间为较短间隔，则可能出现此问题。  
  
 启动一批时创建的批处理 orchestration 实例是释放一批后到数据库仍然存在一个长时间运行过程。 业务流程仍然存在，每次事务日志将会增长由于事务参与持久性。  
  
> [!NOTE]
>  在暂留过程中，批处理业务流程会将事务日志增大约 30kb。  
  
 **解决方法**  
  
 若要解决此问题，请将发行条件修改为增加批处理发布之间的时间。 有关详细信息，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)   
 [处理传入的批次](../core/processing-incoming-batches.md)   
 [对传出的 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)   
 [配置 EDI 批处理](../core/configuring-edi-batches.md)