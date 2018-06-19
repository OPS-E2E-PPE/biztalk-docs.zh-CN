---
title: 如何构建业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79e91ec6ecfa061aa4621effba9a1f868cad5d96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248141"
---
# <a name="how-to-build-orchestrations"></a><span data-ttu-id="5c1f5-102">如何生成业务流程</span><span class="sxs-lookup"><span data-stu-id="5c1f5-102">How to Build Orchestrations</span></span>
<span data-ttu-id="5c1f5-103">完成业务流程绘图后，可将 BizTalk 项目生成到包含可执行业务流程的程序集中。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-103">After you have completed an orchestration drawing, you build your BizTalk project into an assembly that encapsulates an executable orchestration.</span></span>  
  
 <span data-ttu-id="5c1f5-104">在生成过程中，BizTalk 业务流程设计器将检查每个形状，以确定它是否完整并且正确，如果不完整或者不正确，则会在任务列表中报告错误。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-104">During the build process, BizTalk Orchestration Designer examines each shape to determine whether it is complete and correct, and reports an error in the task list if it is not.</span></span>  
  
 <span data-ttu-id="5c1f5-105">在 Visual Studio 中生成时有几种选择：</span><span class="sxs-lookup"><span data-stu-id="5c1f5-105">You have several options for building in Visual Studio:</span></span>  
  
-   <span data-ttu-id="5c1f5-106">可以生成业务流程所在的整个解决方案。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-106">You can build the entire solution in which your orchestration resides.</span></span>  
  
-   <span data-ttu-id="5c1f5-107">可以生成解决方案中的单个项目。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-107">You can build a single project within the solution.</span></span>  
  
-   <span data-ttu-id="5c1f5-108">生成项目或解决方案时可以跳过业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-108">You can skip the orchestration when building the project or solution.</span></span>  
  
 <span data-ttu-id="5c1f5-109">如果要生成其他组件（包括其他业务流程），但不想生成特定业务流程，则可以在业务流程的 .odx 文件的文件属性中指示您不想生成该业务流程，这样便会将其跳过。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-109">If you want to build other components, including other orchestrations, but do not want to build a particular orchestration, you can indicate in the file properties for the orchestration's .odx file that you do not want to build it, and it will be skipped.</span></span>  
  
### <a name="to-build-an-orchestration"></a><span data-ttu-id="5c1f5-110">生成业务流程</span><span class="sxs-lookup"><span data-stu-id="5c1f5-110">To build an orchestration</span></span>  
  
-   <span data-ttu-id="5c1f5-111">创建业务流程后，需要先生成包含该业务流程的 BizTalk 项目，然后才能测试或使用该业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-111">After creating your orchestration, you need to build the BizTalk project that contains it before you can test or use the orchestration.</span></span> <span data-ttu-id="5c1f5-112">可以生成整个解决方案，也可以生成解决方案中的单个项目。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-112">You can build the entire solution, or a single project within the solution.</span></span>  
  
### <a name="to-build-a-solution"></a><span data-ttu-id="5c1f5-113">若要生成解决方案</span><span class="sxs-lookup"><span data-stu-id="5c1f5-113">To build a solution</span></span>  
  
-   <span data-ttu-id="5c1f5-114">在解决方案资源管理器，右键单击该解决方案并选择**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-114">In Solution Explorer, right-click the solution and select **Build Solution**.</span></span>  
  
### <a name="to-build-a-project"></a><span data-ttu-id="5c1f5-115">生成项目</span><span class="sxs-lookup"><span data-stu-id="5c1f5-115">To build a project</span></span>  
  
-   <span data-ttu-id="5c1f5-116">右键单击某个项目并选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-116">Right-click a project and select **Build**.</span></span>  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a><span data-ttu-id="5c1f5-117">在不编译特定业务流程的情况下生成项目或解决方案</span><span class="sxs-lookup"><span data-stu-id="5c1f5-117">To build a project or solution without compiling a particular orchestration</span></span>  
  
-   <span data-ttu-id="5c1f5-118">单击.odx 文件对应，业务流程，然后在属性窗口中，单击**生成操作**属性并选择**无**。</span><span class="sxs-lookup"><span data-stu-id="5c1f5-118">Click the .odx file corresponding to the orchestration, and in the Properties window, click the **Build Action** property and select **None**.</span></span>