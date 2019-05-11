---
title: EDI 接收组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d3b82e8-1168-4c2c-bf1a-886b43ff8108
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93eb1bbb4e1a43d8cb9ff7e2a97cb2a6610c6687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389386"
---
# <a name="edi-receive-components"></a>EDI 接收组件
管道和 EDI/AS2 消息不是此主题处理 EDI 消息中所述的管道组件。 有关处理收到的 EDI/AS2 或 EDI/AS2 消息的信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。 请注意 AS2 接收组件还执行 EDI 处理除 AS2 处理。  
  
## <a name="edi-receive-pipeline"></a>EDI 接收管道  
 EDI 接收 EDI 接收管道中执行处理。 此管道安装在中的 microsoft.biztalk.edi.edipipelines.dll 内[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。 此管道处理通过任何传输接收的 EDI 消息。 它不会处理通过 HTTP 接收 AS2 编码的 EDI 消息。 由 AS2 管道执行 AS2 编码的 EDI 消息的处理。 AS2 接收管道都使用相同的组件来处理和 EDI 管道使用 EDI 消息。  
  
> [!NOTE]
>  如果您创建的接收位置使用 EDIReceive 管道，并且具有 HTTP 传输类型，则可能出现安全问题。 EdiReceive 管道将不会生成 HTTP"200 确定"确认。 如果不返回任何 EDI 确认，则连接将不正常终止，但将保持打开状态。 超时期限已过期时，该连接将超时时间。  
  
 EDIReceive 管道包括以下管道组件：  
  
-   EDI 拆装器  
  
-   BatchMarker。  
  
## <a name="edi-receive-pipeline-components"></a>EDI 接收管道组件  
 EDIReceive 管道使用以下管道组件。 这些组件安装在中的 Microsoft.BizTalk.Edi.PipelineComponents.dll[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。  
  
### <a name="edi-disassembler"></a>EDI 拆装器  
 EDI 拆装器 EDIReceive 管道中执行大多数处理收到的 EDI 编码交换。 有关 EDI 拆装器如何处理 EDI 消息的信息，请参阅[EDI 拆装器的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
### <a name="batchmarker"></a>BatchMarker  
 BatchMarker 管道组件准备的交换进行批处理的提升的 BatchId、 ToBeBatched 和 ToBeRouted 上下文属性所需的批处理的交换处理。 BatchMarker 组件设置这些属性的方式取决于多少贸易合作伙伴协议订阅批元素。  
  
- 如果只有一个协议订阅相应批元素，BatchMarker 组件设置为 True，将 ToBeBatched 上下文属性，以便批处理业务流程提取批元素。  
  
- 如果多个协议订阅批元素，BatchMarker 组件设置为 True，将 ToBeRouted 上下文属性，以便路由业务流程提取批元素。 它还 BatchIds 上下文属性设置为批处理 Id 的空格分隔列表。 路由业务流程将为每个批 ID，制作一份批元素，然后将 ToBeBatched 属性设置为 True 的批元素，每个副本上，以便批处理业务流程将提取所有副本。  
  
  BatchMarker 组件包含在 EDIReceive 管道的最后一个阶段 （贸易合作伙伴协议解析）。 将处理 EDI 消息的所有管道应都包含 BatchMarker 管道组件。  
  
> [!NOTE]
>  可以不包含 EDI 拆装器，以便执行贸易合作伙伴协议解析，而不解析 EDI 消息的接收管道中包含 BatchMarker 组件。  
  
 可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BatchMarker 组件来对非 EDI 消息进行批处理。 有关详细信息，请参阅的"处理非 EDI 消息在 BatchMarker 组件"部分[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)