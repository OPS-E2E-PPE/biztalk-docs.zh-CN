---
title: '步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d832f94f205ab74ee3dbfac06828a750fb89847
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366158"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案
在开始此步骤之前，必须完成[步骤 2A:将文件接收位置为 FileAct 存储和转发 （拉取） 方案添加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)部分。  

### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a>若要添加 FILE 发送端口以捕获 Sw:HandleFileRequest 消息  

1. 启动**BizTalk Server 管理**。  

2. 在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  

3. 右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**  

4. 在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_FA_SendPullResponsetoReceiver**。  

5. 在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  

6. 在中**FILE 传输属性**对话框中**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\FileAct\PullResponse**，然后单击**确定**。  

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
 [步骤 2A:为 FileAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)