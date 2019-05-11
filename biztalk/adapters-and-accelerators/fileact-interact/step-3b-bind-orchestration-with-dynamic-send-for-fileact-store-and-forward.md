---
title: 步骤 3b:将替换为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定 |Microsoft Docs
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
ms.openlocfilehash: 02a31f1b96c3cbdab57c82ecb73973c2b15306ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365622"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>步骤 3b:将替换为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定
在开始此步骤之前，必须完成[步骤 3A:创建为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)。  
  
### <a name="to-add-a-file-receive-location"></a>若要添加的文件接收位置  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台，在左窗格中，展开 BizTalk Server 管理，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**. 验证的状态**BizTalkServerApplication**托管实例和 FileActhost 实例是**运行**。 如果没有，请右键单击主机实例，然后单击**启动**。  
  
3.  在左窗格中，展开应用程序，然后展开 BizTalk Application 1。 单击业务流程。  
  
4.  右键单击**DynamicSendOrchestration**然后单击**属性**。  
  
5.  在中**业务流程属性**对话框中，在左窗格中，单击**绑定**并执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**主机**|从下拉列表中，选择**BizTalkServer 应用程序**。|  
    |**动态请求**|从下拉列表中，选择**Tutorial_FA_DynamicSendPort**。|  
    |**SendPullResponseToSender**|从下拉列表中，选择**Tutorial_FA_SendPullResponsetoReceiver**。|  
  
## <a name="see-also"></a>请参阅  
 [步骤 3a:创建为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)