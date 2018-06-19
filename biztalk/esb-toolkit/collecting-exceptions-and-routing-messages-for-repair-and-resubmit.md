---
title: 收集异常和修复，重新提交路由消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a1d080cc3b87cf371729c51e1b1f26e07ae521e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006758"
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a><span data-ttu-id="bebd6-102">收集异常和修复，重新提交路由消息</span><span class="sxs-lookup"><span data-stu-id="bebd6-102">Collecting Exceptions and Routing Messages for Repair and Resubmit</span></span>
<span data-ttu-id="bebd6-103">在使用此种情况下，自定义异常处理程序选取通过 Web 服务收到的错误消息，并将它路由到中随附的 InfoPath 模板与兼容的格式为磁盘文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bebd6-103">In this use case, a custom exception handler picks up a fault message received through a Web service and routes it to a disk file in a format compatible with an InfoPath template included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="bebd6-104">用户可以使用 Microsoft InfoPath 打开文件，编辑消息内容，然后重新提交以进行处理，该消息，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="bebd6-104">The user can open the file using Microsoft InfoPath, edit the message contents, and resubmit the message for processing, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="bebd6-105">![收集异常修复](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3 CollectingExceptionsRepair")</span><span class="sxs-lookup"><span data-stu-id="bebd6-105">![Collecting Exceptions Repair](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3-CollectingExceptionsRepair")</span></span>  
  
 <span data-ttu-id="bebd6-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="bebd6-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="bebd6-107">**路由修复并重新提交一条的消息**</span><span class="sxs-lookup"><span data-stu-id="bebd6-107">**Routing a message for repair and resubmission**</span></span>  
  
 <span data-ttu-id="bebd6-108">修复和重新提交自定义异常处理程序示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="bebd6-108">The Repair and Resubmit Custom Exception Handler sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="bebd6-109">当业务流程中的进程时遇到错误，异常处理程序，业务流程生成和发布 ESB 错误消息。</span><span class="sxs-lookup"><span data-stu-id="bebd6-109">When a process in an orchestration encounters an error, the exception handler in that orchestration generates and publishes an ESB fault message.</span></span> <span data-ttu-id="bebd6-110">此错误消息包括，在其负载中，消息 （包括其与 BizTalk Server 相关的上下文属性），处于"航班"时出现异常，由 BizTalk 业务流程引擎捕获当前异常。</span><span class="sxs-lookup"><span data-stu-id="bebd6-110">This fault message includes, in its payload, the messages (including their context properties that are related to BizTalk Server) that were "in flight" when the exception occurred, and the current exception caught by the BizTalk Orchestration engine.</span></span> <span data-ttu-id="bebd6-111">发布 ESB 错误消息后，它是与订阅业务流程 （自定义异常处理程序），提取和检查正在进行的消息和系统异常对象，并从中将正在进行的消息路由到文件文件夹中，取消排队用户可以编辑使用 InfoPath 的消息，并将其重新提交给 BizTalk Server 进行处理。</span><span class="sxs-lookup"><span data-stu-id="bebd6-111">After an ESB fault message is published, it is de-queued to a subscribing orchestration (a custom exception handler) that extracts and inspects the in-flight messages and the system exception object, and routes the in-flight messages to a file folder, from which a user can edit the message using InfoPath and resubmit it to BizTalk Server for processing.</span></span>  
  
 <span data-ttu-id="bebd6-112">有关详细信息，请参阅[运行修复和重新提交自定义异常处理程序示例](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="bebd6-112">For more information, see [Running the Repair and Resubmit Custom Exception Handler Sample](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md).</span></span>