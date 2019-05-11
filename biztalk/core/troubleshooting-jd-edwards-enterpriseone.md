---
title: JD Edwards EnterpriseOne 适配器故障排除 |Microsoft Docs
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
ms.openlocfilehash: c92761a93dbbad66f8248c8b95a4f0247f64421c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295758"
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a><span data-ttu-id="a836f-102">Troubleshooting JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="a836f-102">Troubleshooting JD Edwards EnterpriseOne</span></span>

## <a name="overview"></a><span data-ttu-id="a836f-103">概述</span><span class="sxs-lookup"><span data-stu-id="a836f-103">Overview</span></span>
<span data-ttu-id="a836f-104">本部分介绍常见的问题和错误消息可能会遇到的 BizTalk 适配器中用于 JD Edwards EnterpriseOne 和提供可能的更正。</span><span class="sxs-lookup"><span data-stu-id="a836f-104">This section describes common issues and error messages you might encounter in BizTalk Adapter for JD Edwards EnterpriseOne and provides possible corrections for them.</span></span> <span data-ttu-id="a836f-105">此外，它还讨论了 Windows 的事件跟踪的使用。</span><span class="sxs-lookup"><span data-stu-id="a836f-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="a836f-106">可以使用下列调试/跟踪工具来解决适配器：</span><span class="sxs-lookup"><span data-stu-id="a836f-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="a836f-107">BizTalk Server 本机调试 （例如，跟踪类型在端口上） 或业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="a836f-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="a836f-108">提交到事件日志的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a836f-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="a836f-109">捕获发送器、 接收器和管理通过 BTAJDEEnterpriseOneTrace.cmd 和工具的消息转换.etl 的文件，例如 tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="a836f-109">The capture of transmitter, receiver, and management messages through BTAJDEEnterpriseOneTrace.cmd and a tool that converts.etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a836f-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a836f-110">Next steps</span></span>
  
-   [<span data-ttu-id="a836f-111">错误消息</span><span class="sxs-lookup"><span data-stu-id="a836f-111">Error Messages</span></span>](../core/error-messages1.md)  
  
-   [<span data-ttu-id="a836f-112">使用 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="a836f-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows4.md)  
  
-   [<span data-ttu-id="a836f-113">适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="a836f-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter1.md)