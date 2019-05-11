---
title: Microsoft.BizTalk.DefaultPipelines 引用 |Microsoft Docs
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
ms.openlocfilehash: a183aa499b5acb56813fcb0433d2fd57258a777d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324843"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a>Microsoft.BizTalk.DefaultPipelines Reference
**Microsoft.BizTalk.DefaultPipelines**命名空间包含以下管道：  
  
- XMLReceive  
  
- PassThruReceive  
  
- XMLTransmit  
  
- PassThruTransmit  
  
  管道是一个软件组件，用于定义和链接一个或多个阶段的处理的消息接收或发送的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 阶段包括诸如编码或解码、 拆装或组装和解密或加密。 这些函数的实现特定的顺序。 可以使用管道设计器创建接收和发送管道。  
  
  BizTalk 项目中包含的默认管道引用可以处理所有类型的文档使用**PassThruReceive**并**PassThruTransmit**管道。  
  
  以下列表显示了各默认管道中的默认组件。 其中还指示了每个管道中的组件的默认顺序。 可以添加和删除组件，如有必要。  
  
  默认 XMLReceive 管道中的默认组件包括：  
  
- 解密器  
  
- 解码器  
  
- 拆装器  
  
- 验证程序  
  
- 参与方解析  
  
  默认 XMLTransmit 管道中的默认组件包括：  
  
- 组装器  
  
- 编码器  
  
- 那样  
  
## <a name="see-also"></a>请参阅  
 [使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md)   
 [关于 BizTalk 项目中包含的 BizTalk 命名空间引用](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)