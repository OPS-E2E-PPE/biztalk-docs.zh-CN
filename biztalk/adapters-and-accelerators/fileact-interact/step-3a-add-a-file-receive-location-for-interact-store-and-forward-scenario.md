---
title: "步骤 3A： 添加一个文件接收位置交互应用商店应用和向前方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f4bae51-6869-4334-a3a1-ef7e662197ca
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d2027878771249ceb2dcb45683a71b4475a75cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a>步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置
完成[步骤 2： 将 SWIFTNet 配置添加到交互应用商店应用和转发方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)在开始此步骤之前。
  
## <a name="add-a-file-receive-location"></a>添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
4.  在**接收端口属性**窗口中，名称接收端口，Tutorial_IA_InputRequest_SnF。  
  
5.  在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。  
  
6.  在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，键入 C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF，，然后单击**确定**。  
  
8.  在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**接收处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**接收管道**|从下拉列表中选择**XMLReceive**。|  
  
9. 单击 **“确定”**。  
  
## <a name="complete-steps"></a>完成步骤
 [步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [步骤 3c： 添加文件发送端口交互应用商店应用和向前情况下捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)