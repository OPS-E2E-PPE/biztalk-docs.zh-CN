---
title: Microsoft.BizTalk.DefaultPipelines 引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines
- PassThruTransmit pipelines
- XMLReceive pipelines
- pipelines, XMLTransmit
- Pipeline Designer
- pipelines, XMLReceive
- pipelines, about pipelines
- PassThruReceive pipelines
- XMLTransmit pipelines
- namespaces, Microsoft.BizTalk.DefaultPipelines namespace
- Microsoft.BizTalk.DefaultPipelines namespace
ms.assetid: a54f8813-9c6f-4afe-8c76-2db3fa478947
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ad7cad78e3e8606371a5fa49673297cf590ddbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263405"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a>Microsoft.BizTalk.DefaultPipelines 引用
**Microsoft.BizTalk.DefaultPipelines**命名空间包含以下管道：  
  
-   XMLReceive  
  
-   PassThruReceive  
  
-   XMLTransmit  
  
-   PassThruTransmit  
  
 管道是一个软件组件，用于定义并链接一个或多个阶段，处理消息接收或发送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这些阶段包括诸如编码或解码、拆装或组装、解密或加密这类功能。 这些功能是按特定顺序实现的。 可以使用管道设计器来创建接收管道和发送管道。  
  
 包含在 BizTalk 项目的默认管道引用可以处理所有类型的文档使用**PassThruReceive**和**PassThruTransmit**管道。  
  
 下面分别列出了各默认管道中的默认组件。 其中还指示了每个管道中组件的默认顺序。 如有必要，可以添加和删除组件。  
  
 默认 XMLReceive 管道中的默认组件包括：  
  
-   解密器  
  
-   解码器  
  
-   拆装器  
  
-   验证程序  
  
-   参与方解析  
  
 默认 XMLTransmit 管道中的默认组件包括：  
  
-   组装器  
  
-   编码器  
  
-   加密器  
  
## <a name="see-also"></a>另请参阅  
 [创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)   
 [有关 BizTalk 项目中包含的 BizTalk Namespace 引用](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)