---
title: 第 1 步：配置和启用 BatchControlPort 接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fdc4260109769fd025b33e6b14d8fd3465d4e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289115"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a><span data-ttu-id="12b1f-102">第 1 步：配置和启用 BatchControlPort 接收端口</span><span class="sxs-lookup"><span data-stu-id="12b1f-102">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>
<span data-ttu-id="12b1f-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 安装程序将创建接收端口，批处理控制端口，若要处理的消息的批处理业务流程使用来启动，请停止，和时间的批次。</span><span class="sxs-lookup"><span data-stu-id="12b1f-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) setup creates a receive port, the batch control port, to handle the messages that the batch orchestration uses to start, stop, and time batches.</span></span> <span data-ttu-id="12b1f-104">这些消息包括批处理激活、 批处理终止和计时器消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="12b1f-104">These messages include the batch activation, batch termination, and batch timer messages.</span></span> <span data-ttu-id="12b1f-105">在此步骤中，将批处理控制端口，将接收管道配置和启用端口。</span><span class="sxs-lookup"><span data-stu-id="12b1f-105">In this step, you configure the receive pipeline for the batch control port, and enable the port.</span></span>  
  
### <a name="to-configure-and-enable-batchcontrolport"></a><span data-ttu-id="12b1f-106">若要配置和启用 BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="12b1f-106">To configure and enable BatchControlPort</span></span>  
  
1. <span data-ttu-id="12b1f-107">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-107">Start **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="12b1f-108">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-108">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="12b1f-109">单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-109">Click **Receive Locations**.</span></span>  
  
3. <span data-ttu-id="12b1f-110">右键单击**BatchControlLocation**，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-110">Right-click **BatchControlLocation**, and then click **Disable**.</span></span>  
  
4. <span data-ttu-id="12b1f-111">右键单击**BatchControlLocation**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-111">Right-click **BatchControlLocation**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="12b1f-112">在接收位置属性对话框中，对于**接收管道**，选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-112">In the Receive Location Properties dialog box, for **Receive Pipeline**, select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.Click **OK**.</span></span>  
  
6. <span data-ttu-id="12b1f-113">在 BizTalk 管理控制台中，右键单击**BatchControlLocation**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="12b1f-113">In the BizTalk Administration Console, right-click **BatchControlLocation**, and then click **Enable**.</span></span>  
  
   <span data-ttu-id="12b1f-114">请继续执行[步骤 2:启用批处理业务流程](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="12b1f-114">Proceed to [Step 2: Enable the Batch Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span></span>