---
title: 调试业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging, Orchestration Debugger
- debugging, orchestrations
- Orchestration Debugger, about Orchestration Debugger
- Orchestrations Debugger
- orchestrations, debugging
- debugging, HAT
- HAT, debugging
ms.assetid: aae99cfd-d3dd-41c8-ae7a-b2733352cd69
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c231513ad75520fcadd88e5dd7d88104ddeeced5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238581"
---
# <a name="debugging-an-orchestration"></a><span data-ttu-id="73732-102">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="73732-102">Debugging an Orchestration</span></span>
<span data-ttu-id="73732-103">使用业务流程调试器可以按每个形状来跟踪单个业务流程实例的活动。</span><span class="sxs-lookup"><span data-stu-id="73732-103">The Orchestration Debugger enables you to track the activity of a single orchestration instance on a shape-by-shape basis.</span></span> <span data-ttu-id="73732-104">业务流程调试器显示在业务流程设计器中创建的业务流程的呈现视图。</span><span class="sxs-lookup"><span data-stu-id="73732-104">It displays a rendered view of the orchestration created in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="73732-105">您可以在 BizTalk Server 管理控制台中访问“组概述”页中的业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="73732-105">You access the Orchestration Debugger in the Group Overview Page in the BizTalk Server Administration Console.</span></span>  <span data-ttu-id="73732-106">此操作通过快捷菜单从跟踪查询的输出中完成，方法是右键单击与业务流程类型关联的任一服务或消息实例。</span><span class="sxs-lookup"><span data-stu-id="73732-106">This is done from the output of a tracking query through a shortcut menu by right-clicking any service or message instance associated with an orchestration type.</span></span> <span data-ttu-id="73732-107">进入此页后，您可以在业务流程调试器和“消息流”视图之间来回切换。</span><span class="sxs-lookup"><span data-stu-id="73732-107">Once you're in i this page, you can switch back and forth between the Orchestration Debugger and the Message Flow view.</span></span>  
  
 <span data-ttu-id="73732-108">业务流程调试器提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="73732-108">The Orchestration Debugger provides the following functionality:</span></span>  
  
-   <span data-ttu-id="73732-109">显示业务流程的呈现视图，可以在其中重新执行特定业务流程的每个处理步骤。</span><span class="sxs-lookup"><span data-stu-id="73732-109">Displays a rendered view of the orchestration in which you can replay each processing step for that particular orchestration.</span></span>  
  
-   <span data-ttu-id="73732-110">使用业务流程调试器可以在任何业务流程形状之前设置断点并继续执行。</span><span class="sxs-lookup"><span data-stu-id="73732-110">Enables you to set breakpoints before any orchestration shape and continue execution.</span></span>  
  
-   <span data-ttu-id="73732-111">使用业务流程调试器可以查看特定的变量和消息数据。</span><span class="sxs-lookup"><span data-stu-id="73732-111">Enables you to look at specific variables and message data.</span></span>  
  
-   <span data-ttu-id="73732-112">在业务流程调试器中打开特定业务流程实例时，将自动启用该实例的所有跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="73732-112">Automatically enables all of the tracking options for a particular orchestration instance when that instance opens in the Orchestration Debugger.</span></span>  
  
-   <span data-ttu-id="73732-113">使用业务流程调试器可以继续、恢复为调试、终止特定业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="73732-113">It gives you the ability to continue, resume in debug, and terminate the particular orchestration instance.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73732-114">取消部署程序集时，数据库将保留该程序集的跟踪选项和断点信息。</span><span class="sxs-lookup"><span data-stu-id="73732-114">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for the undeployed assembly.</span></span> <span data-ttu-id="73732-115">如果随后部署相同程序集，则将还原该程序集的选项和断点信息。</span><span class="sxs-lookup"><span data-stu-id="73732-115">If you subsequently deploy the same assembly, the options and breakpoint information for that assembly are restored.</span></span>  
  
 <span data-ttu-id="73732-116">使用业务流程调试器的两种模式包括：</span><span class="sxs-lookup"><span data-stu-id="73732-116">The two modes for using the Orchestration Debugger are:</span></span>  
  
-   [<span data-ttu-id="73732-117">报告在业务流程调试器中的模式</span><span class="sxs-lookup"><span data-stu-id="73732-117">Reporting Mode in Orchestration Debugger</span></span>](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [<span data-ttu-id="73732-118">在调试器中业务流程交互模式</span><span class="sxs-lookup"><span data-stu-id="73732-118">Interactive Mode in Orchestration Debugger</span></span>](../core/interactive-mode-in-orchestration-debugger.md)  
  
 <span data-ttu-id="73732-119">取决于服务的状态，功能各不相同。</span><span class="sxs-lookup"><span data-stu-id="73732-119">The capabilities differ depending on the state of the service.</span></span> <span data-ttu-id="73732-120">通过调用当前处于“在断点处”状态的任意服务实例，可以从任意视图执行交互调试。</span><span class="sxs-lookup"><span data-stu-id="73732-120">You can perform interactive debugging by invoking any service instance currently in the In Breakpoint state, from any view.</span></span> <span data-ttu-id="73732-121">有关调试业务流程的信息，请参阅[如何调用业务流程调试器和消息流视图](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md)。</span><span class="sxs-lookup"><span data-stu-id="73732-121">For information about debugging an orchestration, see [How to Invoke the Orchestration Debugger and the Message Flow Views](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73732-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="73732-122">In This Section</span></span>  
  
-   [<span data-ttu-id="73732-123">业务流程调试器用户界面</span><span class="sxs-lookup"><span data-stu-id="73732-123">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)  
  
-   [<span data-ttu-id="73732-124">使用业务流程调试器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="73732-124">Considerations when Using Orchestration Debugger</span></span>](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [<span data-ttu-id="73732-125">使用业务流程调试器视图</span><span class="sxs-lookup"><span data-stu-id="73732-125">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)