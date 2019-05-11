---
title: 步骤 3b:为 FileAct 存储和转发方案添加 FILEACT 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f30bb7d-1efb-4350-8809-be35f5634ea0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7879dacb4aab2e2d14ec4a00025569484fc52d57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365723"
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a>步骤 3b:为 FileAct 存储和转发方案添加 FILEACT 接收位置
在开始此步骤之前，必须完成[步骤 3A:为 FileAct 存储和转发方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)。  
  
### <a name="to-add-an-fileact-receive-location"></a>若要添加 FILEACT 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，名称的接收端口，Tutorial_FA_HandleRequestOneWay_SnF。  
  
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
    |**FileCompression**|从下拉列表中，选择无。|  
    |**PhysicalFolderName**|在服务器上键入文件夹的名称。 例如，C:\Fileact\ServerLocation。|  
    |**SubscribeFileEvents**|从下拉列表中，选择**FALSE**。|  
    |**TransferAnswer**|从下拉列表中，选择**已接受**。|  
    |**AllFileEvents**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**事件终结点**|键入相应压降终结点。|  
    |**FullFileStatus**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**超时**|键入适当的会发生超时之前等待的秒数。|  
    |**获取队列**|键入基于 SWIFT 与预配的队列名称。|  
    |**ForceAcquire**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**排序依据**|从下拉列表中，选择**FileAct**。|  
    |**推送会话**|从下拉列表中，选择 **，则返回 TRUE**。|  
    |**恢复模式**|从下拉列表中，选择**FALSE**。|  
    |**SNL 终结点**|键入压降路由组的相应终结点。 此值应与配置中压降 SnL 终结点匹配。|  
  
8.  单击“确定” 。  
  
9. 在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerIsolatedHost**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
10. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [步骤 3a:为 FileAct 存储和转发方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获为 FileAct 存储和转发方案: handlefilerequest 和 sw: handlesnfrequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [步骤 3D:添加 FILEACT 发送端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)