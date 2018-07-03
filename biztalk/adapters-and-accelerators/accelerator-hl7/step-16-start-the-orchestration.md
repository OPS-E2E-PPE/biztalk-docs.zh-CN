---
title: 步骤 16： 启动业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- message enrichment tutorial, orchestrations
ms.assetid: a9032b0b-1497-4f6a-8474-a94c14976be0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d2d1429d6b5d8df7facf55900683356200279b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992766"
---
# <a name="step-16-start-the-orchestration"></a>步骤 16： 启动业务流程
在此步骤中，您才能将相关联的业务流程与该业务流程将在其中运行的物理环境中设计的业务流程登记服务。 此外，启动业务流程的处理，以便可以测试你的应用程序。  
  
### <a name="to-start-the-orchestration"></a>若要启动的业务流程  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在控制台树窗格中，在**业务流程**，右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**登记**.  
  
2. 右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**启动**。  
  
   > [!NOTE]
   >  确保你已启动**MLLPSendPort**发送端口并启用**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**接收位置。  
  
   请继续执行[步骤 17： 创建 WSClient 应用程序](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)