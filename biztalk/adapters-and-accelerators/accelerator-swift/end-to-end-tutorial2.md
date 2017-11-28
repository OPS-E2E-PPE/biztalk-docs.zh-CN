---
title: "端到端 Tutorial2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorial, about the tutorial
- tutorial
- tutorial, workflow
ms.assetid: 1aba93b9-6991-46ef-a3bc-3815a5ff473f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4022595ed05cb779d11e09d66080024ac76654
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="574e6-102">端到端教程</span><span class="sxs-lookup"><span data-stu-id="574e6-102">End-to-End Tutorial</span></span>
<span data-ttu-id="574e6-103">本教程包含描述如何创建和设置的详细的步骤[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="574e6-103">This tutorial contains detailed steps that describe how to create and set up a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solution.</span></span> <span data-ttu-id="574e6-104">模块和课程使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]创建架构，业务流程和管道组件使用 A4SWIFT 映射。</span><span class="sxs-lookup"><span data-stu-id="574e6-104">The modules and lessons use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create the schema, maps orchestrations, and pipeline components using A4SWIFT.</span></span>  
  
 <span data-ttu-id="574e6-105">下图显示的工作流的端到端 A4SWIFT 解决方案的常见集成引擎使用方案。</span><span class="sxs-lookup"><span data-stu-id="574e6-105">The following figure shows the workflow of a common Integration Engine usage scenario for an end-to-end A4SWIFT solution.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")  
  
|<span data-ttu-id="574e6-106">A4SWIFT 教程工作流密钥</span><span class="sxs-lookup"><span data-stu-id="574e6-106">A4SWIFT Tutorial Workflow Key</span></span>|  
|-----------------------------------|  
|<span data-ttu-id="574e6-107">**ASM** = SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="574e6-107">**ASM** = SWIFT Assembler</span></span>|  
|<span data-ttu-id="574e6-108">**DASM** = SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="574e6-108">**DASM** = SWIFT Disassembler</span></span>|  
|<span data-ttu-id="574e6-109">**MTxxx** = A4SWIFT 消息类型</span><span class="sxs-lookup"><span data-stu-id="574e6-109">**MTxxx** = A4SWIFT Message type</span></span>|  
|<span data-ttu-id="574e6-110">**SIPN** = SWIFT 安全 IP 网络</span><span class="sxs-lookup"><span data-stu-id="574e6-110">**SIPN** = SWIFT Secure IP Network</span></span>|  
  
 <span data-ttu-id="574e6-111">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="574e6-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="574e6-112">模块 1： 创建 SWIFT 解决方案</span><span class="sxs-lookup"><span data-stu-id="574e6-112">Module 1: Creating a SWIFT Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/module-1-creating-a-swift-solution.md)  
  
-   [<span data-ttu-id="574e6-113">模块 2： 添加新的架构项目</span><span class="sxs-lookup"><span data-stu-id="574e6-113">Module 2: Adding a New Schemas Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)  
  
-   [<span data-ttu-id="574e6-114">模块 3： 添加的管道项目</span><span class="sxs-lookup"><span data-stu-id="574e6-114">Module 3: Adding a Pipeline Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)  
  
-   [<span data-ttu-id="574e6-115">模块 4： 添加 XML 接收位置和平面文件发送端口</span><span class="sxs-lookup"><span data-stu-id="574e6-115">Module 4: Adding an XML Receive Location and Flat File Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)  
  
-   [<span data-ttu-id="574e6-116">模块 5： 添加平面文件接收位置和 XML 发送端口</span><span class="sxs-lookup"><span data-stu-id="574e6-116">Module 5: Adding a Flat File Receive Location and XML Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)  
  
-   [<span data-ttu-id="574e6-117">模块 6： 部署业务规则</span><span class="sxs-lookup"><span data-stu-id="574e6-117">Module 6: Deploying the Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)  
  
-   [<span data-ttu-id="574e6-118">模块 7： 测试的有效的平面文件实例</span><span class="sxs-lookup"><span data-stu-id="574e6-118">Module 7: Testing a Valid Flat File Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)