---
title: 批处理业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
- batch orchestration
- orchestrations, batch orchestration
- messages, batching
- batching, batch orchestration
- batching, messages
ms.assetid: b449d8d5-72a2-46c8-a2b1-380431175f4d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2271170d91990e5874168a18ed274c1502a93158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971590"
---
# <a name="batch-orchestration"></a><span data-ttu-id="51bab-102">批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="51bab-102">Batch Orchestration</span></span>
<span data-ttu-id="51bab-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 提供了可用于处理批处理业务流程 (BatchOrchestration.dll)。</span><span class="sxs-lookup"><span data-stu-id="51bab-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides an orchestration (BatchOrchestration.dll) that you can use to process batches.</span></span> <span data-ttu-id="51bab-104">此业务流程可以处理 HL7 编码 (2.X) 消息和/或确认 (Ack) 的批处理。</span><span class="sxs-lookup"><span data-stu-id="51bab-104">This orchestration can process batches of HL7-encoded (2.X) messages and/or acknowledgments (ACKs).</span></span> <span data-ttu-id="51bab-105">业务流程是一个本机[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]业务流程添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]（如下所列在 BizTalk 浏览器中的业务流程） 设置到的 BizTalk 业务流程的集。</span><span class="sxs-lookup"><span data-stu-id="51bab-105">The orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations (as listed under Orchestrations in BizTalk Explorer).</span></span>  
  
 <span data-ttu-id="51bab-106">业务流程处理批处理激活，批处理终止，并且批处理计时器消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用来控制批处理。</span><span class="sxs-lookup"><span data-stu-id="51bab-106">The orchestration works with batch activation, batch termination, and batch timer messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] uses to control batches.</span></span> <span data-ttu-id="51bab-107">业务流程也适用于批处理控制端口，这是一个接收端口的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序将安装来处理控制消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="51bab-107">The orchestration also works with the batch control port, which is a receive port that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup installs to handle batch control messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bab-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="51bab-108">See Also</span></span>  
 <span data-ttu-id="51bab-109">[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="51bab-109">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 [<span data-ttu-id="51bab-110">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="51bab-110">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)