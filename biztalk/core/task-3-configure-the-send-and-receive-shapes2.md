---
title: "任务 3： 配置发送和接收 Shapes2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebe7141-f2bd-4e6a-9204-d61bd64286af
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6923a90b43d1bdc3004a03ac588dd2410d81a3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a>任务 3： 配置发送和接收形状
使用以下过程可以配置发送和接收形状。  
  
### <a name="to-configure-the-send-and-receive-shapes"></a>若要配置发送和接收形状  
  
1.  按以下顺序将发送和接收形状从工具箱拖到业务流程的中心。  
  
2.  设置以下参数：  
  
    |形状|Name|设置|  
    |-----------|----------|-------------|  
    |Receive1|Activate|True|  
    ||消息|BeginDocMsg|  
    ||Name|ReceiveBeginDoc|  
    ||运算|BeginDoc.Operation_1.Request|  
    |Send1|消息|BeginDocSessionMsg|  
    ||Name|SendBeginDoc|  
    ||运算|JDEPort.Operation_1.Request|  
    |Receive2|Activate|False|  
    ||消息|BeginDocResponseMsg|  
    ||Name|ReceiveBeginDocResponse|  
    ||运算|JDEPort.Operation_1.Response|  
    |Send2|消息|EditLineSessionMsg|  
    ||Name|SendEditLine|  
    ||运算|JDEPort.Operation_2.Request|  
    |Receive3|Activate|False|  
    ||消息|EditLineResponseMsg|  
    ||Name|ReceiveEditLine|  
    ||运算|JDEPort.Operation_2.Response|  
    |Send3|消息|EndDocSessionMsg|  
    ||Name|SendEndDoc|  
    ||运算|JDEPort.Operation_3.Request|  
    |Receive4|Activate|False|  
    ||消息|EndDocResponseMsg|  
    ||Name|ReceiveEndDocResponse|  
    ||运算|JDEPort.Operation_3.Response|  
    |Send4|消息|EndDocResponseMsg|  
    ||Name|SendEndDocResponse|  
    ||运算|EndDocOut.Operation_1.Request|  
  
## <a name="see-also"></a>另请参阅  
 [任务 1： 创建端口](../core/task-1-create-the-ports1.md)   
 [任务 2： 创建消息](../core/task-2-create-the-messages2.md)   
 [任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md)   
 [任务 5： 配置转换形状](../core/task-5-configure-the-transform-shape2.md)