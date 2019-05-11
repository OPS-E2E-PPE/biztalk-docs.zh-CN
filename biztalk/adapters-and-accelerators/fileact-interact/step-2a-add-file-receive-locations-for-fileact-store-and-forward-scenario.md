---
title: 步骤 2A-添加 FILE 接收位置 |Microsoft Docs
description: 步骤 2A-添加 FILE 接收位置为 FileAct 存储和转发 （拉取） 方案，BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13720ebb-fbe4-4fe1-a095-9ae14c62def1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30311c846b26142e0beeea5ab503dd9599b41e18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366192"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 2A:为 FileAct 存储和转发 （拉取） 方案添加文件接收位置
在开始此步骤之前，必须完成[步骤 1:配置 SWIFT 适配器为 FileAct 存储和转发 （拉取） 方案](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)。  
  
## <a name="add-a-file-receive-location"></a>添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_FA_InputRequest_SnF**。  
  
5.  在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
6.  在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**，然后单击**确定**。  
  
8.  在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
9. 单击“确定” 。  
  
10. 重复步骤 1 和 2。  
  
11. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
12. 在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_ FA_InputRequest_PullMode**。  
  
13. 在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
14. 在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
15. 在中**FILE 传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\PullRequest**，然后单击**确定**。  
  
16. 在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
17. 单击“确定” 。  
  
## <a name="next-steps"></a>后续步骤
-  [步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)