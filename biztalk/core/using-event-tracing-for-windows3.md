---
title: 事件跟踪用于 Windows3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- consumer application
- BTATIBCOEMSTrace command
- Event Tracing for Windows
ms.assetid: 71954431-2015-4d50-b69e-500c883b1e04
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75b2b339c99dcf1b64368c73381d1dbe81e0fb39
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973611"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="469ad-102">使用适用于 Windows 跟踪的事件</span><span class="sxs-lookup"><span data-stu-id="469ad-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="469ad-103">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="469ad-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="469ad-104">使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="469ad-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="469ad-105">激活 ETW 后，会创建一个 \*.etl 文件以接收这些消息。</span><span class="sxs-lookup"><span data-stu-id="469ad-105">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="469ad-106">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="469ad-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="469ad-107">若要执行此操作，你必须提供要解释的使用者应用程序 \*.etl 文件，例如，tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="469ad-107">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="469ad-108">例如，tracerpt.exe 应用程序将为 \*到两个文本文件的.etl 文件︰ summary.txt 和 dumpfile.csv。</span><span class="sxs-lookup"><span data-stu-id="469ad-108">For example, the tracerpt.exe application converts the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="469ad-109">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="469ad-109">ETW Components</span></span>  
 <span data-ttu-id="469ad-110">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="469ad-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="469ad-111">**控制器应用程序**︰ 激活和停用的提供程序 （例如，tracelog.exe 或 logman.exe）。</span><span class="sxs-lookup"><span data-stu-id="469ad-111">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="469ad-112">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="469ad-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="469ad-113">这将确保 BTATIBCO EMSTrace 调用可以定位到系统中的 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="469ad-113">This makes sure that BTATIBCO EMSTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="469ad-114">默认情况下，BTATIBCO EMSTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="469ad-114">By default, BTATIBCO EMSTrace searches the current path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="469ad-115">tracelog.exe 可以从 Microsoft SDK 中获得，并且与用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器提供的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="469ad-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="469ad-116">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="469ad-116">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="469ad-117">**使用者应用程序**︰ 读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="469ad-117">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="469ad-118">为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。</span><span class="sxs-lookup"><span data-stu-id="469ad-118">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="469ad-119">通常，当控制器停用跟踪时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="469ad-119">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="469ad-120">若要使用使用者应用程序而无需停用跟踪，控制器必须激活了实时选项中，跟踪\<实时\>=-rt。</span><span class="sxs-lookup"><span data-stu-id="469ad-120">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
-   <span data-ttu-id="469ad-121">**提供程序**︰ 提供的事件。</span><span class="sxs-lookup"><span data-stu-id="469ad-121">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="469ad-122">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器包括三个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="469ad-122">BizTalk Adapter for TIBCO Enterprise Message Service includes three different providers.</span></span> <span data-ttu-id="469ad-123">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="469ad-123">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="469ad-124">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="469ad-124">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="469ad-125">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器具有允许您记录不同类型消息的提供程序：</span><span class="sxs-lookup"><span data-stu-id="469ad-125">BizTalk Adapter for TIBCO Enterprise Message Service has providers that enable you to log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="469ad-126">**接收方日志记录提供程序**:\<跟踪元素\>交换机 **-接收方**。</span><span class="sxs-lookup"><span data-stu-id="469ad-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
     <span data-ttu-id="469ad-127">使用 **-接收方** 以获得在运行时收到了适配器的日志的任何消息。</span><span class="sxs-lookup"><span data-stu-id="469ad-127">Use **-receiver** to obtain any messages from the log that were received by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="469ad-128">**发送器日志记录提供程序**:\<跟踪元素\>交换机 **-发送器**。</span><span class="sxs-lookup"><span data-stu-id="469ad-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="469ad-129">使用 **-发送器**以获得在运行时该适配器已传输的日志的任何消息。</span><span class="sxs-lookup"><span data-stu-id="469ad-129">Use **-transmitter**to obtain any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
### <a name="btatibcoemstrace-command"></a><span data-ttu-id="469ad-130">BTATIBCOEMSTrace 命令</span><span class="sxs-lookup"><span data-stu-id="469ad-130">BTATIBCOEMSTrace Command</span></span>  
 <span data-ttu-id="469ad-131">若要使用 ETW，运行 TIBCO 企业消息服务命令，BTATIBCOEMSTrace.cmd BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="469ad-131">To use ETW, run the BizTalk Adapter for TIBCO Enterprise Message Service command, BTATIBCOEMSTrace.cmd.</span></span> <span data-ttu-id="469ad-132">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="469ad-132">You use this command as follows:</span></span>  
  
```  
BTATIBCOEMSTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA TIBCOEMSTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="469ad-133">其中：</span><span class="sxs-lookup"><span data-stu-id="469ad-133">Where:</span></span>  
  
-   <span data-ttu-id="469ad-134">**\<跟踪元素\>** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="469ad-134">**\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="469ad-135">其选项如下：</span><span class="sxs-lookup"><span data-stu-id="469ad-135">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="469ad-136">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="469ad-136">**-transmitter**</span></span>  
  
-   <span data-ttu-id="469ad-137">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="469ad-137">**-receiver**</span></span>  
  
-   <span data-ttu-id="469ad-138">**-启动、-停止**︰ 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="469ad-138">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="469ad-139">**-cir \<MB\>**： 大小和类型的文件。</span><span class="sxs-lookup"><span data-stu-id="469ad-139">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="469ad-140">**-cir** 是圆形文件。</span><span class="sxs-lookup"><span data-stu-id="469ad-140">**-cir** is a circular file.</span></span> <span data-ttu-id="469ad-141">**\<MB\>**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="469ad-141">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="469ad-142">**-seq \<MB\>**： 大小和类型的文件。</span><span class="sxs-lookup"><span data-stu-id="469ad-142">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="469ad-143">**-seq** 是连续的文件。</span><span class="sxs-lookup"><span data-stu-id="469ad-143">**-seq** is a sequential file.</span></span> <span data-ttu-id="469ad-144">**\<MB\>**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="469ad-144">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="469ad-145">**-rt**︰ 上设置的实时模式。</span><span class="sxs-lookup"><span data-stu-id="469ad-145">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="469ad-146">**日志文件**︰ 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="469ad-146">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="469ad-147">例如：</span><span class="sxs-lookup"><span data-stu-id="469ad-147">For example:</span></span>  
  
```  
BTATIBCOEMSTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCOEMSTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="469ad-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="469ad-148">See Also</span></span>  
 [<span data-ttu-id="469ad-149">故障排除 TIBCO 企业消息服务</span><span class="sxs-lookup"><span data-stu-id="469ad-149">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)