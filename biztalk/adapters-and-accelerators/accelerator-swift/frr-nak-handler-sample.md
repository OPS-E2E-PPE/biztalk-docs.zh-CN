---
title: "FRR 否认处理程序示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a3881b8bcf4b62af7653ef6214b4fccdf8402d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-nak-handler-sample"></a><span data-ttu-id="7c889-102">FRR 否认处理程序示例</span><span class="sxs-lookup"><span data-stu-id="7c889-102">FRR NAK Handler Sample</span></span>
<span data-ttu-id="7c889-103">FRR 否认处理程序示例演示如何使用 SWIFT 响应创建 FIN 响应对帐 (FRR) 具有关联的处理消息的自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="7c889-103">The FRR NAK Handler sample demonstrates how to create a custom handler to process messages that FIN Response Reconciliation (FRR) has correlated with SWIFT responses.</span></span> <span data-ttu-id="7c889-104">此自定义处理程序处理提供 MTS21_FIN_ACKNAK 负确认消息，指示，SWIFT 未成功收到消息 A4SWIFT FRR 具有相关的消息。</span><span class="sxs-lookup"><span data-stu-id="7c889-104">This custom handler processes messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from A4SWIFT.</span></span> <span data-ttu-id="7c889-105">自定义处理程序添加到该消息，使两个部分构成消息的消息的对象时出错，而且有助于提升会导致消息修复业务流程来选取消息的属性。</span><span class="sxs-lookup"><span data-stu-id="7c889-105">The custom handler adds an error object to the message, making the message a two-part message, and promotes the properties that cause the message-repair orchestration to pick up the message.</span></span> <span data-ttu-id="7c889-106">因此，repairer 可以修复消息并重新发送到 SWIFT 联盟访问 (SAA)。</span><span class="sxs-lookup"><span data-stu-id="7c889-106">As a result, a repairer can fix the message and resend it to SWIFT Alliance Access (SAA).</span></span>  
  
 <span data-ttu-id="7c889-107">**示例组件**</span><span class="sxs-lookup"><span data-stu-id="7c889-107">**Sample Components**</span></span>  
  
 <span data-ttu-id="7c889-108">FRR 否认处理程序示例包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="7c889-108">The FRR NAK Handler sample includes the following components:</span></span>  
  
-   <span data-ttu-id="7c889-109">**RepairSWIFTRejectedMessage.odx。**</span><span class="sxs-lookup"><span data-stu-id="7c889-109">**RepairSWIFTRejectedMessage.odx.**</span></span> <span data-ttu-id="7c889-110">此业务流程是处理 SWIFT 无法成功接收，将它路由到消息修复业务流程，以便 repairer 可以修复并重新发送消息的消息的自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="7c889-110">This orchestration is the custom handler that processes a message that SWIFT could not successfully receive, routing it to the message-repair orchestration so a repairer can fix and resend the message.</span></span>  
  
-   <span data-ttu-id="7c889-111">**RepairSWIFTRejectedMessage.btproj。**</span><span class="sxs-lookup"><span data-stu-id="7c889-111">**RepairSWIFTRejectedMessage.btproj.**</span></span> <span data-ttu-id="7c889-112">此项目包括 RepairSWIFTRejectedMessage.odx 和所需项目的引用，生成和部署。</span><span class="sxs-lookup"><span data-stu-id="7c889-112">This project includes RepairSWIFTRejectedMessage.odx and the references required for the project to build and deploy.</span></span>  
  
-   <span data-ttu-id="7c889-113">**RepairSWIFTRejectedMessage.sln。**</span><span class="sxs-lookup"><span data-stu-id="7c889-113">**RepairSWIFTRejectedMessage.sln.**</span></span> <span data-ttu-id="7c889-114">此解决方案包括 RepairSWIFTRejectedMessage.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="7c889-114">This solution includes the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
 <span data-ttu-id="7c889-115">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="7c889-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="7c889-116">实现 FRR 否认处理程序示例</span><span class="sxs-lookup"><span data-stu-id="7c889-116">Implementing the FRR NAK Handler Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
-   [<span data-ttu-id="7c889-117">FRR 否认处理程序示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="7c889-117">How the FRR NAK Handler Sample Works</span></span>](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
