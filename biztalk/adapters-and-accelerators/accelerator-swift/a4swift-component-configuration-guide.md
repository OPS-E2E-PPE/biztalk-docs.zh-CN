---
title: "A4SWIFT 组件配置指南 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: A4SWIFT, configuration guide
ms.assetid: ff4a3ee7-2fd9-44e7-8aa3-c3d214a6ce68
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 396e28d49b3e6a43e188e8358a045c3c91a627cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a4swift-component-configuration-guide"></a><span data-ttu-id="8ae26-102">A4SWIFT 组件配置指南</span><span class="sxs-lookup"><span data-stu-id="8ae26-102">A4SWIFT Component Configuration Guide</span></span>
<span data-ttu-id="8ae26-103">本指南提供有关配置信息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8ae26-103">This guide provides information about configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="8ae26-104">在安装 A4SWIFT 和完成 A4SWIFT 配置向导 （如安装指南中所述） 后，请执行此配置指南中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8ae26-104">Perform the steps in this configuration guide after you have installed A4SWIFT and completed the A4SWIFT Configuration Wizard (as described in the Installation Guide).</span></span> <span data-ttu-id="8ae26-105">此配置指南包括以下说明：</span><span class="sxs-lookup"><span data-stu-id="8ae26-105">This configuration guide includes the following instructions:</span></span>  
  
-   <span data-ttu-id="8ae26-106">配置消息传递方案的 A4SWIFT 运行时的安装后步骤。</span><span class="sxs-lookup"><span data-stu-id="8ae26-106">Post-installation steps for configuring the A4SWIFT runtime for messaging scenarios.</span></span>  
  
-   <span data-ttu-id="8ae26-107">如何配置消息修复和新的提交。</span><span class="sxs-lookup"><span data-stu-id="8ae26-107">How to configure Message Repair and New Submission.</span></span> <span data-ttu-id="8ae26-108">若要执行此操作，你必须首先手动配置 A4SWIFT 运行时。</span><span class="sxs-lookup"><span data-stu-id="8ae26-108">To do so, you must first manually configure the A4SWIFT runtime.</span></span> <span data-ttu-id="8ae26-109">这不需要配置 FIN 响应对帐。</span><span class="sxs-lookup"><span data-stu-id="8ae26-109">This does not require that you configure FIN Response Reconciliation.</span></span>  
  
-   <span data-ttu-id="8ae26-110">如何配置 FIN 响应对帐。</span><span class="sxs-lookup"><span data-stu-id="8ae26-110">How to configure FIN Response Reconciliation.</span></span> <span data-ttu-id="8ae26-111">若要执行此操作，你必须首先手动配置 A4SWIFT 运行时。</span><span class="sxs-lookup"><span data-stu-id="8ae26-111">To do so, you must first manually configure the A4SWIFT runtime.</span></span> <span data-ttu-id="8ae26-112">这不需要配置消息修复和新的提交。</span><span class="sxs-lookup"><span data-stu-id="8ae26-112">This does not require that you configure Message Repair and New Submission.</span></span>  
  
 <span data-ttu-id="8ae26-113">下图显示你将配置的 A4SWIFT 组件。</span><span class="sxs-lookup"><span data-stu-id="8ae26-113">The following figure shows the A4SWIFT components that you will configure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-component-configuration.gif "A4SWIFT_Component_Configuration")  
  
 <span data-ttu-id="8ae26-114">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="8ae26-114">This section contains:</span></span>  
  
-   [<span data-ttu-id="8ae26-115">配置 A4SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="8ae26-115">Configuring the A4SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)  
  
-   [<span data-ttu-id="8ae26-116">配置消息修复和新的提交</span><span class="sxs-lookup"><span data-stu-id="8ae26-116">Configuring Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="8ae26-117">配置 FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="8ae26-117">Configuring FIN Response Reconciliation</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)