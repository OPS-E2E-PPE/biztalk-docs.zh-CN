---
title: "故障排除博士 Edwards OneWorld |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
ms.assetid: 15d73c2a-c6ee-46bf-8837-9c6ae3b098d2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b79e1bab85b52f816788b4e5e3550a5fa8059a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-jd-edwards-oneworld"></a><span data-ttu-id="3ba52-102">JD Edwards OneWorld 疑难解答</span><span class="sxs-lookup"><span data-stu-id="3ba52-102">Troubleshooting JD Edwards OneWorld</span></span>
<span data-ttu-id="3ba52-103">本节描述您可能在用于 JD Edwards OneWorld 的 BizTalk 适配器中遇到的常见问题和错误消息，并提供可能的更正方法。</span><span class="sxs-lookup"><span data-stu-id="3ba52-103">This section describes common issues and error messages that you might encounter in BizTalk Adapter for JD Edwards OneWorld, and provides possible corrections.</span></span> <span data-ttu-id="3ba52-104">此外，还讨论 windows 事件跟踪的用法。</span><span class="sxs-lookup"><span data-stu-id="3ba52-104">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="3ba52-105">可以使用下列调试/跟踪工具来解决适配器问题：</span><span class="sxs-lookup"><span data-stu-id="3ba52-105">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="3ba52-106">BizTalk Server 本机调试（例如，您端口扩业务流程调试器上的跟踪类型）。</span><span class="sxs-lookup"><span data-stu-id="3ba52-106">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="3ba52-107">提交到事件日志的错误消息。</span><span class="sxs-lookup"><span data-stu-id="3ba52-107">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="3ba52-108">捕获的发送器、 接收方和管理消息通过 BTAJDEOneWorldTrace.cmd 和将.etl 文件，如 tracerpt.exe 或 tracedmp.exe 转换的工具。</span><span class="sxs-lookup"><span data-stu-id="3ba52-108">The capture of transmitter, receiver, and management messages through BTAJDEOneWorldTrace.cmd and a tool that converts the .etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ba52-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="3ba52-109">In This Section</span></span>  
  
-   [<span data-ttu-id="3ba52-110">错误消息</span><span class="sxs-lookup"><span data-stu-id="3ba52-110">Error Messages</span></span>](../core/error-messages2.md)  
  
-   [<span data-ttu-id="3ba52-111">使用适用于 Windows 跟踪的事件</span><span class="sxs-lookup"><span data-stu-id="3ba52-111">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows2.md)  
  
-   [<span data-ttu-id="3ba52-112">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="3ba52-112">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter3.md)