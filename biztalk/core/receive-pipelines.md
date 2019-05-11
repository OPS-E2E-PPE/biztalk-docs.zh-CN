---
title: 接收管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, about receive pipelines
- receive pipelines, message flow
- receive pipelines
- messages, receive pipelines
- messages, message flow
- pipelines, receive pipelines
- receive pipelines, stages
ms.assetid: ee75c1d4-00b7-4177-bca3-1447a39d2238
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a0fd7d5a0cba8543ae44bb6a8e0632cbf33c9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398206"
---
# <a name="receive-pipelines"></a>接收管道
下图显示消息处理工作流，其中突出显示了接收管道：  
  
 ![消息处理工作流的图示。](../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")  
消息处理工作流示意图  
  
 接收适配器收到消息后，接收管道将对该消息进行处理。 接收管道将获取初始消息，执行一些转换，并将原始数据拆为零条、一条或多条消息。 然后，BizTalk Server 即可对各条消息进行处理。  
  
> [!NOTE]
>  如果向接收管道添加了使用组件，则该管道不会生成消息。 在这种情况下，管道组件将使用消息，但不生成任何输出消息。 如果使用组件置于拆装组件之后，则在使用第一个消息后将停止管道执行，并且不会从拆装组件中检索任何后续消息。  
  
 在创建时的业务流程，你可以创建新的接收管道或可以使用两个默认之一接收 BizTalk Server 中包含的管道-传递接收管道或 XML 接收管道。 有关这些默认管道的详细信息，请参阅[默认管道](../core/default-pipelines.md)。  
  
 接收管道包括四个阶段：解码、 反汇编、 验证和解析参与方。 本主题包含了有关填充这些阶段的设计注意事项。  
  
> [!NOTE]
>  在此版本中，不支持更改这些阶段在管道中的顺序或存在状态。  
  
## <a name="decode-stage"></a>解码阶段  
  
-   此阶段用于对消息进行解码或解密的组件。  
  
    -   如果需要将传入消息从一种格式解码为另一种格式，则需要在此阶段中放置 MIME/SMIME 解码器管道组件或自定义解码组件。  
  
-   只要此阶段获取一条消息，就生成一条消息。  
  
-   此阶段可包含 0 到 255 个组件。  
  
-   此阶段中的所有组件均将运行。  
  
## <a name="disassemble-stage"></a>拆装阶段  
  
-   此阶段用于对消息进行解析或拆装的组件。  
  
    -   此阶段内的组件可探测消息以查看是否可识别消息的格式。 其中一个组件将根据格式的识别情况拆装消息。  
  
    -   如果此阶段包含多个组件，则只运行第一个识别消息格式的组件。 如果此阶段内的所有组件均无法识别消息格式，则消息处理将失败。  
  
    -   此阶段应包含可实施特殊行为以拆装消息内容的所有自定义组件。  
  
    -   此阶段可包含 0 到 255 个组件。 如果此阶段不包含任何组件，则会以直通方式传递消息。  
  
## <a name="validate-stage"></a>验证阶段  
  
-   此阶段用于对消息格式进行验证的组件。  
  
    -   管道组件只能处理与该组件中指定的架构相符的消息。 如果管道所收到消息的架构与管道中的任何组件均不关联，则不会处理该消息。 此时，将根据提交该消息的适配器挂起该消息或向发件人发送错误消息。  
  
    -   此阶段中的组件用于验证拆装阶段生成的 XML 消息。 此阶段中的组件将指定用于执行 XML 验证的架构。  
  
-   此阶段可包含 0 到 255 个组件。  
  
-   此阶段中的所有组件均将运行。  
  
    -   此阶段可能会运行多次。 拆装阶段每创建一条消息，此阶段就会运行一次。  
  
## <a name="resolveparty-stage"></a>解析参与方阶段  
  
-   此阶段是一个占位符，供[方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
-   此阶段可能会运行多次。 拆装阶段每创建一条消息，此阶段就会运行一次。  
  
-   此阶段可包含 0 到 255 个组件。  
  
-   此阶段中的所有组件均将运行。  
  
## <a name="see-also"></a>另请参阅  
 [发送管道](../core/send-pipelines.md)   
 [有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md)   
 [类型的管道组件](../core/types-of-pipeline-components.md)   
 [默认管道](../core/default-pipelines.md)   
 [管道模板](../core/pipeline-templates.md)   
 [管道组件](../core/pipeline-components.md)   
 [类型的管道](../core/types-of-pipelines.md)