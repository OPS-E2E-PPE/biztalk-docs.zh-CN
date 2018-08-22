---
title: 发送管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, message flow
- send pipelines, about send pipelines
- messages, message flow
- send pipelines, stages
- pipelines, send pipelines
- messages, send pipelines
ms.assetid: c963b2d8-3b2b-4575-8105-c750deae8189
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef08909dbc47e11f5c9fecae6f65e01dbe79441b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270173"
---
# <a name="send-pipelines"></a>发送管道
下图显示消息处理工作流，其中突出显示了发送管道：  
  
 ![消息的处理的工作流的图示。](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")  
消息处理工作流示意图  
  
 发送管道负责在将文档发送到最终目标之前对其进行处理。 发送管道获取一条消息，并生成一条要发送的消息。  
  
 你可以创建新的发送管道或可以使用 BizTalk Server 中包含两个默认发送管道之一-传递发送管道和 XML 发送管道。  
  
 默认情况下，发送管道由三个空阶段组成：预组装、组装和编码。 本主题包含了有关填充这些阶段的设计注意事项。  
  
> [!NOTE]
>  如果向发送管道添加了使用组件，则该管道不会生成消息。  
  
## <a name="pre-assemble-stage"></a>预组装阶段  
  
-   此阶段是自定义组件的占位符，这些自定义组件将在对消息进行序列化之前对该消息执行某些操作。  
  
-   此阶段对每条消息运行一次。  
  
-   此阶段可包含 0 到 255 个组件。  
  
-   此阶段中的所有组件均将运行。  
  
## <a name="assemble-stage"></a>组装阶段  
  
-   此阶段中的组件负责组装或序列化消息，并将该消息转换为 XML 或从 XML 进行转换。  
  
-   此阶段可以不包含任何组件，也可以包含一个组件。  
  
-   此阶段中的所有组件均将运行。  
  
## <a name="encode-stage"></a>编码阶段  
  
-   此阶段用于对消息进行编码或加密的组件。  
  
    -   如果需要对消息进行签名，请将 MIME/SMIME 编码器组件或自定义编码组件置于此阶段。  
  
-   此阶段对每条消息运行一次。  
  
-   此阶段可包含 0 到 255 个组件。  
  
-   此阶段中的所有组件均将执行。  
  
## <a name="see-also"></a>另请参阅  
 [接收管道](../core/receive-pipelines.md)   
 [有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md)   
 [类型的管道](../core/types-of-pipelines.md)   
 [默认管道](../core/default-pipelines.md)   
 [管道模板](../core/pipeline-templates.md)   
 [管道组件](../core/pipeline-components.md)   
 [类型的管道组件](../core/types-of-pipeline-components.md)