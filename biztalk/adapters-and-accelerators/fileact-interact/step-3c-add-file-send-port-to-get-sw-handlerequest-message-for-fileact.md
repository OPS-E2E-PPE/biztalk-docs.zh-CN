---
title: 步骤 3c： 将文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息添加 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc0a9173-20df-4c73-80ee-755987d639d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f0b649e7f8d1c85898677ddc0301851dd302
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224869"
---
# <a name="step-3c-add-a-file-send-port-to-capture-swhandlerequest-message-for-the-fileact-real-time-scenario"></a>步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息
在开始此步骤之前，必须完成[步骤 3B: FileAct 实时方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlefilerequest-message"></a>若要添加一个文件，将发送端口捕获 Sw:HandleFileRequest 消息  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**  
  
4.  在**发送端口属性**窗口中，名称发送端口 Tutorial_FA_SendResponseToReceiver。  
  
5.  在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ResponseServer，，然后单击**确定**。  
  
7.  在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
  
8.  在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中选择**BTS。MessageType**。|  
    |**运算符**|从下拉列表中选择 **==** 。|  
    |**值**|类型**软件 HandleFileRequest**。|  
    |**分组依据**|保留默认值|  
  
9. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [步骤 3A： 添加一个文件接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3D: FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)