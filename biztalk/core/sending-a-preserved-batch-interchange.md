---
title: 发送保留的批交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9bc2207-e34d-4d06-a224-bd7f8e498c27
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 327ef8db3042199cc541d53402ea25c8d36b4a06
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399077"
---
# <a name="sending-a-preserved-batch-interchange"></a>发送保留的批交换
当 EDI 发送管道处理出站时保留的批处理交换时，它处理批的交换作为一个整体。 它通常重用现有信封 （控制） 段中创建 EDI 交换，而不应用基于协议的信封。 发生这种情况时**入站批处理选项**属性设置为**保留交换-出错时挂起交换**或**保留交换-挂起事务集错误**。  
  
## <a name="schema-validation"></a>架构验证  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 验证使用批架构和服务架构保留批的信封。 批架构用于验证保留消息; 的根节点服务架构用于验证交换、 组和事务集标头和尾部。 有关批架构的详细信息，请参阅[EDI 批架构](../core/edi-batch-schemas.md)。 服务架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 验证在项目中使用文档架构的批处理交换中的文档。  
  
## <a name="send-side-processing"></a>发送端处理  
 当 EDI 组装器处理保留的交换时，它通常使用相同的交换、 组和事务集标头时接收批处理交换中存在。  
  
- 对于 X12 交换，在单向协议选项卡中的不同页上的属性设置**协议属性**对话框中 (这将决定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将创建的传出的 ISA、 GS 和 ST 标头交换） 通常不适用。  
  
- 对于 EDIFACT 交换，通常使用协议属性中的 UNA 设置。 UNA 段中是可选的 EDIFACT 编码的消息，但它是必需的序列化保留的批交换。 如果没有 UNA 段中的 XML 实例的值，将使用发送管道组件的默认属性值。 如果发送管道组件属性值，则将挂起保留的批的中间 XML 消息。  
  
- 如果您将升级`EDI.PopulateInterchangeValues`上下文属性设置为"True"（在自定义组件中） 保留交换，发送端口中的 EdiAssembler 会将所有填充的交换、 组和事务集标头为协议中设置的值属性。  
  
- 如果您将升级`EDIOverride.OverrideEdiHeader`上下文属性设置为"True"的交换的发送管道处理之前，您可以重写出站文档的信封值通过设置适当`EDIOverride`上下文属性值。 有关详细信息，请参阅[替代 EDI 标头](../core/overriding-edi-headers.md)。  
  
  对于保留的交换的没有任何错误，则组装器将会保留与交换的组和交换中的组的序列中的事务集的序列。  
  
> [!NOTE]
>  您可以发送保留的批使用 XML 发送管道。 但是，若要执行此操作需要更改批架构的命名空间。 有关详细信息，请参阅[使用 XML 发送管道发送保留批](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)。  
  
## <a name="error-processing"></a>错误处理  
 EDI 发送管道将批处理的 EDI 交换为保留批识别由于 XML 中的保留标记。 此标记，或者\<X12InterchangeXml\>或\<EdifactInterchangeXml\>，应用于 XML 由 EDI 接收管道。  
  
 具有以下特殊情况适用于错误时挂起事务集：  
  
-   如果在组中的所有事务都集将无效，则 EDI 发送管道将包含组控制段中生成的 EDI 中，但组将不包含任何事务都集 （因为它们将被删除）。 组页脚总数更新为零。 交换控制段保持不变。  
  
-   如果交换中的所有事务集无效，然后交换控制段将仍包含在生成的 EDI 交换，但该交换将不包含任何事务集 （因为它们将被删除）。 这会构成一个空交换。  
  
-   如果组控制段或交换控制段无效，将生成的 EDI 编码的交换。 日志将创建在事件查看器，指示已拒绝交换。  
  
## <a name="see-also"></a>请参阅  
 [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)