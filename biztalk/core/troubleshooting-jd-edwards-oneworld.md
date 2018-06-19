---
title: 故障排除博士 Edwards OneWorld |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15d73c2a-c6ee-46bf-8837-9c6ae3b098d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85c4b1099814c4cf7489f18ae5cd921f46f180bc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015604"
---
# <a name="troubleshooting-jd-edwards-oneworld"></a><span data-ttu-id="786ca-102">JD Edwards OneWorld 疑难解答</span><span class="sxs-lookup"><span data-stu-id="786ca-102">Troubleshooting JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="786ca-103">概述</span><span class="sxs-lookup"><span data-stu-id="786ca-103">Overview</span></span>
<span data-ttu-id="786ca-104">本节描述您可能在用于 JD Edwards OneWorld 的 BizTalk 适配器中遇到的常见问题和错误消息，并提供可能的更正方法。</span><span class="sxs-lookup"><span data-stu-id="786ca-104">This section describes common issues and error messages that you might encounter in BizTalk Adapter for JD Edwards OneWorld, and provides possible corrections.</span></span> <span data-ttu-id="786ca-105">此外，还讨论 windows 事件跟踪的用法。</span><span class="sxs-lookup"><span data-stu-id="786ca-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="786ca-106">可以使用下列调试/跟踪工具来解决适配器问题：</span><span class="sxs-lookup"><span data-stu-id="786ca-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="786ca-107">BizTalk Server 本机调试（例如，您端口扩业务流程调试器上的跟踪类型）。</span><span class="sxs-lookup"><span data-stu-id="786ca-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="786ca-108">提交到事件日志的错误消息。</span><span class="sxs-lookup"><span data-stu-id="786ca-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="786ca-109">捕获的发送器、 接收方和管理消息通过 BTAJDEOneWorldTrace.cmd 和将.etl 文件，如 tracerpt.exe 或 tracedmp.exe 转换的工具。</span><span class="sxs-lookup"><span data-stu-id="786ca-109">The capture of transmitter, receiver, and management messages through BTAJDEOneWorldTrace.cmd and a tool that converts the .etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="786ca-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="786ca-110">Next steps</span></span>
  
-   [<span data-ttu-id="786ca-111">错误消息</span><span class="sxs-lookup"><span data-stu-id="786ca-111">Error Messages</span></span>](../core/error-messages2.md)  
  
-   [<span data-ttu-id="786ca-112">使用 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="786ca-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows2.md)  
  
-   [<span data-ttu-id="786ca-113">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="786ca-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter3.md)