---
title: "发送保留的批处理交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9bc2207-e34d-4d06-a224-bd7f8e498c27
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5813bb4881535290422e2ba01d20d4370f4e604
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="sending-a-preserved-batch-interchange"></a>发送保留的批交换
当 EDI 发送管道处理保留的出站批交换时，会将批交换作为一个整体来处理。 在创建 EDI 交换时，它通常重用现有信封（控制）段，而不会基于协议应用信封。 发生这种情况时**入站批处理选项**属性设置为**保留交换-出错时暂停交换**或**保留交换-时暂停事务集错误**。  
  
## <a name="schema-validation"></a>架构验证  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证的信封中使用批处理架构和服务架构保留批处理。 批架构用于验证保留消息的根节点；服务架构用于验证交换、组和事务集标头及尾部。 有关批处理架构的详细信息，请参阅[批处理的 EDI 架构](../core/edi-batch-schemas.md)。 有关服务架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证批处理的交换，在你的项目中使用的文档架构中的文档。  
  
## <a name="send-side-processing"></a>发送端处理  
 当 EDI 组装器处理保留的交换时，使用的交换、组和事务集标头通常与收到批交换时存在于此批交换中的交换、组和事务集标头相同。  
  
-   为交换的 X12 的单向协议选项卡中的不同页上的属性设置**协议属性**对话框 (这将决定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将创建的传出的 ISA，GS 和 ST 标头交换） 通常不适用于。  
  
-   对于 EDIFACT 交换，通常使用协议属性中的 UNA 设置。 UNA 段在 EDIFACT 编码消息中是可选的，但对于序列化保留的批交换，该段则是必需的。 如果 XML 实例中的 UNA 段未设置值，将使用发送管道组件的默认属性值。 如果未对发送管道组件的属性赋值，那么将挂起保留批的中间 XML 消息。  
  
-   如果针对保留的交换（在自定义组件中）将 `EDI.PopulateInterchangeValues` 上下文属性升级为“True”，则发送端口中的 EdiAssembler 会将所有交换、组和事务集标头填充为在协议属性中设置的值。  
  
-   如果在发送管道处理此交换前将此交换的 `EDIOverride.OverrideEdiHeader` 上下文属性升级为“True”，则可以通过设置适当的 `EDIOverride` 上下文属性值来覆盖出站文档的信封值。 有关详细信息，请参阅[重写 EDI 标头](../core/overriding-edi-headers.md)。  
  
 对于保留的没有任何错误的交换，组装器将保留各个事务集在该交换的组中的序列以及各个组在该交换中的序列。  
  
> [!NOTE]
>  使用 XML 发送管道可以发送保留批。 但是，若要执行此操作，您需要更改批架构的命名空间。 有关详细信息，请参阅[与 XML 发送管道发送保留批处理](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)。  
  
## <a name="error-processing"></a>错误处理  
 由于 XML 中存在保留标记，EDI 发送管道将批处理 EDI 交换识别为保留批。 此标记，或者\<X12InterchangeXml\>或\<EdifactInterchangeXml\>，按以下方式应用于 XML EDI 接收管道。  
  
 挂起的出错事务集具有以下特殊情况：  
  
-   如果组中的所有事务集无效，那么 EDI 发送管道将在生成的 EDI 中包含组控制段，但该组不包含任何事务集（因为将被删除）。 组页脚总数更新为零。 交换控制段保留不变。  
  
-   如果交换中的所有事务集无效，那么生成的 EDI 交换仍将包含交换控制段，但该交换将不包含任何事务集（因为将被删除）。 这会构成一个空交换。  
  
-   如果组控制段或交换控制段无效，则不会生成 EDI 编码的交换。 将在事件查看器中创建一个日志，指示已拒绝交换。  
  
## <a name="see-also"></a>另请参阅  
 [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)