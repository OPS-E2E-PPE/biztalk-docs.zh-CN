---
title: 报告在业务流程调试器模式下 |Microsoft 文档
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
ms.openlocfilehash: f51c80c8e11545180720a5ec1cf0f28b7f8b6f6d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268565"
---
# <a name="reporting-mode-in-orchestration-debugger"></a><span data-ttu-id="68fde-102">业务流程调试器中的“报告”模式</span><span class="sxs-lookup"><span data-stu-id="68fde-102">Reporting Mode in Orchestration Debugger</span></span>
<span data-ttu-id="68fde-103">“报告”模式使用跟踪的事件来显示所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="68fde-103">Reporting mode uses tracked events to show what has happened.</span></span> <span data-ttu-id="68fde-104">它将使用数据使用跟踪**业务流程事件**选项标志。</span><span class="sxs-lookup"><span data-stu-id="68fde-104">It uses data tracked using the **Orchestration Events** option flag.</span></span> <span data-ttu-id="68fde-105">必须在执行业务流程实例之前设置此标志。</span><span class="sxs-lookup"><span data-stu-id="68fde-105">This flag must be set prior to the execution of the orchestration instance.</span></span> <span data-ttu-id="68fde-106">若要启用事件跟踪适用于特定的业务流程，请参阅[如何配置跟踪为业务流程](../core/how-to-configure-tracking-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="68fde-106">To enable event tracking for a particular orchestration, see [How to Configure Tracking for an Orchestration](../core/how-to-configure-tracking-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="68fde-107">**业务流程事件**选项跟踪的每个形状中业务流程执行事件发生。</span><span class="sxs-lookup"><span data-stu-id="68fde-107">The **Orchestration Events** option tracks the execution of each shape in the orchestration as it happens.</span></span> <span data-ttu-id="68fde-108">在报表模式下，你可以重播步骤或在业务流程的类上设置断点，以便你可以然后调试使用交互模式的新实例。</span><span class="sxs-lookup"><span data-stu-id="68fde-108">In reporting mode, you can replay the steps or set breakpoints on the class of orchestration so that you can then debug new instances using interactive mode.</span></span>  
  
 <span data-ttu-id="68fde-109">在执行目标业务程序之后，即可对要检查的业务流程使用某个报告视图查询。</span><span class="sxs-lookup"><span data-stu-id="68fde-109">After you have executed the business process you are interested in, you can use one of the Reporting view queries for the orchestration you wish to examine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fde-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68fde-110">See Also</span></span>  
 <span data-ttu-id="68fde-111">[在调试器中业务流程交互模式](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="68fde-111">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 <span data-ttu-id="68fde-112">[调试业务流程](../core/debugging-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="68fde-112">[Debugging an Orchestration](../core/debugging-an-orchestration.md) </span></span>  
 [<span data-ttu-id="68fde-113">业务流程调试器用户界面</span><span class="sxs-lookup"><span data-stu-id="68fde-113">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)