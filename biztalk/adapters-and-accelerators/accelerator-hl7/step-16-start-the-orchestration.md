---
title: "步骤 16： 启动业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- message enrichment tutorial, orchestrations
ms.assetid: a9032b0b-1497-4f6a-8474-a94c14976be0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5256d33dc6751db34d1d827624d2dbe2644639e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-16-start-the-orchestration"></a>步骤 16： 启动业务流程
在此步骤中，为了将业务流程将在其中运行的物理环境与业务流程中设计的业务流程相关联登记服务。 此外，以便你可以测试你的应用程序启动业务流程的处理。  
  
### <a name="to-start-the-orchestration"></a>若要启动业务流程  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]下管理控制台，在控制台树窗格中，**业务流程**，右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**Enlist**.  
  
2.  右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**启动**。  
  
    > [!NOTE]
    >  确保你已启动**MLLPSendPort**发送端口和启用**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**接收位置。  
  
 继续执行[步骤 17： 创建 WSClient 应用程序](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)