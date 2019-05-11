---
title: 端到端 Tutorial2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, about the tutorial
- tutorial
- tutorial, workflow
ms.assetid: 1aba93b9-6991-46ef-a3bc-3815a5ff473f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9eaa3a70c6ee734d409d8235a99d203879dcd7ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377946"
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="c95c5-102">端到端教程</span><span class="sxs-lookup"><span data-stu-id="c95c5-102">End-to-End Tutorial</span></span>
<span data-ttu-id="c95c5-103">本教程包含详细的步骤说明了如何创建并设置 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="c95c5-103">This tutorial contains detailed steps that describe how to create and set up a Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solution.</span></span> <span data-ttu-id="c95c5-104">模块和课程使用 Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]创建架构，将业务流程和管道组件使用 A4SWIFT 映射。</span><span class="sxs-lookup"><span data-stu-id="c95c5-104">The modules and lessons use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create the schema, maps orchestrations, and pipeline components using A4SWIFT.</span></span>  
  
 <span data-ttu-id="c95c5-105">下图显示了一个端到端 A4SWIFT 解决方案的常见集成引擎使用方案的工作流。</span><span class="sxs-lookup"><span data-stu-id="c95c5-105">The following figure shows the workflow of a common Integration Engine usage scenario for an end-to-end A4SWIFT solution.</span></span>  
  
 <span data-ttu-id="c95c5-106">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")</span><span class="sxs-lookup"><span data-stu-id="c95c5-106">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")</span></span>  
  
|<span data-ttu-id="c95c5-107">A4SWIFT 教程工作流项</span><span class="sxs-lookup"><span data-stu-id="c95c5-107">A4SWIFT Tutorial Workflow Key</span></span>|  
|-----------------------------------|  
|<span data-ttu-id="c95c5-108">**ASM** = SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="c95c5-108">**ASM** = SWIFT Assembler</span></span>|  
|<span data-ttu-id="c95c5-109">**DASM** = SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="c95c5-109">**DASM** = SWIFT Disassembler</span></span>|  
|<span data-ttu-id="c95c5-110">**MTxxx** = A4SWIFT 消息类型</span><span class="sxs-lookup"><span data-stu-id="c95c5-110">**MTxxx** = A4SWIFT Message type</span></span>|  
|<span data-ttu-id="c95c5-111">**SIPN** = SWIFT 的安全 IP 网络</span><span class="sxs-lookup"><span data-stu-id="c95c5-111">**SIPN** = SWIFT Secure IP Network</span></span>|  
  
 <span data-ttu-id="c95c5-112">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="c95c5-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="c95c5-113">模块 1：创建 SWIFT 解决方案</span><span class="sxs-lookup"><span data-stu-id="c95c5-113">Module 1: Creating a SWIFT Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/module-1-creating-a-swift-solution.md)  
  
-   [<span data-ttu-id="c95c5-114">模块 2：添加新架构项目</span><span class="sxs-lookup"><span data-stu-id="c95c5-114">Module 2: Adding a New Schemas Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)  
  
-   [<span data-ttu-id="c95c5-115">模块 3：添加管道项目</span><span class="sxs-lookup"><span data-stu-id="c95c5-115">Module 3: Adding a Pipeline Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)  
  
-   [<span data-ttu-id="c95c5-116">模块 4：添加 XML 接收位置和平面文件发送端口</span><span class="sxs-lookup"><span data-stu-id="c95c5-116">Module 4: Adding an XML Receive Location and Flat File Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)  
  
-   [<span data-ttu-id="c95c5-117">模块 5：添加平面文件接收位置和 XML 发送端口</span><span class="sxs-lookup"><span data-stu-id="c95c5-117">Module 5: Adding a Flat File Receive Location and XML Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)  
  
-   [<span data-ttu-id="c95c5-118">模块 6：部署业务规则</span><span class="sxs-lookup"><span data-stu-id="c95c5-118">Module 6: Deploying the Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)  
  
-   [<span data-ttu-id="c95c5-119">模块 7：测试有效的平面文件实例</span><span class="sxs-lookup"><span data-stu-id="c95c5-119">Module 7: Testing a Valid Flat File Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)