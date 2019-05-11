---
title: 管道 |Microsoft Docs
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
ms.openlocfilehash: e8ef3fab99e8356d00da859a29548064fc4af086
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395746"
---
# <a name="pipelines"></a>管道
管道是 Microsoft BizTalk Server 提供的管道和筛选器的集成模式的实现的一个组件。 在接收和发送的消息，有业务原因对消息，以使其进入或离开 BizTalk Server 准备好执行转换。  
  
 常见示例是，您可能需要将以逗号分隔的平面文件转换为 XML 文件，以便利用 BizTalk Server 中的某些功能映射; 例如平面文件拆装器组件实现这一。 通常需要执行几种类型的转换到一条消息之前接收或发送; 集成方案中使用管道为满足此要求。 管道可让开发人员定义的一系列将一条消息时对其执行的转换已接收或发送。  
  
 有两种类型的管道，发送和接收，以及这些与在其中执行的端口匹配。 *发送管道*执行的发送端口和请求/响应的响应部分在接收端口，而*接收管道*执行在接收位置，和要求/响应的响应部分发送端口。 实际上，接收管道都应使用转换而旨在使用已被订阅并且 BizTalk server 发送的消息的发送管道发布到 MessageBox 数据库的消息。  
  
 每个管道包含一组执行管道时按顺序执行的阶段。 每个阶段可以包含零个或多个组件。 最大组件数取决于该阶段。  
  
## <a name="receive-pipeline-stages"></a>接收管道阶段  
 ![接收管道阶段](../core/media/arch-pipe-receive.gif "arch_pipe_receive")  
  
|阶段|用途|  
|-----------|-------------|  
|**Decode**|进行解密或解码的消息数据|  
|**反汇编**|将交换拆装成较小的消息并解析消息内容|  
|**验证**|验证消息的数据，通常根据某个架构|  
|**解析参与方**|标识与消息或消息上下文中某些安全令牌相关联的 BizTalk Server 参与方|  
  
## <a name="send-pipeline-stages"></a>发送管道阶段  
 ![发送管道阶段](../core/media/arch-pipe-send.gif "arch_pipe_send")  
  
|阶段|用途|  
|-----------|-------------|  
|**Pre-assemble**|执行任何必要的消息处理在组装消息之前|  
|**组合**|组装消息并使其可以执行如添加信封，将 XML 转换为平面文件或在接收管道的拆装阶段的补充其他任务的步骤来传输做好准备|  
|**Encode**|进行编码或加密前传递消息|  
  
 在管道中的阶段都有*执行模式*要么都的或第一个匹配项，它控制如果多个组件添加到阶段执行的组件。 对于模式的所有阶段，调用每个组件来处理该消息中的阶段中配置的顺序。 第一个匹配模式时，每个组件进行轮询，以指示它是正确的组件，直到找到匹配项，此时匹配的组件执行，而不执行其余的组件。  
  
 作为执行模式的示例，接收管道的拆装阶段是第一个匹配阶段，因此调用阶段中的每个组件以查看它识别该消息并可以对其进行处理。 如果该组件发出肯定的响应，然后不查询该阶段中的任何其他组件以查看如果它们可以处理该消息。 但是，接收管道的解码阶段具有执行模式的好处是，这意味着调用在此阶段中的每个组件来处理该消息在其中配置的顺序。 第一个解码器可能是对消息进行解密，而第二个可能要对从某种压缩格式消息进行解压缩。  
  
 当开发人员希望在一个接收管道中使用多个拆装器时，将出现在管道处理过程的执行模式的一种常见结果。 通常拆装组件仅略有不同，例如两个相似但不同配置的架构与平面文件拆装器。 在这种情况下，虽然消息实际上可能匹配的第二个拆装器中定义的架构，可能会通过它可以处理该消息其探测确定第一个拆装器。 它是仅在处理发现错误的消息和挂起的消息后。 在这些情况下，可以创建新的拆装器中，具有更多特定探测逻辑或创建两个不同的管道并接收不同中不同的消息接收位置。  
  
## <a name="pipeline-deployment"></a>管道部署  
 在部署包含管道的程序集时，管理数据库将保存管道。 管道是与以下结果与程序集的特定版本相关联：  
  
-   如果部署使用相同管道的多个程序集时，管理数据库将为每个程序集创建管道的一个条目。  
  
-   当您删除包含管道的程序集时，管理数据库中删除与该程序集相关联的管道。 由于没有为管理数据库中每个关联的程序集的管道的副本，因此删除一个程序集不会影响其他。  
  
## <a name="see-also"></a>请参阅  
 [项目](../core/artifacts.md)