---
title: 步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9503976d47f70a0077b5a30598d5daa826855e1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365466"
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a>步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案
完整[步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)开始此步骤之前。
  
## <a name="add-an-interact-send-port"></a>添加 INTERACT 发送端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
4.  在中**发送端口属性**窗口中，命名发送端口**Tutorial_IA_SendRequest_RealTime**。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。  
  
6.  在中**交互传输属性**对话框框中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|根据压降连接需要设置密码。|  
    |**用户名**|根据压降连接需要设置的用户名。|  
    |**适配器模式**|从下拉列表中，选择**实时**。|  
    |**消息格式**|**InteractMessage**。|  
    |**不可否认指示器**|**FALSE**。|  
    |**请求类型**|键入适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。|  
    |**ResponseCrypto**|**FALSE**。|  
    |**请求者**|将其设置为适当\<请求程序\>为基础的 SWIFT 应用预配的字符串。|  
    |**响应方**|将其设置为适当\<响应方\>为基础的 SWIFT 应用预配的字符串。|  
    |**服务名称**|将其设置为适当\<服务名称\>、 根据使用 SWIFT 应用预配。|  
    |**送达通知**|从下拉列表中，选择**FALSE**。|  
    |**通知队列**|键入相应的队列名称，根据你使用 SWIFT 预配。|  
  
    > [!NOTE]
    >  如果只传输有效负载，集到交互"Payloadonly"MessageFormat 接收端口和 INTERACT 发送端口。 设置接收并向 PassThru 发送管道。  
  
7.  单击“确定” 。  
  
8.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择交互主机。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
    |**接收管道**|**XMLReceive**|  
  
9. 在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中，选择**BTS。ReceivePortName**。|  
    |**“运算符”**|从下拉列表中，选择**==**。|  
    |**ReplTest1**|类型**Tutorial_IA_InputRequest_RealTime**。|  
    |**分组依据**|保留默认值。|  
  
10. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [步骤 3a:添加 FILE 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)