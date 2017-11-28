---
title: "处理对帐的消息集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc9f35f9381f82df90acb92e9536bbd967901a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-reconciled-message-sets"></a><span data-ttu-id="2c4d0-102">处理已协调消息集</span><span class="sxs-lookup"><span data-stu-id="2c4d0-102">Handling Reconciled Message Sets</span></span>
<span data-ttu-id="2c4d0-103">当 SAA 返回响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]在消息框中，记录的响应和匹配的响应或对原始消息的响应。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-103">When SAA returns a response to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] records the response in the MessageBox, and matches the response or responses to the original message.</span></span> <span data-ttu-id="2c4d0-104">你可以实现自定义应用程序行为通过使用此信息。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-104">You can implement custom application behavior using this information.</span></span> <span data-ttu-id="2c4d0-105">为此，请开发自定义处理程序实现协调的消息响应集到特定于客户的反应。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-105">To do so, develop custom handlers that implement customer-specific reactions to reconciled message/response sets.</span></span> <span data-ttu-id="2c4d0-106">你可以创建自定义处理程序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c4d0-106">You can create custom handlers that do the following:</span></span>  
  
-   <span data-ttu-id="2c4d0-107">处理提供 MTS21_FIN_ACKNAK 负确认消息，指示 SWIFT 没有成功收到来自的消息的消息所具有相关的 FRR [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-107">Process messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="2c4d0-108">这可以启用 repairer 修复消息并重新将其发送到 SAA 和 SWIFT 网络，它在修复之后希望能成功接收消息。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-108">This can enable a repairer to fix the message and re-send it to SAA and the SWIFT network, which after the repair will hopefully be able to receive the message successfully.</span></span> <span data-ttu-id="2c4d0-109">有关此解决方案的详细信息，请参阅[FRR 否认处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-109">For more information about this solution, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
-   <span data-ttu-id="2c4d0-110">删除消息响应集由业务流程到文件的文件夹发布具有唯一的文件名称，该值指示集合中的消息的关系。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-110">Drop message-response sets published by the orchestration into a file folder with unique file names indicating the relationships of the messages in the set.</span></span> <span data-ttu-id="2c4d0-111">然后，你可以在这些消息上执行业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-111">You can then perform business logic on these messages.</span></span>  
  
-   <span data-ttu-id="2c4d0-112">处理超时消息。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-112">Process timed-out messages.</span></span>  
  
-   <span data-ttu-id="2c4d0-113">消息传输将结果记录，然后放弃实际的消息。</span><span class="sxs-lookup"><span data-stu-id="2c4d0-113">Log the results of message transmission and then discard the actual messages.</span></span>