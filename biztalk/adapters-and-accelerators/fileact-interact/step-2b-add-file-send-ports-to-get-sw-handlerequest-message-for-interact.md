---
title: 步骤 2B： 添加文件发送端口交互应用商店应用和进 （请求） 方案中捕获 Sw:HandleRequest 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24200d21ef4a2047b94f9d818864a0a9da2ceb3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225237"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a>步骤 2B： 添加要捕获 Sw:HandleRequest 消息交互，应用商店应用和进 （请求） 方案的文件发送端口
在开始此步骤之前，必须完成[步骤 2A： 添加接收的文件位置的交互，存储和转发 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>若要添加一个文件，将发送端口捕获 Sw:HandleRequest 消息  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**  
  
4.  在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendPullResponsetoReceiver**。  
  
5.  在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在**文件传输属性**对话框中，在**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\PullResponse**，然后单击**确定**。  
  
7.  在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
  
8.  单击 **“确定”**。  
  
9. 重复步骤 1 和 2。  
  
10. 右键单击**发送端口**，指向**新建**，然后单击**动态请求-响应发送端口**。  
  
11. 在**发送端口属性**窗口中，名称发送端口 **，Tutorial_IA_DynamicSendPort**。  
  
12. 在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
13. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)