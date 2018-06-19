---
title: 模块 3： 添加的管道项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, creating pipelines
- projects, pipelines
- pipelines, adding to projects
ms.assetid: 38bf1629-df29-4bea-840b-60b354b06430
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d14e0f334514fd35a7f8de963f7fb457e3fbbd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208157"
---
# <a name="module-3-adding-a-pipeline-project"></a><span data-ttu-id="914cf-102">模块 3： 添加的管道项目</span><span class="sxs-lookup"><span data-stu-id="914cf-102">Module 3: Adding a Pipeline Project</span></span>
<span data-ttu-id="914cf-103">在此模块中，你将新项目添加到你的解决方案，其中包含自定义发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="914cf-103">In this module, you add a new project to your solution that contains your custom send and receive pipelines.</span></span> <span data-ttu-id="914cf-104">因为你正在使用 SWIFT，这些消息是在性质的平面文件，不能使用附带的默认管道[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="914cf-104">Because you are working with SWIFT messages, which are flat file in nature, you cannot use the default pipelines that are included with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="914cf-105">SWIFT 消息需要更高级别的验证因此[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括自定义反汇编程序 (DASM) 和用于 SWIFT 消息汇编程序 (ASM) 组件。</span><span class="sxs-lookup"><span data-stu-id="914cf-105">SWIFT messages require additional levels of validation so [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes custom disassembler (DASM) and assembler (ASM) components for use with SWIFT messages.</span></span>  
  
 <span data-ttu-id="914cf-106">在此模块，您还添加一条新管道项目中，添加接收和发送管道，并使用 SWIFT DASM 和 ASM。</span><span class="sxs-lookup"><span data-stu-id="914cf-106">In this module, you also add a new pipeline project, add receive and send pipelines, and use the SWIFT DASM and ASM.</span></span>  
  
 <span data-ttu-id="914cf-107">选择 BizTalk 项目模板中公开的 BizTalk 工具，如 BizTalk 映射程序[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]开发环境。</span><span class="sxs-lookup"><span data-stu-id="914cf-107">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
 <span data-ttu-id="914cf-108">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="914cf-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="914cf-109">第 1 课： 将管道项目添加到解决方案</span><span class="sxs-lookup"><span data-stu-id="914cf-109">Lesson 1: Adding a Pipelines Project to the Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-adding-a-pipelines-project-to-the-solution.md)  
  
-   [<span data-ttu-id="914cf-110">第 2 课： 添加项目引用</span><span class="sxs-lookup"><span data-stu-id="914cf-110">Lesson 2: Adding Project References</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)  
  
-   [<span data-ttu-id="914cf-111">第 3 课： 添加自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="914cf-111">Lesson 3: Adding a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="914cf-112">第 4 课： 向工具箱添加 SWIFT 汇编程序和反汇编程序</span><span class="sxs-lookup"><span data-stu-id="914cf-112">Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)  
  
-   [<span data-ttu-id="914cf-113">第 5 课： 添加自定义接收管道的 SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="914cf-113">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="914cf-114">第 6 课： 创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="914cf-114">Lesson 6: Creating a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="914cf-115">第 7 课： 添加自定义发送管道 SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="914cf-115">Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="914cf-116">第 8 课： 构建和部署程序集</span><span class="sxs-lookup"><span data-stu-id="914cf-116">Lesson 8: Building and Deploying the Assembly</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-8-building-and-deploying-the-assembly.md)