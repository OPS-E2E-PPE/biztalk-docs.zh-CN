---
title: "步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和向前方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f30bb7d-1efb-4350-8809-be35f5634ea0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c717d23886860363ca9c94d1eec79195f873fff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a>步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和转发方案
在开始此步骤之前，必须完成[步骤 3A： 添加文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)。  
  
### <a name="to-add-an-fileact-receive-location"></a>若要添加 FILEACT 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口，Tutorial_FA_HandleRequestOneWay_SnF。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**FILEACT**，和然后单击**配置**。  
  
7.  在**FILEACT 传输属性**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名称。|  
    |**应用程序名称**|键入的服务器\<应用程序接口名称 > 压降框中路由组。|  
    |**加密模式**|从下拉列表中选择**高级**。|  
    |**FACrypto 模式**|从下拉列表中选择**高级**。|  
    |**日志消息**|从下拉列表中选择**TRUE**。 这样将捕获和 BAM 门户中跟踪消息事件。|  
    |**MemberRef**|从下拉列表中选择**ResponsePayload**。|  
    |**不可否认性指示器**|从下拉列表中选择**FALSE**。|  
    |**响应方**|键入相应\<响应方 > 基于 SWIFT 你设置的字符串。|  
    |**ResponseCrypto**|从下拉列表中选择**FALSE**。|  
    |**确认指示器**|从下拉列表中选择**ResponsePayload**。|  
    |**FileCompression**|从下拉列表中，选择无。|  
    |**PhysicalFolderName**|键入服务器上的文件夹的名称。 例如，C:\Fileact\ServerLocation。|  
    |**SubscribeFileEvents**|从下拉列表中选择**FALSE**。|  
    |**TransferAnswer**|从下拉列表中选择**已接受**。|  
    |**AllFileEvents**|从下拉列表中选择**TRUE**。|  
    |**事件终结点**|键入相应压降终结点。|  
    |**FullFileStatus**|从下拉列表中选择**TRUE**。|  
    |**超时**|键入适当数量会发生超时之前等待的秒。|  
    |**获取队列**|键入根据 SWIFT 你设置的队列名称。|  
    |**ForceAcquire**|从下拉列表中选择**TRUE**。|  
    |**排序依据**|从下拉列表中选择**FileAct**。|  
    |**推送会话**|从下拉列表中选择**TRUE**。|  
    |**恢复模式**|从下拉列表中选择**FALSE**。|  
    |**SNL 终结点**|键入压降路由组的相应终结点。 此值应与匹配压降中配置的 SnL 终结点。|  
  
8.  单击 **“确定”**。  
  
9. 在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerIsolatedHost**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [步骤 3A： 添加一个文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 3c： 添加要捕获的 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息的 FileAct 应用商店和向前情况下的文件发送端口](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [步骤 3D： 添加 FILEACT 发送端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)