---
title: BizTalk Server 如何发送 EDI 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4eaf1085-4244-4df2-9d89-52ebdf6bcbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24d55493c8ae467886dc8fa91404a414ac55a336
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387492"
---
# <a name="how-biztalk-server-sends-edi-messages"></a>BizTalk Server 如何发送 EDI 消息
当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送 EDI 消息时，它会执行协议查找和架构发现、 验证消息、 发送确认 （如果适用），但 EDI 批处理进行序列化。 此处理将由 EDI 发送管道中的 EDI 组装器执行。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 发送组件](../core/edi-send-components.md)  
  
-   [传出 EDI 消息的协议解析和架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)  
  
-   [EDI 汇编程序的工作原理](../core/how-the-edi-assembler-works.md)  
  
-   [替代 EDI 标头](../core/overriding-edi-headers.md)  
  
-   [验证传出的 EDI 消息](../core/validation-of-outgoing-edi-messages.md)  
  
-   [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)  
  
-   [处理收到的确认](../core/processing-a-received-acknowledgment.md)