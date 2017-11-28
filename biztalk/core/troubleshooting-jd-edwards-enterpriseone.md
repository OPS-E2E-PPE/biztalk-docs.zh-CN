---
title: "故障排除博士 Edwards EnterpriseOne |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting [JD Edwards EnterpriseOne adapters]
- JD Edwards EnterpriseOne adapters, troubleshooting
- adapters [JD Edwards EnterpriseOne adapters], troubleshooting
ms.assetid: 7b3e68fa-b81d-4767-ab62-3200ce89d81c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d32a4db56dc60d3a57d6e43985cc30a2868098bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a><span data-ttu-id="86dfc-102">JD Edwards EnterpriseOne 疑难解答</span><span class="sxs-lookup"><span data-stu-id="86dfc-102">Troubleshooting JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="86dfc-103">本部分介绍在用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中可能遇到的常见问题和错误消息并为其提供可能的更正。</span><span class="sxs-lookup"><span data-stu-id="86dfc-103">This section describes common issues and error messages you might encounter in BizTalk Adapter for JD Edwards EnterpriseOne and provides possible corrections for them.</span></span> <span data-ttu-id="86dfc-104">此外，还讨论 windows 事件跟踪的用法。</span><span class="sxs-lookup"><span data-stu-id="86dfc-104">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="86dfc-105">可以使用下列调试/跟踪工具来解决适配器问题：</span><span class="sxs-lookup"><span data-stu-id="86dfc-105">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="86dfc-106">BizTalk Server 本机调试（例如，您端口扩业务流程调试器上的跟踪类型）。</span><span class="sxs-lookup"><span data-stu-id="86dfc-106">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="86dfc-107">提交到事件日志的错误消息。</span><span class="sxs-lookup"><span data-stu-id="86dfc-107">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="86dfc-108">通过 BTAJDEEnterpriseOneTrace.cmd 和转换 .etl 文件的工具（例如 tracerpt.exe 或 tracedmp.exe）捕获传输器、接收器和管理消息。</span><span class="sxs-lookup"><span data-stu-id="86dfc-108">The capture of transmitter, receiver, and management messages through BTAJDEEnterpriseOneTrace.cmd and a tool that converts.etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86dfc-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="86dfc-109">In This Section</span></span>  
  
-   [<span data-ttu-id="86dfc-110">错误消息</span><span class="sxs-lookup"><span data-stu-id="86dfc-110">Error Messages</span></span>](../core/error-messages1.md)  
  
-   [<span data-ttu-id="86dfc-111">使用适用于 Windows 跟踪的事件</span><span class="sxs-lookup"><span data-stu-id="86dfc-111">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows4.md)  
  
-   [<span data-ttu-id="86dfc-112">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="86dfc-112">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter1.md)