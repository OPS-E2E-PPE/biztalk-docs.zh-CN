---
title: 步骤 3B： 将绑定与 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb973066-8797-4f51-a89e-3845f2811605
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10111de1080aacd532be96f501be1d20acda1dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224381"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>步骤 3B： 将绑定与 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程
在开始此步骤之前，必须完成[步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)。  
  
### <a name="to-add-a-file-receive-location"></a>若要添加文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，在左窗格中，展开 BizTalk Server 管理，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**. 验证的状态**BizTalkServerApplication**托管实例和 FileActhost 实例是**运行**。 如果没有，右键单击主机实例，然后单击**启动**。  
  
3.  在左窗格中，展开应用程序，然后展开 BizTalk 应用程序 1。 单击业务流程。  
  
4.  右键单击**DynamicSendOrchestration**单击**属性**。  
  
5.  在**业务流程属性**对话框中，在左窗格中，单击**绑定**和执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**主机**|从下拉列表中选择**BizTalkServer 应用程序**。|  
    |**动态请求**|从下拉列表中选择**Tutorial_FA_DynamicSendPort**。|  
    |**SendPullResponseToSender**|从下拉列表中选择**Tutorial_FA_SendPullResponsetoReceiver**。|  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)