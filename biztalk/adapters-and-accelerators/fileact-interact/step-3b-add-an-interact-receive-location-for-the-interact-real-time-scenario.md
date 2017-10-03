---
title: "步骤 3B： 添加交互接收位置交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59780635-e1b6-4e74-a89a-73ec26d6c670
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9912e47f56dcf9c8ccc42af944616858ec9b93fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario"></a>步骤 3B： 添加交互接收位置交互实时方案
完成[步骤 3A： 对于交互的实时方案中添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)在开始此步骤之前。
  
## <a name="add-an-interact-receive-location"></a>添加交互接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_HandleRequestOneWay_RealTime**。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。  
  
7.  在**交互传输属性**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名称。|  
    |**应用程序名称**|键入的服务器\<*应用程序接口名称*> 压降框中路由组。|  
    |**加密模式**|从下拉列表中选择**高级**。|  
    |**LogMessageBody**|从下拉列表中选择**FALSE**。 **注意：**如果设置为 TRUE 时，它将保留跟踪数据库的消息正文。 但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。|  
    |**日志消息**|从下拉列表中选择**TRUE**。 这样将捕获和 BAM 门户中跟踪消息事件。|  
    |**消息格式**|从下拉列表中选择**InterActMessage**。|  
    |**MemberRef**|从下拉列表中选择**ResponseHeader**。|  
    |**不可否认性指示器**|从下拉列表中选择**FALSE**。|  
    |**响应方**|键入相应\< *ResponderDN*> 基于 SWIFT 你设置的字符串。|  
    |**ResponseCrypto**|从下拉列表中选择**FALSE**。|  
    |**超时**|应发生类型适当数量的连接超时前的秒数。|  
    |**获取队列**|将此属性的默认值。 此属性用于存储转发方案。|  
    |**ForceAcquire**|将此属性的默认值。 此属性用于存储转发方案。|  
    |**排序依据**|将此属性的默认值。 此属性用于存储转发方案。|  
    |**推送会话**|将此属性的默认值。 此属性用于存储转发方案。|  
    |**恢复模式**|将此属性的默认值。 此属性用于存储转发方案。|  
    |**SNL 终结点**|将此属性的默认值。 此属性用于存储转发方案。|  
  
8.  单击 **“确定”**。  
  
9. 在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerIsolatedHost**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [步骤 3A： 添加一个文件接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [步骤 3c： 添加要捕获的 Sw:HandleRequest 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [步骤 3D： 添加要捕获的 Sw:HandleResponse 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [步骤 3E： 添加的交互发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)