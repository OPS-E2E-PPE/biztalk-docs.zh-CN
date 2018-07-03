---
title: 步骤 1： 配置和启用 BatchControlPort 接收端口 |Microsoft Docs
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
ms.openlocfilehash: 1fb11e0638a66fa7d22332d1cbca103a14490528
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988246"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a><span data-ttu-id="26113-102">步骤 1： 配置和启用 BatchControlPort 接收端口</span><span class="sxs-lookup"><span data-stu-id="26113-102">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>
<span data-ttu-id="26113-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 安装程序将创建接收端口，批处理控制端口，若要处理的消息的批处理业务流程使用来启动，请停止，和时间的批次。</span><span class="sxs-lookup"><span data-stu-id="26113-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) setup creates a receive port, the batch control port, to handle the messages that the batch orchestration uses to start, stop, and time batches.</span></span> <span data-ttu-id="26113-104">这些消息包括批处理激活、 批处理终止和计时器消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="26113-104">These messages include the batch activation, batch termination, and batch timer messages.</span></span> <span data-ttu-id="26113-105">在此步骤中，将批处理控制端口，将接收管道配置和启用端口。</span><span class="sxs-lookup"><span data-stu-id="26113-105">In this step, you configure the receive pipeline for the batch control port, and enable the port.</span></span>  
  
### <a name="to-configure-and-enable-batchcontrolport"></a><span data-ttu-id="26113-106">若要配置和启用 BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="26113-106">To configure and enable BatchControlPort</span></span>  
  
1. <span data-ttu-id="26113-107">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="26113-107">Start **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="26113-108">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**。</span><span class="sxs-lookup"><span data-stu-id="26113-108">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="26113-109">单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="26113-109">Click **Receive Locations**.</span></span>  
  
3. <span data-ttu-id="26113-110">右键单击**BatchControlLocation**，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="26113-110">Right-click **BatchControlLocation**, and then click **Disable**.</span></span>  
  
4. <span data-ttu-id="26113-111">右键单击**BatchControlLocation**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="26113-111">Right-click **BatchControlLocation**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="26113-112">在接收位置属性对话框中，对于**接收管道**，选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="26113-112">In the Receive Location Properties dialog box, for **Receive Pipeline**, select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.Click **OK**.</span></span>  
  
6. <span data-ttu-id="26113-113">在 BizTalk 管理控制台中，右键单击**BatchControlLocation**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="26113-113">In the BizTalk Administration Console, right-click **BatchControlLocation**, and then click **Enable**.</span></span>  
  
   <span data-ttu-id="26113-114">请继续执行[步骤 2： 启用批处理业务流程](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="26113-114">Proceed to [Step 2: Enable the Batch Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span></span>