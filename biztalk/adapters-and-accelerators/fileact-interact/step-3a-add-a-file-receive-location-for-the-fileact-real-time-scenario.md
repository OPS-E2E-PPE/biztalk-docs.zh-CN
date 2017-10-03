---
title: "步骤 3A： 添加一个文件接收位置 FileAct 实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b044b4-6611-493f-969c-02b52cb56ba7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 266b29281ea7518cffee1461da2a3eaac66d9429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario"></a>步骤 3A： 添加一个文件接收位置 FileAct 实时方案
在开始此步骤之前，必须完成[步骤 2： 将 SWIFTNet 配置添加到 FileAct 实时方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)。  
  
### <a name="to-add-a-file-receive-location"></a>若要添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口，Tutorial_FA_InputRequest_RealTime。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，在**接收文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime，，然后单击**确定**。  
  
8.  在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [步骤 3D: FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)