---
title: BizTalk 框架拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36269df0c1b93ca68ffeb41d78742e926af14c92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358050"
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a>BizTalk 框架拆装器管道组件
BizTalk 框架拆装器管道组件分析 XML 数据，并确定它是否包含基于 BizTalk 框架消息传送负载。 管道组件将保存消息上下文，并使用需要生成 BizTalk 框架属性创建新的消息上下文。 此属性用于将消息路由到 BizTalk 框架入站处理程序，因此它可以接收要处理的消息。  
  
 如果发件人请求一个 BizTalk 框架信封中使用 deliverReceiptRequest 头部，BizTalk 框架拆装器管道组件将生成所生成消息的确认。 这是由 BizTalk 框架组装器管道组件中生成送达回执属性控制。 有关 BizTalk Framework 的详细信息，请参阅[BizTalk 框架组装器管道组件](../core/biztalk-framework-assembler-pipeline-component.md)。  
  
 有关配置 BizTalk 框架拆装器管道组件和创建业务流程的信息，请参阅[如何配置 BizTalk 框架拆装器管道组件](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 BizTalk 框架拆装器管道组件](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)   
 [管道组件](../core/pipeline-components.md)