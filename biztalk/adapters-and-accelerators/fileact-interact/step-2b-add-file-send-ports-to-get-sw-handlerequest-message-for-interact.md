---
title: '步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案 |Microsoft Docs'
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
ms.openlocfilehash: 36ca62623cc6dd78f9c980fa35c3f0e744bc2666
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366115"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a>步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案
在开始此步骤之前，必须完成[步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)。  

### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>若要添加一个 FILE 发送端口以捕获 sw: handlerequest 消息  

1. 启动**BizTalk Server 管理**。  

2. 在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  

3. 右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**  

4. 在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_IA_SendPullResponsetoReceiver**。  

5. 在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  

6. 在中**FILE 传输属性**对话框中**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\PullResponse**，然后单击**确定**。  

7. 在中**发送端口属性**窗口中，执行以下操作：  


   |   **使用此**    |                        **若要执行此操作**                         |
   |-------------------|---------------------------------------------------------------|
   | **发送处理程序**  | 从下拉列表中，选择**BizTalkServerApplication**。 |
   | **发送管道** |       从下拉列表中，选择**XMLTransmit**。        |


8. 单击“确定” 。  

9. 重复步骤 1 和 2。  

10. 右键单击**发送端口**，依次指向**新建**，然后单击**动态要求响应发送端口**。  

11. 在中**发送端口属性**窗口中，命名发送端口<strong>，Tutorial_IA_DynamicSendPort</strong>。  

12. 在中**发送端口属性**窗口中，执行以下操作：  


    |     **使用此**     |                  **若要执行此操作**                  |
    |----------------------|--------------------------------------------------|
    |  **发送管道**   | 从下拉列表中，选择**XMLTransmit**。 |
    | **接收管道** | 从下拉列表中，选择**XMLReceive**。  |


13. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)