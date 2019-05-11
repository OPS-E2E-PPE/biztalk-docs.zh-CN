---
title: 任务 3：配置发送和接收 Shapes1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e258d22-755b-48a4-9f9e-e9398f6b68b1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8621f5d4aa6cb9d15caf708b7089ca2c1aab82c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399243"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a>任务 3：配置发送和接收形状
使用以下过程来配置发送和接收形状。  
  
### <a name="to-configure-the-send-and-receive-shapes"></a>若要配置发送和接收形状  
  
1.  将发送和接收形状从工具箱中按以下顺序业务流程的中心。  
  
2.  设置以下参数：  
  
    |形状|“属性”|设置|  
    |-----------|----------|-------------|  
    |Receive1|Activate|True|  
    ||消息|BeginDocMsg|  
    ||“属性”|ReceiveBeginDoc|  
    ||操作|BeginDoc.Operation_1.Request|  
    |Send1 上|消息|BeginDocSessionMsg|  
    ||“属性”|SendBeginDoc|  
    ||操作|JDEPort.Operation_1.Request|  
    |Receive2|Activate|False|  
    ||消息|BeginDocResponseMsg|  
    ||“属性”|ReceiveBeginDocResponse|  
    ||操作|JDEPort.Operation_1.Response|  
    |Send2 上|消息|EditLineSessionMsg|  
    ||“属性”|SendEditLine|  
    ||操作|JDEPort.Operation_2.Request|  
    |Receive3|Activate|False|  
    ||消息|EditLineResponseMsg|  
    ||“属性”|ReceiveEditLine|  
    ||操作|JDEPort.Operation_2.Response|  
    |Send3|消息|EndDocSessionMsg|  
    ||“属性”|SendEndDoc|  
    ||操作|JDEPort.Operation_3.Request|  
    |Receive4|Activate|False|  
    ||消息|EndDocResponseMsg|  
    ||“属性”|ReceiveEndDocResponse|  
    ||操作|JDEPort.Operation_3.Response|  
    |Send4|消息|EndDocResponseMsg|  
    ||“属性”|SendEndDocResponse|  
    ||操作|EndDocOut.Operation_1.Request|  
  
## <a name="see-also"></a>请参阅  
 [任务 1:创建端口](../core/task-1-create-the-ports2.md)   
 [任务 2:创建消息](../core/task-2-create-the-messages1.md)   
 [任务 4:配置构造消息形状](../core/task-4-configure-the-construct-message-shape2.md)   
 [任务 5:配置转换形状](../core/task-5-configure-the-transform-shape1.md)