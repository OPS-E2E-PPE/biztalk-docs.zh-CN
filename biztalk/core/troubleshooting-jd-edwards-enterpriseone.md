---
title: 故障排除博士 Edwards EnterpriseOne 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b3e68fa-b81d-4767-ab62-3200ce89d81c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d46fd3375f49f9fabd6ce8028cc226bce5885db
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015934"
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a><span data-ttu-id="48c76-102">JD Edwards EnterpriseOne 疑难解答</span><span class="sxs-lookup"><span data-stu-id="48c76-102">Troubleshooting JD Edwards EnterpriseOne</span></span>

## <a name="overview"></a><span data-ttu-id="48c76-103">概述</span><span class="sxs-lookup"><span data-stu-id="48c76-103">Overview</span></span>
<span data-ttu-id="48c76-104">本部分介绍在用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中可能遇到的常见问题和错误消息并为其提供可能的更正。</span><span class="sxs-lookup"><span data-stu-id="48c76-104">This section describes common issues and error messages you might encounter in BizTalk Adapter for JD Edwards EnterpriseOne and provides possible corrections for them.</span></span> <span data-ttu-id="48c76-105">此外，还讨论 windows 事件跟踪的用法。</span><span class="sxs-lookup"><span data-stu-id="48c76-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="48c76-106">可以使用下列调试/跟踪工具来解决适配器问题：</span><span class="sxs-lookup"><span data-stu-id="48c76-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="48c76-107">BizTalk Server 本机调试（例如，您端口扩业务流程调试器上的跟踪类型）。</span><span class="sxs-lookup"><span data-stu-id="48c76-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="48c76-108">提交到事件日志的错误消息。</span><span class="sxs-lookup"><span data-stu-id="48c76-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="48c76-109">通过 BTAJDEEnterpriseOneTrace.cmd 和转换 .etl 文件的工具（例如 tracerpt.exe 或 tracedmp.exe）捕获传输器、接收器和管理消息。</span><span class="sxs-lookup"><span data-stu-id="48c76-109">The capture of transmitter, receiver, and management messages through BTAJDEEnterpriseOneTrace.cmd and a tool that converts.etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="48c76-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="48c76-110">Next steps</span></span>
  
-   [<span data-ttu-id="48c76-111">错误消息</span><span class="sxs-lookup"><span data-stu-id="48c76-111">Error Messages</span></span>](../core/error-messages1.md)  
  
-   [<span data-ttu-id="48c76-112">使用 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="48c76-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows4.md)  
  
-   [<span data-ttu-id="48c76-113">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="48c76-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter1.md)