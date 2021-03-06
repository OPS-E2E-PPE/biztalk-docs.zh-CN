---
title: 步骤 3b:为 FileAct 实时方案添加 FILEACT 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e086c86-1525-4cef-b7e5-a66e14bd8d4f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b4e02b94e567ad80cafc858ce347f2007d8913c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365647"
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario"></a>步骤 3b:为 FileAct 实时方案添加 FILEACT 接收位置
在开始此步骤之前，必须完成[步骤 3A:为 FileAct 实时方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-add-a-fileact-receive-location"></a>若要添加 FILEACT 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，名称的接收端口，Tutorial_FA_HandleRequestOneWay_RealTime。  
  
5.  在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
6.  在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**FILEACT**，和然后单击**配置**。  
  
7.  在中**FILEACT 传输属性**对话框框中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名。|  
    |**应用程序名称**|键入的服务器\<应用程序接口名称\>为压降框路由组。|  
    |**加密模式**|从下拉列表中，选择**高级**。|  
    |**FACrypto 模式**|从下拉列表中，选择**高级**。|  
    |**LogMessages**|从下拉列表中，选择 **，则返回 TRUE**。 这样，要捕获和跟踪在 BAM 门户中的消息事件。|  
    |**MemberRef**|从下拉列表中，选择**ResponsePayload**。|  
    |**不可否认指示器**|从下拉列表中，选择**FALSE**。|  
    |**响应方**|键入适当\<响应方\>为基础的 SWIFT 应用预配的字符串。|  
    |**ResponseCrypto**|从下拉列表中，选择**FALSE**。|  
    |**确认指示器**|从下拉列表中，选择**ResponsePayload**。|  
    |**FileCompression**|从下拉列表中，选择**None**。|  
    |**PhysicalFolderName**|在服务器上键入文件夹的名称。 例如，C:\Fileact\ServerLocation。|  
    |**SubscribeFileEvents**|从下拉列表中，选择**FALSE**。|  
    |**TransferAnswer**|从下拉列表中，选择**已接受**。|  
    |**AllFileEvents**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**事件终结点**|键入压降路由组的相应终结点。 此值应与配置中压降 SnL 终结点匹配。|  
    |**FullFileStatus**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**超时**|键入适当的会发生超时之前等待的秒数。|  
    |**获取队列**|保留此属性的默认值。 此属性用于存储和转发方案。|  
    |**ForceAcquire**|保留此属性的默认值。 此属性用于存储和转发方案。|  
    |**排序依据**|保留此属性的默认值。 此属性用于存储和转发方案。|  
    |**推送会话**|保留此属性的默认值。 此属性用于存储和转发方案。|  
    |**恢复模式**|保留此属性的默认值。 此属性用于存储和转发方案。|  
    |**SNL 终结点**|保留此属性的默认值。 此属性用于存储和转发方案。|  
  
8.  单击“确定” 。  
  
9. 在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerIsolatedHost**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
10. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [步骤 3a:为 FileAct 实时方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获为 FileAct 实时方案： handlerequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [步骤 3D:为 FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)