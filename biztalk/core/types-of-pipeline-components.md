---
title: "类型的管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: pipelines, components
ms.assetid: 9b493758-6b0f-4223-94bb-8f077ee735a9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ba18aed137380f6b3d491ad52cfcee94bf111a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="types-of-pipeline-components"></a>类型的管道组件
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了三种管道组件类型：常规、组装和拆装。 这三种类型均可实现探测功能。 本主题介绍每种组件类型及其通常所用的阶段。  
  
## <a name="general"></a>常规  
 常规组件在接收一个消息后对其进行处理，然后生成一个消息，或不生成任何消息。  
  
 提供的常规组件包括 MIME/SMIME 解码器、MIME/SMIME 编码器、参与方解析和验证器组件。 您可能需要创建自定义常规组件，以便在发送消息前压缩消息的大小，或在等待用于处理消息的其他信息时使用该消息。  
  
 常规组件应置于解码、编码、预组装、解析参与方或验证阶段中。  
  
 有关开发常规管道组件的信息，请参阅[开发的常规管道组件](../core/developing-a-general-pipeline-component.md)。  
  
## <a name="assembling"></a>组合  
 组装组件用于执行准备待发送消息方面的许多工作。 首先，该组件会根据组装器的类型和架构中设置的属性，将 XML 消息转换为相应的 XML 或非 XML 本地格式。 此外，组装组件还会将消息组装并包装到信封中，或向消息添加头部或尾部（或同时添加这二者）。 在组装期间，某些属性将从消息上下文移至文档的正文，或移至信封。  
  
 BizTalk 框架组装器、平面文件组装器和 XML 组装器组件是默认的组装组件。  
  
 组装组件应置于发送管道的组装阶段。  
  
 有关开发组装管道组件的信息，请参阅[开发组合管道组件](../core/developing-an-assembling-pipeline-component.md)。  
  
## <a name="disassembling"></a>反汇编  
 拆装组件对消息进行许多准备，以根据 BizTalk Server 中使用的信封和文档架构将消息拆分成若干个单独文档。 首先，拆装组件会将非 XML 消息转换成其 XML 表示形式，这对于 BizTalk Server 处理消息来说是必需的。 然后，该消息被拆装成可以发送给不同业务流程的单个消息。 拆装消息时需要执行以下步骤：移除信封，根据信封和消息架构将消息拆分成单个文档，然后将属性从信封移至各消息上下文中。 另外，某些属性可能从消息的正文升级到头部。 要升级的属性是由架构确定的。  
  
 拆装组件还必须设置消息类型属性，以用于正确地路由消息。 消息类型属性是消息正文的 Namespace#RootElement。 诸如内容类型和字符集之类的其他属性则被设置为上下文属性的一部分。  
  
 BizTalk 框架拆装器、平面文件拆装器和 XML 拆装器组件是 BizTalk Server 提供的默认拆装组件。  
  
 拆装组件应用于接收管道的拆装阶段。  
  
 有关开发分解管道组件的信息，请参阅[开发反汇编管道组件](../core/developing-a-disassembling-pipeline-component.md)。  
  
## <a name="probing"></a>探测  
 探测组件可以检查消息的第一部分，以确定组件是否可以识别此消息的格式。 如果格式是已知的，则会将整个消息交给此组件进行处理。  
  
 有关开发探测的信息管道组件，请参阅[开发探测管道组件](../core/developing-a-probing-pipeline-component.md)。  
  
## <a name="see-also"></a>另请参阅  
 [类型的管道](../core/types-of-pipelines.md)   
 [默认管道](../core/default-pipelines.md)   
 [管道模板](../core/pipeline-templates.md)   
 [管道组件](../core/pipeline-components.md)   
 [有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md)