---
title: FIN 响应对帐 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ACKs
- FRR
- FIN Response Reconciliation
- SAA
- NAKs
- FRR, about FRR
- acknowledgements
- FIN Response Reconciliation, about FIN Response Reconciliation
- FIN Response Reconciliation, acknowledgements
ms.assetid: 987b932b-e487-4ca8-acd0-410d71df8e6d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c2b74012c5f33967773234902a7475b8052f769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377853"
---
# <a name="fin-response-reconciliation"></a><span data-ttu-id="887f6-102">FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="887f6-102">FIN Response Reconciliation</span></span>
<span data-ttu-id="887f6-103">FIN 响应对帐 (FRR) 功能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]协调与相应的原始消息的发送 FIN 响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="887f6-103">The FIN Response Reconciliation (FRR) feature of [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconciles a FIN response with the corresponding original message sent by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="887f6-104">这会建立原始消息的状态并启用[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]执行基于该状态的步骤。</span><span class="sxs-lookup"><span data-stu-id="887f6-104">This establishes the status of the original message, and enables [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to take steps based upon that status.</span></span> <span data-ttu-id="887f6-105">而无需对帐，这不是可能。</span><span class="sxs-lookup"><span data-stu-id="887f6-105">Without reconciliation, this would not be possible.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="887f6-106">会知道，它已成功 （或未成功） 将原始消息发送到 SAA，和它必须从 SAA，指示状态的传输，它接收的响应，但它将不能两者之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="887f6-106">would know that it successfully (or unsuccessfully) sent the original message to SAA, and it would have the response that it received from SAA, indicating the status of the transmission, but it would not be able to make the connection between the two.</span></span> <span data-ttu-id="887f6-107">FRR 建立该连接。</span><span class="sxs-lookup"><span data-stu-id="887f6-107">FRR establishes that connection.</span></span>  
  
 <span data-ttu-id="887f6-108">FIN 响应是确认 (Ack) 或否定确认 (NAKs) 发送到 SAA [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，或由 SWIFT 网络发送到 SAA，并转发到 SAA 按[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="887f6-108">FIN responses are acknowledgments (ACKs) or negative acknowledgments (NAKs) sent by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], or sent by the SWIFT network to SAA and then forwarded by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="887f6-109">这些确认存在定义消息的业务状态。</span><span class="sxs-lookup"><span data-stu-id="887f6-109">The presence or absence of these acknowledgments defines the business status of the message.</span></span> <span data-ttu-id="887f6-110">你可以监视通过业务活动监视 (BAM) 报告此状态。</span><span class="sxs-lookup"><span data-stu-id="887f6-110">You can monitor this status through Business Activity Monitoring (BAM) reporting.</span></span>  
  
 <span data-ttu-id="887f6-111">此外可以实现 FRR 周围的自定义应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="887f6-111">You can also implement custom application behavior around FRR.</span></span> <span data-ttu-id="887f6-112">自定义处理程序可以实现自己的逻辑来处理的 FIN 响应对帐的集。</span><span class="sxs-lookup"><span data-stu-id="887f6-112">A custom handler can implement your own logic for handling reconciled sets of FIN responses.</span></span> <span data-ttu-id="887f6-113">处理的消息的 FRR 具有相关 MTS21_FIN_ACKNAK NAK 消息的自定义处理程序的示例，请参阅[FRR NAK 处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="887f6-113">For an example of a custom handler that processes messages that FRR has correlated with a MTS21_FIN_ACKNAK NAK message, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
 <span data-ttu-id="887f6-114">默认情况下安装 FRR 业务流程[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="887f6-114">The FRR orchestration is installed by default by the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program.</span></span> <span data-ttu-id="887f6-115">您需要通过创建接收管道中，配置的 FRR 系统接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="887f6-115">You need to configure the FRR system by creating a receive pipeline, receive locations, and send ports.</span></span> <span data-ttu-id="887f6-116">此外需要配置 FRR 来指定它应等待多长延迟 NAKs 和响应一般情况下。</span><span class="sxs-lookup"><span data-stu-id="887f6-116">You also need to configure FRR to specify how long it should wait for delayed NAKs, and for responses in general.</span></span> <span data-ttu-id="887f6-117">FRR 配置和管理有关的详细信息，请参阅[配置 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)并[管理 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)。</span><span class="sxs-lookup"><span data-stu-id="887f6-117">For more information about FRR configuration and administration, see [Configuring FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) and [Administering FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="887f6-118">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="887f6-118">This section contains:</span></span>  
  
-   [<span data-ttu-id="887f6-119">FIN 响应类型</span><span class="sxs-lookup"><span data-stu-id="887f6-119">FIN Response Types</span></span>](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [<span data-ttu-id="887f6-120">FRR 处理</span><span class="sxs-lookup"><span data-stu-id="887f6-120">FRR Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [<span data-ttu-id="887f6-121">FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="887f6-121">FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [<span data-ttu-id="887f6-122">从后端应用程序接收消息的 FRR 接收位置</span><span class="sxs-lookup"><span data-stu-id="887f6-122">FRR Receive Location for Messages from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="887f6-123">向 SWIFT 发送消息的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="887f6-123">FRR Send Port for Messages to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [<span data-ttu-id="887f6-124">从 SWIFT 接收消息的 FRR 接收位置</span><span class="sxs-lookup"><span data-stu-id="887f6-124">FRR Receive Location for Messages from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [<span data-ttu-id="887f6-125">向自定义处理程序发送消息的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="887f6-125">FRR Send Ports for Messages to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [<span data-ttu-id="887f6-126">处理已对帐的消息集</span><span class="sxs-lookup"><span data-stu-id="887f6-126">Handling Reconciled Message Sets</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)