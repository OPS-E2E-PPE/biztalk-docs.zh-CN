---
title: 步骤 3a:为 FileAct 实时方案添加文件接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73b044b4-6611-493f-969c-02b52cb56ba7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e25342d623d9d9d32c055b450c9751af6b0cd18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365755"
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario"></a>步骤 3a:为 FileAct 实时方案添加文件接收位置
在开始此步骤之前，必须完成[步骤 2:为 FileAct 实时方案向 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)。  
  
### <a name="to-add-a-file-receive-location"></a>若要添加 FILE 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，名称的接收端口，Tutorial_FA_InputRequest_RealTime。  
  
5.  在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
6.  在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中**接收文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime，，然后单击**确定**。  
  
8.  在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
9. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [步骤 3b:为 FileAct 实时方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获为 FileAct 实时方案： handlerequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [步骤 3D:为 FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)