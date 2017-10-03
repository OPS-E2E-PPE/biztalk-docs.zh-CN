---
title: "步骤 2： 启用批处理业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f8b18e41aacf61ac4e55e1c8047e9685179656a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-enable-the-batch-orchestration"></a><span data-ttu-id="bb258-102">步骤 2： 启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="bb258-102">Step 2: Enable the Batch Orchestration</span></span>
<span data-ttu-id="bb258-103">批处理业务流程控制创建批处理。</span><span class="sxs-lookup"><span data-stu-id="bb258-103">The batch orchestration controls the create batch process.</span></span> <span data-ttu-id="bb258-104">它维护有关要包括在批处理中的所有消息的引用、 控制出站批处理事务、 生成批处理消息，将路由传出的批处理，并处理传入确认批。</span><span class="sxs-lookup"><span data-stu-id="bb258-104">It maintains references for all messages to be included in the batch, controls the outbound batch transaction, generates the batch message, routes the outgoing batch, and processes incoming acknowledgment batches.</span></span> <span data-ttu-id="bb258-105">你需要登记创建批处理进程工作批次业务流程。</span><span class="sxs-lookup"><span data-stu-id="bb258-105">You need to enlist the batch orchestration for the create batch process to work.</span></span>  
  
### <a name="to-enable-the-batch-orchestration"></a><span data-ttu-id="bb258-106">若要启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="bb258-106">To enable the batch orchestration</span></span>  
  
1.  <span data-ttu-id="bb258-107">在 BizTalk 管理控制台中，单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="bb258-107">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bb258-108">在控制台树中，业务流程属性对话框中单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="bb258-108">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="bb258-109">在**绑定**窗格中，为**主机**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="bb258-109">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="bb258-110">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bb258-110">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="bb258-111">在 BizTalk 管理控制台中，右键单击**BatchOrchestration.Orchestration_1**，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="bb258-111">In the BizTalk Administration Console, right-click **BatchOrchestration.Orchestration_1**, and then click **Enlist**.</span></span>  
  
 <span data-ttu-id="bb258-112">继续执行[步骤 3： 创建和配置目标方](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)。</span><span class="sxs-lookup"><span data-stu-id="bb258-112">Proceed to [Step 3: Create and Configure a Destination Party](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span></span>