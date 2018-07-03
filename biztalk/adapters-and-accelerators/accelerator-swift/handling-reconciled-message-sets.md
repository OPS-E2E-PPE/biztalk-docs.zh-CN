---
title: 处理已对帐的消息集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d3a06955e0072348098ddd7f191bf4862fb119a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986086"
---
# <a name="handling-reconciled-message-sets"></a><span data-ttu-id="a4603-102">处理已对帐的消息集</span><span class="sxs-lookup"><span data-stu-id="a4603-102">Handling Reconciled Message Sets</span></span>
<span data-ttu-id="a4603-103">SAA 时返回的响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]记录响应消息框，并与匹配的响应或对原始消息的响应。</span><span class="sxs-lookup"><span data-stu-id="a4603-103">When SAA returns a response to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] records the response in the MessageBox, and matches the response or responses to the original message.</span></span> <span data-ttu-id="a4603-104">您可以实现使用此信息的自定义应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="a4603-104">You can implement custom application behavior using this information.</span></span> <span data-ttu-id="a4603-105">若要执行此操作，开发自定义处理程序实现特定于客户的反应到已对帐的消息响应集。</span><span class="sxs-lookup"><span data-stu-id="a4603-105">To do so, develop custom handlers that implement customer-specific reactions to reconciled message/response sets.</span></span> <span data-ttu-id="a4603-106">你可以创建自定义处理程序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a4603-106">You can create custom handlers that do the following:</span></span>  

- <span data-ttu-id="a4603-107">处理与 MTS21_FIN_ACKNAK 否定确认消息，指示 SWIFT 未成功收到来自消息的消息的 FRR 具有相关[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a4603-107">Process messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="a4603-108">这可以使 repairer 修复消息并重新将其发送到 SAA 和 SWIFT 网络，这在修复之后希望能够成功接收消息。</span><span class="sxs-lookup"><span data-stu-id="a4603-108">This can enable a repairer to fix the message and re-send it to SAA and the SWIFT network, which after the repair will hopefully be able to receive the message successfully.</span></span> <span data-ttu-id="a4603-109">有关此解决方案的详细信息，请参阅[FRR NAK 处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a4603-109">For more information about this solution, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  

- <span data-ttu-id="a4603-110">删除发布的业务流程置于一个文件夹，该值指示消息在集中的关系的唯一文件名的消息响应集。</span><span class="sxs-lookup"><span data-stu-id="a4603-110">Drop message-response sets published by the orchestration into a file folder with unique file names indicating the relationships of the messages in the set.</span></span> <span data-ttu-id="a4603-111">然后可以对这些消息来执行业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="a4603-111">You can then perform business logic on these messages.</span></span>  

- <span data-ttu-id="a4603-112">处理超时消息。</span><span class="sxs-lookup"><span data-stu-id="a4603-112">Process timed-out messages.</span></span>  

- <span data-ttu-id="a4603-113">记录的消息传输结果，然后丢弃的实际消息。</span><span class="sxs-lookup"><span data-stu-id="a4603-113">Log the results of message transmission and then discard the actual messages.</span></span>
