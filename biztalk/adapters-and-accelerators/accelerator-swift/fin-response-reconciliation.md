---
title: FIN 响应对帐 |Microsoft 文档
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
ms.openlocfilehash: 5452dbacb8a9a20c8d2e62d62f6043aaea2d18da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208253"
---
# <a name="fin-response-reconciliation"></a><span data-ttu-id="3d111-102">FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="3d111-102">FIN Response Reconciliation</span></span>
<span data-ttu-id="3d111-103">FIN 响应对帐 (FRR) 功能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]与相应的原始消息发送的协调 FIN 响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d111-103">The FIN Response Reconciliation (FRR) feature of [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconciles a FIN response with the corresponding original message sent by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="3d111-104">这建立原始消息的状态，并使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]执行基于该状态的步骤。</span><span class="sxs-lookup"><span data-stu-id="3d111-104">This establishes the status of the original message, and enables [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to take steps based upon that status.</span></span> <span data-ttu-id="3d111-105">而无需对帐，这将不是可能发生的情形。</span><span class="sxs-lookup"><span data-stu-id="3d111-105">Without reconciliation, this would not be possible.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3d111-106">会知道，它 （无论成功) 发送原始消息到 SAA，并且它必须从 SAA，指示的状态的传输，收到的响应，但它将不能使这两者之间的连接。</span><span class="sxs-lookup"><span data-stu-id="3d111-106"> would know that it successfully (or unsuccessfully) sent the original message to SAA, and it would have the response that it received from SAA, indicating the status of the transmission, but it would not be able to make the connection between the two.</span></span> <span data-ttu-id="3d111-107">FRR 建立该连接。</span><span class="sxs-lookup"><span data-stu-id="3d111-107">FRR establishes that connection.</span></span>  
  
 <span data-ttu-id="3d111-108">FIN 响应是否确认 (Ack) 或否定确认 (NAKs) 发送到 SAA [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，或由 SWIFT 网络发送给 SAA，然后转发到 SAA 由[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d111-108">FIN responses are acknowledgments (ACKs) or negative acknowledgments (NAKs) sent by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], or sent by the SWIFT network to SAA and then forwarded by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="3d111-109">传送这些确认存在定义消息的业务的状态。</span><span class="sxs-lookup"><span data-stu-id="3d111-109">The presence or absence of these acknowledgments defines the business status of the message.</span></span> <span data-ttu-id="3d111-110">你可以监视通过业务活动监视 (BAM) 报告此状态。</span><span class="sxs-lookup"><span data-stu-id="3d111-110">You can monitor this status through Business Activity Monitoring (BAM) reporting.</span></span>  
  
 <span data-ttu-id="3d111-111">你也可以实现 FRR 周围的自定义应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="3d111-111">You can also implement custom application behavior around FRR.</span></span> <span data-ttu-id="3d111-112">自定义处理程序可以实现自己的逻辑来处理对帐的套 FIN 响应。</span><span class="sxs-lookup"><span data-stu-id="3d111-112">A custom handler can implement your own logic for handling reconciled sets of FIN responses.</span></span> <span data-ttu-id="3d111-113">自定义处理程序处理的消息，具有相关的 FRR MTS21_FIN_ACKNAK 否认消息的示例，请参阅[FRR 否认处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="3d111-113">For an example of a custom handler that processes messages that FRR has correlated with a MTS21_FIN_ACKNAK NAK message, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
 <span data-ttu-id="3d111-114">默认情况下，通过安装 FRR 业务流程[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="3d111-114">The FRR orchestration is installed by default by the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program.</span></span> <span data-ttu-id="3d111-115">你需要通过创建接收管道，配置 FRR 系统接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="3d111-115">You need to configure the FRR system by creating a receive pipeline, receive locations, and send ports.</span></span> <span data-ttu-id="3d111-116">你还需要配置 FRR 指定它应等待的时间延迟 NAKs 和响应一般情况下。</span><span class="sxs-lookup"><span data-stu-id="3d111-116">You also need to configure FRR to specify how long it should wait for delayed NAKs, and for responses in general.</span></span> <span data-ttu-id="3d111-117">有关 FRR 配置和管理的详细信息，请参阅[配置 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)和[管理 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)。</span><span class="sxs-lookup"><span data-stu-id="3d111-117">For more information about FRR configuration and administration, see [Configuring FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) and [Administering FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="3d111-118">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="3d111-118">This section contains:</span></span>  
  
-   [<span data-ttu-id="3d111-119">FIN 响应类型</span><span class="sxs-lookup"><span data-stu-id="3d111-119">FIN Response Types</span></span>](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [<span data-ttu-id="3d111-120">FRR 处理</span><span class="sxs-lookup"><span data-stu-id="3d111-120">FRR Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [<span data-ttu-id="3d111-121">FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="3d111-121">FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [<span data-ttu-id="3d111-122">FRR 从后端应用程序接收的消息的位置</span><span class="sxs-lookup"><span data-stu-id="3d111-122">FRR Receive Location for Messages from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="3d111-123">消息到 SWIFT FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="3d111-123">FRR Send Port for Messages to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [<span data-ttu-id="3d111-124">FRR 从 SWIFT 接收的消息的位置</span><span class="sxs-lookup"><span data-stu-id="3d111-124">FRR Receive Location for Messages from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [<span data-ttu-id="3d111-125">为到自定义处理程序的消息的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="3d111-125">FRR Send Ports for Messages to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [<span data-ttu-id="3d111-126">处理已协调消息集</span><span class="sxs-lookup"><span data-stu-id="3d111-126">Handling Reconciled Message Sets</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)