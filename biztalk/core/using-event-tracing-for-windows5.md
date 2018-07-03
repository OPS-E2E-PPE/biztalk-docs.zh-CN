---
title: 使用事件跟踪用于 Windows5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- events, Event Tracing for Windows
- controller application
- ETW components
- consumer application
- Provider
- Event Tracing for Windows
- Event Tracing for Windows, components
- BTAPeopleSoftTrace command
ms.assetid: 330ef84b-5e2a-4b79-85a9-72271eb489d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fa744d7182f6238d71765afac2411b60974b5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000030"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="66d04-102">使用的 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="66d04-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="66d04-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器将错误、 警告和信息消息记录到 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="66d04-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="66d04-104">使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="66d04-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="66d04-105">如果启用 ETW，将创建一个 \*.etl 文件以接收消息。</span><span class="sxs-lookup"><span data-stu-id="66d04-105">When ETW is enabled, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="66d04-106">该文件为二进制格式，必须经过转换才能进行读取。</span><span class="sxs-lookup"><span data-stu-id="66d04-106">The file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="66d04-107">若要执行此操作必须具有可用于解释的使用者应用程序\*.etl 文件; 例如，tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="66d04-107">To do this you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="66d04-108">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="66d04-108">ETW Components</span></span>  
 <span data-ttu-id="66d04-109">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="66d04-109">Event Tracing for Windows has three components:</span></span>  
  
- <span data-ttu-id="66d04-110">**控制器应用程序**： 激活和停用 （例如，tracelog.exe 或 logman.exe） 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="66d04-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
   <span data-ttu-id="66d04-111">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="66d04-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="66d04-112">这可确保`BTAPeopleSoftTrace`调用可以在系统中找到 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="66d04-112">This makes sure that `BTAPeopleSoftTrace` calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="66d04-113">默认状态下，BTAPeopleSoftTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="66d04-113">By default, BTAPeopleSoftTrace searches the current path.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="66d04-114">tracelog.exe 可从 Microsoft SDK 获得，它与用于 PeopleSoft Enterprise 的 BizTalk 适配器提供的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="66d04-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="66d04-115">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="66d04-115">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="66d04-116">**使用者应用程序**： 读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="66d04-116">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="66d04-117">为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。</span><span class="sxs-lookup"><span data-stu-id="66d04-117">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="66d04-118">通常，当控制器停用跟踪时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="66d04-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="66d04-119">若要使用使用者不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪\<实时\>=-rt。</span><span class="sxs-lookup"><span data-stu-id="66d04-119">To use the consumer without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="66d04-120">**提供程序：** 提供事件。</span><span class="sxs-lookup"><span data-stu-id="66d04-120">**Provider:** Provides the event.</span></span>  
  
   <span data-ttu-id="66d04-121">用于 PeopleSoft Enterprise 的 BizTalk 适配器具有五个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="66d04-121">BizTalk Adapter for PeopleSoft Enterprise has five different providers.</span></span> <span data-ttu-id="66d04-122">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="66d04-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="66d04-123">若要查找中已注册的提供程序**\wmi\eventtrace**路径，可以使用诸如 WMI CIM Studio 等工具。</span><span class="sxs-lookup"><span data-stu-id="66d04-123">To find the registered providers in the **root\WMI\EventTrace** path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="66d04-124">用于 PeopleSoft Enterprise 的 BizTalk 适配器具有五个提供程序，从而允许您记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="66d04-124">BizTalk Adapter for PeopleSoft Enterprise has five providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="66d04-125">**接收方日志记录提供程序**:\<跟踪元素\>交换机 **-接收方**。</span><span class="sxs-lookup"><span data-stu-id="66d04-125">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="66d04-126">**接收器 CastDetails 提供程序**:\<跟踪元素\>交换机 **-castDetailsReceive**。</span><span class="sxs-lookup"><span data-stu-id="66d04-126">**Receiver CastDetails Provider**: The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
- <span data-ttu-id="66d04-127">**发送器日志记录提供程序**:\<跟踪元素\>交换机 **-发送器**。</span><span class="sxs-lookup"><span data-stu-id="66d04-127">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span>  
  
- <span data-ttu-id="66d04-128">**发送器 CastDetails 提供程序**:\<跟踪元素\>交换机 **-castDetailsTransmit**。</span><span class="sxs-lookup"><span data-stu-id="66d04-128">**Transmitter CastDetails Provider**: The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
- <span data-ttu-id="66d04-129">**管理日志记录提供程序**:\<跟踪元素\>交换机 **-管理**。</span><span class="sxs-lookup"><span data-stu-id="66d04-129">**Management Logging Provider**: The \<Trace element\> switch is **-management**.</span></span>  
  
## <a name="btapeoplesofttrace-command"></a><span data-ttu-id="66d04-130">BTAPeopleSoftTrace 命令</span><span class="sxs-lookup"><span data-stu-id="66d04-130">BTAPeopleSoftTrace Command</span></span>  
 <span data-ttu-id="66d04-131">若要使用 ETW，请运行适配器命令**BTAPeopleSoftTrace.cmd**。</span><span class="sxs-lookup"><span data-stu-id="66d04-131">To use ETW, run the adapter command, **BTAPeopleSoftTrace.cmd**.</span></span> <span data-ttu-id="66d04-132">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="66d04-132">You use this command as follows:</span></span>  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="66d04-133">其中：</span><span class="sxs-lookup"><span data-stu-id="66d04-133">Where:</span></span>  
  
- <span data-ttu-id="66d04-134">\<跟踪元素\>（必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="66d04-134">\<Trace element\> (required) is the kind of provider.</span></span>  
  
   <span data-ttu-id="66d04-135">选项如下：</span><span class="sxs-lookup"><span data-stu-id="66d04-135">Options are as follows:</span></span>  
  
  -   <span data-ttu-id="66d04-136">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="66d04-136">**-castDetailsTransmit**</span></span>  
  
  -   <span data-ttu-id="66d04-137">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="66d04-137">**-transmitter**</span></span>  
  
  -   <span data-ttu-id="66d04-138">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="66d04-138">**-castDetailsReceive**</span></span>  
  
  -   <span data-ttu-id="66d04-139">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="66d04-139">**-receiver**</span></span>  
  
  -   <span data-ttu-id="66d04-140">**-管理**</span><span class="sxs-lookup"><span data-stu-id="66d04-140">**-management**</span></span>  
  
  -   <span data-ttu-id="66d04-141">**-启动、-停止**： 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="66d04-141">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="66d04-142">**-cir \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="66d04-142">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="66d04-143">-cir 是循环文件。</span><span class="sxs-lookup"><span data-stu-id="66d04-143">-cir is a circular file.</span></span> <span data-ttu-id="66d04-144">\<MB\>： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="66d04-144">\<MB\>: Size in megabytes.</span></span>  
  
- <span data-ttu-id="66d04-145">**-seq \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="66d04-145">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="66d04-146">-seq 是顺序文件。</span><span class="sxs-lookup"><span data-stu-id="66d04-146">-seq is a sequential file.</span></span> <span data-ttu-id="66d04-147">\<MB\>： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="66d04-147">\<MB\>: Size in megabytes.</span></span>  
  
- <span data-ttu-id="66d04-148">**-rt**： 设置实时模式。</span><span class="sxs-lookup"><span data-stu-id="66d04-148">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="66d04-149">**日志文件**: （C:\rtlog.etl 是默认值） 的日志文件的名称。</span><span class="sxs-lookup"><span data-stu-id="66d04-149">**Logfile**: Name of the log file (C:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="66d04-150">例如：</span><span class="sxs-lookup"><span data-stu-id="66d04-150">For example:</span></span>  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="66d04-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="66d04-151">See Also</span></span>  
 [<span data-ttu-id="66d04-152">PeopleSoft 疑难解答</span><span class="sxs-lookup"><span data-stu-id="66d04-152">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)