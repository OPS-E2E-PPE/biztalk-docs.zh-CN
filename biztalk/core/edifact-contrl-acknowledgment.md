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
ms.openlocfilehash: 7808b02e5aebcf9f03e06a13ebbbcff8b1f43b0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350130"
---
# <a name="edifact-contrl-acknowledgment"></a>EDIFACT CONTRL 确认
CONTRL 确认 (ACK) 用作 EDIFACT 编码消息的技术和功能确认。 作为技术确认，CONTRL 消息指示交换的接收。 作为功能确认，CONTRL 消息指示接受或拒绝收到的交换、 组或消息，与错误或不受支持的功能的列表。  
  
 完整 CONTRL 消息用作功能确认。 功能确认的部分会重复使用的技术确认。 如果选择了技术和功能确认的参与方属性的发送方或全局属性中，BizTalk Server 将生成两个 CONTRL 消息： 一个技术 CONTRL 确认和功能 CONTRL 确认。  
  
 CONTRL 确认与 EFACT_\<版本号\>_CONTRL.xsd 架构。  
  
## <a name="technical-acknowledgement"></a>技术确认  
 技术确认指示交换的收件人：  
  
-   已收到主题交换;  
  
-   确认已选中以确保正确的语法; 复制到报告 UCI 段的数据元素的主题交换部分  
  
-   已接受如下责任通知发件人的确认或拒绝的其他部分的主题交换;  
  
-   已采取合理的预防措施确保发送方能收到相应通知。  
  
## <a name="functional-acknowledgement"></a>功能确认  
 功能确认指示交换的收件人：  
  
- 已收到确认; 的交换的引用的级别 (s)  
  
- 已签入能继续处理交换; 的已确认引用级别中没有任何致命语法错误  
  
- 已签入所有组成部分已确认的服务段在语义上是都正确的 （是否未不报告任何错误）;  
  
- 将遵守与已确认引用级别的服务段; 中请求的操作  
  
- 已接受比发送一条 CONTRL 消息，如果任何语法或语义错误，上文所述更高版本中检测到的相关部分或部分而无法处理其他某种原因而后的部件具有通过其他方式通知发件人的职责已确认中提交的 CONTRL 消息;  
  
- 已采取合理的预防措施确保检测到此类错误，并且发件人将收到通知。  
  
  拒绝表示交换的收件人：  
  
- 无法确认主题交换或 CONTRL 消息中; 中指出的原因而的相关部分，  
  
- 并不需要任何进一步的操作中的主题交换被拒绝的一部分包含的业务信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [作为技术确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a>请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)