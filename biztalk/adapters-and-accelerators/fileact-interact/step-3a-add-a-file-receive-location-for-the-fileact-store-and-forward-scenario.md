---
title: "步骤 3A： 添加一个文件接收位置 FileAct 应用商店应用和向前方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ecbf4a-a2b4-4534-8ca1-3bfbb6a697bf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e02f636500ed21d4442a43078bcd407c91d69d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario"></a>步骤 3A： 添加一个文件接收位置 FileAct 应用商店应用和转发方案
在开始此步骤之前，必须完成[步骤 2： 将 SWIFTNet 配置添加到 FileAct 应用商店应用和转发方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)。  
  
### <a name="to-add-a-file-receive-location"></a>若要添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口，Tutorial_FA_InputRequest_SnF。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，在**接收文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF，，然后单击**确定**。  
  
8.  在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [步骤 3c： 添加要捕获的 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息的 FileAct 应用商店和向前情况下的文件发送端口](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [步骤 3D： 添加 FILEACT 发送端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)