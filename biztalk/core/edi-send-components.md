---
title: "EDI 发送组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5520a0c1dd0a6ef7e42818314a9f87733aebcb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-send-components"></a>EDI 发送组件
本主题中介绍的管道和管道组件用于处理不是 EDI/AS2 消息的 EDI 消息。 有关发送 EDI/AS2 或非 EDI/AS2 消息的信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。 请注意，除 AS2 处理以外，AS2 发送组件还执行 EDI 处理。  
  
## <a name="edi-send-pipeline"></a>EDI 发送管道  
 EDI 发送处理工作都将在下列 EDISend 管道中进行。 该管道安装在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 下的 `Microsoft.BizTalk.Edi.EdiPipelines.dll` 中。  
  
 **EDISend 管道**  
  
 此管道将生成和发送 EDI 消息。 但不会处理通过 HTTP 接收的 AS2 编码的 EDI 消息。 AS2 编码的 EDI 消息的处理是通过 AS2 管道执行的。 AS2 发送管道和 EDI 管道使用相同的组件来处理 EDI 消息。  
  
> [!NOTE]
>  不支持从业务流程中运行 EDISend 管道。  
  
> [!NOTE]
>  AS2EDISend 管道通过 AS2 传输生成和发送 EDI 消息。 有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。  
  
 该管道由 EDI 组装器管道组件组成：  
  
## <a name="edi-send-pipeline-component"></a>EDI 发送管道组件  
 EDISend 管道使用 EDI 组装器管道组件。 此组件安装在`Microsoft.BizTalk.Edi.PipelineComponents.dll`中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。  
  
 对 EDISend 管道中的 EDI 编码交换的处理大部分是由 EDI 组装器执行的。 有关如何 EDI 汇编器处理 EDI 消息的信息，请参阅[EDI 汇编程序的工作原理](../core/how-the-edi-assembler-works.md)。