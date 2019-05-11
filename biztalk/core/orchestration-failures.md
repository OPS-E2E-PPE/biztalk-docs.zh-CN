---
title: 业务流程故障 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception block [Orchestration Designer], suspended orchestrations
- HAT, Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], HAT
- orchestrations, troubleshooting [HAT]
- orchestrations, errors
- HAT, Orchestration Debugger
- Orchestration Debugger
- errors, orchestrations
- HAT, troubleshooting orchestrations
- orchestrations, HAT
- HAT, orchestrations
ms.assetid: d0a799fb-7859-4774-b444-979f22f04215
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3eaebe4244dfd1e7ad60cf6541c4573a9f2158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262999"
---
# <a name="orchestration-failures"></a><span data-ttu-id="29541-102">业务流程故障</span><span class="sxs-lookup"><span data-stu-id="29541-102">Orchestration Failures</span></span>
<span data-ttu-id="29541-103">业务流程的难易程度有所不同;例如，业务流程可能调用.NET 对象或构造转换和分配形状中的消息。</span><span class="sxs-lookup"><span data-stu-id="29541-103">Orchestrations vary in complexity; for example, an orchestration may call a .NET object or construct messages via transform and assignment shape.</span></span> <span data-ttu-id="29541-104">因此，不可能列出所有可能的故障，由于其内容的多样性以及自定义级别。</span><span class="sxs-lookup"><span data-stu-id="29541-104">As a result, it is impossible to list out every possible failure, due to the variety of its content as well as level of customization.</span></span> <span data-ttu-id="29541-105">但是，在业务流程中发生的所有故障都表现为异常。</span><span class="sxs-lookup"><span data-stu-id="29541-105">However, all failures encountered in orchestrations appear as exceptions.</span></span>  
  
 <span data-ttu-id="29541-106">如果业务流程不包括任何**CatchException**形状的异常，异常导致业务流程挂起，并且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="29541-106">If an orchestration does not include any **CatchException** shape for an exception, the exception causes the orchestration to be Suspended, but not resumable.</span></span> <span data-ttu-id="29541-107">这意味着消息和服务实例跟踪或 WMI 脚本，无法恢复该实例。</span><span class="sxs-lookup"><span data-stu-id="29541-107">This means that message and service instance tracking, or a WMI script, cannot recover the instance.</span></span> <span data-ttu-id="29541-108">但是，您可以保存与挂起相关联的所有消息 （不可恢复） 实例的诊断和手动重试使用跟踪 （或 WMI 脚本）。</span><span class="sxs-lookup"><span data-stu-id="29541-108">However, you can save all messages associated with the Suspended (not Resumable) instance using tracking (or WMI script) for diagnostic and manual retry.</span></span>  
  
 <span data-ttu-id="29541-109">若要诊断该问题，使用业务流程调试器查看在实例挂起之前执行的最后一个形状。</span><span class="sxs-lookup"><span data-stu-id="29541-109">To diagnose the problem, use the Orchestration Debugger to see the last shape executed before the instance is suspended.</span></span> <span data-ttu-id="29541-110">此外可以查看使用业务流程调试器的异常详细信息。</span><span class="sxs-lookup"><span data-stu-id="29541-110">You can also view exception details using the Orchestration Debugger.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29541-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="29541-111">See Also</span></span>  
 <span data-ttu-id="29541-112">[调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md) </span><span class="sxs-lookup"><span data-stu-id="29541-112">[Investigating Orchestration, Port, and Message Failures](../core/investigating-orchestration-port-and-message-failures.md) </span></span>  
 [<span data-ttu-id="29541-113">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="29541-113">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)