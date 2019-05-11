---
title: FRR NAK 处理程序示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c39c564595852fa8c19d3d9f26b5ba5946f6c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377565"
---
# <a name="frr-nak-handler-sample"></a><span data-ttu-id="3bc83-102">FRR NAK 处理程序示例</span><span class="sxs-lookup"><span data-stu-id="3bc83-102">FRR NAK Handler Sample</span></span>
<span data-ttu-id="3bc83-103">FRR NAK 处理程序示例演示如何使用 SWIFT 响应创建 FIN 响应对帐 (FRR) 具有关联的处理消息的自定义处理。</span><span class="sxs-lookup"><span data-stu-id="3bc83-103">The FRR NAK Handler sample demonstrates how to create a custom handler to process messages that FIN Response Reconciliation (FRR) has correlated with SWIFT responses.</span></span> <span data-ttu-id="3bc83-104">此自定义处理程序处理 MTS21_FIN_ACKNAK 否定确认消息，指示的 SWIFT 没有成功收到消息 A4SWIFT FRR 具有相关的消息。</span><span class="sxs-lookup"><span data-stu-id="3bc83-104">This custom handler processes messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from A4SWIFT.</span></span> <span data-ttu-id="3bc83-105">自定义处理程序将错误对象添加到该消息，使消息分为两部分消息，并将导致消息修复业务流程选取该消息的属性升级。</span><span class="sxs-lookup"><span data-stu-id="3bc83-105">The custom handler adds an error object to the message, making the message a two-part message, and promotes the properties that cause the message-repair orchestration to pick up the message.</span></span> <span data-ttu-id="3bc83-106">因此，repairer 可以解决该消息并重新发送到 SWIFT 联盟访问 (SAA)。</span><span class="sxs-lookup"><span data-stu-id="3bc83-106">As a result, a repairer can fix the message and resend it to SWIFT Alliance Access (SAA).</span></span>  
  
 <span data-ttu-id="3bc83-107">**示例组件**</span><span class="sxs-lookup"><span data-stu-id="3bc83-107">**Sample Components**</span></span>  
  
 <span data-ttu-id="3bc83-108">FRR NAK 处理程序示例包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="3bc83-108">The FRR NAK Handler sample includes the following components:</span></span>  
  
- <span data-ttu-id="3bc83-109">**RepairSWIFTRejectedMessage.odx.**</span><span class="sxs-lookup"><span data-stu-id="3bc83-109">**RepairSWIFTRejectedMessage.odx.**</span></span> <span data-ttu-id="3bc83-110">此业务流程是处理 SWIFT 无法成功接收，其路由到消息修复业务流程以便 repairer 进行修复，重新发送消息的消息的自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="3bc83-110">This orchestration is the custom handler that processes a message that SWIFT could not successfully receive, routing it to the message-repair orchestration so a repairer can fix and resend the message.</span></span>  
  
- <span data-ttu-id="3bc83-111">**RepairSWIFTRejectedMessage.btproj.**</span><span class="sxs-lookup"><span data-stu-id="3bc83-111">**RepairSWIFTRejectedMessage.btproj.**</span></span> <span data-ttu-id="3bc83-112">此项目包括 RepairSWIFTRejectedMessage.odx 和项目所需的引用来构建和部署。</span><span class="sxs-lookup"><span data-stu-id="3bc83-112">This project includes RepairSWIFTRejectedMessage.odx and the references required for the project to build and deploy.</span></span>  
  
- <span data-ttu-id="3bc83-113">**RepairSWIFTRejectedMessage.sln.**</span><span class="sxs-lookup"><span data-stu-id="3bc83-113">**RepairSWIFTRejectedMessage.sln.**</span></span> <span data-ttu-id="3bc83-114">此解决方案包括 RepairSWIFTRejectedMessage.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="3bc83-114">This solution includes the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
  <span data-ttu-id="3bc83-115">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="3bc83-115">This section contains:</span></span>  
  
- [<span data-ttu-id="3bc83-116">实现 FRR NAK 处理程序示例</span><span class="sxs-lookup"><span data-stu-id="3bc83-116">Implementing the FRR NAK Handler Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
- [<span data-ttu-id="3bc83-117">FRR NAK 处理程序示例工作原理</span><span class="sxs-lookup"><span data-stu-id="3bc83-117">How the FRR NAK Handler Sample Works</span></span>](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
