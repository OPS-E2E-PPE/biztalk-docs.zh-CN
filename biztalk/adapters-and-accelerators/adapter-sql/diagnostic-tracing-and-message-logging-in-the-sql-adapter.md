---
title: 诊断跟踪和消息日志记录中的 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6599b4d-5650-4592-96af-ee43fb36357d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fbcdac66c40a4b1d9c2b35d2f8268a63c8bd0e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968150"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a><span data-ttu-id="d3eb4-102">诊断跟踪和消息日志记录中的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="d3eb4-102">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>
<span data-ttu-id="d3eb4-103">诊断跟踪有助于有效地诊断使用适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="d3eb4-104">适配器客户端可以激活在两个级别的诊断跟踪：</span><span class="sxs-lookup"><span data-stu-id="d3eb4-104">Adapter clients can activate diagnostic tracing at two levels:</span></span>  
  
- <span data-ttu-id="d3eb4-105">适配器客户端和适配器之间</span><span class="sxs-lookup"><span data-stu-id="d3eb4-105">Between the adapter client and the adapter</span></span>  
  
- <span data-ttu-id="d3eb4-106">适配器内</span><span class="sxs-lookup"><span data-stu-id="d3eb4-106">Within the adapter</span></span>  
  
  <span data-ttu-id="d3eb4-107">本部分提供有关激活在以下级别的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-107">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="d3eb4-108">适配器客户端和适配器之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="d3eb4-108">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="d3eb4-109">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-109">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="d3eb4-110">WCF 跟踪用于跟踪来自适配器客户端使用 WCF 服务模型，并且可在诊断序列化问题的输入的 XML。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-110">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="d3eb4-111">WCF 通道模型或从适配器到适配器客户端的输出消息，不使用 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-111">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="d3eb4-112">通过将一段摘录添加到各自的配置文件，可以激活 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-112">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="d3eb4-113">此外，可以启用跟踪都在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-113">Also, you can enable tracing both at design time and run time.</span></span>  
  
- <span data-ttu-id="d3eb4-114">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-114">**Tracing at design time**.</span></span> <span data-ttu-id="d3eb4-115">为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-115">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="d3eb4-116">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-116">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="d3eb4-117">因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-117">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="d3eb4-118">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-118">**Tracing at run time**.</span></span> <span data-ttu-id="d3eb4-119">对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-119">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="d3eb4-120">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-120">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="d3eb4-121">为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-121">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="d3eb4-122">若要启用 WCF 跟踪，请添加以下摘录中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-122">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="d3eb4-123">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-123">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="d3eb4-124">有关 WCF 跟踪的详细信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-124">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d3eb4-125">请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-125">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="d3eb4-126">有关建议，请参阅[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-126">For recommendations see [Best practices to secure the SQL adapter](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span></span>
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="d3eb4-127">在适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="d3eb4-127">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="d3eb4-128">适配器记录到跟踪文件，例如错误、 警告和信息性消息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-128">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="d3eb4-129">此类信息可了解该适配器中的过程流和诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-129">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="d3eb4-130">可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪的 BizTalk 应用程序和 WCF 服务模型应用程序通过向各自的配置文件添加一段摘录。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-130">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="d3eb4-131">此外，可以启用跟踪都在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-131">Also, you can enable tracing both at design time and run time.</span></span>  
  
- <span data-ttu-id="d3eb4-132">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-132">**Tracing at design time**.</span></span> <span data-ttu-id="d3eb4-133">为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-133">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="d3eb4-134">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-134">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="d3eb4-135">因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-135">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="d3eb4-136">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-136">**Tracing at run time**.</span></span> <span data-ttu-id="d3eb4-137">对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-137">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="d3eb4-138">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-138">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="d3eb4-139">为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-139">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="d3eb4-140">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-140">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Sql" switchValue="Information">  
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
  
 <span data-ttu-id="d3eb4-141">这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-141">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="d3eb4-142">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="d3eb4-142">Viewing the Traces</span></span>  
 <span data-ttu-id="d3eb4-143">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-143">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="d3eb4-144">有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和时遇到问题](https://msdn.microsoft.com/library/aa751795.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-144">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="d3eb4-145">为 BizTalk 应用程序配置跟踪</span><span class="sxs-lookup"><span data-stu-id="d3eb4-145">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="d3eb4-146">在 BizTalk Server 管理控制台，可以配置各种跟踪选项的项，如发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-146">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="d3eb4-147">跟踪配置设置，可跟踪入站和出站事件数据、 消息属性、 消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-147">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="d3eb4-148">有关为 BizTalk 应用程序配置跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-148">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="d3eb4-149">此外可以使用运行状况与活动跟踪 (HAT) 来查看历史记录或跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-149">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="d3eb4-150">有关详细信息，请参阅[查看历史记录和跟踪数据](../../core/viewing-historical-and-tracked-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d3eb4-150">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3eb4-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3eb4-151">See Also</span></span>  
 [<span data-ttu-id="d3eb4-152">SQL 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="d3eb4-152">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)