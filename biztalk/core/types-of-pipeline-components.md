---
title: 类型的管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 9b493758-6b0f-4223-94bb-8f077ee735a9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b8ad31d2e135aec1283b5057e6b39de45ad422
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379925"
---
# <a name="types-of-pipeline-components"></a>类型的管道组件
三种类型的管道组件所含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]： 常规、 组装和拆装。 这三种类型的任何可实现探测功能。 本主题介绍每种类型的组件，并在其中每个组件通常使用的阶段。  
  
## <a name="general"></a>常规  
 常规组件接收一个消息、 处理消息，并生成零个或一个消息。  
  
 常规组件包括的 MIME/SMIME 解码器、 MIME/SMIME 编码器、 参与方解析和验证程序组件。 您可能需要创建自定义常规组件在发送前，压缩的消息大小，或等待其他信息以对其进行处理时使用一条消息。  
  
 常规组件应置于解码、 编码、 预组装、 解析参与方，或验证阶段。  
  
 有关开发常规管道组件的信息，请参阅[开发常规管道组件](../core/developing-a-general-pipeline-component.md)。  
  
## <a name="assembling"></a>组合  
 组装组件具有方面的许多工作来准备要发送的消息。 首先，该组件将 XML 消息转换为消息，根据组装器和架构中设置属性的类型的相应 XML 或非 XML 本机格式。 此外，组装组件组装和将消息包装到信封中，或添加一个标头或尾部 （或两者） 消息。 在组装期间，某些属性将移动消息上下文中的文档的正文或信封。  
  
 BizTalk 框架组装器、 平面文件组装器和 XML 组装器组件是默认的组装组件。  
  
 组装组件应置于发送管道的组装阶段中。  
  
 有关开发组装管道组件的信息，请参阅[开发组装管道组件](../core/developing-an-assembling-pipeline-component.md)。  
  
## <a name="disassembling"></a>反汇编  
 拆装组件完成许多任务来准备要拆分为单独的文档，根据信封的消息，BizTalk Server 中使用的文档架构。 首先，拆装组件可能会将非 XML 消息转换为其 XML 表示形式，这是处理所需的 BizTalk server。 接下来，该消息被拆装成可以发送给不同业务流程的单个消息。 该消息被拆装通过移除信封，将消息拆分成单个文档根据信封和消息架构，然后将属性从信封移到单独的消息上下文。 此外，某些属性可以升级从消息的正文为标头。 由架构确定升级的属性。  
  
 拆装组件还必须设置恰当地使用消息路由的消息的消息类型属性。 消息类型属性是消息正文的 Namespace #RootElement。 其他属性，如内容类型和字符集设置为上下文属性的一部分。  
  
 BizTalk 框架拆装器、 平面文件拆装器和 XML 拆装器组件是默认拆装组件包含在 BizTalk Server。  
  
 接收管道的拆装阶段中，应使用拆装组件。  
  
 有关开发拆装管道组件的信息，请参阅[开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)。  
  
## <a name="probing"></a>探测  
 探测组件可以检查该消息来查看其是否在该组件理解的格式中的第一个部分。 如果格式已知的则会将整个消息交给此组件进行处理。  
  
 有关开发探测管道组件，请参阅[开发探测管道组件](../core/developing-a-probing-pipeline-component.md)。  
  
## <a name="see-also"></a>请参阅  
 [类型的管道](../core/types-of-pipelines.md)   
 [默认管道](../core/default-pipelines.md)   
 [管道模板](../core/pipeline-templates.md)   
 [管道组件](../core/pipeline-components.md)   
 [关于管道、阶段和组件](../core/about-pipelines-stages-and-components.md)