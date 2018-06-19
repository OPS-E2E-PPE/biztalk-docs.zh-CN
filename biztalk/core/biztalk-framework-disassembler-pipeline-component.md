---
title: BizTalk Framework 反汇编程序管道组件 |Microsoft 文档
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
ms.openlocfilehash: e1ab54ddb9ef0b5fa389e6716fc4426978dcbd7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230581"
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 反汇编程序管道组件
BizTalk 框架拆装器管道组件可以解析 XML 数据并确定其是否包含基于 BizTalk 框架的消息传送负载。 该管道组件将保存消息上下文，并使用 BizTalk 框架属性创建需要生成的新的消息上下文。 此属性用于将消息路由到 BizTalk 框架入站处理程序，因此它可以接收要处理的消息。  
  
 如果发送方在 BizTalk 框架信封中使用 deliverReceiptRequest 头部来请求确认，则 BizTalk 框架拆装器管道组件将为所生成的消息生成确认。 这由 BizTalk 框架拆装器管道组件中的生成送达回执属性控制。 有关 BizTalk Framework 的详细信息，请参阅[BizTalk Framework 汇编程序管道组件](../core/biztalk-framework-assembler-pipeline-component.md)。  
  
 有关配置 BizTalk Framework 反汇编程序管道组件以及创建业务流程的信息，请参阅[如何配置 BizTalk Framework 反汇编程序管道组件](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何将 BizTalk Framework 反汇编程序管道组件配置](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)   
 [管道组件](../core/pipeline-components.md)