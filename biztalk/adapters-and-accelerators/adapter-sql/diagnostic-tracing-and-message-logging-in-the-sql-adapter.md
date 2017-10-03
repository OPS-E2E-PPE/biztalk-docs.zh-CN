---
title: "诊断跟踪和消息日志记录中的 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6599b4d-5650-4592-96af-ee43fb36357d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff799af25c6ba74301eeab19eb793c2e84fd90e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a><span data-ttu-id="832e5-102">诊断跟踪和消息日志记录中的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="832e5-102">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>
<span data-ttu-id="832e5-103">诊断跟踪有助于有效地诊断都使用适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="832e5-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="832e5-104">适配器客户端可以激活两个级别的诊断跟踪：</span><span class="sxs-lookup"><span data-stu-id="832e5-104">Adapter clients can activate diagnostic tracing at two levels:</span></span>  
  
-   <span data-ttu-id="832e5-105">适配器客户端和适配器之间</span><span class="sxs-lookup"><span data-stu-id="832e5-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="832e5-106">在该适配器</span><span class="sxs-lookup"><span data-stu-id="832e5-106">Within the adapter</span></span>  
  
 <span data-ttu-id="832e5-107">本部分提供有关激活这些级别的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="832e5-107">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="832e5-108">适配器客户端和适配器之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="832e5-108">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="832e5-109">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="832e5-109">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="832e5-110">WCF 跟踪用于跟踪的输入的 XML，来自适配器客户端，通过使用 WCF 服务模型，而在诊断序列化问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="832e5-110">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="832e5-111">WCF 跟踪不用于 WCF 通道模型或从适配器到适配器客户端的输出消息。</span><span class="sxs-lookup"><span data-stu-id="832e5-111">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="832e5-112">可以通过将一段摘录添加到各自的配置文件来激活对 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="832e5-112">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="832e5-113">此外，你可以启用跟踪同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="832e5-113">Also, you can enable tracing both at design time and run time.</span></span>  
  
-   <span data-ttu-id="832e5-114">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="832e5-114">**Tracing at design time**.</span></span> <span data-ttu-id="832e5-115">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="832e5-115">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="832e5-116">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="832e5-116">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="832e5-117">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器 >*: files\microsoft Visual Studio * \<版本 >*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="832e5-117">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive>*:\Program Files\Microsoft Visual Studio *\<version>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="832e5-118">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="832e5-118">**Tracing at run time**.</span></span> <span data-ttu-id="832e5-119">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="832e5-119">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="832e5-120">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序中，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。有关[!INCLUDE[prague](../../includes/prague-md.md)]，此文件位于通常下\<安装驱动器 >: files\microsoft [!INCLUDE[prague](../../includes/prague-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="832e5-120">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[prague](../../includes/prague-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[prague](../../includes/prague-md.md)].</span></span>  
  
    -   <span data-ttu-id="832e5-121">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="832e5-121">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="832e5-122">若要启用 WCF 跟踪，添加以下摘录内容中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="832e5-122">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
\<system.diagnostics>  
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
  \</system.diagnostics>  
  \<system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  \</system.serviceModel>  
```  
  
 <span data-ttu-id="832e5-123">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="832e5-123">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="832e5-124">有关 WCF 跟踪的详细信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。</span><span class="sxs-lookup"><span data-stu-id="832e5-124">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="832e5-125">请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="832e5-125">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="832e5-126">有关建议，请参阅[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="832e5-126">For recommendations see [Best practices to secure the SQL adapter](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span></span>
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="832e5-127">跟踪中的适配器</span><span class="sxs-lookup"><span data-stu-id="832e5-127">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="832e5-128">适配器登录到跟踪文件，如错误、 警告和信息性消息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="832e5-128">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="832e5-129">此类信息可用于了解在适配器中的处理流程和与适配器诊断问题。</span><span class="sxs-lookup"><span data-stu-id="832e5-129">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="832e5-130">你可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，BizTalk 应用程序和 WCF 服务模型应用程序通过将一段摘录添加到各自的配置文件。</span><span class="sxs-lookup"><span data-stu-id="832e5-130">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="832e5-131">此外，你可以启用跟踪同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="832e5-131">Also, you can enable tracing both at design time and run time.</span></span>  
  
-   <span data-ttu-id="832e5-132">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="832e5-132">**Tracing at design time**.</span></span> <span data-ttu-id="832e5-133">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="832e5-133">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="832e5-134">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="832e5-134">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="832e5-135">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器 >*: files\microsoft Visual Studio * \<版本 >*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="832e5-135">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive>*:\Program Files\Microsoft Visual Studio *\<version>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="832e5-136">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="832e5-136">**Tracing at run time**.</span></span> <span data-ttu-id="832e5-137">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="832e5-137">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="832e5-138">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序中，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。有关[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]，此文件位于通常下\<安装驱动器 >: files\microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="832e5-138">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
    -   <span data-ttu-id="832e5-139">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="832e5-139">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="832e5-140">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录内容中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="832e5-140">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
\<system.diagnostics>  
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
  \</system.diagnostics>  
```  
  
 <span data-ttu-id="832e5-141">这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="832e5-141">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="832e5-142">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="832e5-142">Viewing the Traces</span></span>  
 <span data-ttu-id="832e5-143">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="832e5-143">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="832e5-144">有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和问题](https://msdn.microsoft.com/library/aa751795.aspx)。</span><span class="sxs-lookup"><span data-stu-id="832e5-144">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="832e5-145">配置 BizTalk 应用程序的跟踪</span><span class="sxs-lookup"><span data-stu-id="832e5-145">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="832e5-146">BizTalk Server 管理控制台允许你配置的项目例如发送端口的各种跟踪选项，并接收端口。</span><span class="sxs-lookup"><span data-stu-id="832e5-146">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="832e5-147">跟踪配置设置，您可以跟踪入站和出站事件数据、 消息属性，消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="832e5-147">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="832e5-148">有关配置 BizTalk 应用程序的跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="832e5-148">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="832e5-149">你可以使用运行状况和活动跟踪 (HAT) 来查看历史记录或跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="832e5-149">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="832e5-150">有关详细信息，请参阅[查看历史记录和跟踪数据](../../core/viewing-historical-and-tracked-data.md)。</span><span class="sxs-lookup"><span data-stu-id="832e5-150">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="832e5-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="832e5-151">See Also</span></span>  
 [<span data-ttu-id="832e5-152">解决 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="832e5-152">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)