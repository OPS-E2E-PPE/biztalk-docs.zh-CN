---
title: '步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9314f86-a2c9-4ef3-8474-b7e2e2f8bf66
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aefaf744405a64b294cefaeb983acca8c0176c9c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365389"
---
# <a name="step-3e-add-a-file-send-port-to-capture-swexchangefileresponse-message-for-the-fileact-real-time-scenario"></a>步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案
在开始此步骤之前，必须完成[步骤 3D:为 FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-swexchangefileresponse-message"></a>若要添加一个 FILE 发送端口以捕获 sw: exchangefileresponse 消息  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**  
  
4.  在中**发送端口属性**窗口中，命名该发送端口，Tutorial_FA_SendResponseToSender。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ResponseClient，，然后单击**确定**。  
  
7.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
  
8.  在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中，选择**BTS。SPName**。|  
    |**“运算符”**|从下拉列表中，选择**==**。|  
    |**ReplTest1**|类型 Tutorial_FA_SendRequest_RealTime。|  
    |**分组依据**|保留默认值。|  
  
9. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [步骤 3a:为 FileAct 实时方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3b:为 FileAct 实时方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获为 FileAct 实时方案： handlerequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [步骤 3D:为 FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)