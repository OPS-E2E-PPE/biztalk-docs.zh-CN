---
title: 步骤 3c:添加 FILE 发送端口以获取： handlerequest-InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31e9c942-ba74-4ae2-b6e1-5266d0fbcb14
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1deeb12f4af2cf5540217463c211f31a385ba3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365663"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a>步骤 3c:添加 FILE 发送端口以获取： handlerequest-InterAct 实时方案
当向合作伙伴发送一条消息时，SWIFT 转换消息标头并将消息转发给您作为： handlerequest 消息的合作伙伴。 在开始此步骤之前，必须完成[步骤 3B:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a>若要添加一个 FILE 发送端口以捕获： handlerequest 消息  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**  
  
4.  在中**发送端口属性**窗口中，命名发送端口**Tutorial_IA_SendResponseToReceiver**。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Interact\HandleRequest，，然后单击**确定**。  
  
7.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
  
8.  在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中，选择**BTS。ReceivePortName**。|  
    |**“运算符”**|从下拉列表中，选择**==**。|  
    |**ReplTest1**|类型**Tutorial_IA_HandleRequestOneWay_RealTime。**|  
    |**分组依据**|保留默认值。|  
  
9. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [步骤 3a:添加 FILE 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)