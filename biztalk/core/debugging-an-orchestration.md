---
title: 调试业务流程 |Microsoft Docs
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
ms.openlocfilehash: 7b0e1ad8529e3f91f5b34ad60585677892989368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390441"
---
# <a name="debugging-an-orchestration"></a><span data-ttu-id="4a853-102">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="4a853-102">Debugging an Orchestration</span></span>
<span data-ttu-id="4a853-103">业务流程调试器，您可以在形状的形状的基础上跟踪单个业务流程实例的活动。</span><span class="sxs-lookup"><span data-stu-id="4a853-103">The Orchestration Debugger enables you to track the activity of a single orchestration instance on a shape-by-shape basis.</span></span> <span data-ttu-id="4a853-104">它将显示在业务流程设计器中创建的业务流程的呈现的视图。</span><span class="sxs-lookup"><span data-stu-id="4a853-104">It displays a rendered view of the orchestration created in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="4a853-105">访问 BizTalk Server 管理控制台中组概述页中的业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="4a853-105">You access the Orchestration Debugger in the Group Overview Page in the BizTalk Server Administration Console.</span></span>  <span data-ttu-id="4a853-106">这是通过快捷菜单的跟踪查询输出中，请右键单击任一服务或业务流程类型与实例相关联的消息。</span><span class="sxs-lookup"><span data-stu-id="4a853-106">This is done from the output of a tracking query through a shortcut menu by right-clicking any service or message instance associated with an orchestration type.</span></span> <span data-ttu-id="4a853-107">您可以在我此页上，您可以来回切换之间业务流程调试器和消息流视图。</span><span class="sxs-lookup"><span data-stu-id="4a853-107">Once you're in i this page, you can switch back and forth between the Orchestration Debugger and the Message Flow view.</span></span>  
  
 <span data-ttu-id="4a853-108">业务流程调试器提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="4a853-108">The Orchestration Debugger provides the following functionality:</span></span>  
  
- <span data-ttu-id="4a853-109">显示可以在其中重播特定业务流程的每个处理步骤的业务流程的呈现的视图。</span><span class="sxs-lookup"><span data-stu-id="4a853-109">Displays a rendered view of the orchestration in which you can replay each processing step for that particular orchestration.</span></span>  
  
- <span data-ttu-id="4a853-110">可以是任何业务流程形状之前设置断点并继续执行。</span><span class="sxs-lookup"><span data-stu-id="4a853-110">Enables you to set breakpoints before any orchestration shape and continue execution.</span></span>  
  
- <span data-ttu-id="4a853-111">使您能够查看特定的变量和消息数据。</span><span class="sxs-lookup"><span data-stu-id="4a853-111">Enables you to look at specific variables and message data.</span></span>  
  
- <span data-ttu-id="4a853-112">自动启用的所有特定业务流程实例的跟踪选项时该实例将在业务流程调试器中打开。</span><span class="sxs-lookup"><span data-stu-id="4a853-112">Automatically enables all of the tracking options for a particular orchestration instance when that instance opens in the Orchestration Debugger.</span></span>  
  
- <span data-ttu-id="4a853-113">这样，可以继续，请恢复为调试，然后终止特定业务流程实例的功能。</span><span class="sxs-lookup"><span data-stu-id="4a853-113">It gives you the ability to continue, resume in debug, and terminate the particular orchestration instance.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4a853-114">如果取消部署程序集，数据库将保留的跟踪选项和取消部署程序集的断点信息。</span><span class="sxs-lookup"><span data-stu-id="4a853-114">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for the undeployed assembly.</span></span> <span data-ttu-id="4a853-115">如果随后部署相同程序集，将还原的选项和断点信息，该程序集。</span><span class="sxs-lookup"><span data-stu-id="4a853-115">If you subsequently deploy the same assembly, the options and breakpoint information for that assembly are restored.</span></span>  
  
  <span data-ttu-id="4a853-116">使用业务流程调试器的两种模式是：</span><span class="sxs-lookup"><span data-stu-id="4a853-116">The two modes for using the Orchestration Debugger are:</span></span>  
  
- [<span data-ttu-id="4a853-117">业务流程调试器中的“报告”模式</span><span class="sxs-lookup"><span data-stu-id="4a853-117">Reporting Mode in Orchestration Debugger</span></span>](../core/reporting-mode-in-orchestration-debugger.md)  
  
- [<span data-ttu-id="4a853-118">业务流程调试器中的“交互”模式</span><span class="sxs-lookup"><span data-stu-id="4a853-118">Interactive Mode in Orchestration Debugger</span></span>](../core/interactive-mode-in-orchestration-debugger.md)  
  
  <span data-ttu-id="4a853-119">功能不同，具体取决于服务的状态。</span><span class="sxs-lookup"><span data-stu-id="4a853-119">The capabilities differ depending on the state of the service.</span></span> <span data-ttu-id="4a853-120">您可以执行交互式调试通过调用当前在在断点处状态，从任意视图中的任何服务实例。</span><span class="sxs-lookup"><span data-stu-id="4a853-120">You can perform interactive debugging by invoking any service instance currently in the In Breakpoint state, from any view.</span></span> <span data-ttu-id="4a853-121">有关调试业务流程的信息，请参阅[如何调用业务流程调试器和消息流视图](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md)。</span><span class="sxs-lookup"><span data-stu-id="4a853-121">For information about debugging an orchestration, see [How to Invoke the Orchestration Debugger and the Message Flow Views](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a853-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="4a853-122">In This Section</span></span>  
  
-   [<span data-ttu-id="4a853-123">业务流程调试器用户界面</span><span class="sxs-lookup"><span data-stu-id="4a853-123">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)  
  
-   [<span data-ttu-id="4a853-124">使用业务流程调试器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="4a853-124">Considerations when Using Orchestration Debugger</span></span>](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [<span data-ttu-id="4a853-125">使用“业务流程调试器”视图</span><span class="sxs-lookup"><span data-stu-id="4a853-125">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)