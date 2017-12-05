---
title: "诊断跟踪和消息日志记录为 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing
- message logging
- tracing, within the adapter
- tracing, between the adapter client and the adapter
ms.assetid: 971d34e4-5609-42c6-85b9-d9b1989fc47d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d3b7dc5c4feb78abb71360de4497aa20c9e9638
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter"></a><span data-ttu-id="80852-102">诊断跟踪和消息日志记录为 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="80852-102">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>
<span data-ttu-id="80852-103">诊断跟踪有助于有效地诊断都使用适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="80852-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="80852-104">本主题提供有关以下两种类型的支持的跟踪信息[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="80852-104">This topic provides information about the following two types of tracing supported with [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span></span>  
  
-   <span data-ttu-id="80852-105">适配器客户端和适配器之间的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="80852-105">WCF tracing between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="80852-106">适配器中的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="80852-106">WCF tracing within the adapter</span></span>  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="80852-107">适配器客户端和适配器之间的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="80852-107">WCF Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="80852-108">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="80852-108">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="80852-109">WCF 跟踪用于跟踪的输入的 XML，来自适配器客户端，通过使用 WCF 服务模型，而在诊断序列化问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="80852-109">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model, and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="80852-110">WCF 跟踪不用于 WCF 通道模型或从适配器到适配器客户端的输出消息。</span><span class="sxs-lookup"><span data-stu-id="80852-110">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="80852-111">可以通过将一段摘录添加到各自的配置文件来激活对 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="80852-111">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="80852-112">此外，您可以启用跟踪，同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="80852-112">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="80852-113">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="80852-113">**Tracing at design-time**.</span></span> <span data-ttu-id="80852-114">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80852-114">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="80852-115">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80852-115">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="80852-116">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="80852-116">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="80852-117">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="80852-117">**Tracing at run-time**.</span></span> <span data-ttu-id="80852-118">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="80852-118">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="80852-119">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="80852-119">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="80852-120">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="80852-120">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="80852-121">若要启用 WCF 跟踪，添加以下摘录内容中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="80852-121">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="80852-122">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="80852-122">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="80852-123">[WCF 跟踪](https://msdn.microsoft.com/library/ms730342.aspx)提供良好的详细信息。</span><span class="sxs-lookup"><span data-stu-id="80852-123">[WCF Tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more good information.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="80852-124">请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="80852-124">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="80852-125">有关建议，请参阅[最佳做法来保护 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="80852-125">For recommendations, see [Best practices to secure the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)</span></span>
  
## <a name="wcf-tracing-within-the-adapter"></a><span data-ttu-id="80852-126">适配器中的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="80852-126">WCF tracing within the adapter</span></span>  
 <span data-ttu-id="80852-127">适配器登录到跟踪文件，如错误、 警告和信息性消息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="80852-127">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="80852-128">此类信息可用于了解在适配器中的处理流程和与适配器诊断问题。</span><span class="sxs-lookup"><span data-stu-id="80852-128">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="80852-129">你可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，BizTalk 应用程序和 WCF 服务模型应用程序通过将一段摘录添加到各自的配置文件。</span><span class="sxs-lookup"><span data-stu-id="80852-129">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="80852-130">此外，您可以启用跟踪，同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="80852-130">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="80852-131">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="80852-131">**Tracing at design-time**.</span></span> <span data-ttu-id="80852-132">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80852-132">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="80852-133">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80852-133">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="80852-134">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="80852-134">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="80852-135">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="80852-135">**Tracing at run-time**.</span></span> <span data-ttu-id="80852-136">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="80852-136">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="80852-137">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="80852-137">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="80852-138">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="80852-138">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="80852-139">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录内容中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="80852-139">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name=" Microsoft.Adapters.OracleDB" switchValue="Information">  
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
  
 <span data-ttu-id="80852-140">这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="80852-140">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="80852-141">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="80852-141">Viewing the traces</span></span>  
 <span data-ttu-id="80852-142">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="80852-142">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="80852-143">请参阅[使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)。</span><span class="sxs-lookup"><span data-stu-id="80852-143">See [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="80852-144">配置 BizTalk 应用程序的跟踪</span><span class="sxs-lookup"><span data-stu-id="80852-144">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="80852-145">BizTalk Server 管理控制台允许你配置的项目例如发送端口的各种跟踪选项，并接收端口。</span><span class="sxs-lookup"><span data-stu-id="80852-145">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="80852-146">跟踪配置设置，您可以跟踪入站和出站事件数据、 消息属性，消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="80852-146">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="80852-147">[管理项目](../../core/managing-artifacts.md)包括详细信息。</span><span class="sxs-lookup"><span data-stu-id="80852-147">[Managing Artifacts](../../core/managing-artifacts.md) includes more info.</span></span> 

  
## <a name="see-also"></a><span data-ttu-id="80852-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80852-148">See Also</span></span>  
[<span data-ttu-id="80852-149">对 Oracle 数据库适配器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="80852-149">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)