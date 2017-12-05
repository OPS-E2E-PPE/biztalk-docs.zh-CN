---
title: "步骤 3B： 添加交互接收位置交互应用商店应用和向前方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9aa8e153cf510f2d24cbe30a62317d26810e4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a>步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置
完成[步骤 3A： 添加文件接收位置交互应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)在开始此步骤之前。
  
## <a name="add-an-interact-receive-location"></a>添加交互接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口，Tutorial_IA_HandleRequestOneWay_SnF。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。  
  
7.  在**交互传输属性**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名称。|  
    |**应用程序名称**|键入的服务器\<应用程序接口名称\>压降框中路由组。|  
    |**加密模式**|从下拉列表中选择**高级**。|  
    |**LogMessageBody**|从下拉列表中选择**FALSE**。 **注意：**如果设置为 TRUE 时，它会保留 BizTalk 跟踪数据库的消息正文。 但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。|  
    |**日志消息**|从下拉列表中选择**TRUE**。 这样将捕获和 BAM 门户中跟踪消息事件。|  
    |**消息格式**|从下拉列表中选择**InterActMessage**。|  
    |**MemberRef**|从下拉列表中选择**ResponseHeader**。|  
    |**不可否认性指示器**|从下拉列表中选择**FALSE**。|  
    |**响应方**|键入相应\<响应方\>基于 SWIFT 你设置的字符串。|  
    |**ResponseCrypto**|从下拉列表中选择**FALSE**。|  
    |**超时**|键入适当数量会发生超时之前等待的秒。|  
    |**获取队列**|键入根据 SWIFT 你设置的队列名称。|  
    |**ForceAcquire**|从下拉列表中选择**TRUE**。|  
    |**排序依据**|从下拉列表中选择**交互**。|  
    |**推送会话**|从下拉列表中选择**TRUE**。|  
    |**恢复模式**|从下拉列表中选择**TRUE**。|  
    |**SNL 终结点**|键入压降路由组的相应终结点。 此值应与匹配压降中配置的 SnL 终结点。|  
  
8.  单击 **“确定”**。  
  
9. 在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerIsolatedHost**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
10. 单击 **“确定”**。  
  
## <a name="complete-steps"></a>完成步骤
 [步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [步骤 3C：为 InterAct 存储和转发方案添加 FILE 发送端口以捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [步骤 3D：为 InterAct 存储和转发方案添加 INTERACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)