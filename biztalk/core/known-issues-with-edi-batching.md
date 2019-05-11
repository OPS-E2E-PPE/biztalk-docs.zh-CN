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
ms.openlocfilehash: 9941e6f88bc7bd23a9825a1960a2dcf9f92466f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330403"
---
# <a name="known-issues-with-edi-batching"></a>EDI 批处理的已知的问题
本主题介绍批处理中的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a>即使子文档批注设置为是未执行子文档拆分  
 **症状**  
  
 即使该交换的 HIPAA 架构中的 subdocument_creation_break 批注设置为"是"。 不 HIPAA 交换拆分为子文档  
  
 **可能的原因**  
  
- 入站的批处理选项发送参与方设置为"保留交换"。 HIPAA 文档将不会拆分为子文档如果出现这种情况，即使 HIPAA 架构中的 subdocument_creation_break 批注设置为"是"。  
  
- Subdocument_break 批注设置为"是"，但 subdocument_creation_break 批注未设置为"是"。  
  
  **解决方法**  
  
- 在中**验证和确认生成设置**页**EDI 属性**发送参与方的对话框中设置**入站批处理**选项属性任一**交换拆分为事务集-出错时挂起事务集**或**交换拆分为事务集-出错时挂起交换**。  
  
- HIPAA 文档将不会拆分为子文档除非的 subdocument_creation_break 批注设置为"是"。  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a>如果激活批处理业务流程时，更改批处理的配置设置了批处理验证可能会失败  
 如果在批处理业务流程正在处理一批更改批配置设置，新的配置设置将不选取该批处理。 这可能导致发送管道中的验证错误。  
  
 这些设置位于 EDI 属性对话框的批处理页。  
  
 若要解决此问题，请重新启动与批处理业务流程关联的主机实例。 这会更改批配置设置，以将立即生效。  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a>BatchControlMessageRecvLoc 接收位置只能在 64 位计算机上运行的 32 位计算机上或在 WOW 中  
 SQL 适配器只能在 32 位计算机上或在 64 位计算机上在 WOW64 仿真器下运行。 因此，BatchControlMessageRecvLoc 接收位置，这由安装程序安装和使用 SQL 适配器，将只能在 32 位计算机上或在 WOW 下运行在 64 位计算机上时。 此接收位置是批处理所必需的。  
  
 当运行 BatchControlMessageRecvLoc 接收位置在 WOW 64 位计算机上的时，您应该在另一台主机运行批处理业务流程。 如果接收位置的同一主机上运行，批处理业务流程也将在 WOW 下运行，您可能会丢失在 64 位计算机上运行的好处。  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a>批处理可以拾取意外发送端口  
 当批处理业务流程发布交换时，它将升级两个属性：ToBeBatched = False 和 DestinationPartyName = \< *PartyName*\>。 订阅到一个或两个这些属性的发送端口可以提取这些批处理交换。 请确保发送端口的筛选器的配置，以便发送端口将提取的批处理交换，它应提取。  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a>批元素计数大于所需数量的批处理的事务集可能不会提示批处理发布  
 如果批处理发布条件基于每个组或交换的事务集数目，即使批元素计数大于发布批处理所需的事务集数目，可能不会发布一批。 如果你启用确认，并设置筛选条件以将这些确认添加到批处理的批处理，则可以发生这种情况。 在本例中，组 （或交换） 中的批元素数目将大于每组 （或交换） 的事务集数目。 在此情况下，批处理不会释放如果每个组 （或交换） 的事务集数目小于所需的批处理发布数，但在同一时间的批元素数目可能会大于的事务集数目所需的批处理发布。  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a>单击开始了未不保存任何批处理元素  
 **症状**  
  
 当**启动**单击了在参与方批处理页中，已收集任何消息批处理。  
  
 **可能的原因**  
  
 从该处的日期时间**启动**被单击时间早于输入中的日期时间**激活**部分。 因此，业务流程实例已激活，但为批处理收集任何消息。 有关详细信息，请参阅[配置传出批](../core/configuring-an-outgoing-batch.md)。  
  
 **解决方法**  
  
 单击**停止**中遇到此问题的批处理配置批处理页。 设置**激活**至任一**立即启动**或早于当前时间中，输入日期时间，然后单击**启动**。 当提示重置**启动**日期时间为当前时间中，单击**确定**。 BizTalk Server 将开始在该点收集的一批消息。  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a>EDIFACT 批处理中的字节数可能取决于使用的字符集  
 在某些 EDIFACT 字符集中的字符可能是双字节字符，而在其他 EDIFACT 字符集，它们可能是单字节字符。 因此，设置基于该交换中的字符数的批发布条件时的交换中的字节数可能会因使用的字符集。  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a>字符"<"和"&"，必须以编码形式一批的信封中表示  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持以下字符以其文本的形式创建一个批处理 EDI 交换的信封字段时:"<"和"&"。  
  
 传出的批处理交换的信封字段中按原义使用任一字符将导致挂起消息，如果 EdiSend 管道用于序列化交换。  
  
 如果需要在一批的信封字段中使用下列字符之一，可以在 BizTalk 管理器中配置信封字段时在下表中使用编码的相应值：  
  
|字符|编码|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 当 BizTalk Server 验证字段的长度限制在 BizTalk Server 中的合作伙伴协议管理器 (PAM) 屏幕中，以该编码格式的每个字符当你使用上述编码格式之一时，计为单个字符管理控制台。 例如，即使编码"&lt;"只表示单个字符"\<"在批处理 EDI 交换，BizTalk Server 会将此字符计为四个字符根据特定字段的长度限制进行验证时. 这仅适用于 PAM 问题不是 EDI 组装器。  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a>在执行升级批处理业务流程期间出现异常  
 **症状**  
  
 使用自定义管道组件时，用于设置 EDI。在传入文档的 DestinationPartyId 属性，可能会收到异常发生在升级批处理业务流程的执行过程中应用程序事件日志指出的错误。  
  
 **可能的原因**  
  
 如果错误消息 ="找不到批"，此错误表明升级批处理业务流程无法即可成功辨别传入文档的批。  
  
 **解决方法**  
  
 升级批处理业务流程使用 EDI。若要查找的参与方名称的 DestinationPartyId。 该业务流程将构造一个使用参与方名称，EDI 的字符串。EncodingType 和字符串"Default"，然后查找具有匹配的批名称的批处理配置。 如果任何批配置不存在具有此名称，应用程序事件日志记录此错误并挂起业务流程实例。  
  
> [!NOTE]
>  例如，如果参与方名称为 Contoso 和 EDI。EncodingType 是 X12，业务流程将查找名为 ContosoX12Default 的批处理。  
  
 若要解决此问题，请确保批处理存在与将升级批处理业务流程通过构造的字符串匹配的名称。  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a>标记为 EDI 消息。ToBeBatched = True，并且 EDI。DestinationParties 将被挂起  
 **现象**  
  
 当使用自定义管道组件来标记通过设置 EDI 批处理的消息。ToBeBatched = True，并且 EDI。DestinationParties 到一系列方 Id，该消息将挂起的指出没有任何订户路由故障。  
  
 **可能的原因**  
  
 在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时应处理一条消息，则会将 EDI 设置的多个批处理配置。DestinationParties 属性设置为一个空格分隔参与方 Id 的列表。 路由业务流程订阅具有 EDI 消息。ToBeBatched = True，并且 EDI。DestinationParties 属性，并将使用包含在 EDI 的参与方 id 列表。要为每个 ID，创建一条消息并将消息传递到批处理业务流程的 DestinationParties 属性。  确定使用参与方的批 ID 使用，因为每个参与方配置可能只有一个批配置。  
  
 在 BizTalk Server 中，每个参与方可以有多个批配置，因此已不再够用，仅显示参与方 ID 用于确定要使用的批处理配置。  若要指示必须通过多个批处理配置处理消息，消息必须具有 EDI。BatchIDs 属性设置为一个空格分隔批 Id 应将消息发送到的列表。  
  
> [!NOTE]
>  处理消息只有一个使用标记时的一方使用 EDI 的 ID。DestinationPartyId 属性升级批处理业务流程将处理该消息。 有关详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
 **解决方法**  
  
 升级自定义管道组件，以便设置 EDI。而不是 EDI BatchIDs 属性。DestinationParties。  每个参与方，可以在 EDI 属性批处理设置页上找到特定批的批 ID。  
  
> [!NOTE]
>  如果 BatchMarker 管道组件使用的消息进行批处理标记不会出现此问题。  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a>批处理筛选器刷新超时是硬编码为 15 分钟  
 在修改时批处理筛选条件，它将需要 15 分钟才能使更改生效。 无法修改此刷新时间间隔。 如果希望筛选器会立即生效，请重新启动 BizTalk Server 主机进程。  
  
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
>  在持久化期间，批处理业务流程将通过约 30kb 扩大事务日志。  
  
 **解决方法**  
  
 若要解决此问题，请修改释放条件，以便增加批处理发布之间的时间。 有关详细信息，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)   
 [处理传入批](../core/processing-incoming-batches.md)   
 [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)   
 [配置 EDI 批](../core/configuring-edi-batches.md)