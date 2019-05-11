---
title: 使用断点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, suspended orchestrations
- Orchestration Debugger, Message Flow view
- Orchestration Debugger, service options
- Message Flow view [Orchestration Debugger]
ms.assetid: aad1a2b0-d705-49cd-85f7-b0ab2e473bcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d1129e2eaa6c31a90e89e99f377f825990ee614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398544"
---
# <a name="working-with-breakpoints"></a><span data-ttu-id="6c23f-102">使用断点</span><span class="sxs-lookup"><span data-stu-id="6c23f-102">Working with Breakpoints</span></span>
<span data-ttu-id="6c23f-103">通过将附加到挂起的业务流程，或通过在类上设置断点，可以设置断点。</span><span class="sxs-lookup"><span data-stu-id="6c23f-103">You can set breakpoints by attaching to a suspended orchestration, or by setting a breakpoint on a class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c23f-104">如果取消部署程序集，数据库将保留的跟踪选项和断点信息，该程序集。</span><span class="sxs-lookup"><span data-stu-id="6c23f-104">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for that assembly.</span></span> <span data-ttu-id="6c23f-105">如果随后部署再次在同一程序集中，将还原的选项和断点信息，该程序集。</span><span class="sxs-lookup"><span data-stu-id="6c23f-105">If you subsequently deploy the same assembly again, the options and breakpoint information for that assembly are restored.</span></span>  
  
### <a name="to-attach-to-a-suspended-orchestration"></a><span data-ttu-id="6c23f-106">若要将附加到挂起的业务流程</span><span class="sxs-lookup"><span data-stu-id="6c23f-106">To attach to a suspended orchestration</span></span>  
  
1.  <span data-ttu-id="6c23f-107">选择使用挂起形状，自动挂起的业务流程，然后转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="6c23f-107">Select an automatically suspended orchestration using a suspend shape, and then go to Step 3.</span></span>  
  
2.  <span data-ttu-id="6c23f-108">刷新视图以检查实例现在显示处于 Suspended 状态。</span><span class="sxs-lookup"><span data-stu-id="6c23f-108">Refresh the view to check that the instance now appears in a Suspended state.</span></span>  
  
3.  <span data-ttu-id="6c23f-109">单击**恢复为调试**。</span><span class="sxs-lookup"><span data-stu-id="6c23f-109">Click **Resume in Debug**.</span></span>  
  
     <span data-ttu-id="6c23f-110">业务流程将在断点处状态恢复。</span><span class="sxs-lookup"><span data-stu-id="6c23f-110">The orchestration resumes in an In Breakpoint state.</span></span> <span data-ttu-id="6c23f-111">你现在可以以交互方式调试。</span><span class="sxs-lookup"><span data-stu-id="6c23f-111">You can now debug interactively.</span></span>  
  
### <a name="to-switch-to-the-message-flow-view"></a><span data-ttu-id="6c23f-112">若要切换到消息流视图</span><span class="sxs-lookup"><span data-stu-id="6c23f-112">To switch to the Message Flow view</span></span>  
  
-   <span data-ttu-id="6c23f-113">右键单击结果列表中的单元格并选择**消息流**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="6c23f-113">Right-click a cell in the Results list and select **Message Flow** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c23f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c23f-114">See Also</span></span>  
 [<span data-ttu-id="6c23f-115">使用“业务流程调试器”视图</span><span class="sxs-lookup"><span data-stu-id="6c23f-115">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)