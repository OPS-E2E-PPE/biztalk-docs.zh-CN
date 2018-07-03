---
title: EDIFACT CONTRL 确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8489f89714871f23fec329b44cafb4180f91c874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996894"
---
# <a name="edifact-contrl-acknowledgment"></a>EDIFACT CONTRL 确认
CONTRL 确认 (ACK) 用作 EDIFACT 编码消息的技术确认和功能确认。 作为技术确认，CONTRL 消息用于指示交换的接收。 作为功能确认，CONTRL 消息用错误或不支持功能的列表指示接收到的交换、组或消息是已接受还是拒绝。  
  
 完整 CONTRL 消息用作功能确认。 功能确认的某些部分可再次用于技术确认。 如果选择了技术和功能确认的参与方属性的发送方或全局属性中，BizTalk Server 将生成两个 CONTRL 消息： 一个技术 CONTRL 确认和功能 CONTRL 确认。  
  
 CONTRL 确认与 EFACT_\<版本号\>_CONTRL.xsd 架构。  
  
## <a name="technical-acknowledgement"></a>技术确认  
 技术确认指示交换的收件人：  
  
-   已收到主题交换；  
  
-   确认已检查的主题交换的各个部分，以确保复制到报告 UCI 段中的数据元素使用了正确的语法；  
  
-   已接受就主题交换的其他部分的确认或拒绝通知发送方这一责任；  
  
-   已采取合理的预防措施确保发送方能收到相应通知。  
  
## <a name="functional-acknowledgement"></a>功能确认  
 功能确认指示交换的收件人：  
  
- 已收到所确认的交换的引用级别；  
  
- 已检查在确认的引用级别中是否有可导致交换的进一步处理无法进行的致命语法错误；  
  
- 已检查所有确认的服务段部分在语义上是否都是正确的（如果未报告错误，则正确）；  
  
- 将按照在服务段的已确认引用级别中请求的操作执行；  
  
- 已接受如下责任：当以后在相关部分中检测到上述任何语法或语义错误时，或者在已在提交的 CONTRL 消息中确认相应部分之后由于其他原因而无法处理该部分时，通过发送 CONTRL 消息以外的方式通知发送方；  
  
- 已采取合理的预防措施确保能够检测到此类错误并相应通知发送方。  
  
  拒绝表示交换的收件人：  
  
- 由于 CONTRL 消息中指出的原因而无法确认主题交换或其相关部分；  
  
- 不会对拒绝的主题交换部分中包含的业务信息进一步采取任何操作。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [作为技术确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a>请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)