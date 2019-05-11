---
title: 如何生成业务流程 |Microsoft Docs
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
ms.openlocfilehash: f755ea3b2aa01919d7f5d40a9eca92fd3529c629
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387076"
---
# <a name="how-to-build-orchestrations"></a><span data-ttu-id="cd28f-102">如何生成业务流程</span><span class="sxs-lookup"><span data-stu-id="cd28f-102">How to Build Orchestrations</span></span>
<span data-ttu-id="cd28f-103">完成业务流程绘图后，封装可执行业务流程的程序集生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="cd28f-103">After you have completed an orchestration drawing, you build your BizTalk project into an assembly that encapsulates an executable orchestration.</span></span>  
  
 <span data-ttu-id="cd28f-104">在生成过程中，BizTalk 业务流程设计器将检查以确定它是否是完整且正确，并报告错误的任务列表中，如果不是每个形状。</span><span class="sxs-lookup"><span data-stu-id="cd28f-104">During the build process, BizTalk Orchestration Designer examines each shape to determine whether it is complete and correct, and reports an error in the task list if it is not.</span></span>  
  
 <span data-ttu-id="cd28f-105">必须在 Visual Studio 中生成的几个选项：</span><span class="sxs-lookup"><span data-stu-id="cd28f-105">You have several options for building in Visual Studio:</span></span>  
  
- <span data-ttu-id="cd28f-106">您可以构建您的业务流程所在的整个解决方案。</span><span class="sxs-lookup"><span data-stu-id="cd28f-106">You can build the entire solution in which your orchestration resides.</span></span>  
  
- <span data-ttu-id="cd28f-107">可以生成解决方案中的单个项目。</span><span class="sxs-lookup"><span data-stu-id="cd28f-107">You can build a single project within the solution.</span></span>  
  
- <span data-ttu-id="cd28f-108">生成项目或解决方案时，可以跳过该业务流程。</span><span class="sxs-lookup"><span data-stu-id="cd28f-108">You can skip the orchestration when building the project or solution.</span></span>  
  
  <span data-ttu-id="cd28f-109">如果想要生成其他组件，包括其他业务流程，但不是想生成特定的业务流程，你可以指示在业务流程的.odx 文件，您不想要生成它，并将跳过的文件属性。</span><span class="sxs-lookup"><span data-stu-id="cd28f-109">If you want to build other components, including other orchestrations, but do not want to build a particular orchestration, you can indicate in the file properties for the orchestration's .odx file that you do not want to build it, and it will be skipped.</span></span>  
  
### <a name="to-build-an-orchestration"></a><span data-ttu-id="cd28f-110">若要生成业务流程</span><span class="sxs-lookup"><span data-stu-id="cd28f-110">To build an orchestration</span></span>  
  
-   <span data-ttu-id="cd28f-111">在创建后您的业务流程，需要生成包含它，然后才能测试或使用该业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="cd28f-111">After creating your orchestration, you need to build the BizTalk project that contains it before you can test or use the orchestration.</span></span> <span data-ttu-id="cd28f-112">您可以构建整个解决方案中的单个项目。</span><span class="sxs-lookup"><span data-stu-id="cd28f-112">You can build the entire solution, or a single project within the solution.</span></span>  
  
### <a name="to-build-a-solution"></a><span data-ttu-id="cd28f-113">若要生成的解决方案</span><span class="sxs-lookup"><span data-stu-id="cd28f-113">To build a solution</span></span>  
  
-   <span data-ttu-id="cd28f-114">在解决方案资源管理器，右键单击解决方案并选择**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="cd28f-114">In Solution Explorer, right-click the solution and select **Build Solution**.</span></span>  
  
### <a name="to-build-a-project"></a><span data-ttu-id="cd28f-115">若要生成项目</span><span class="sxs-lookup"><span data-stu-id="cd28f-115">To build a project</span></span>  
  
-   <span data-ttu-id="cd28f-116">右键单击项目并选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="cd28f-116">Right-click a project and select **Build**.</span></span>  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a><span data-ttu-id="cd28f-117">若要生成项目或解决方案而无需编译特定业务流程</span><span class="sxs-lookup"><span data-stu-id="cd28f-117">To build a project or solution without compiling a particular orchestration</span></span>  
  
-   <span data-ttu-id="cd28f-118">单击.odx 文件对应，向业务流程，并在属性窗口中，单击**生成操作**属性，然后选择**None**。</span><span class="sxs-lookup"><span data-stu-id="cd28f-118">Click the .odx file corresponding to the orchestration, and in the Properties window, click the **Build Action** property and select **None**.</span></span>