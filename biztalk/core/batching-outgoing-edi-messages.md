---
title: "对传出的 EDI 消息进行批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 852b85e0de23e01e39891adba56053683d18a9b8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="batching-outgoing-edi-messages"></a>对传出 EDI 消息进行批处理
如果已为协议（与将接收它的业务合作伙伴相关联）启用了批处理，则 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将对 EDI 事务集进行批处理。 使用协议的 EDI 属性可以执行以下操作：  
  
-   定义多个传出批处理  
  
-   定义交换  
  
-   定义交换中的组  
  
-   设置批处理发布条件  
  
-   设置批处理激活条件。  
  
 Microsoft BizTalk Server EDI 和 AS2 启用 EDI 交换的以下处理：  
  
-   EDI 交换可以包含事务集和/或确认。  
  
-   EDI 接收管道可以拆分到 XML 事务集，以做进一步的处理的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，或者它可以保留交换，将通过其传递[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在其收到的窗体中。  
  
-   EDI 路由业务流程使[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行批处理设置多个传出交换到单个事务。  
  
-   批处理业务流程的 EDI 组合 XML 事务集成的 EDI 交换中，并验证和提供根据协议的 EDI 属性交换。  
  
 EDI 批处理（又称为交换）包含消息组，而消息组包含各个消息。 传出批处理可包含多个组，不过每一种文档类型只允许有一个组。 组中可以包含多个事务集，但每个事务集必须属于相同的文档类型。 消息信封用于包装各个事务集、各个组和整个交换。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置传出批](../core/configuring-an-outgoing-batch.md)  
  
-   [汇编批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)  
  
-   [发送保留的批交换](../core/sending-a-preserved-batch-interchange.md)