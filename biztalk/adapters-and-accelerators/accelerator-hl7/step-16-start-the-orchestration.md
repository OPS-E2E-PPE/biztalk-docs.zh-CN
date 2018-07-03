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
# <a name="step-16-start-the-orchestration"></a><span data-ttu-id="469a4-102">步骤 16： 启动业务流程</span><span class="sxs-lookup"><span data-stu-id="469a4-102">Step 16: Start the Orchestration</span></span>
<span data-ttu-id="469a4-103">在此步骤中，您才能将相关联的业务流程与该业务流程将在其中运行的物理环境中设计的业务流程登记服务。</span><span class="sxs-lookup"><span data-stu-id="469a4-103">In this step, you enlist the service in order to associate the business process that you designed in the orchestration with the physical environment in which the orchestration will run.</span></span> <span data-ttu-id="469a4-104">此外，启动业务流程的处理，以便可以测试你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="469a4-104">Additionally, you start the processing of the orchestration so that you can test your application.</span></span>  
  
### <a name="to-start-the-orchestration"></a><span data-ttu-id="469a4-105">若要启动的业务流程</span><span class="sxs-lookup"><span data-stu-id="469a4-105">To start the orchestration</span></span>  
  
1. <span data-ttu-id="469a4-106">在中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在控制台树窗格中，在**业务流程**，右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**登记**.</span><span class="sxs-lookup"><span data-stu-id="469a4-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree pane, under **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Enlist**.</span></span>  
  
2. <span data-ttu-id="469a4-107">右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="469a4-107">Right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Start**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="469a4-108">确保你已启动**MLLPSendPort**发送端口并启用**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**接收位置。</span><span class="sxs-lookup"><span data-stu-id="469a4-108">Ensure that you have started the **MLLPSendPort** send port and enabled the **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** receive location.</span></span>  
  
   <span data-ttu-id="469a4-109">请继续执行[步骤 17： 创建 WSClient 应用程序](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)。</span><span class="sxs-lookup"><span data-stu-id="469a4-109">Proceed to [Step 17: Create the WSClient Application](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469a4-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="469a4-110">See Also</span></span>  
 [<span data-ttu-id="469a4-111">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="469a4-111">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)