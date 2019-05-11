---
title: JD Edwards OneWorld 疑难解答 |Microsoft Docs
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
ms.openlocfilehash: f8d6ee388cc2d19cca67e8f4eda2d4d6cd11c05d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295745"
---
# <a name="troubleshooting-jd-edwards-oneworld"></a><span data-ttu-id="3e725-102">Troubleshooting JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="3e725-102">Troubleshooting JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="3e725-103">概述</span><span class="sxs-lookup"><span data-stu-id="3e725-103">Overview</span></span>
<span data-ttu-id="3e725-104">本部分介绍常见的问题和错误消息，您可能用于 JD Edwards OneWorld 的 BizTalk 适配器中遇到和提供可能的更正方法。</span><span class="sxs-lookup"><span data-stu-id="3e725-104">This section describes common issues and error messages that you might encounter in BizTalk Adapter for JD Edwards OneWorld, and provides possible corrections.</span></span> <span data-ttu-id="3e725-105">此外，它还讨论了 Windows 的事件跟踪的使用。</span><span class="sxs-lookup"><span data-stu-id="3e725-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="3e725-106">可以使用下列调试/跟踪工具来解决适配器：</span><span class="sxs-lookup"><span data-stu-id="3e725-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="3e725-107">BizTalk Server 本机调试 （例如，跟踪类型在端口上） 或业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="3e725-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="3e725-108">提交到事件日志的错误消息。</span><span class="sxs-lookup"><span data-stu-id="3e725-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="3e725-109">捕获发送器、 接收器和管理消息通过 BTAJDEOneWorldTrace.cmd 和转换.etl 文件，例如 tracerpt.exe 或 tracedmp.exe 的工具。</span><span class="sxs-lookup"><span data-stu-id="3e725-109">The capture of transmitter, receiver, and management messages through BTAJDEOneWorldTrace.cmd and a tool that converts the .etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3e725-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3e725-110">Next steps</span></span>
  
-   [<span data-ttu-id="3e725-111">错误消息</span><span class="sxs-lookup"><span data-stu-id="3e725-111">Error Messages</span></span>](../core/error-messages2.md)  
  
-   [<span data-ttu-id="3e725-112">使用 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="3e725-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows2.md)  
  
-   [<span data-ttu-id="3e725-113">适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="3e725-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter3.md)