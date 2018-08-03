---
title: 诊断跟踪和消息日志记录 SAP 适配器的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and adapter
- tracing, within the adapter
- tracing, between the adapter and the LOB application
- troubleshooting, tracing and logging
ms.assetid: 5c60af54-896d-4873-acbf-32fbcd051ee2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40204b7d8835a4cc7231cee2b20938b03042f7a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966822"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-sap-adapter"></a><span data-ttu-id="06377-102">诊断跟踪和 SAP 适配器的消息日志记录</span><span class="sxs-lookup"><span data-stu-id="06377-102">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>
<span data-ttu-id="06377-103">诊断跟踪有助于有效地诊断使用适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="06377-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="06377-104">适配器客户端可以激活的三个级别的诊断跟踪：</span><span class="sxs-lookup"><span data-stu-id="06377-104">Adapter clients can activate diagnostic tracing at three levels:</span></span>  
  
- <span data-ttu-id="06377-105">适配器客户端和适配器之间</span><span class="sxs-lookup"><span data-stu-id="06377-105">Between the adapter client and the adapter</span></span>  
  
- <span data-ttu-id="06377-106">适配器内</span><span class="sxs-lookup"><span data-stu-id="06377-106">Within the adapter</span></span>  
  
- <span data-ttu-id="06377-107">在适配器和业务 (LOB) 应用程序之间</span><span class="sxs-lookup"><span data-stu-id="06377-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
  <span data-ttu-id="06377-108">本部分提供有关激活在以下级别的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="06377-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="06377-109">适配器客户端和适配器之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="06377-109">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="06377-110">适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="06377-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="06377-111">WCF 跟踪用于跟踪来自适配器客户端使用 WCF 服务模型，并且可在诊断序列化问题的输入的 XML。</span><span class="sxs-lookup"><span data-stu-id="06377-111">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="06377-112">WCF 通道模型或从适配器到适配器客户端的输出消息，不使用 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="06377-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="06377-113">通过将一段摘录添加到各自的配置文件，可以激活 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="06377-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="06377-114">此外，可以启用跟踪在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="06377-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="06377-115">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="06377-115">**Tracing at design-time**.</span></span> <span data-ttu-id="06377-116">为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="06377-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="06377-117">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="06377-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="06377-118">因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="06377-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="06377-119">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="06377-119">**Tracing at run-time**.</span></span> <span data-ttu-id="06377-120">对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。</span><span class="sxs-lookup"><span data-stu-id="06377-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="06377-121">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="06377-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="06377-122">为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="06377-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="06377-123">若要启用 WCF 跟踪，请添加以下摘录中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="06377-123">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="06377-124">这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="06377-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="06377-125">有关 WCF 跟踪的详细信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。</span><span class="sxs-lookup"><span data-stu-id="06377-125">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="06377-126">请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="06377-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="06377-127">有关建议，请参阅[最佳做法来保护 SAP 适配器](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="06377-127">For recommendations see [Best practices to secure the SAP adapter](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md).</span></span>  
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="06377-128">在适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="06377-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="06377-129">适配器记录到跟踪文件，例如错误、 警告和信息性消息的不同类别的有用信息。</span><span class="sxs-lookup"><span data-stu-id="06377-129">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="06377-130">此类信息可了解该适配器中的过程流和诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="06377-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="06377-131">可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪的 BizTalk 应用程序和 WCF 服务模型应用程序通过向各自的配置文件添加一段摘录。</span><span class="sxs-lookup"><span data-stu-id="06377-131">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="06377-132">此外，可以启用跟踪在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="06377-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="06377-133">**在设计时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="06377-133">**Tracing at design-time**.</span></span> <span data-ttu-id="06377-134">为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="06377-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="06377-135">所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="06377-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="06377-136">因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。</span><span class="sxs-lookup"><span data-stu-id="06377-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="06377-137">**在运行时跟踪**。</span><span class="sxs-lookup"><span data-stu-id="06377-137">**Tracing at run-time**.</span></span> <span data-ttu-id="06377-138">对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。</span><span class="sxs-lookup"><span data-stu-id="06377-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="06377-139">有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="06377-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="06377-140">为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="06377-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="06377-141">若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录中的`<configuration>`标记。</span><span class="sxs-lookup"><span data-stu-id="06377-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.SAP" switchValue="Information">  
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
  
 <span data-ttu-id="06377-142">这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。</span><span class="sxs-lookup"><span data-stu-id="06377-142">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="06377-143">在适配器和 LOB 应用程序之间的跟踪</span><span class="sxs-lookup"><span data-stu-id="06377-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="06377-144">若要诊断您怀疑的问题与 LOB 应用程序，必须启用该适配器与 LOB 应用程序之间的通信的跟踪。</span><span class="sxs-lookup"><span data-stu-id="06377-144">To diagnose issues that you suspect are related to the LOB application, you must enable tracing for communication between the adapter and the LOB application.</span></span> <span data-ttu-id="06377-145">适配器还取决于 LOB 跟踪 （客户端/服务器端） 访问此信息。</span><span class="sxs-lookup"><span data-stu-id="06377-145">Adapters also depend on LOB tracing (client/server side) to access this information.</span></span> <span data-ttu-id="06377-146">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使适配器客户端能够通过在连接 URI 中指定"RfcSdkTrace"参数启用 SAP 系统中的跟踪。</span><span class="sxs-lookup"><span data-stu-id="06377-146">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enables adapter clients to turn on tracing within the SAP system by specifying the "RfcSdkTrace" parameter in the connection URI.</span></span> <span data-ttu-id="06377-147">必须指定此参数，以启用到 SAP 系统中跟踪信息流 RFC SDK。</span><span class="sxs-lookup"><span data-stu-id="06377-147">You must specify this parameter to enable the RFC SDK to trace information flow within the SAP system.</span></span> <span data-ttu-id="06377-148">有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="06377-148">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="06377-149">此外，还可以创建的跟踪级别设置为 RFC SDK RFC_TRACE 环境变量。</span><span class="sxs-lookup"><span data-stu-id="06377-149">Additionally, you can also create an RFC_TRACE environment variable that sets the level of tracing for the RFC SDK.</span></span> <span data-ttu-id="06377-150">RFC_TRACE 是由 SAP 定义一个环境变量，并由 RFC SDK。</span><span class="sxs-lookup"><span data-stu-id="06377-150">RFC_TRACE is an environment variable defined by SAP and is used by the RFC SDK.</span></span> <span data-ttu-id="06377-151">如果此变量没有定义，则设置为 0，RFC SDK 跟踪级别是最低要求。</span><span class="sxs-lookup"><span data-stu-id="06377-151">If this variable is not defined or is set to 0, the RFC SDK tracing level is bare minimum.</span></span> <span data-ttu-id="06377-152">如果该变量设置为 1 或 2，是更详细的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="06377-152">If the variable is set to 1 or 2, the tracing level is more detailed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06377-153">而不考虑是否设置 RFC_TRACE 环境变量，启用了 RFC SDK 跟踪*仅*如果"RfcSdkTrace"参数设置为 true 的连接 URI 中。</span><span class="sxs-lookup"><span data-stu-id="06377-153">Irrespective of whether the RFC_TRACE environment variable is set, the RFC SDK tracing is enabled *only* if the "RfcSdkTrace" parameter is set to true in the connection URI.</span></span> <span data-ttu-id="06377-154">此环境变量的值仅控制 RFC SDK 跟踪的级别。</span><span class="sxs-lookup"><span data-stu-id="06377-154">The value of this environment variable solely governs the level of RFC SDK tracing.</span></span> <span data-ttu-id="06377-155">如果 RfcSdkTrace 设置为 true 时，该消息在适配器和 SAP 系统之间跟踪复制到您的计算机上的"system32"文件夹。</span><span class="sxs-lookup"><span data-stu-id="06377-155">If RfcSdkTrace is set to true, the message traces between the adapter and the SAP system are copied to the “system32” folder on your computer.</span></span> <span data-ttu-id="06377-156">若要将 RFC SDK 跟踪保存到其他某个位置，可以设置 RFC_TRACE_DIR 环境变量。</span><span class="sxs-lookup"><span data-stu-id="06377-156">To save the RFC SDK traces to some other location, you can set the RFC_TRACE_DIR environment variable.</span></span> <span data-ttu-id="06377-157">有关这些环境变量的详细信息，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="06377-157">For more information about these environment variables refer to the SAP documentation.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="06377-158">查看跟踪内容</span><span class="sxs-lookup"><span data-stu-id="06377-158">Viewing the Traces</span></span>  
 <span data-ttu-id="06377-159">Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="06377-159">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="06377-160">有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和时遇到问题](https://msdn.microsoft.com/library/aa751795.aspx)。</span><span class="sxs-lookup"><span data-stu-id="06377-160">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="06377-161">为 BizTalk 应用程序配置跟踪</span><span class="sxs-lookup"><span data-stu-id="06377-161">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="06377-162">在 BizTalk Server 管理控制台，可以配置各种跟踪选项的项，如发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="06377-162">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="06377-163">跟踪配置设置，可跟踪入站和出站事件数据、 消息属性、 消息正文和业务流程。</span><span class="sxs-lookup"><span data-stu-id="06377-163">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="06377-164">有关为 BizTalk 应用程序配置跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="06377-164">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="06377-165">此外可以使用运行状况与活动跟踪 (HAT) 来查看历史记录或跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="06377-165">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="06377-166">有关详细信息，请参阅[查看历史记录和跟踪数据](../../core/viewing-historical-and-tracked-data.md)。</span><span class="sxs-lookup"><span data-stu-id="06377-166">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="06377-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="06377-167">See Also</span></span>  
[<span data-ttu-id="06377-168">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="06377-168">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)