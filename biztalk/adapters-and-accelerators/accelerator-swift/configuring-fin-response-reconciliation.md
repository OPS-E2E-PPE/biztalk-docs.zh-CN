---
title: 配置 FIN 响应对帐 |Microsoft Docs
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
ms.openlocfilehash: 6fa404335d4136c2c51f990d8c81b753bfcc020c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527527"
---
# <a name="configuring-fin-response-reconciliation"></a><span data-ttu-id="c95cc-102">配置 FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="c95cc-102">Configuring FIN Response Reconciliation</span></span>
<span data-ttu-id="c95cc-103">必须执行以下各节中，若要配置 Microsoft 中的步骤[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]FIN 响应对帐 (FRR) 功能，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="c95cc-103">You must perform the steps in the following sections to configure the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN Response Reconciliation (FRR) feature, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="c95cc-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")</span><span class="sxs-lookup"><span data-stu-id="c95cc-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")</span></span>  
  
 <span data-ttu-id="c95cc-105">在 A4SWIFT 安装向导中，您可以选择安装消息修复和新提交以及 FRR，或消息修复和新提交，而无需 FRR 或如果没有消息修复和新提交的 FRR。</span><span class="sxs-lookup"><span data-stu-id="c95cc-105">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FRR, or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="c95cc-106">因此，在本部分中的说明进行操作不要假定您在安装和配置消息修复和新提交。</span><span class="sxs-lookup"><span data-stu-id="c95cc-106">As a result, the instructions in this section do not assume that you are installing and configuring Message Repair and New Submission.</span></span> <span data-ttu-id="c95cc-107">它们执行操作，但是，假设已执行中的步骤[配置 A4SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="c95cc-107">They do, however, assume that you have performed the steps in the [Configuring the A4SWIFT Runtime](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span></span>  
  
 <span data-ttu-id="c95cc-108">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="c95cc-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="c95cc-109">绑定和启动 FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="c95cc-109">Binding and Starting the FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [<span data-ttu-id="c95cc-110">创建 FRR 接收管道</span><span class="sxs-lookup"><span data-stu-id="c95cc-110">Creating the FRR Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [<span data-ttu-id="c95cc-111">创建从后端应用程序接收的 FRR 接收位置</span><span class="sxs-lookup"><span data-stu-id="c95cc-111">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="c95cc-112">创建从 SWIFT 接收的 FRR 接收位置</span><span class="sxs-lookup"><span data-stu-id="c95cc-112">Creating the FRR Receive Location for Receiving from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [<span data-ttu-id="c95cc-113">创建 FRR 发送管道</span><span class="sxs-lookup"><span data-stu-id="c95cc-113">Creating the FRR Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [<span data-ttu-id="c95cc-114">创建发送到 SWIFT 的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="c95cc-114">Creating the FRR Send Port for Sending to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [<span data-ttu-id="c95cc-115">创建发送到自定义图柄的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="c95cc-115">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)