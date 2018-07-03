---
title: 模块 3： 添加管道项目 |Microsoft Docs
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
ms.openlocfilehash: 85305614cec2757a91aa006238b3eb1ca4fbdbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970654"
---
# <a name="module-3-adding-a-pipeline-project"></a><span data-ttu-id="d7a87-102">模块 3： 添加管道项目</span><span class="sxs-lookup"><span data-stu-id="d7a87-102">Module 3: Adding a Pipeline Project</span></span>
<span data-ttu-id="d7a87-103">在此模块中，将新项目添加到你的解决方案，其中包含自定义发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="d7a87-103">In this module, you add a new project to your solution that contains your custom send and receive pipelines.</span></span> <span data-ttu-id="d7a87-104">由于你正在使用的平面文件在本质上 SWIFT 消息不能使用随 Microsoft 默认管道[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7a87-104">Because you are working with SWIFT messages, which are flat file in nature, you cannot use the default pipelines that are included with Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="d7a87-105">SWIFT 消息需要附加的验证级别，因此 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括自定义拆装器 (DASM) 和用于 SWIFT 消息组装器 (ASM) 组件。</span><span class="sxs-lookup"><span data-stu-id="d7a87-105">SWIFT messages require additional levels of validation so Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes custom disassembler (DASM) and assembler (ASM) components for use with SWIFT messages.</span></span>  
  
 <span data-ttu-id="d7a87-106">在此模块中，您还添加新的管道项目中，添加接收和发送管道，并使用 SWIFT DASM 和 ASM。</span><span class="sxs-lookup"><span data-stu-id="d7a87-106">In this module, you also add a new pipeline project, add receive and send pipelines, and use the SWIFT DASM and ASM.</span></span>  
  
 <span data-ttu-id="d7a87-107">选择 BizTalk 项目模板会公开 BizTalk 工具，如 BizTalk 映射器中，在 Microsoft 内部[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]开发环境。</span><span class="sxs-lookup"><span data-stu-id="d7a87-107">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
 <span data-ttu-id="d7a87-108">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="d7a87-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="d7a87-109">第 1 课：将管道项目添加到解决方案</span><span class="sxs-lookup"><span data-stu-id="d7a87-109">Lesson 1: Adding a Pipelines Project to the Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-adding-a-pipelines-project-to-the-solution.md)  
  
-   [<span data-ttu-id="d7a87-110">第 2 课：添加项目引用</span><span class="sxs-lookup"><span data-stu-id="d7a87-110">Lesson 2: Adding Project References</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)  
  
-   [<span data-ttu-id="d7a87-111">第 3 课：添加自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="d7a87-111">Lesson 3: Adding a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="d7a87-112">第 4 课：将 SWIFT 汇编程序和反汇编程序添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="d7a87-112">Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)  
  
-   [<span data-ttu-id="d7a87-113">第 5 课：将 SWIFT 反汇编程序添加到自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="d7a87-113">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="d7a87-114">第 6 课：创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="d7a87-114">Lesson 6: Creating a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="d7a87-115">第 7 课：将 SWIFT 汇编程序添加到自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="d7a87-115">Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="d7a87-116">第 8 课：生成和部署程序集</span><span class="sxs-lookup"><span data-stu-id="d7a87-116">Lesson 8: Building and Deploying the Assembly</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-8-building-and-deploying-the-assembly.md)