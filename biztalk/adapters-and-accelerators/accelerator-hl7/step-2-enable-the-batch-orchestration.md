---
title: 第 2 步：启用批处理业务流程 |Microsoft Docs
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
ms.openlocfilehash: f0afe72cdf0ea747e5236f02577de16acb685061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288615"
---
# <a name="step-2-enable-the-batch-orchestration"></a><span data-ttu-id="ff670-102">第 2 步：启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="ff670-102">Step 2: Enable the Batch Orchestration</span></span>
<span data-ttu-id="ff670-103">批处理业务流程控制创建批处理过程。</span><span class="sxs-lookup"><span data-stu-id="ff670-103">The batch orchestration controls the create batch process.</span></span> <span data-ttu-id="ff670-104">它维护要包含在批处理中的所有消息的引用、 控制出站批事务、 生成批消息，将路由传出批，和处理传入确认批。</span><span class="sxs-lookup"><span data-stu-id="ff670-104">It maintains references for all messages to be included in the batch, controls the outbound batch transaction, generates the batch message, routes the outgoing batch, and processes incoming acknowledgment batches.</span></span> <span data-ttu-id="ff670-105">您需要创建批处理过程，以便批处理业务流程登记。</span><span class="sxs-lookup"><span data-stu-id="ff670-105">You need to enlist the batch orchestration for the create batch process to work.</span></span>  
  
### <a name="to-enable-the-batch-orchestration"></a><span data-ttu-id="ff670-106">若要启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="ff670-106">To enable the batch orchestration</span></span>  
  
1. <span data-ttu-id="ff670-107">在 BizTalk 管理控制台中，单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ff670-107">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="ff670-108">在业务流程属性对话框中，在控制台树中，单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="ff670-108">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
3. <span data-ttu-id="ff670-109">在中**绑定**窗格中，对于**主机**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="ff670-109">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="ff670-110">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ff670-110">Click **OK**.</span></span>  
  
4. <span data-ttu-id="ff670-111">在 BizTalk 管理控制台中，右键单击**BatchOrchestration.Orchestration_1**，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="ff670-111">In the BizTalk Administration Console, right-click **BatchOrchestration.Orchestration_1**, and then click **Enlist**.</span></span>  
  
   <span data-ttu-id="ff670-112">请继续执行[步骤 3:创建并配置目标参与方](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)。</span><span class="sxs-lookup"><span data-stu-id="ff670-112">Proceed to [Step 3: Create and Configure a Destination Party](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span></span>