---
title: 步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195480b616437eea7b1cfafa703d4ec5d0bd2b54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225269"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a>步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置
在开始此步骤之前，必须完成[步骤 2： 将 SWIFTNet 配置添加到交互应用商店应用和转发方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)。  
  
### <a name="to-add-a-file-receive-location"></a>若要添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_InputRequest_SnF**。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**，然后单击**确定**。  
  
8.  在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 单击 **“确定”**。  
  
10. 重复步骤 1 和 2。  
  
11. 右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
12. 在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_InputRequest_PullMode**。  
  
13. 在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
14. 在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
15. 在**文件传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\PullRequest**，然后单击**确定**。  
  
16. 在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
17. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2B： 添加要捕获 Sw:HandleRequest 消息交互，应用商店应用和进 （请求） 方案的文件发送端口](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)   
 [步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)