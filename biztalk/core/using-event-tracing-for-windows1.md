---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: f394629849f1c06328ca66ec6eb6cc21c574982a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969022"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="5ef04-101">使用的 Windows 事件跟踪</span><span class="sxs-lookup"><span data-stu-id="5ef04-101">Using Event Tracing for Windows</span></span>
<span data-ttu-id="5ef04-102">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器将错误、 警告和信息消息记录到 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="5ef04-102">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="5ef04-103">使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="5ef04-103">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="5ef04-104">激活 ETW 后，会创建一个 \*.etl 文件以接收这些消息。</span><span class="sxs-lookup"><span data-stu-id="5ef04-104">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="5ef04-105">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="5ef04-105">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="5ef04-106">若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件，例如，tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="5ef04-106">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="5ef04-107">例如，tracerpt.exe 应用程序会将转换\*.etl 文件到两个文本文件： summary.txt 和 dumpfile.csv。</span><span class="sxs-lookup"><span data-stu-id="5ef04-107">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="5ef04-108">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="5ef04-108">ETW Components</span></span>  
 <span data-ttu-id="5ef04-109">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="5ef04-109">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="5ef04-110">**控制器应用程序**： 激活和停用 （例如，tracelog.exe 或 logman.exe） 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ef04-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="5ef04-111">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="5ef04-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="5ef04-112">这确保 BTATIBCO RendezvousTrace 调用可以在系统中找到 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="5ef04-112">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="5ef04-113">默认情况下，BTATIBCO RendezvousTrace 搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="5ef04-113">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ef04-114">tracelog.exe 可以从 Microsoft SDK，并与用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器提供的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="5ef04-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="5ef04-115">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="5ef04-115">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="5ef04-116">**使用者应用程序**： 读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="5ef04-116">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="5ef04-117">为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。</span><span class="sxs-lookup"><span data-stu-id="5ef04-117">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="5ef04-118">通常，当控制器停用跟踪时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5ef04-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="5ef04-119">若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪\<实时\>=-rt。</span><span class="sxs-lookup"><span data-stu-id="5ef04-119">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="5ef04-120">**提供程序**： 提供的事件。</span><span class="sxs-lookup"><span data-stu-id="5ef04-120">**Provider**: Provides the event.</span></span>  
  
   <span data-ttu-id="5ef04-121">用于 TIBCO Rendezvous 的 BizTalk 适配器包括三个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ef04-121">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="5ef04-122">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="5ef04-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="5ef04-123">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="5ef04-123">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="5ef04-124">用于 TIBCO Rendezvous 的 BizTalk 适配器具有三个提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ef04-124">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="5ef04-125">这允许您记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="5ef04-125">This lets you log different kinds of messages:</span></span>  
  
- <span data-ttu-id="5ef04-126">**接收方日志记录提供程序**:\<跟踪元素\>交换机 **-接收方**。</span><span class="sxs-lookup"><span data-stu-id="5ef04-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="5ef04-127">使用 **-接收方**可在运行时适配器接收到日志中获取所有消息。</span><span class="sxs-lookup"><span data-stu-id="5ef04-127">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
- <span data-ttu-id="5ef04-128">**发送器日志记录提供程序**:\<跟踪元素\>交换机 **-发送器**。</span><span class="sxs-lookup"><span data-stu-id="5ef04-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
   <span data-ttu-id="5ef04-129">使用 **-发送器**可获取所有消息的日志中的已传输的适配器在运行时。</span><span class="sxs-lookup"><span data-stu-id="5ef04-129">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="5ef04-130"><strong>管理日志记录提供程序 —</strong>\<跟踪元素\>交换机 **-管理**。</span><span class="sxs-lookup"><span data-stu-id="5ef04-130"><strong>Management Logging Provider—</strong>the \<Trace element\> switch is **-management**.</span></span>  
  
   <span data-ttu-id="5ef04-131">使用 **-管理**可浏览服务器系统的过程中生成日志中获取所有消息。</span><span class="sxs-lookup"><span data-stu-id="5ef04-131">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="5ef04-132">BTATIBCORVTrace 命令</span><span class="sxs-lookup"><span data-stu-id="5ef04-132">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="5ef04-133">若要使用 ETW，运行 BizTalk Adapter for TIBCO Rendezvous 命令 BTATIBCORVTrace.cmd。</span><span class="sxs-lookup"><span data-stu-id="5ef04-133">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="5ef04-134">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="5ef04-134">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="5ef04-135">位置： **\<跟踪元素\>** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ef04-135">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="5ef04-136">其选项如下：</span><span class="sxs-lookup"><span data-stu-id="5ef04-136">Its options are as follows:</span></span>  
  
- <span data-ttu-id="5ef04-137">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="5ef04-137">**-transmitter**</span></span>  
  
- <span data-ttu-id="5ef04-138">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="5ef04-138">**-receiver**</span></span>  
  
- <span data-ttu-id="5ef04-139">**-管理**</span><span class="sxs-lookup"><span data-stu-id="5ef04-139">**-management**</span></span>  
  
- <span data-ttu-id="5ef04-140">**-启动、-停止**： 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ef04-140">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="5ef04-141">**-cir \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="5ef04-141">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="5ef04-142">**-cir**是循环文件。</span><span class="sxs-lookup"><span data-stu-id="5ef04-142">**-cir** is a circular file.</span></span> <span data-ttu-id="5ef04-143">**\<MB\>**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="5ef04-143">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="5ef04-144">**-seq \<MB\>**： 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="5ef04-144">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="5ef04-145">**-seq**是顺序文件。</span><span class="sxs-lookup"><span data-stu-id="5ef04-145">**-seq** is a sequential file.</span></span> <span data-ttu-id="5ef04-146">**\<MB\>**： 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="5ef04-146">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="5ef04-147">**-rt**： 设置实时模式。</span><span class="sxs-lookup"><span data-stu-id="5ef04-147">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="5ef04-148">**日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="5ef04-148">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="5ef04-149">例如：</span><span class="sxs-lookup"><span data-stu-id="5ef04-149">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ef04-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef04-150">See Also</span></span>  
 [<span data-ttu-id="5ef04-151">TIBCO Rendezvous 疑难解答</span><span class="sxs-lookup"><span data-stu-id="5ef04-151">Troubleshooting TIBCO Rendezvous</span></span>](../core/troubleshooting-tibco-rendezvous.md)