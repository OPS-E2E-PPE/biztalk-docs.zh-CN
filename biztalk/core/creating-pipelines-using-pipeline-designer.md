---
title: 使用管道设计器创建管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, processing messages
- pipelines, Pipeline Designer
- Pipeline Designer, about Pipeline Designer
ms.assetid: 858302d8-a912-4199-95e5-4322db789b4e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead846de3a731a73ee1c0908801485d67ff68a79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353624"
---
# <a name="creating-pipelines-using-pipeline-designer"></a>使用管道设计器创建管道
Microsoft BizTalk Server 程序主要处理 XML 文档格式。 若要充分利用 BizTalk Server 处理的消息，必须经常将它转换从其本机格式转换为 XML 表示形式。 BizTalk Server 管道对传入和传出消息执行此转换，以及其他特定于数据的操作 （例如数据加密或解密、 属性升级等）。 本部分提供有关管道和管道设计器的概念和特定于任务的信息。  
  
 若要准备的消息进行处理服务器在适配器接收后或准备服务器处理后发送一条消息，管道的作用。  
  
 管道通常执行：  
  
- 数据规范化为各种格式为 XML。  
  
- 数据转换为 XML 为各种格式。  
  
- 属性升级和降级。  
  
- 文档拆装和组装。  
  
- 文档解码和编码。  
  
- 文档解密和加密。  
  
- 文档签名和数字签名验证。  
  
  下图显示工作流所涉及到使用管道来处理一条消息。  
  
  ![消息的处理的工作流的图示。](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")  
  消息处理工作流示意图  
  
  如图所示，该消息是从适配器传递到接收管道它将转换为 XML。 然后可以使用的业务流程，或传递到发送管道，再到发送适配器消息。  
  
  有关使用键盘快捷键的管道设计器的信息，请参阅[管道设计器键盘快捷方式](../core/pipeline-designer-keyboard-shortcuts.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [关于管道、阶段和组件](../core/about-pipelines-stages-and-components.md)  
  
-   [使用管道设计器](../core/using-pipeline-designer.md)  
  
-   [使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [配置本地管道组件](../core/configuring-native-pipeline-components.md)  
  
-   [如何部署管道](../core/how-to-deploy-pipelines.md)  
  
-   [如何确保管道安全](../core/how-to-secure-pipelines.md)