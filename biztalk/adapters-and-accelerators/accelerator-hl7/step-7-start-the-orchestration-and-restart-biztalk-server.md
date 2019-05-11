---
title: 步骤 7：启动业务流程和重新启动 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa5168b0-4642-4842-a57a-ed7fa35fe161
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6421a4deb0883c1dcf3054b816020707c285f290
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287910"
---
# <a name="step-7-start-the-orchestration-and-restart-biztalk-server"></a><span data-ttu-id="2c54b-102">步骤 7：启动业务流程和重新启动 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2c54b-102">Step 7: Start the Orchestration and Restart BizTalk Server</span></span>
<span data-ttu-id="2c54b-103">在此步骤中，将启动业务流程，然后重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，以便在本教程中所做的更改将生效。</span><span class="sxs-lookup"><span data-stu-id="2c54b-103">In this step, you start the orchestration, and then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] so that the changes that you made in this tutorial will take effect.</span></span>  
  
### <a name="to-start-the-orchestration-and-restart-biztalk-server"></a><span data-ttu-id="2c54b-104">若要启动该业务流程和重新启动 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2c54b-104">To start the orchestration and restart BizTalk Server</span></span>  
  
1. <span data-ttu-id="2c54b-105">在 BizTalk 管理控制台中，单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="2c54b-105">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Start**.</span></span>  
  
2. <span data-ttu-id="2c54b-106">展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="2c54b-106">Expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="2c54b-107">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="2c54b-107">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span> <span data-ttu-id="2c54b-108">验证状态是否**已停止**，然后**运行**。</span><span class="sxs-lookup"><span data-stu-id="2c54b-108">Verify that the status indicates **Stopped**, and then **Running**.</span></span>  
  
   <span data-ttu-id="2c54b-109">请继续执行[步骤 8:测试 Create-batch 方案](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="2c54b-109">Proceed to [Step 8: Test the Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md).</span></span>