---
title: 对传出 EDI 消息进行批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57eaeee848ae5c9ea316b9f0b5998805581faca1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358283"
---
# <a name="batching-outgoing-edi-messages"></a>对传出 EDI 消息进行批处理
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将 EDI 事务集如果批处理已启用的关联将接收它的业务合作伙伴的协议。 为协议的 EDI 属性可以执行以下操作：  
  
- 定义多个传出批处理  
  
- 定义交换  
  
- 交换中定义的组  
  
- 设置批处理发布条件  
  
- 设置批处理激活条件。  
  
  Microsoft BizTalk Server EDI 和 AS2 可 EDI 交换进行以下处理：  
  
- EDI 交换可以包含事务集和/或确认。  
  
- EDI 接收管道可以将 XML 事务集做进一步的处理某个交换拆分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，也可以保留交换，将其传递[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]形式接收。  
  
- EDI 路由业务流程，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行批处理的单个事务集到多个传出交换。  
  
- EDI 批处理业务流程 XML 事务集组装成 EDI 交换，并验证和根据协议的 EDI 属性将交换传送。  
  
  EDI 批，又称为交换，包含消息组，而消息组包含各个消息。 传出批处理可包含多个组，但每个文档类型的一个组。 一个组可以包含多个事务集，但每个必须文档类型相同。 消息信封用于包装各个事务集、 单个组和整个交换。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置传出批](../core/configuring-an-outgoing-batch.md)  
  
-   [汇编批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)  
  
-   [发送保留的批交换](../core/sending-a-preserved-batch-interchange.md)