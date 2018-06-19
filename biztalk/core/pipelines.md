---
title: 管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines
- deploying, pipelines
- receive pipelines, about receive pipelines
- pipelines, deploying
- send pipelines, about send pipelines
- receive pipelines
- pipelines, about pipelines
- send pipelines, stages
- send pipelines
- pipelines, receive pipelines
- pipelines, send pipelines
- receive pipelines, stages
ms.assetid: 76947dd8-728a-4fa3-bd33-7a708ae82cac
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5fec49dcc9ba21c5d117188f280f7e9b65fe2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265269"
---
# <a name="pipelines"></a>管道
管道是 Microsoft BizTalk Server 的组件，用于提供管道和筛选器集成模式的实现方式。 在接收和发送消息的过程中，由于业务原因，需要对消息执行转换，以便为其进入或离开 BizTalk Server 做准备。  
  
 一个常见示例就是您可能需要将一个以逗号分隔的平面文件转换成一个 XML 文件，以便利用 BizTalk Server 中的某些功能（例如映射）；平面文件拆装器组件实现的就是这样的功能。 在集成方案中，常需要在接收或发送消息之前对消息执行几种类型的转换；管道就是用于满足这种需求的。 使用管道，开发人员可以定义在接收或发送消息时对消息执行的一系列转换。  
  
 有两种类型的管道：发送管道和接收管道，这两种管道都与相应的端口（在其中执行管道）匹配。 *发送管道*在发送端口执行，在一个请求/响应的响应部分接收端口，而*接收管道*执行中接收位置和一个请求/响应的响应部分中发送端口。 实际上，接收管道可用于转换发布到 MessageBox 数据库的消息，而发送管道则用于已被订阅并且发送出 BizTalk Server 的消息。  
  
 每个管道都有一组阶段，执行管道时按顺序执行这些阶段。 每个阶段可以包含零个或多个组件。 最大组件数取决于具体的阶段。  
  
## <a name="receive-pipeline-stages"></a>接收管道阶段  
 ![接收管道阶段](../core/media/arch-pipe-receive.gif "arch_pipe_receive")  
  
|阶段|用途|  
|-----------|-------------|  
|**解码**|对消息数据进行解密或解码|  
|**反汇编**|将交换拆装成更小的消息并解析消息内容|  
|**验证**|验证消息数据，通常根据某个架构验证|  
|**解析参与方**|标识消息或消息上下文中与某些安全令牌相关联的 BizTalk Server 参与方|  
  
## <a name="send-pipeline-stages"></a>发送管道阶段  
 ![发送管道阶段](../core/media/arch-pipe-send.gif "arch_pipe_send")  
  
|阶段|用途|  
|-----------|-------------|  
|**预先组合**|在组装消息之前执行任何必要的消息处理|  
|**将组合**|通过添加信封、将 XML 转换为平面文件，或是执行其他一些接收管道中拆装阶段的补充任务等步骤，组装消息并为其传输做准备。|  
|**编码**|在传送前对消息进行编码或加密|  
  
 在管道中的阶段都具有*执行模式*的任一 All 或第一个匹配项，它控制如果多个组件添加到某一阶段获取执行的组件。 对于使用“全部”模式的阶段，按照每个组件在阶段中的配置顺序来调用组件处理消息。 如果模式为“第一个匹配”，将轮询每个组件以指示其是否为正确的组件，直到找到一个匹配项，此时将执行匹配的组件，而不执行其余的组件。  
  
 作为执行模式的一个示例，接收管道的拆装阶段为“第一个匹配”阶段，因此将调用阶段中的每个组件以了解其是否能够识别和处理消息。 如果组件发出肯定的响应，则不会再查询该阶段中的其他组件是否也能够处理消息。 但是，接收管道的解码阶段具有“全部”执行模式，这意味着系统将按照组件的配置顺序调用此阶段中的每个组件来处理消息。 第一个解码器可能是用于解密消息，而第二个则可能用于从某种压缩格式中对消息进行解压缩。  
  
 当开发人员希望在一个接收管道中使用多个拆装器时，在管道处理过程中会出现执行模式的一种常见结果。 通常拆装组件之间仅有轻微的不同，例如配置有相似但不同架构的两个平面文件拆装器。 在这种情况下，尽管消息可能与第二个拆装器中定义的架构匹配，但是第一个拆装器可能通过其探测确定它能够处理该消息。 只有在处理消息之后才能发现错误而消息被挂起。 在这些情况下，您可以新建一个具有更多特定探测逻辑的拆装器，或者创建两个不同的管道并在不同的接收位置接收不同的消息。  
  
## <a name="pipeline-deployment"></a>管道部署  
 在部署包含管道的程序集时，管理数据库将保存该管道。 管道与特定版本的程序集相关联的结果如下：  
  
-   如果部署使用相同管道的多个程序集，则管理数据库将为每个程序集的管道创建一个条目。  
  
-   删除包含管道的程序集时，管理数据库将删除与该程序集相关联的管道。 由于每个相关联的程序集在管理数据库中都有一个管道副本，因此删除一个程序集并不会影响其他程序集。  
  
## <a name="see-also"></a>另请参阅  
 [项目](../core/artifacts.md)