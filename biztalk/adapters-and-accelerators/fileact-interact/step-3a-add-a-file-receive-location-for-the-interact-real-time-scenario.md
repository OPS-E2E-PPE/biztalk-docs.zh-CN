---
title: 步骤 3a:添加 FILE 接收位置 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5579375-8c05-4583-bcaa-b483ac275d8a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 776a5b8c708e9b86c6bd844fc2dcb46aed9efe40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365673"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a>步骤 3a:添加 FILE 接收位置 InterAct 实时方案
设置接收位置，可用于轻松地删除测试文件进行验证。 此位置用于测试的方案。  
  
## <a name="add-a-file-receive-location"></a>添加 FILE 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_IA_InputRequest_RealTime**。  
  
5.  在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
6.  在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**，然后单击**确定**。  
  
8.  在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
9. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)