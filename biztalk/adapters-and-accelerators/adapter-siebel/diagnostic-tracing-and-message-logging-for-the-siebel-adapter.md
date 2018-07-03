---
title: 诊断跟踪和消息日志记录 Siebel 适配器的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ab369a74058f374ee229eb25d0697dc96f539ed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994574"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a><span data-ttu-id="a1ece-102">诊断跟踪和 Siebel 适配器的消息日志记录</span><span class="sxs-lookup"><span data-stu-id="a1ece-102">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>
<span data-ttu-id="a1ece-103">适配器客户端可以启用诊断跟踪以有效地诊断使用适配器时遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="a1ece-103">Adapter clients can enable diagnostic tracing to effectively diagnose problems encountered while using the adapters.</span></span> <span data-ttu-id="a1ece-104">适配器客户端可以激活三个不同级别的跟踪：</span><span class="sxs-lookup"><span data-stu-id="a1ece-104">Adapter clients can activate tracing at three different levels:</span></span>  
  
- <span data-ttu-id="a1ece-105">适配器客户端和适配器之间</span><span class="sxs-lookup"><span data-stu-id="a1ece-105">Between the adapter client and the adapter</span></span>  
  
- <span data-ttu-id="a1ece-106">适配器内</span><span class="sxs-lookup"><span data-stu-id="a1ece-106">Within the adapter</span></span>  
  
- <span data-ttu-id="a1ece-107">在适配器和业务 (LOB) 应用程序之间</span><span class="sxs-lookup"><span data-stu-id="a1ece-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
  <span data-ttu-id="a1ece-108">本部分提供有关激活在以下级别的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="a1ece-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="a1ece-109">适配器客户端和适配器之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="a1ece-109">Tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="a1ece-110">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="a1ece-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="a1ece-111">WCF 跟踪用于跟踪来自适配器的客户端使用 WCF 服务模型的输入的 Xml，并且有助于诊断序列化问题。</span><span class="sxs-lookup"><span data-stu-id="a1ece-111">WCF tracing is used to trace the input XMLs coming from the adapter client using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="a1ece-112">WCF 通道模型或从适配器到适配器客户端的输出消息，不使用 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="a1ece-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="a1ece-113">通过将一段摘录添加到各自的配置文件，可以激活 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="a1ece-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="a1ece-114">此外，可以启用跟踪在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="a1ece-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="a1ece-115">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a1ece-115">**Tracing at design-time**.</span></span> <span data-ttu-id="a1ece-116">为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1ece-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="a1ece-117">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1ece-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a1ece-118">因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="a1ece-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="a1ece-119">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a1ece-119">**Tracing at run-time**.</span></span> <span data-ttu-id="a1ece-120">对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。</span><span class="sxs-lookup"><span data-stu-id="a1ece-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="a1ece-121">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="a1ece-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="a1ece-122">为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a1ece-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="a1ece-123">若要启用 WCF 跟踪，必须添加以下摘录中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="a1ece-123">To enable WCF tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>
  
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
  
 <span data-ttu-id="a1ece-124">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="a1ece-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="a1ece-125">[WCF 跟踪](https://msdn.microsoft.com/library/ms730342.aspx)提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1ece-125">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more info.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a1ece-126">请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="a1ece-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="a1ece-127">请参阅[最佳做法来保护 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="a1ece-127">See [Best practices to secure the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span></span> 
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="a1ece-128">在适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="a1ece-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="a1ece-129">BizTalk 适配器包中的适配器记录到跟踪文件，例如错误、 警告和信息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="a1ece-129">The adapters in the BizTalk Adapter Pack log different categories of useful information to the trace file such as errors, warnings, and information.</span></span> <span data-ttu-id="a1ece-130">此类信息可了解该适配器中的过程流和诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="a1ece-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="a1ece-131">可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪的 BizTalk 应用程序和 WCF 服务模型应用程序通过向各自的配置文件添加一段摘录。</span><span class="sxs-lookup"><span data-stu-id="a1ece-131">You can activate [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="a1ece-132">此外，可以启用跟踪在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="a1ece-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="a1ece-133">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a1ece-133">**Tracing at design-time**.</span></span> <span data-ttu-id="a1ece-134">为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1ece-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="a1ece-135">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1ece-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a1ece-136">因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="a1ece-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="a1ece-137">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a1ece-137">**Tracing at run-time**.</span></span> <span data-ttu-id="a1ece-138">对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。</span><span class="sxs-lookup"><span data-stu-id="a1ece-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="a1ece-139">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="a1ece-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="a1ece-140">为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a1ece-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="a1ece-141">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，必须添加以下摘录中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="a1ece-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>  
  
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
  
 <span data-ttu-id="a1ece-142">这会将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="a1ece-142">This would save the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="a1ece-143">在适配器和 LOB 应用程序之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="a1ece-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="a1ece-144">必须启用该适配器与诊断问题怀疑 LOB 应用程序中的 LOB 应用程序之间的通信的跟踪。</span><span class="sxs-lookup"><span data-stu-id="a1ece-144">You must enable tracing for communication between the adapter and the LOB application to diagnose issues you suspect within the LOB application.</span></span> <span data-ttu-id="a1ece-145">适配器还取决于 LOB 跟踪 （客户端/服务器端），以获取访问此信息。</span><span class="sxs-lookup"><span data-stu-id="a1ece-145">Adapters also depend on LOB tracing (client/server side) to get access to this information.</span></span> <span data-ttu-id="a1ece-146">打开 LOB 跟踪的具体情况不在本文档。</span><span class="sxs-lookup"><span data-stu-id="a1ece-146">The specifics of turning on LOB tracing are excluded from this document.</span></span>  
  
 <span data-ttu-id="a1ece-147">此外，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供的绑定属性 (**日志数据**)，，如果设置为**True**如果跟踪级别设置为**Verbose**，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]记录在适配器和 Siebel 系统之间的信息流。</span><span class="sxs-lookup"><span data-stu-id="a1ece-147">Additionally, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides a binding property (**LogData**), which if set to **True** and if the trace level is set to **Verbose**, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] logs the information flow between the adapter and the Siebel system.</span></span> <span data-ttu-id="a1ece-148">与相同的跟踪文件中的适配器跟踪一起记录此信息。</span><span class="sxs-lookup"><span data-stu-id="a1ece-148">This information is logged along with the adapter traces in the same trace file.</span></span>  
  
 <span data-ttu-id="a1ece-149">有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a1ece-149">For more information about this binding property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="a1ece-150">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="a1ece-150">Viewing the Traces</span></span>  
 <span data-ttu-id="a1ece-151">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="a1ece-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="a1ece-152">有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a1ece-152">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="a1ece-153">为 BizTalk 应用程序配置跟踪</span><span class="sxs-lookup"><span data-stu-id="a1ece-153">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="a1ece-154">在 BizTalk 管理控制台，可配置发送端口等各种跟踪选项时，接收端口。</span><span class="sxs-lookup"><span data-stu-id="a1ece-154">The BizTalk Administration Console enables you to configure various tracking options for things such as send ports, receive ports.</span></span> <span data-ttu-id="a1ece-155">跟踪配置设置，可跟踪入站/出站事件数据、 消息属性、 消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="a1ece-155">The tracking configuration settings enable you to track inbound/outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="a1ece-156">有关为 BizTalk 应用程序配置跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="a1ece-156">For more information about configuring tracking for BizTalk applications, see [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
<span data-ttu-id="a1ece-157">此外可以使用组中心，将[查看跟踪消息和实例数据](../../core/viewing-tracked-message-and-instance-data.md)，包括跟踪的清单和最佳实践。</span><span class="sxs-lookup"><span data-stu-id="a1ece-157">You can also use Group Hub to [Viewing Tracked Message and Instance Data](../../core/viewing-tracked-message-and-instance-data.md), including a tracking checklist, and best practices.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1ece-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1ece-158">See Also</span></span>  
[<span data-ttu-id="a1ece-159">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="a1ece-159">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)