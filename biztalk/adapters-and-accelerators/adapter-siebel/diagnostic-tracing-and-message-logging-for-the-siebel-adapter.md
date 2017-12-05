---
title: "诊断跟踪和消息日志记录为 Siebel 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6b27dd6d169c9ea7e5012be3e03329e6888522
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a><span data-ttu-id="55c23-102">诊断跟踪和消息日志记录为 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="55c23-102">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>
<span data-ttu-id="55c23-103">适配器客户端可以启用诊断跟踪，以有效地诊断时使用适配器遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="55c23-103">Adapter clients can enable diagnostic tracing to effectively diagnose problems encountered while using the adapters.</span></span> <span data-ttu-id="55c23-104">适配器客户端可以激活三个不同级别的跟踪：</span><span class="sxs-lookup"><span data-stu-id="55c23-104">Adapter clients can activate tracing at three different levels:</span></span>  
  
-   <span data-ttu-id="55c23-105">适配器客户端和适配器之间</span><span class="sxs-lookup"><span data-stu-id="55c23-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="55c23-106">在该适配器</span><span class="sxs-lookup"><span data-stu-id="55c23-106">Within the adapter</span></span>  
  
-   <span data-ttu-id="55c23-107">适配器-的业务线 (LOB) 应用程序之间</span><span class="sxs-lookup"><span data-stu-id="55c23-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
 <span data-ttu-id="55c23-108">本部分提供有关激活这些级别的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="55c23-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="55c23-109">适配器客户端和适配器之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="55c23-109">Tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="55c23-110">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="55c23-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="55c23-111">WCF 跟踪可用于跟踪输入的 Xml 来自适配器客户端使用 WCF 服务模型，并在诊断序列化问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="55c23-111">WCF tracing is used to trace the input XMLs coming from the adapter client using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="55c23-112">WCF 跟踪不用于 WCF 通道模型或从适配器到适配器客户端的输出消息。</span><span class="sxs-lookup"><span data-stu-id="55c23-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="55c23-113">可以通过将一段摘录添加到各自的配置文件来激活对 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="55c23-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="55c23-114">此外，您可以启用跟踪，同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="55c23-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="55c23-115">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="55c23-115">**Tracing at design-time**.</span></span> <span data-ttu-id="55c23-116">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55c23-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="55c23-117">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55c23-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="55c23-118">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="55c23-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="55c23-119">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="55c23-119">**Tracing at run-time**.</span></span> <span data-ttu-id="55c23-120">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="55c23-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="55c23-121">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="55c23-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="55c23-122">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="55c23-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="55c23-123">若要启用 WCF 跟踪，必须添加以下摘录内容中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="55c23-123">To enable WCF tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>
  
```  
<system.diagnostics>  
    <sources>  
      <source name ="System.ServiceModel" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.ServiceModel.MessageLogging"   
              switchValue="Verbose, ActivityTracing">          
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.Runtime.Serialization" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
   </sources>  
   <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"                
           traceOutputOptions="LogicalOperationStack"   
           initializeData="C:\log\WCFTrace.svclog" />  
   </sharedListeners>  
   <trace autoflush="true" />  
  </system.diagnostics>  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  </system.serviceModel>  
```  
  
 <span data-ttu-id="55c23-124">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="55c23-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="55c23-125">[WCF 跟踪](https://msdn.microsoft.com/library/ms730342.aspx)提供了详细的信息。</span><span class="sxs-lookup"><span data-stu-id="55c23-125">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more info.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="55c23-126">请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="55c23-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="55c23-127">请参阅[最佳做法来保护在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="55c23-127">See [Best practices to secure the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span></span> 
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="55c23-128">跟踪中的适配器</span><span class="sxs-lookup"><span data-stu-id="55c23-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="55c23-129">BizTalk 适配器包中的适配器记录到跟踪文件，如错误、 警告和信息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="55c23-129">The adapters in the BizTalk Adapter Pack log different categories of useful information to the trace file such as errors, warnings, and information.</span></span> <span data-ttu-id="55c23-130">此类信息可用于了解在适配器中的处理流程和与适配器诊断问题。</span><span class="sxs-lookup"><span data-stu-id="55c23-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="55c23-131">你可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，BizTalk 应用程序和 WCF 服务模型应用程序通过将一段摘录添加到各自的配置文件。</span><span class="sxs-lookup"><span data-stu-id="55c23-131">You can activate [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="55c23-132">此外，您可以启用跟踪，同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="55c23-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="55c23-133">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="55c23-133">**Tracing at design-time**.</span></span> <span data-ttu-id="55c23-134">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55c23-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="55c23-135">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55c23-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="55c23-136">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="55c23-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="55c23-137">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="55c23-137">**Tracing at run-time**.</span></span> <span data-ttu-id="55c23-138">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="55c23-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="55c23-139">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="55c23-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="55c23-140">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="55c23-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="55c23-141">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，必须添加以下摘录内容中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="55c23-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Siebel" switchValue="Information">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"   
   traceOutputOptions="LogicalOperationStack"   
          initializeData="C:\log\AdapterTrace.svclog" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="55c23-142">这会将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="55c23-142">This would save the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="55c23-143">适配器 LOB 应用程序之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="55c23-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="55c23-144">必须启用该适配器与要诊断你怀疑 LOB 应用程序中的问题的 LOB 应用程序之间的通信的跟踪。</span><span class="sxs-lookup"><span data-stu-id="55c23-144">You must enable tracing for communication between the adapter and the LOB application to diagnose issues you suspect within the LOB application.</span></span> <span data-ttu-id="55c23-145">适配器还依赖于 LOB 跟踪 （客户端/服务器端），以获取访问此信息。</span><span class="sxs-lookup"><span data-stu-id="55c23-145">Adapters also depend on LOB tracing (client/server side) to get access to this information.</span></span> <span data-ttu-id="55c23-146">本文档将从排除启用的 LOB 跟踪功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55c23-146">The specifics of turning on LOB tracing are excluded from this document.</span></span>  
  
 <span data-ttu-id="55c23-147">此外，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供的绑定属性 (**日志数据**)，，如果设置为**True**和如果跟踪级别设置为**详细**、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]记录适配器和 Siebel 系统之间的信息流。</span><span class="sxs-lookup"><span data-stu-id="55c23-147">Additionally, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides a binding property (**LogData**), which if set to **True** and if the trace level is set to **Verbose**, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] logs the information flow between the adapter and the Siebel system.</span></span> <span data-ttu-id="55c23-148">此信息以及相同的跟踪文件中的适配器跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="55c23-148">This information is logged along with the adapter traces in the same trace file.</span></span>  
  
 <span data-ttu-id="55c23-149">有关此绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="55c23-149">For more information about this binding property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="55c23-150">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="55c23-150">Viewing the Traces</span></span>  
 <span data-ttu-id="55c23-151">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="55c23-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="55c23-152">有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)。</span><span class="sxs-lookup"><span data-stu-id="55c23-152">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="55c23-153">配置 BizTalk 应用程序的跟踪</span><span class="sxs-lookup"><span data-stu-id="55c23-153">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="55c23-154">BizTalk 管理控制台，可配置为发送端口等的各种跟踪选项时，接收端口。</span><span class="sxs-lookup"><span data-stu-id="55c23-154">The BizTalk Administration Console enables you to configure various tracking options for things such as send ports, receive ports.</span></span> <span data-ttu-id="55c23-155">跟踪配置设置，您可以跟踪入站/出站事件数据、 消息属性，消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="55c23-155">The tracking configuration settings enable you to track inbound/outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="55c23-156">有关配置 BizTalk 应用程序的跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="55c23-156">For more information about configuring tracking for BizTalk applications, see [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
<span data-ttu-id="55c23-157">你还可以使用组中心数据库到[查看跟踪消息和实例数据](../../core/viewing-tracked-message-and-instance-data.md)，包括跟踪的清单和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="55c23-157">You can also use Group Hub to [Viewing Tracked Message and Instance Data](../../core/viewing-tracked-message-and-instance-data.md), including a tracking checklist, and best practices.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55c23-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55c23-158">See Also</span></span>  
[<span data-ttu-id="55c23-159">解决在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="55c23-159">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)