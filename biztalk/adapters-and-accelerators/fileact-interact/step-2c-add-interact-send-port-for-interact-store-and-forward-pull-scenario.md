---
title: 步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口 |Microsoft 文档
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
ms.openlocfilehash: fb46943b20676dbe98f79db8760043bb51606c56
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964171"
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a>步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口
在开始此步骤之前，必须完成[步骤 2B： 发送端口添加文件，以捕获 Sw:HandleRequest 消息交互，应用商店应用和向前 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)。  
  
### <a name="to-add-an-interact-send-port"></a>若要添加交互发送端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
4.  在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendRequest_SnF**。  
  
5.  在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。  
  
6.  在**交互传输属性**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|根据压降连接需要设置密码。|  
    |**用户名**|根据压降连接需要设置的用户名。|  
    |**消息格式**|**InteractMessage**|  
    |**不可否认性指示器**|**FALSE**|  
    |**请求类型**|键入相应\<RequestType\>基于 SWIFT 你设置的字符串。|  
    |**ResponseCrypto**|**FALSE**|  
    |**请求者**|键入相应\<RequestorDN\>基于 SWIFT 你设置的字符串。|  
    |**响应方**|键入相应\<ResponderDN\>基于 SWIFT 你设置的字符串。|  
    |**服务名称**|键入相应\<服务名称\>，具体取决 SWIFT 你预配。|  
    |**传递通知**|从下拉列表中选择**FALSE**。|  
    |**通知队列**|键入相应的队列名称，基于 SWIFT 你预配。|  
  
    > [!NOTE]
    >  如果只传输负载，设置到交互中的"负载"MessageFormat receive 端口和交互发送端口。 设置为 PassThru 接收和发送管道。  
  
7.  单击 **“确定”**。  
  
8.  在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择的交互主机。|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中选择**BTS。ReceivePortName**。|  
    |**运算符**|从下拉列表中选择 **==** 。|  
    |**值**|类型**Tutorial_IA_InputRequest_SnF**。|  
    |**分组依据**|保留默认值。|  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [步骤 2B：为 InterAct 存储和转发（拉取）方案添加 FILE 发送端口以捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)