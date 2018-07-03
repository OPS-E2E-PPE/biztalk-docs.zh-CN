---
title: TIBCO Rendezvous 疑难解答 |Microsoft Docs
description: 使用 Windows 事件跟踪到 troubl 用于 BizTalk Server 中的 TIBCO Rendezvous = esdhoot Microsoft BizTalk 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b7bc3ab-16fa-4e91-8730-9431473b2fb4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccbf7efb3d61f35c1fb54eb709471f0913314ea7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977881"
---
# <a name="troubleshoot-tibco-rendezvous"></a><span data-ttu-id="162d6-103">TIBCO Rendezvous 疑难解答</span><span class="sxs-lookup"><span data-stu-id="162d6-103">Troubleshoot TIBCO Rendezvous</span></span>
  
## <a name="use-event-tracing-for-windows"></a><span data-ttu-id="162d6-104">使用 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="162d6-104">Use Event Tracing for Windows</span></span>
<span data-ttu-id="162d6-105">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器将错误、 警告和信息消息记录到 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="162d6-105">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="162d6-106">使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="162d6-106">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="162d6-107">激活 ETW 后，会创建一个 \*.etl 文件以接收这些消息。</span><span class="sxs-lookup"><span data-stu-id="162d6-107">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="162d6-108">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="162d6-108">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="162d6-109">若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件，例如，tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="162d6-109">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="162d6-110">例如，tracerpt.exe 应用程序会将转换\*.etl 文件到两个文本文件： summary.txt 和 dumpfile.csv。</span><span class="sxs-lookup"><span data-stu-id="162d6-110">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="162d6-111">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="162d6-111">ETW Components</span></span>  
 <span data-ttu-id="162d6-112">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="162d6-112">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="162d6-113">**控制器应用程序**： 激活和停用 （例如，tracelog.exe 或 logman.exe） 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="162d6-113">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="162d6-114">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="162d6-114">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="162d6-115">这确保 BTATIBCO RendezvousTrace 调用可以在系统中找到 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="162d6-115">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="162d6-116">默认情况下，BTATIBCO RendezvousTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="162d6-116">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="162d6-117">tracelog.exe 可以从 Microsoft SDK，并与用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器提供的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="162d6-117">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="162d6-118">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="162d6-118">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="162d6-119">**使用者应用程序**： 读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="162d6-119">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="162d6-120">为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。</span><span class="sxs-lookup"><span data-stu-id="162d6-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="162d6-121">通常，当控制器停用跟踪时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="162d6-121">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="162d6-122">若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪\<实时\>=-rt。</span><span class="sxs-lookup"><span data-stu-id="162d6-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="162d6-123">**提供程序**： 提供的事件。</span><span class="sxs-lookup"><span data-stu-id="162d6-123">**Provider**: Provides the event.</span></span>  
  
   <span data-ttu-id="162d6-124">用于 TIBCO Rendezvous 的 BizTalk 适配器包括三个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="162d6-124">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="162d6-125">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="162d6-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="162d6-126">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="162d6-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="162d6-127">用于 TIBCO Rendezvous 的 BizTalk 适配器具有三个提供程序。</span><span class="sxs-lookup"><span data-stu-id="162d6-127">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="162d6-128">这允许您记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="162d6-128">This lets you log different kinds of messages:</span></span>  
  
- <span data-ttu-id="162d6-129">**接收方日志记录提供程序**:\<跟踪元素\>交换机 **-接收方**。</span><span class="sxs-lookup"><span data-stu-id="162d6-129">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="162d6-130">使用 **-接收方**可在运行时适配器接收到日志中获取所有消息。</span><span class="sxs-lookup"><span data-stu-id="162d6-130">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
- <span data-ttu-id="162d6-131">**发送器日志记录提供程序**:\<跟踪元素\>交换机 **-发送器**。</span><span class="sxs-lookup"><span data-stu-id="162d6-131">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
   <span data-ttu-id="162d6-132">使用 **-发送器**可获取所有消息的日志中的已传输的适配器在运行时。</span><span class="sxs-lookup"><span data-stu-id="162d6-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="162d6-133"><strong>管理日志记录提供程序 —</strong>\<跟踪元素\>交换机 **-管理**。</span><span class="sxs-lookup"><span data-stu-id="162d6-133"><strong>Management Logging Provider—</strong>the \<Trace element\> switch is **-management**.</span></span>  
  
   <span data-ttu-id="162d6-134">使用 **-管理**可浏览服务器系统的过程中生成日志中获取所有消息。</span><span class="sxs-lookup"><span data-stu-id="162d6-134">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="162d6-135">BTATIBCORVTrace 命令</span><span class="sxs-lookup"><span data-stu-id="162d6-135">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="162d6-136">若要使用 ETW，运行 BizTalk Adapter for TIBCO Rendezvous 命令 BTATIBCORVTrace.cmd。</span><span class="sxs-lookup"><span data-stu-id="162d6-136">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="162d6-137">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="162d6-137">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="162d6-138">位置： **\<跟踪元素\>** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="162d6-138">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="162d6-139">其选项如下：</span><span class="sxs-lookup"><span data-stu-id="162d6-139">Its options are as follows:</span></span>  
  
- <span data-ttu-id="162d6-140">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="162d6-140">**-transmitter**</span></span>  
  
- <span data-ttu-id="162d6-141">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="162d6-141">**-receiver**</span></span>  
  
- <span data-ttu-id="162d6-142">**-管理**</span><span class="sxs-lookup"><span data-stu-id="162d6-142">**-management**</span></span>  
  
- <span data-ttu-id="162d6-143">**-启动、-停止**： 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="162d6-143">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="162d6-144">**-cir \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="162d6-144">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="162d6-145">**-cir**是循环文件。</span><span class="sxs-lookup"><span data-stu-id="162d6-145">**-cir** is a circular file.</span></span> <span data-ttu-id="162d6-146">**\<MB\>**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="162d6-146">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="162d6-147">**-seq \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="162d6-147">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="162d6-148">**-seq**是顺序文件。</span><span class="sxs-lookup"><span data-stu-id="162d6-148">**-seq** is a sequential file.</span></span> <span data-ttu-id="162d6-149">**\<MB\>**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="162d6-149">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="162d6-150">**-rt**： 设置实时模式。</span><span class="sxs-lookup"><span data-stu-id="162d6-150">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="162d6-151">**日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="162d6-151">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="162d6-152">例如：</span><span class="sxs-lookup"><span data-stu-id="162d6-152">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
## <a name="see-more"></a><span data-ttu-id="162d6-153">查看更多</span><span class="sxs-lookup"><span data-stu-id="162d6-153">See more</span></span>
[<span data-ttu-id="162d6-154">处理异常</span><span class="sxs-lookup"><span data-stu-id="162d6-154">Handle exceptions</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="162d6-155">Security</span><span class="sxs-lookup"><span data-stu-id="162d6-155">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)  
[<span data-ttu-id="162d6-156">体系结构</span><span class="sxs-lookup"><span data-stu-id="162d6-156">Architecture</span></span>](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)