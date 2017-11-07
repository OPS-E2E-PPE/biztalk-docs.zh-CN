---
title: "解决 TIBCO 会合 |Microsoft 文档"
description: "使用 Windows 事件跟踪 troubl = esdhoot Microsoft BizTalk 适配器用于 BizTalk Server 中的 TIBCO 会合"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b7bc3ab-16fa-4e91-8730-9431473b2fb4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b860aa0d0253185f1c9ecc6f7a525776abfab5d6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="troubleshoot-tibco-rendezvous"></a><span data-ttu-id="8bce6-103">解决 TIBCO 会合</span><span class="sxs-lookup"><span data-stu-id="8bce6-103">Troubleshoot TIBCO Rendezvous</span></span>
  
## <a name="use-event-tracing-for-windows"></a><span data-ttu-id="8bce6-104">用于 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="8bce6-104">Use Event Tracing for Windows</span></span>
<span data-ttu-id="8bce6-105">Microsoft BizTalk Adapter for TIBCO 会合将错误、 警告和信息消息记录到 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="8bce6-105">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="8bce6-106">使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="8bce6-106">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="8bce6-107">激活 ETW 后，会创建一个 *.etl 文件以接收这些消息。</span><span class="sxs-lookup"><span data-stu-id="8bce6-107">When ETW is activated, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="8bce6-108">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="8bce6-108">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="8bce6-109">若要执行此操作，你必须提供要解释的使用者应用程序\*.etl 文件，例如，tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="8bce6-109">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="8bce6-110">例如，tracerpt.exe 应用程序会将转换\*到两个文本文件的.etl 文件： summary.txt 和 dumpfile.csv。</span><span class="sxs-lookup"><span data-stu-id="8bce6-110">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="8bce6-111">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="8bce6-111">ETW Components</span></span>  
 <span data-ttu-id="8bce6-112">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="8bce6-112">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="8bce6-113">**控制器应用程序**： 激活和停用的提供程序 （例如，tracelog.exe 或 logman.exe）。</span><span class="sxs-lookup"><span data-stu-id="8bce6-113">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="8bce6-114">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="8bce6-114">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="8bce6-115">这将确保 BTATIBCO RendezvousTrace 调用可以定位到系统中的 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="8bce6-115">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="8bce6-116">默认情况下，BTATIBCO RendezvousTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="8bce6-116">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bce6-117">tracelog.exe 则可从 Microsoft SDK，并且与提供的 Microsoft BizTalk 适配器用于 TIBCO 会合的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="8bce6-117">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="8bce6-118">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="8bce6-118">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="8bce6-119">**使用者应用程序**： 读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-119">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="8bce6-120">为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="8bce6-121">通常，当控制器停用跟踪时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8bce6-121">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="8bce6-122">若要使用使用者应用程序而无需停用跟踪，控制器必须激活了实时选项中，跟踪\<实时 > =-rt。</span><span class="sxs-lookup"><span data-stu-id="8bce6-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time> = -rt.</span></span>  
  
-   <span data-ttu-id="8bce6-123">**提供程序**： 提供的事件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-123">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="8bce6-124">TIBCO 会合的 BizTalk 适配器包括三个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="8bce6-124">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="8bce6-125">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="8bce6-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="8bce6-126">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="8bce6-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="8bce6-127">用于 TIBCO Rendezvous 的 BizTalk 适配器具有三个提供程序。</span><span class="sxs-lookup"><span data-stu-id="8bce6-127">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="8bce6-128">这样就可以记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="8bce6-128">This lets you log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="8bce6-129">**接收方日志记录提供程序**:\<跟踪元素 > 交换机**-接收方**。</span><span class="sxs-lookup"><span data-stu-id="8bce6-129">**Receiver Logging Provider**: The \<Trace element> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="8bce6-130">使用**-接收方**以获取已在运行时适配器接收到日志中的任何消息。</span><span class="sxs-lookup"><span data-stu-id="8bce6-130">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
-   <span data-ttu-id="8bce6-131">**发送器日志记录提供程序**:\<跟踪元素 > 交换机**-发送器**。</span><span class="sxs-lookup"><span data-stu-id="8bce6-131">**Transmitter Logging Provider**: the \<Trace element> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="8bce6-132">使用**-发送器**以获取已传输的适配器在运行时日志中的任何消息。</span><span class="sxs-lookup"><span data-stu-id="8bce6-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="8bce6-133">**管理日志记录提供程序-**\<跟踪元素 > 交换机**-管理**。</span><span class="sxs-lookup"><span data-stu-id="8bce6-133">**Management Logging Provider—**the \<Trace element> switch is **-management**.</span></span>  
  
     <span data-ttu-id="8bce6-134">使用**-管理**若要获取的服务器系统浏览过程中生成了日志中的任何消息。</span><span class="sxs-lookup"><span data-stu-id="8bce6-134">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="8bce6-135">BTATIBCORVTrace 命令</span><span class="sxs-lookup"><span data-stu-id="8bce6-135">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="8bce6-136">若要使用 ETW，运行 TIBCO 会合命令，BTATIBCORVTrace.cmd BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="8bce6-136">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="8bce6-137">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="8bce6-137">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="8bce6-138">其中： **\<跟踪元素 >** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="8bce6-138">Where: **\<Trace element>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="8bce6-139">其选项如下：</span><span class="sxs-lookup"><span data-stu-id="8bce6-139">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="8bce6-140">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="8bce6-140">**-transmitter**</span></span>  
  
-   <span data-ttu-id="8bce6-141">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="8bce6-141">**-receiver**</span></span>  
  
-   <span data-ttu-id="8bce6-142">**-管理**</span><span class="sxs-lookup"><span data-stu-id="8bce6-142">**-management**</span></span>  
  
-   <span data-ttu-id="8bce6-143">**-启动、-停止**： 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="8bce6-143">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="8bce6-144">**-cir \<MB >**： 大小和类型的文件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-144">**-cir \<MB>**: Size and kind of file.</span></span> <span data-ttu-id="8bce6-145">**-cir**是圆形文件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-145">**-cir** is a circular file.</span></span> <span data-ttu-id="8bce6-146">**\<MB >**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="8bce6-146">**\<MB>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="8bce6-147">**-seq \<MB >**： 大小和类型的文件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-147">**-seq \<MB>**: Size and kind of file.</span></span> <span data-ttu-id="8bce6-148">**-seq**是连续的文件。</span><span class="sxs-lookup"><span data-stu-id="8bce6-148">**-seq** is a sequential file.</span></span> <span data-ttu-id="8bce6-149">**\<MB >**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="8bce6-149">**\<MB>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="8bce6-150">**-rt**： 上设置的实时模式。</span><span class="sxs-lookup"><span data-stu-id="8bce6-150">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="8bce6-151">**日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="8bce6-151">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="8bce6-152">例如：</span><span class="sxs-lookup"><span data-stu-id="8bce6-152">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
## <a name="see-more"></a><span data-ttu-id="8bce6-153">查看更多</span><span class="sxs-lookup"><span data-stu-id="8bce6-153">See more</span></span>
[<span data-ttu-id="8bce6-154">处理异常</span><span class="sxs-lookup"><span data-stu-id="8bce6-154">Handle exceptions</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="8bce6-155">安全性</span><span class="sxs-lookup"><span data-stu-id="8bce6-155">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)  
[<span data-ttu-id="8bce6-156">体系结构</span><span class="sxs-lookup"><span data-stu-id="8bce6-156">Architecture</span></span>](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)