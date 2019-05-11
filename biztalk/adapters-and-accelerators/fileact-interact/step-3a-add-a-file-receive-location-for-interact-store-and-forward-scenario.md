---
title: 步骤 3a:为 InterAct 存储和转发方案添加文件接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f4bae51-6869-4334-a3a1-ef7e662197ca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb4594877cb4679bbb355d8ea9ee66041c12dfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365923"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a>步骤 3a:为 InterAct 存储和转发方案添加文件接收位置
完整[步骤 2:向为 InterAct 存储和转发方案 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)开始此步骤之前。
  
## <a name="add-a-file-receive-location"></a>添加 FILE 接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**  
  
4.  在中**接收端口属性**窗口中，名称的接收端口，Tutorial_IA_InputRequest_SnF。  
  
5.  在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。  
  
6.  在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中，键入 C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF，，然后单击**确定**。  
  
8.  在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
9. 单击“确定” 。  
  
## <a name="complete-steps"></a>完成的步骤
 [步骤 3：创建发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 3b:为 InterAct 存储和转发方案添加 INTERACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [步骤 3D:为 InterAct 存储和转发方案添加 INTERACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)