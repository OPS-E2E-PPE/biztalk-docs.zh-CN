---
title: "EDI 接收组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d3b82e8-1168-4c2c-bf1a-886b43ff8108
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc53f4c592b767c8061fb1ed8134636322b35b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-receive-components"></a>EDI 接收组件
本主题中介绍的管道和管道组件用于处理不是 EDI/AS2 消息的 EDI 消息。 有关处理收到的 EDI/AS2 或非 EDI/AS2 消息的信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。 请注意，除 AS2 处理以外，AS2 接收组件还执行 EDI 处理。  
  
## <a name="edi-receive-pipeline"></a>EDI 接收管道  
 EDI 接收处理在 EDI 接收管道中执行。 此管道安装在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 中的 Microsoft.BizTalk.Edi.EdiPipelines.dll 内。 该管道用于处理通过任何传输接收的 EDI 消息， 但不会处理通过 HTTP 接收的 AS2 编码的 EDI 消息。 由 AS2 管道执行 AS2 编码 EDI 消息的处理。 AS2 接收管道和 EDI 管道使用相同的组件来处理 EDI 消息。  
  
> [!NOTE]
>  如果创建的接收位置使用 EDIReceive 管道，但采用 HTTP 传输类型，则可能会导致安全问题。 EdiReceive 管道将不生成 HTTP“200 OK”确认。 如果未返回 EDI 确认，连接将以非正常方式终止，但仍保持打开状态。 当超时期过后，该连接将超时。  
  
 EDIReceive 管道包括以下管道组件：  
  
-   EDI 拆装器  
  
-   BatchMarker。  
  
## <a name="edi-receive-pipeline-components"></a>EDI 接收管道组件  
 EDIReceive 管道使用以下管道组件。 这些组件安装在 Microsoft.BizTalk.Edi.PipelineComponents.dll 中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。  
  
### <a name="edi-disassembler"></a>EDI 拆装器  
 对 EDIReceive 管道中收到的 EDI 编码交换的处理大部分是由 EDI 拆装器执行的。 EDI 反汇编程序如何处理 EDI 消息的信息，请参阅[EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
### <a name="batchmarker"></a>BatchMarker  
 BatchMarker 管道组件通过以下方法来准备要进行批处理的交换：升级处理批交换所需的 BatchId、ToBeBatched 和 ToBeRouted 上下文属性。 BatchMarker 组件设置这些属性的方式取决于有多少贸易合作伙伴协议订阅相应批元素。  
  
-   如果只有一个协议订阅此批元素，BatchMarker 组件会将 ToBeBatched 上下文属性设置为 True，以便批处理业务流程提取批元素。  
  
-   如果有多个协议订阅批元素，BatchMarker 组件会将 ToBeRouted 上下文属性设置为 True，以便路由业务流程提取批元素。 它还将 BatchIds 上下文属性设置为一个以空格分隔的批处理 ID 列表。 然后，路由业务流程将为每一个批处理 ID 创建一个批元素副本，并将每个批元素副本的 ToBeBatched 属性设置为 True，以便批处理业务流程提取所有副本。  
  
 BatchMarker 组件包含在 EDIReceive 管道的最后一个阶段（贸易合作伙伴协议解析）中。 将要处理 EDI 消息的所有管道都应包含 BatchMarker 管道组件。  
  
> [!NOTE]
>  BatchMarker 组件所在的接收管道可以不包含 EDI 拆装器，以便在不解析 EDI 消息的情况下就可以执行贸易合作伙伴协议解析。  
  
 可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 BatchMarker 组件来对非 EDI 消息进行批处理。 有关详细信息，请参阅的"处理非 EDI 消息中 BatchMarker 组件"部分[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md)