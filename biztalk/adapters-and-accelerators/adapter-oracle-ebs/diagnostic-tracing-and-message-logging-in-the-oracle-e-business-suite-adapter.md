---
title: "诊断跟踪和消息日志记录中的 Oracle E-business Suite 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d6be2a-cbd0-4c9c-be6f-9631063346e2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de2444cecbd661e9af4457f5f19c7e929d1c9c5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="cab1b-102">诊断跟踪和消息日志记录与 Oracle E-business Suite 适配器中</span><span class="sxs-lookup"><span data-stu-id="cab1b-102">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="cab1b-103">诊断跟踪有助于有效地诊断都使用适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="cab1b-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="cab1b-104">本主题提供有关以下三种类型的支持的跟踪信息[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cab1b-104">This topic provides information about the following three types of tracing supported with [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
-   <span data-ttu-id="cab1b-105">Oracle 服务器端跟踪使用客户端标识符</span><span class="sxs-lookup"><span data-stu-id="cab1b-105">Oracle server-side tracing using a client identifier</span></span>
  
-   <span data-ttu-id="cab1b-106">适配器客户端和适配器之间的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="cab1b-106">WCF tracing between the adapter client and the adapter</span></span>
  
-   <span data-ttu-id="cab1b-107">适配器中的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="cab1b-107">WCF tracing within the adapter</span></span>
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a><span data-ttu-id="cab1b-108">Oracle 服务器端跟踪使用客户端标识符</span><span class="sxs-lookup"><span data-stu-id="cab1b-108">Oracle server side tracing using a client identifier</span></span>  
 <span data-ttu-id="cab1b-109">Oracle 允许你对 Oracle 数据库的客户端应用程序执行的操作执行服务器端跟踪。</span><span class="sxs-lookup"><span data-stu-id="cab1b-109">Oracle allows you to perform server-side tracing for the operations performed by client applications on the Oracle database.</span></span> <span data-ttu-id="cab1b-110">由于可以将从客户端应用程序请求路由到不同的数据库会话，它将成为难以跟踪该请求的源。</span><span class="sxs-lookup"><span data-stu-id="cab1b-110">Because requests from client applications can be routed to different database sessions, it becomes difficult to trace the origin of the request.</span></span> <span data-ttu-id="cab1b-111">但是，Oracle 便于端到端应用程序跟踪使用客户端标识符。</span><span class="sxs-lookup"><span data-stu-id="cab1b-111">However, Oracle facilitates end-to-end application tracing using client identifiers.</span></span> 
 
 <span data-ttu-id="cab1b-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开`OracleConnectionClientId`绑定属性，它允许你在该适配器用于连接到 Oracle 的连接的设计时指定的客户端标识符。</span><span class="sxs-lookup"><span data-stu-id="cab1b-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes the `OracleConnectionClientId` binding property that allows you to specify the client identifier at the design time for the connection used by the adapter to connect to Oracle.</span></span> <span data-ttu-id="cab1b-113">适配器客户端标识符可帮助你在选择性跟踪中的适配器上的客户端 Oracle，执行的操作，还允许你筛选和查看 Oracle 服务器跟踪基于客户端标识符。</span><span class="sxs-lookup"><span data-stu-id="cab1b-113">The adapter client identifier helps you in selective tracing of the operations performed by the adapter client on Oracle, and also allows you to filter and view the Oracle server traces based on the client identifier.</span></span> <span data-ttu-id="cab1b-114">有关如何启用 Oracle 中的客户端标识符的跟踪的信息，请参阅[http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746)。</span><span class="sxs-lookup"><span data-stu-id="cab1b-114">For information about how you can enable tracing for client identifiers in Oracle, see [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746).</span></span>  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="cab1b-115">适配器客户端和适配器之间的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="cab1b-115">WCF tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="cab1b-116">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="cab1b-116">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="cab1b-117">WCF 跟踪用于跟踪的输入的 XML，来自适配器客户端，通过使用 WCF 服务模型，而在诊断序列化问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="cab1b-117">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="cab1b-118">WCF 跟踪不用于 WCF 通道模型或从适配器到适配器客户端的输出消息。</span><span class="sxs-lookup"><span data-stu-id="cab1b-118">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="cab1b-119">可以通过将一段摘录添加到各自的配置文件来激活对 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="cab1b-119">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="cab1b-120">此外，您可以启用跟踪，同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="cab1b-120">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="cab1b-121">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="cab1b-121">**Tracing at design-time**.</span></span> <span data-ttu-id="cab1b-122">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cab1b-122">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="cab1b-123">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cab1b-123">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="cab1b-124">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="cab1b-124">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="cab1b-125">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="cab1b-125">**Tracing at run-time**.</span></span> <span data-ttu-id="cab1b-126">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="cab1b-126">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="cab1b-127">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="cab1b-127">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="cab1b-128">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="cab1b-128">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="cab1b-129">若要启用 WCF 跟踪，添加以下摘录内容中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="cab1b-129">To enable WCF tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
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
  
 <span data-ttu-id="cab1b-130">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="cab1b-130">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="cab1b-131">[WCF 跟踪](https://msdn.microsoft.com/library/ms730342.aspx)提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="cab1b-131">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more information.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cab1b-132">请确保减轻暴露敏感业务数据，可以启用跟踪时导致的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="cab1b-132">Make sure you mitigate potential security threats of exposing sensitive business data that can be caused when enabling tracing.</span></span> <span data-ttu-id="cab1b-133">有关建议，请参阅[消息和实例数据跟踪的最佳做法](../../core/best-practices-for-message-and-instance-data-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="cab1b-133">For recommendations, see the [Best Practices for Message and Instance Data Tracking](../../core/best-practices-for-message-and-instance-data-tracking.md).</span></span>  
  
## <a name="wcf-tracing-within-the-adapter"></a><span data-ttu-id="cab1b-134">适配器中的 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="cab1b-134">WCF tracing within the adapter</span></span>  
 <span data-ttu-id="cab1b-135">适配器登录到跟踪文件，如错误、 警告和信息性消息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="cab1b-135">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="cab1b-136">此类信息可用于了解在适配器中的处理流程和与适配器诊断问题。</span><span class="sxs-lookup"><span data-stu-id="cab1b-136">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="cab1b-137">你可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，BizTalk 应用程序和 WCF 服务模型应用程序通过将一段摘录添加到各自的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cab1b-137">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="cab1b-138">此外，您可以启用跟踪，同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="cab1b-138">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="cab1b-139">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="cab1b-139">**Tracing at design-time**.</span></span> <span data-ttu-id="cab1b-140">对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cab1b-140">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="cab1b-141">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cab1b-141">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="cab1b-142">因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="cab1b-142">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="cab1b-143">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="cab1b-143">**Tracing at run-time**.</span></span> <span data-ttu-id="cab1b-144">对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。</span><span class="sxs-lookup"><span data-stu-id="cab1b-144">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="cab1b-145">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。有关[!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)]，此文件位于通常下\<安装驱动器\>: files\microsoft [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cab1b-145">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)], this file is available typically under \<installation drive\>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)].</span></span> <span data-ttu-id="cab1b-146">BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="cab1b-146">For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="cab1b-147">WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="cab1b-147">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="cab1b-148">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录内容中的`<configuration>`标记：</span><span class="sxs-lookup"><span data-stu-id="cab1b-148">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.OracleEBS" switchValue="Information">  
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
  
 <span data-ttu-id="cab1b-149">这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="cab1b-149">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="cab1b-150">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="cab1b-150">Viewing the traces</span></span>  
 <span data-ttu-id="cab1b-151">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="cab1b-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="cab1b-152">[使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)提供有关此工具的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="cab1b-152">[Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx) provides more details on this tool.</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="cab1b-153">配置 BizTalk 应用程序的跟踪</span><span class="sxs-lookup"><span data-stu-id="cab1b-153">Configuring tracking for BizTalk applications</span></span>  
 <span data-ttu-id="cab1b-154">BizTalk Server 管理控制台允许你配置的项目例如发送端口的各种跟踪选项，并接收端口。</span><span class="sxs-lookup"><span data-stu-id="cab1b-154">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="cab1b-155">跟踪配置设置，您可以跟踪入站和出站事件数据、 消息属性，消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="cab1b-155">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="cab1b-156">有关配置 BizTalk 应用程序的跟踪的详细信息，请参阅[管理和跟踪你的项目](../../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="cab1b-156">For more information about configuring tracking for BizTalk applications, see [Managing and tracking your artifacts](../../core/managing-artifacts.md).</span></span>  
  
 <span data-ttu-id="cab1b-157">你还可以使用组中心数据库到[查看跟踪的消息和实例数据](../../core/viewing-tracked-message-and-instance-data.md)，包括最佳实践，保存跟踪查询，和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cab1b-157">You can also use Group Hub to [view tracked message and instance data](../../core/viewing-tracked-message-and-instance-data.md), including best practices, saving tracking queries, and more.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cab1b-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cab1b-158">See Also</span></span>  
[<span data-ttu-id="cab1b-159">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="cab1b-159">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)