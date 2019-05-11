---
title: 报告业务流程调试器中的模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, Reporting mode
- Reporting mode [Orchestration Debugger]
ms.assetid: 014a444c-2867-4156-b009-8518e8250d4d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 436457dd8addc1add819a657e61113eaa8a2ec91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397871"
---
# <a name="reporting-mode-in-orchestration-debugger"></a><span data-ttu-id="de939-102">业务流程调试器中的报告模式</span><span class="sxs-lookup"><span data-stu-id="de939-102">Reporting Mode in Orchestration Debugger</span></span>
<span data-ttu-id="de939-103">报告模式使用跟踪的事件来显示已发生了什么情况。</span><span class="sxs-lookup"><span data-stu-id="de939-103">Reporting mode uses tracked events to show what has happened.</span></span> <span data-ttu-id="de939-104">它使用跟踪使用的数据**业务流程事件**选项标志。</span><span class="sxs-lookup"><span data-stu-id="de939-104">It uses data tracked using the **Orchestration Events** option flag.</span></span> <span data-ttu-id="de939-105">在业务流程实例的执行之前，必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="de939-105">This flag must be set prior to the execution of the orchestration instance.</span></span> <span data-ttu-id="de939-106">若要启用的特定业务流程事件跟踪功能，请参阅[如何为业务流程配置跟踪](../core/how-to-configure-tracking-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="de939-106">To enable event tracking for a particular orchestration, see [How to Configure Tracking for an Orchestration](../core/how-to-configure-tracking-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="de939-107">**业务流程事件**选项跟踪业务流程中每个形状的执行，因为它发生。</span><span class="sxs-lookup"><span data-stu-id="de939-107">The **Orchestration Events** option tracks the execution of each shape in the orchestration as it happens.</span></span> <span data-ttu-id="de939-108">可以在报告模式下，重放步骤或业务流程的类上设置断点，以便你可以调试使用交互模式的新实例。</span><span class="sxs-lookup"><span data-stu-id="de939-108">In reporting mode, you can replay the steps or set breakpoints on the class of orchestration so that you can then debug new instances using interactive mode.</span></span>  
  
 <span data-ttu-id="de939-109">已执行您感兴趣的业务流程后，你可以使用报告视图查询之一为你想要检查业务流程。</span><span class="sxs-lookup"><span data-stu-id="de939-109">After you have executed the business process you are interested in, you can use one of the Reporting view queries for the orchestration you wish to examine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de939-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="de939-110">See Also</span></span>  
 <span data-ttu-id="de939-111">[业务流程调试器中的交互模式](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="de939-111">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 <span data-ttu-id="de939-112">[调试业务流程](../core/debugging-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="de939-112">[Debugging an Orchestration](../core/debugging-an-orchestration.md) </span></span>  
 [<span data-ttu-id="de939-113">业务流程调试器用户界面</span><span class="sxs-lookup"><span data-stu-id="de939-113">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)