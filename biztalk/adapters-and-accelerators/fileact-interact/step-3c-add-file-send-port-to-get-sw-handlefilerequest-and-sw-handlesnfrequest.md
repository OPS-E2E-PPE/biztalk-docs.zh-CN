---
title: '步骤 3c:添加 FILE 发送端口以捕获为 FileAct 存储和转发方案: handlefilerequest 和 sw: handlesnfrequest 消息 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca89ba30184664aada5f312dc021f858234bc39c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365588"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a>步骤 3c:添加 FILE 发送端口以捕获为 FileAct 存储和转发方案: handlefilerequest 和 sw: handlesnfrequest 消息
在开始此步骤之前，必须完成[步骤 3B:为 FileAct 存储和转发方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a>若要添加一个 FILE 发送端口以捕获 Sw:ResponseServer 消息  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**  
  
4.  在中**发送端口属性**窗口中，命名该发送端口，Tutorial_FA_SendResponseToReceiver。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ResponseServer，，然后单击**确定**。  
  
7.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
  
8.  在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**第一行：属性**|从下拉列表中，选择**BTS。MessageType**。|  
    |**第一行：!**|从下拉列表中，选择**==**。|  
    |**第一行：值**|类型**Sw HandleFileRequest**。|  
    |**第一行：分组依据**|从下拉列表中，选择**或**。|  
    |**第二行：属性**|从下拉列表中，选择**BTS。MessageType**。|  
    |**第二行：!**|从下拉列表中，选择**==**。|  
    |**第二行：值**|类型**Sw HandleSnFRequest**。|  
    |**第二行：分组依据**|保留默认值。|  
  
9. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [步骤 3a:为 FileAct 存储和转发方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 3b:为 FileAct 存储和转发方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [步骤 3D:添加 FILEACT 发送端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)