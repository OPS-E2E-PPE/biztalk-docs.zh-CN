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
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a>诊断跟踪和消息日志记录为 Siebel 适配器
适配器客户端可以启用诊断跟踪，以有效地诊断时使用适配器遇到的问题。 适配器客户端可以激活三个不同级别的跟踪：  
  
-   适配器客户端和适配器之间  
  
-   在该适配器  
  
-   适配器-的业务线 (LOB) 应用程序之间  
  
 本部分提供有关激活这些级别的跟踪信息。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>适配器客户端和适配器之间的跟踪  
 适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。 WCF 跟踪可用于跟踪输入的 Xml 来自适配器客户端使用 WCF 服务模型，并在诊断序列化问题非常有用。 WCF 跟踪不用于 WCF 通道模型或从适配器到适配器客户端的输出消息。 可以通过将一段摘录添加到各自的配置文件来激活对 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。 此外，您可以启用跟踪，同时在设计时和运行时。  
  
-   **在设计时跟踪**。 对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。  
  
-   **在运行时跟踪**。 对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。  
  
    -   有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。  
  
    -   WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。  
  
 若要启用 WCF 跟踪，必须添加以下摘录内容中的`<configuration>`标记：
  
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
  
 这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。 [WCF 跟踪](https://msdn.microsoft.com/library/ms730342.aspx)提供了详细的信息。
  
> [!IMPORTANT]
>  请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。 请参阅[最佳做法来保护在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md) 
  
## <a name="tracing-within-the-adapter"></a>跟踪中的适配器  
 BizTalk 适配器包中的适配器记录到跟踪文件，如错误、 警告和信息的不同类别的有用信息。 此类信息可用于了解在适配器中的处理流程和与适配器诊断问题。 你可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，BizTalk 应用程序和 WCF 服务模型应用程序通过将一段摘录添加到各自的配置文件。 此外，您可以启用跟踪，同时在设计时和运行时。  
  
-   **在设计时跟踪**。 对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。  
  
-   **在运行时跟踪**。 对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。  
  
    -   有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。  
  
    -   WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。  
  
 若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，必须添加以下摘录内容中的`<configuration>`标记：  
  
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
  
 这会将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a>适配器 LOB 应用程序之间的跟踪  
 必须启用该适配器与要诊断你怀疑 LOB 应用程序中的问题的 LOB 应用程序之间的通信的跟踪。 适配器还依赖于 LOB 跟踪 （客户端/服务器端），以获取访问此信息。 本文档将从排除启用的 LOB 跟踪功能的详细信息。  
  
 此外，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供的绑定属性 (**日志数据**)，，如果设置为**True**和如果跟踪级别设置为**详细**、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]记录适配器和 Siebel 系统之间的信息流。 此信息以及相同的跟踪文件中的适配器跟踪记录。  
  
 有关此绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  
  
## <a name="viewing-the-traces"></a>查看跟踪内容  
 Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。 有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)。  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>配置 BizTalk 应用程序的跟踪  
 BizTalk 管理控制台，可配置为发送端口等的各种跟踪选项时，接收端口。 跟踪配置设置，您可以跟踪入站/出站事件数据、 消息属性，消息正文和业务流程。 有关配置 BizTalk 应用程序的跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。
  
你还可以使用组中心数据库到[查看跟踪消息和实例数据](../../core/viewing-tracked-message-and-instance-data.md)，包括跟踪的清单和最佳做法。
  
## <a name="see-also"></a>另请参阅  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)