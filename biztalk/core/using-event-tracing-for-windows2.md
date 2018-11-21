---
title: 使用事件跟踪用于 Windows2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- Event Tracing for Windows
ms.assetid: 88b91b74-2b2e-40e0-a3e9-1ebd6367abe8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1444e08a8ab824d9c77746f4c7643897a309ecc4
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753149"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="35e02-102">使用的 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="35e02-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="35e02-103">适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="35e02-103">Microsoft BizTalk Adapter for JD Edwards OneWorld logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="35e02-104">可以使用 Windows 事件跟踪 (ETW) 工具来查看更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="35e02-104">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="35e02-105">激活 ETW 后，它会创建\*.etl 文件以接收消息。</span><span class="sxs-lookup"><span data-stu-id="35e02-105">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="35e02-106">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="35e02-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="35e02-107">若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件： 例如，tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="35e02-107">To do this, you must have a consumer application available to interpret the \*.etl file: for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="35e02-108">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="35e02-108">ETW Components</span></span>  
 <span data-ttu-id="35e02-109">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="35e02-109">Event Tracing for Windows has three components:</span></span>  
  
- <span data-ttu-id="35e02-110">**控制器应用程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-110">**Controller application.**</span></span> <span data-ttu-id="35e02-111">激活和停用提供程序（例如 tracelog.exe 或 logman.exe）。</span><span class="sxs-lookup"><span data-stu-id="35e02-111">Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
   <span data-ttu-id="35e02-112">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="35e02-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="35e02-113">这可以确保 BTAJDEdwardsOneWorldTrace 调用可以在系统中找到 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="35e02-113">This ensures that BTAJDEdwardsOneWorldTrace calls can locate tracelog.exe in your system.</span></span> <span data-ttu-id="35e02-114">默认情况下，BTAJDEdwardsOneWorldTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="35e02-114">By default, BTAJDEdwardsOneWorldTrace searches the current path.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="35e02-115">tracelog.exe 可以从 Microsoft SDK 中获得，并与用于 JD Edwards OneWorld 的 BizTalk 适配器提供的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="35e02-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="35e02-116">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="35e02-116">To use logman.exe refer to the logman documentation.</span></span>  
  
- <span data-ttu-id="35e02-117">**使用者应用程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-117">**Consumer application.**</span></span> <span data-ttu-id="35e02-118">读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="35e02-118">Reads logged events.</span></span>  
  
   <span data-ttu-id="35e02-119">为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。</span><span class="sxs-lookup"><span data-stu-id="35e02-119">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="35e02-120">通常，该操作在控制器停用跟踪时完成。</span><span class="sxs-lookup"><span data-stu-id="35e02-120">Normally this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="35e02-121">若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪 **\<实时\>=-rt**。</span><span class="sxs-lookup"><span data-stu-id="35e02-121">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **\<Real time\> = -rt**.</span></span>  
  
- <span data-ttu-id="35e02-122">**提供程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-122">**Provider.**</span></span> <span data-ttu-id="35e02-123">提供事件。</span><span class="sxs-lookup"><span data-stu-id="35e02-123">Provides the event.</span></span>  
  
  <span data-ttu-id="35e02-124">用于 JD Edwards OneWorld 的 BizTalk 适配器包括五个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="35e02-124">BizTalk Adapter for JD Edwards OneWorld includes five different providers.</span></span> <span data-ttu-id="35e02-125">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="35e02-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="35e02-126">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="35e02-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="35e02-127">用于 JD Edwards OneWorld 的 BizTalk 适配器包含五种提供程序，允许您记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="35e02-127">BizTalk Adapter for JD Edwards OneWorld has five providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="35e02-128">**接收方日志记录提供程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-128">**Receiver Logging Provider.**</span></span> <span data-ttu-id="35e02-129">\<跟踪元素\>交换机 **-接收方**。</span><span class="sxs-lookup"><span data-stu-id="35e02-129">The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="35e02-130">**接收器 CastDetails 提供程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-130">**Receiver CastDetails Provider.**</span></span> <span data-ttu-id="35e02-131">\<跟踪元素\>交换机 **-castDetailsReceive**。</span><span class="sxs-lookup"><span data-stu-id="35e02-131">The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
- <span data-ttu-id="35e02-132">**发送器日志记录提供程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-132">**Transmitter Logging Provider.**</span></span> <span data-ttu-id="35e02-133">\<跟踪元素\>交换机 **-发送器**。</span><span class="sxs-lookup"><span data-stu-id="35e02-133">The \<Trace element\> switch is **-transmitter**.</span></span>  
  
- <span data-ttu-id="35e02-134">**发送器 CastDetails 提供程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-134">**Transmitter CastDetails Provider.**</span></span> <span data-ttu-id="35e02-135">\<跟踪元素\>交换机 **-castDetailsTransmit**。</span><span class="sxs-lookup"><span data-stu-id="35e02-135">The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
- <span data-ttu-id="35e02-136">**管理日志记录提供程序。**</span><span class="sxs-lookup"><span data-stu-id="35e02-136">**Management Logging Provider.**</span></span> <span data-ttu-id="35e02-137">\<跟踪元素\>交换机 **-管理**。</span><span class="sxs-lookup"><span data-stu-id="35e02-137">The \<Trace element\> switch is **-management**.</span></span>  
  
  <span data-ttu-id="35e02-138">BTAJDEOneWorldTrace 命令</span><span class="sxs-lookup"><span data-stu-id="35e02-138">BTAJDEOneWorldTrace Command</span></span>  
  
  <span data-ttu-id="35e02-139">若要使用 ETW，运行用于 JD Edwards OneWorld 命令，BTAJDEOneWorldTrace.cmd 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="35e02-139">To use ETW, run the BizTalk Adapter for JD Edwards OneWorld command, BTAJDEOneWorldTrace.cmd.</span></span> <span data-ttu-id="35e02-140">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="35e02-140">You use this command as follows:</span></span>  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="35e02-141">其中：</span><span class="sxs-lookup"><span data-stu-id="35e02-141">Where:</span></span>  
  
- <span data-ttu-id="35e02-142">**\<跟踪元素\>** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="35e02-142">**\<Trace element\>** (required) is the kind of provider.</span></span>  
  
- <span data-ttu-id="35e02-143">其选项是：</span><span class="sxs-lookup"><span data-stu-id="35e02-143">Its options are:</span></span>  
  
  -   <span data-ttu-id="35e02-144">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="35e02-144">**-castDetailsTransmit**</span></span>  
  
  -   <span data-ttu-id="35e02-145">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="35e02-145">**-transmitter**</span></span>  
  
  -   <span data-ttu-id="35e02-146">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="35e02-146">**-castDetailsReceive**</span></span>  
  
  -   <span data-ttu-id="35e02-147">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="35e02-147">**-receiver**</span></span>  
  
  -   <span data-ttu-id="35e02-148">**-管理**</span><span class="sxs-lookup"><span data-stu-id="35e02-148">**-management**</span></span>  
  
  -   <span data-ttu-id="35e02-149">**-启动、-停止**： 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="35e02-149">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
  -   <span data-ttu-id="35e02-150">**-cir \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="35e02-150">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="35e02-151">-cir 是循环文件。</span><span class="sxs-lookup"><span data-stu-id="35e02-151">-cir is a circular file.</span></span> <span data-ttu-id="35e02-152">\<MB\>: meg 中的大小。</span><span class="sxs-lookup"><span data-stu-id="35e02-152">\<MB\>: Size in meg.</span></span>  
  
  -   <span data-ttu-id="35e02-153">**-seq \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="35e02-153">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="35e02-154">-seq 是顺序文件。</span><span class="sxs-lookup"><span data-stu-id="35e02-154">-seq is a sequential file.</span></span> <span data-ttu-id="35e02-155">\<MB\>: meg 中的大小。</span><span class="sxs-lookup"><span data-stu-id="35e02-155">\<MB\>: Size in meg.</span></span>  
  
  -   <span data-ttu-id="35e02-156">**-rt**： 设置实时模式。</span><span class="sxs-lookup"><span data-stu-id="35e02-156">**-rt**: Set the real time mode on.</span></span>  
  
  -   <span data-ttu-id="35e02-157">**日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="35e02-157">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="35e02-158">例如：</span><span class="sxs-lookup"><span data-stu-id="35e02-158">For example:</span></span>  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="35e02-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="35e02-159">See Also</span></span>  
 [<span data-ttu-id="35e02-160">JD Edwards OneWorld 疑难解答</span><span class="sxs-lookup"><span data-stu-id="35e02-160">Troubleshooting JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)