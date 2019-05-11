---
title: 步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3373f7653856800c3cb8a64ca07afe88eb86d192
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366104"
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a>步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口
在开始此步骤之前，必须完成[步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)。  
  
### <a name="to-add-an-interact-send-port"></a>若要添加 INTERACT 发送端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
4.  在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_IA_SendRequest_SnF**。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。  
  
6.  在中**交互传输属性**对话框框中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|根据压降连接需要设置密码。|  
    |**用户名**|根据压降连接需要设置的用户名。|  
    |**消息格式**|**InteractMessage**|  
    |**不可否认指示器**|**FALSE**|  
    |**请求类型**|键入适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。|  
    |**ResponseCrypto**|**FALSE**|  
    |**请求者**|键入适当\<RequestorDN\>为基础的 SWIFT 应用预配的字符串。|  
    |**响应方**|键入适当\<ResponderDN\>为基础的 SWIFT 应用预配的字符串。|  
    |**服务名称**|键入适当\<服务名称\>、 根据使用 SWIFT 应用预配。|  
    |**送达通知**|从下拉列表中，选择**FALSE**。|  
    |**通知队列**|键入相应的队列名称，根据你使用 SWIFT 预配。|  
  
    > [!NOTE]
    >  如果只传输有效负载，设置为"有效负载"，在交互 MessageFormat 接收端口和 INTERACT 发送端口。 将接收和发送管道设置为 PassThru。  
  
7.  单击“确定” 。  
  
8.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择交互主机。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
9. 在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中，选择**BTS。ReceivePortName**。|  
    |**“运算符”**|从下拉列表中，选择**==**。|  
    |**ReplTest1**|类型**Tutorial_IA_InputRequest_SnF**。|  
    |**分组依据**|保留默认值。|  
  
10. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)