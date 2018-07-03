---
title: 步骤 2： 启用批处理业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b44dd71c44f2510b6ccd80a731dd21739ed7055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996166"
---
# <a name="step-2-enable-the-batch-orchestration"></a><span data-ttu-id="779d0-102">步骤 2： 启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="779d0-102">Step 2: Enable the Batch Orchestration</span></span>
<span data-ttu-id="779d0-103">批处理业务流程控制创建批处理过程。</span><span class="sxs-lookup"><span data-stu-id="779d0-103">The batch orchestration controls the create batch process.</span></span> <span data-ttu-id="779d0-104">它维护要包含在批处理中的所有消息的引用、 控制出站批事务、 生成批消息，将路由传出批，和处理传入确认批。</span><span class="sxs-lookup"><span data-stu-id="779d0-104">It maintains references for all messages to be included in the batch, controls the outbound batch transaction, generates the batch message, routes the outgoing batch, and processes incoming acknowledgment batches.</span></span> <span data-ttu-id="779d0-105">您需要创建批处理过程，以便批处理业务流程登记。</span><span class="sxs-lookup"><span data-stu-id="779d0-105">You need to enlist the batch orchestration for the create batch process to work.</span></span>  
  
### <a name="to-enable-the-batch-orchestration"></a><span data-ttu-id="779d0-106">若要启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="779d0-106">To enable the batch orchestration</span></span>  
  
1. <span data-ttu-id="779d0-107">在 BizTalk 管理控制台中，单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="779d0-107">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="779d0-108">在业务流程属性对话框中，在控制台树中，单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="779d0-108">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
3. <span data-ttu-id="779d0-109">在中**绑定**窗格中，对于**主机**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="779d0-109">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="779d0-110">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="779d0-110">Click **OK**.</span></span>  
  
4. <span data-ttu-id="779d0-111">在 BizTalk 管理控制台中，右键单击**BatchOrchestration.Orchestration_1**，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="779d0-111">In the BizTalk Administration Console, right-click **BatchOrchestration.Orchestration_1**, and then click **Enlist**.</span></span>  
  
   <span data-ttu-id="779d0-112">请继续执行[步骤 3： 创建和配置目标参与方](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)。</span><span class="sxs-lookup"><span data-stu-id="779d0-112">Proceed to [Step 3: Create and Configure a Destination Party](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span></span>