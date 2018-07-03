---
title: EDI 批处理的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510ac82b-8a02-4135-87b7-0a5f288f5317
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c33be4da2db28fb38c3f81d3d1aaa5316a0a16a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997166"
---
# <a name="known-issues-with-edi-batching"></a>EDI 批处理的已知问题
本主题介绍了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中批处理的已知问题。  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a>即使子文档批注设置为“是”，也不会执行子文档拆分  
 **症状**  
  
 即使该交换的 HIPAA 架构中的 subdocument_creation_break 批注设置为"是"。 不 HIPAA 交换拆分为子文档  
  
 **可能的原因**  
  
- 入站的批处理选项发送参与方设置为"保留交换"。 在这种情况下，即使已将 HIPAA 架构中的 subdocument_creation_break 批注设置为“是”，HIPAA 文档也不会拆分为子文档。  
  
- Subdocument_break 批注设置为"是"，但 subdocument_creation_break 批注未设置为"是"。  
  
  **解决方法**  
  
- 在中**验证和确认生成设置**页**EDI 属性**发送参与方的对话框中设置**入站批处理**选项属性任一**交换拆分为事务集-出错时挂起事务集**或**交换拆分为事务集-出错时挂起交换**。  
  
- HIPAA 文档将不会拆分为子文档除非的 subdocument_creation_break 批注设置为"是"。  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a>如果在批处理业务流程处于激活状态时更改批配置设置，批处理验证可能会失败  
 如果在批处理业务流程处理批的过程中更改批的配置设置，则新配置设置不会应用于该批。 这会导致发送管道中产生验证错误。  
  
 这些设置位于“EDI 属性”对话框的“批处理”页。  
  
 要解决此问题，请重新启动与批处理业务流程关联的主机实例。 这会导致立即应用批配置设置。  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a>BatchControlMessageRecvLoc 接收位置只能在 32 位计算机或带有 WOW 环境的 64 位计算机上运行  
 SQL 适配器只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。 因此，安装程序安装的使用 SQL 适配器的 BatchControlMessageRecvLoc 接收位置将只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。 此接收位置是批处理所必需的。  
  
 如果在 64 位计算机上的 WOW 下运行 BatchControlMessageRecvLoc 接收位置，则应在其他主机中运行批处理业务流程。 如果运行批处理业务流程的主机与运行接收位置的主机相同，则该批处理业务流程也将在 WOW 下运行，这样您将失去在 64 位计算机上运行所具有的优势。  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a>意外发送端口可以提取批处理  
 时批处理业务流程发布交换，它将升级两个属性： ToBeBatched = False 和 DestinationPartyName = \< *PartyName*\>。 订阅以上任意一个或两个属性的发送端口都可以提取这些批处理交换。 请确保配置发送端口的筛选器，使该发送端口仅提取应提取的批处理交换。  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a>批元素计数大于批处理所需的事务集数目时可能不会提示批处理的发布  
 如果批处理的发布条件基于每组或每个交换的事务集数目，即使批元素计数大于发布批处理所需的事务集数目，也可能不会发布此批处理。 当启用确认并将批处理筛选条件设置为向批处理添加此确认时，则可能出现此问题。 在这种情况下，组（或交换）中的批元素数目将大于每组（或交换）的事务集数目。 在上述情况中，如果每组（或每个交换）的事务集数目小于发布批处理所需的数目，则不会发布批处理；但同时，批元素数目可能大于发布批处理所需的事务集数目。  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a>单击“开始”后未保存任何批元素  
 **症状**  
  
 当**启动**单击了在参与方批处理页中，已收集任何消息批处理。  
  
 **可能的原因**  
  
 从该处的日期时间**启动**被单击时间早于输入中的日期时间**激活**部分。 因此，业务流程实例已激活，但为批处理收集任何消息。 有关详细信息，请参阅[配置传出批](../core/configuring-an-outgoing-batch.md)。  
  
 **解决方法**  
  
 单击**停止**中遇到此问题的批处理配置批处理页。 设置**激活**至任一**立即启动**或早于当前时间中，输入日期时间，然后单击**启动**。 当提示重置**启动**日期时间为当前时间中，单击**确定**。 此时 BizTalk Server 将开始为批处理收集消息。  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a>EDIFACT 批处理中的字节数可能取决于使用的字符集  
 一些字符在某些 EDIFACT 字符集中可能是双字节字符，而在其他 EDIFACT 字符集中则可能是单字节字符。 鉴于以上原因，在您根据交换中的字符数设置批的发布条件时，相应交换中的字节数可能会因使用的字符集而不同。  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a>在批处理的信封中，必须以编码形式表示字符“<”和“&”  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持以下字符以其文本的形式创建一个批处理 EDI 交换的信封字段时:"<"和"&"。  
  
 如果在传出批处理交换的信封字段中按原义使用上述任一字符，当 EdiSend 管道用于序列化交换时可能会导致消息挂起。  
  
 如果需要在批处理的信封字段中使用上述字符之一，以 BizTalk 管理员身份配置信封字段时，您可以使用下表中已编码的相应值：  
  
|字符|编码|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 如果使用上述编码格式之一，当 BizTalk Server 验证字段是否满足在 BizTalk Server 管理控制台的合作伙伴协议管理器 (PAM) 屏幕中的长度限制时，以该编码格式表示的每个字符都将计为一个单独字符。 例如，即使编码"&lt;"只表示单个字符"\<"在批处理 EDI 交换，BizTalk Server 会将此字符计为四个字符根据特定字段的长度限制进行验证时. 此问题仅适用于 PAM，而不适用于 EDI 组装器。  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a>执行升级批处理业务流程期间出现异常  
 **症状**  
  
 当使用在传入文档中设置 EDI.DestinationPartyId 属性的自定义管道组件时，您可能会接收到应用程序事件日志中的错误，指出执行升级批处理业务流程期间发生了异常。  
  
 **可能的原因**  
  
 如果错误消息 ="找不到批"，此错误表明升级批处理业务流程无法即可成功辨别传入文档的批。  
  
 **解决方法**  
  
 升级批处理业务流程使用 EDI.DestinationPartyId 来查找参与方名称。 该业务流程将构造一个使用参与方名称，EDI 的字符串。EncodingType 和字符串"Default"，然后查找具有匹配的批名称的批处理配置。 如果任何批配置不存在具有此名称，应用程序事件日志记录此错误并挂起业务流程实例。  
  
> [!NOTE]
>  例如，如果参与方名称为 Contoso 和 EDI。EncodingType 是 X12，业务流程将查找名为 ContosoX12Default 的批处理。  
  
 若要解决此问题，请确保批处理存在与将升级批处理业务流程通过构造的字符串匹配的名称。  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a>标记为 EDI 消息。ToBeBatched = True，并且 EDI。DestinationParties 将被挂起  
 **现象**  
  
 当使用自定义管道组件来标记通过设置 EDI 批处理的消息。ToBeBatched = True，并且 EDI。DestinationParties 到一系列方 Id，该消息将挂起的指出没有任何订户路由故障。  
  
 **可能的原因**  
  
 在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时应处理一条消息，则会将 EDI 设置的多个批处理配置。DestinationParties 属性设置为一个空格分隔参与方 Id 的列表。 路由业务流程订阅具有 EDI.ToBeBatched = True 和 EDI.DestinationParties 属性的消息，会使用包含在 EDI.DestinationParties 属性中的参与方 ID 列表为每个 ID 创建消息，然后将消息传递到批处理业务流程。  确定使用参与方的批 ID 使用，因为每个参与方配置可能只有一个批配置。  
  
 在 BizTalk Server 中，每个参与方可以有多个批配置，因此已不再够用，仅显示参与方 ID 用于确定要使用的批处理配置。  若要指示必须通过多个批处理配置处理消息，消息必须具有 EDI。BatchIDs 属性设置为一个空格分隔批 Id 应将消息发送到的列表。  
  
> [!NOTE]
>  处理消息只有一个使用标记时的一方使用 EDI 的 ID。DestinationPartyId 属性升级批处理业务流程将处理该消息。 有关详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
 **解决方法**  
  
 升级自定义管道组件，以便其设置 EDI.BatchIDs 属性，而非 EDI.DestinationParties。  每个参与方，可以在 EDI 属性批处理设置页上找到特定批的批 ID。  
  
> [!NOTE]
>  如果 BatchMarker 管道组件使用的消息进行批处理标记不会出现此问题。  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a>批处理筛选器刷新超时是硬编码为 15 分钟  
 在修改时批处理筛选条件，它将需要 15 分钟才能使更改生效。 此刷新时间间隔不能修改。 若要使筛选器立即生效，请重新启动 BizTalk Server 主机进程。  
  
## <a name="the-routingorchestration-suspends-after-reporting-an-uncaught-exception"></a>报告未捕获的异常后挂起 RoutingOrchestration  
 **现象**  
  
 在应用程序事件日志中启动 XLANG/s 的 Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService 失败，因为未捕获时处理目标为多个批处理配置的文档，您都可能会收到错误异常。  
  
 **可能的原因**  
  
 RoutingOrchestration 尝试将消息发送到 BatchingOrchestration 和 BatchingOrchestration 实例未启动时，会出现此错误。  
  
 **解决方法**  
  
 确保在提交文档要进行批处理之前正在运行 BatchingOrchestration 实例。  
  
## <a name="many-active-batches-may-cause-the-biztalkmsgboxdb-logfile-to-grow-large"></a>许多活动的批处理可能会导致 BizTalkMsgBoxDb 日志文件变得大  
 **现象**  
  
 启动多个批次之后，你可能会注意到 BizTalk messagebox 数据库 (BizTalkMsgBoxDb) 的事务日志已增长到很大。  
  
 **可能的原因**  
  
 如果您有大量的批处理发布条件的入门导致短暂的间隔批处理发布 （例如，计划发布每隔一分钟的批处理） 之间，则可以会出现此问题。  
  
 在启动批处理时创建的批处理业务流程实例是一个长时间运行的过程，在释放一批后保存到数据库。 业务流程仍然存在，每次事务日志增长将由于事务参与持久性。  
  
> [!NOTE]
>  在暂留过程中，批处理业务流程会将事务日志增大约 30kb。  
  
 **解决方法**  
  
 若要解决此问题，请将发行条件修改为增加批处理发布之间的时间。 有关详细信息，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)   
 [处理传入批](../core/processing-incoming-batches.md)   
 [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)   
 [配置 EDI 批](../core/configuring-edi-batches.md)