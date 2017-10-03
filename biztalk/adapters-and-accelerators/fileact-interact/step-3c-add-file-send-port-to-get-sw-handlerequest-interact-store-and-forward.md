---
title: "步骤 3c： 添加文件发送端口，以获取 Sw:HandleRequest-交互存储和转发 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c57f2f3a6e2fcfc199e56d34c44aa7667451d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a>步骤 3c： 添加文件发送端口，以获取 Sw:HandleRequest-交互存储和转发
在开始此步骤之前，必须完成[步骤 3B： 添加交互接收位置的交互，存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>若要添加一个文件，将发送端口捕获 Sw:HandleRequest 消息  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**  
  
4.  在**发送端口属性**窗口中，名称发送端口 Tutorial_IA_SendResponseToReceiver。  
  
5.  在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Interact\HandleRequest，，然后单击**确定**。  
  
7.  在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
  
8.  在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中选择**BTS。ReceivePortName**。|  
    |**运算符**|从下拉列表中选择 **==** 。|  
    |**值**|类型**Tutorial_IA_InputRequest_SnF**。|  
    |**分组依据**|保留默认值。|  
  
9. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)