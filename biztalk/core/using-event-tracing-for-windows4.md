---
title: 使用事件跟踪用于 Windows4 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20d24f15ef1ec72e01244e84b8231fe0b2d7a48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982230"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="be772-102">使用的 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="be772-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="be772-103">适用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="be772-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="be772-104">可以使用 Windows 事件跟踪 (ETW) 工具来查看更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="be772-104">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="be772-105">激活 ETW 后，会创建一个 \*.etl 文件以接收这些消息。</span><span class="sxs-lookup"><span data-stu-id="be772-105">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="be772-106">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="be772-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="be772-107">若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件; 例如，tracerpt.exe 或 tracedmp.ex。</span><span class="sxs-lookup"><span data-stu-id="be772-107">To do this, you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.ex.</span></span> <span data-ttu-id="be772-108">Tracept.exe 应用程序将转换\*.etl 到两个文本文件： summary.txt 和 dumpfile.csv。</span><span class="sxs-lookup"><span data-stu-id="be772-108">The tracept.exe application converts the \*.etl into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="be772-109">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="be772-109">ETW Components</span></span>  
 <span data-ttu-id="be772-110">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="be772-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="be772-111">**控制器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="be772-111">**Controller application**.</span></span> <span data-ttu-id="be772-112">激活和停用提供程序（例如 tracelog.exe 或 logman.exe）。</span><span class="sxs-lookup"><span data-stu-id="be772-112">Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="be772-113">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="be772-113">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="be772-114">这可以确保 BTAJDEEnterpriseOneTrace 调用可以在系统中找到 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="be772-114">This ensures that BTAJDEEnterpriseOneTrace calls can locate tracelog.exe in your system.</span></span> <span data-ttu-id="be772-115">默认情况下，BTAJDEEnterpriseOneTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="be772-115">By default, BTAJDEEnterpriseOneTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be772-116">tracelog.exe 可以从 Microsoft SDK 中获得，并与用于 JD Edwards EnterpriseOne 的 BizTalk 适配器提供的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="be772-116">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by  BizTalk Adapter  for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="be772-117">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="be772-117">To use logman.exe, refer to the logman documentation.</span></span>  
  
- <span data-ttu-id="be772-118">**使用者应用程序**。</span><span class="sxs-lookup"><span data-stu-id="be772-118">**Consumer application**.</span></span> <span data-ttu-id="be772-119">读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="be772-119">Reads logged events.</span></span> <span data-ttu-id="be772-120">为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。</span><span class="sxs-lookup"><span data-stu-id="be772-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="be772-121">通常，该操作在控制器停用跟踪时完成。</span><span class="sxs-lookup"><span data-stu-id="be772-121">Normally this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="be772-122">若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪**\<实时\>=-rt**。</span><span class="sxs-lookup"><span data-stu-id="be772-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **\<Real time\> = -rt**.</span></span>  
  
- <span data-ttu-id="be772-123">**提供程序**。</span><span class="sxs-lookup"><span data-stu-id="be772-123">**Provider**.</span></span> <span data-ttu-id="be772-124">用于提供事件。</span><span class="sxs-lookup"><span data-stu-id="be772-124">Used to provide the event.</span></span> <span data-ttu-id="be772-125">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器包括三种不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="be772-125">BizTalk Adapter for JD Edwards EnterpriseOne includes three different providers.</span></span> <span data-ttu-id="be772-126">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="be772-126">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="be772-127">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="be772-127">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="be772-128">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器包含三种提供程序，允许您记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="be772-128">BizTalk Adapter  for JD Edwards EnterpriseOne contains three providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="be772-129">**接收方日志记录提供程序**:\<跟踪元素\>交换机 **-接收方**。</span><span class="sxs-lookup"><span data-stu-id="be772-129">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span> <span data-ttu-id="be772-130">使用 **-接收方**若要获取在运行时由适配器接收的日志中的任何消息。</span><span class="sxs-lookup"><span data-stu-id="be772-130">Use **-receiver** to get any messages from the log that were received by the adapter at run time.</span></span>  
  
- <span data-ttu-id="be772-131">**发送器日志记录提供程序**:\<跟踪元素\>交换机 **-发送器**。</span><span class="sxs-lookup"><span data-stu-id="be772-131">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span> <span data-ttu-id="be772-132">使用 **-发送器**可获取所有消息的日志中的已传输的适配器在运行时。</span><span class="sxs-lookup"><span data-stu-id="be772-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="be772-133">**管理日志记录提供程序**:\<跟踪元素\>交换机 **-管理**使用 **-管理**可获取所有消息的日志中的生成在浏览服务器系统。</span><span class="sxs-lookup"><span data-stu-id="be772-133">**Management Logging Provider**: The \<Trace element\> switch is **-management** Use **-management** to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
### <a name="btajdeenterpriseonetrace-command"></a><span data-ttu-id="be772-134">BTAJDEEnterpriseOneTrace 命令</span><span class="sxs-lookup"><span data-stu-id="be772-134">BTAJDEEnterpriseOneTrace Command</span></span>  
 <span data-ttu-id="be772-135">若要使用 ETW，请运行用于 JD Edwards EnterpriseOne 命令的 BizTalk 适配器**BTAJDEEnterpriseOneTrace.cmd**。</span><span class="sxs-lookup"><span data-stu-id="be772-135">To use ETW, run the BizTalk Adapter for JD Edwards EnterpriseOne command, **BTAJDEEnterpriseOneTrace.cmd**.</span></span> <span data-ttu-id="be772-136">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="be772-136">You use this command as follows:</span></span>  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 <span data-ttu-id="be772-137">位置： **\<跟踪元素\>** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="be772-137">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="be772-138">其选项是：</span><span class="sxs-lookup"><span data-stu-id="be772-138">Its options are:</span></span>  
  
- <span data-ttu-id="be772-139">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="be772-139">**-transmitter**</span></span>  
  
- <span data-ttu-id="be772-140">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="be772-140">**-receiver**</span></span>  
  
- <span data-ttu-id="be772-141">**-管理**</span><span class="sxs-lookup"><span data-stu-id="be772-141">**-management**</span></span>  
  
- <span data-ttu-id="be772-142">**-启动、-停止**： 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="be772-142">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="be772-143">**-cir \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="be772-143">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="be772-144">-cir 是循环文件。</span><span class="sxs-lookup"><span data-stu-id="be772-144">-cir is a circular file.</span></span> <span data-ttu-id="be772-145">\<MB\>: meg 中的大小。</span><span class="sxs-lookup"><span data-stu-id="be772-145">\<MB\>: Size in meg.</span></span>  
  
- <span data-ttu-id="be772-146">**-seq \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="be772-146">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="be772-147">-seq 是顺序文件。</span><span class="sxs-lookup"><span data-stu-id="be772-147">-seq is a sequential file.</span></span> <span data-ttu-id="be772-148">\<MB\>: meg 中的大小。</span><span class="sxs-lookup"><span data-stu-id="be772-148">\<MB\>: Size in meg.</span></span>  
  
- <span data-ttu-id="be772-149">**-rt**： 设置实时模式。</span><span class="sxs-lookup"><span data-stu-id="be772-149">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="be772-150">**日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="be772-150">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="be772-151">例如：</span><span class="sxs-lookup"><span data-stu-id="be772-151">For example:</span></span>  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="be772-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="be772-152">See Also</span></span>  
 [<span data-ttu-id="be772-153">JD Edwards EnterpriseOne 疑难解答</span><span class="sxs-lookup"><span data-stu-id="be772-153">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)