---
title: 配置 FIN 响应对帐 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384a2ea27e3d208864c8b16ec52562e6e1cfa28e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209405"
---
# <a name="configuring-fin-response-reconciliation"></a><span data-ttu-id="46820-102">配置 FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="46820-102">Configuring FIN Response Reconciliation</span></span>
<span data-ttu-id="46820-103">你必须在以下部分来配置中执行步骤[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN 响应对帐 (FRR) 功能，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="46820-103">You must perform the steps in the following sections to configure the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN Response Reconciliation (FRR) feature, as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 <span data-ttu-id="46820-104">在 A4SWIFT 安装向导中，你可以选择安装消息修复和新的提交和 FRR，或消息修复和新的提交，而无需 FRR 或如果没有消息修复和新提交 FRR。</span><span class="sxs-lookup"><span data-stu-id="46820-104">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FRR, or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="46820-105">因此，本部分中的说明进行操作不会假定安装和配置消息修复和新的提交。</span><span class="sxs-lookup"><span data-stu-id="46820-105">As a result, the instructions in this section do not assume that you are installing and configuring Message Repair and New Submission.</span></span> <span data-ttu-id="46820-106">它们，但是，假定你已执行中的步骤[A4SWIFT 运行时配置](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="46820-106">They do, however, assume that you have performed the steps in the [Configuring the A4SWIFT Runtime](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span></span>  
  
 <span data-ttu-id="46820-107">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="46820-107">This section contains:</span></span>  
  
-   [<span data-ttu-id="46820-108">绑定和启动 FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="46820-108">Binding and Starting the FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [<span data-ttu-id="46820-109">创建 FRR 接收管道</span><span class="sxs-lookup"><span data-stu-id="46820-109">Creating the FRR Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [<span data-ttu-id="46820-110">创建 FRR 接收位置用于接收从后端应用程序</span><span class="sxs-lookup"><span data-stu-id="46820-110">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="46820-111">创建 FRR 来接收来自 SWIFT 接收位置</span><span class="sxs-lookup"><span data-stu-id="46820-111">Creating the FRR Receive Location for Receiving from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [<span data-ttu-id="46820-112">创建 FRR 发送管道</span><span class="sxs-lookup"><span data-stu-id="46820-112">Creating the FRR Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [<span data-ttu-id="46820-113">创建用于将发送到 SWIFT FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="46820-113">Creating the FRR Send Port for Sending to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [<span data-ttu-id="46820-114">创建 FRR 发送端口将发送到自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="46820-114">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)