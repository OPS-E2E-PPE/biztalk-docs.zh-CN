---
title: "步骤 3D: FileAct 实时方案添加 FILEACT 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a22ba41-4f43-4fbb-92f7-a0fd7558d2ce
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f7440a0bad39fbfddb6319f4051a397f08ac09f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario"></a>步骤 3D: FileAct 实时方案添加 FILEACT 发送端口
在开始此步骤之前，必须完成[步骤 3c: FileAct 实时方案将文件发送端口添加到捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)。  
  
### <a name="to-add-a-fileact-send-port"></a>若要添加 FILEACT 发送端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
4.  在**发送端口属性**窗口中，名称发送端口 Tutorial_FA_SendRequest_RealTime。  
  
5.  在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**FILEACT**，然后单击**配置**。  
  
6.  在**FILEACT 传输属性**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|根据压降连接需要设置密码。|  
    |**用户名**|根据压降连接需要设置的用户名。|  
    |**适配器模式**|从下拉列表中选择**存储和转发**。|  
    |**不可否认性指示器**|从下拉列表中选择**FALSE**。|  
    |**请求类型**|设置为相应\<RequestType\>基于 SWIFT 你设置的字符串。|  
    |**ResponseCrypto**|从下拉列表中选择**FALSE**。|  
    |**请求者**|设置为相应\<请求者\>基于 SWIFT 你设置的字符串。|  
    |**响应方**|设置为相应\<响应方\>SWIFT 你设置基于字符串。|  
    |**服务名称**|设置为相应\<服务名称\>基于 SWIFT 你预配。|  
    |**确认指示器**|从下拉列表中选择**FALSE**。|  
    |**事件终结点**|从下拉列表中选择**FALSE**。|  
    |**文件压缩**|从下拉列表中选择**无**。|  
    |**物理文件夹名称**|键入 C:\SWIFTAdapterTutorial\Fileact\ClientLocation。|  
    |**传输终结点**|键入压降路由组的相应终结点。 此值应与匹配压降中配置的 SnL 终结点。|  
    |**ServiceProfile**|从下拉列表中选择**事务计数**。|  
    |**传递通知**|从下拉列表中选择**FALSE**。|  
    |**通知队列**|键入根据 SWIFT 你设置的队列名称。|  
  
    > [!NOTE]
    >  如果消息与事务计数要传输，服务配置文件中设置模式为"事务计数"FileAct 发送端口。  
  
7.  单击 **“确定”**。  
  
8.  在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择 Fileact 主机。|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 在发送端口属性窗口上**筛选器**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中选择**BTS。ReceivePortName**。|  
    |**运算符**|从下拉列表中选择 **==** 。|  
    |**值**|类型 Tutorial_FA_InputRequest_RealTime。|  
    |**分组依据**|保留默认值。|  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [步骤 3A： 添加一个文件接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [步骤 3E：为 FileAct 实时方案添加 FILE 发送端口以捕获 Sw:ExchangeFileResponse 消息](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)