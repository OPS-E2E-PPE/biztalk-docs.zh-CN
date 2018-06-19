---
title: 步骤 2A-添加文件接收位置 |Microsoft 文档
description: 步骤 2A-添加文件在 BizTalk Server 接收 FileAct 应用商店应用和进 （请求） 方案的位置
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
ms.openlocfilehash: e297a85f309445c3caf569d2d752be58997e9754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224069"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 2A： 添加文件接收 FileAct 应用商店应用和进 （请求） 方案的位置
在开始此步骤之前，必须完成[步骤 1： 配置 FileAct 应用商店应用和向前 （请求） 方案 SWIFT 适配器](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)。  
  
## <a name="add-a-file-receive-location"></a>添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口， **Tutorial_FA_InputRequest_SnF**。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**，然后单击**确定**。  
  
8.  在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 单击 **“确定”**。  
  
10. 重复步骤 1 和 2。  
  
11. 右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
12. 在**接收端口属性**窗口中，名称接收端口， **Tutorial_ FA_InputRequest_PullMode**。  
  
13. 在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
14. 在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
15. 在**文件传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\PullRequest**，然后单击**确定**。  
  
16. 在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
17. 单击 **“确定”**。  
  
## <a name="next-steps"></a>后续步骤
-  [步骤 2B： 添加文件发送端口，以捕获 Sw:HandleFileRequest 和 Sw:HandleSnFRequest FileAct 存储和转发的消息 （请求） 方案](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [步骤 2c： 添加 FileAct 应用商店应用和进 （请求） 方案 FILEACT 发送端口](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)