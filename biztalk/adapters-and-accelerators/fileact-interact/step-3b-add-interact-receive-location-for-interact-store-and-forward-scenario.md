---
title: 步骤 3b:为 InterAct 存储和转发方案添加 INTERACT 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd50d40c033fa319e2690ea1a3c6773f694bec5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365636"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a>步骤 3b:为 InterAct 存储和转发方案添加 INTERACT 接收位置
完整[步骤 3A:将文件接收位置为 InterAct 存储和转发方案添加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)开始此步骤之前。
  
## <a name="add-an-interact-receive-location"></a>添加 INTERACT 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，名称的接收端口，Tutorial_IA_HandleRequestOneWay_SnF。  
  
5.  在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
6.  在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。  
  
7.  在中**交互传输属性**对话框框中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名。|  
    |**应用程序名称**|键入的服务器\<应用程序接口名称\>为压降框路由组。|  
    |**加密模式**|从下拉列表中，选择**高级**。|  
    |**LogMessageBody**|从下拉列表中，选择**FALSE**。 **注意：** 如果设置为 TRUE 时，它将保留消息正文 BizTalk 跟踪数据库中。 但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。|  
    |**LogMessages**|从下拉列表中，选择 **，则返回 TRUE**。 这样，要捕获和跟踪在 BAM 门户中的消息事件。|  
    |**消息格式**|从下拉列表中，选择**InterActMessage**。|  
    |**MemberRef**|从下拉列表中，选择**ResponseHeader**。|  
    |**不可否认指示器**|从下拉列表中，选择**FALSE**。|  
    |**响应方**|键入适当\<响应方\>为基础的 SWIFT 应用预配的字符串。|  
    |**ResponseCrypto**|从下拉列表中，选择**FALSE**。|  
    |**超时**|键入适当的会发生超时之前等待的秒数。|  
    |**获取队列**|键入基于 SWIFT 与预配的队列名称。|  
    |**ForceAcquire**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**排序依据**|从下拉列表中，选择**Interact**。|  
    |**推送会话**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**恢复模式**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**SNL 终结点**|键入压降路由组的相应终结点。 此值应与配置中压降 SnL 终结点匹配。|  
  
8.  单击“确定” 。  
  
9. 在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerIsolatedHost**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
10. 单击“确定” 。  
  
## <a name="complete-steps"></a>完成的步骤
 [步骤 3：创建发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 3a:为 InterAct 存储和转发方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [步骤 3D:为 InterAct 存储和转发方案添加 INTERACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)