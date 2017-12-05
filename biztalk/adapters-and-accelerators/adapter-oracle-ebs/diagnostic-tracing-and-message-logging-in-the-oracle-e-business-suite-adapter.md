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
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a>诊断跟踪和消息日志记录与 Oracle E-business Suite 适配器中
诊断跟踪有助于有效地诊断都使用适配器时可能遇到的问题。 本主题提供有关以下三种类型的支持的跟踪信息[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   Oracle 服务器端跟踪使用客户端标识符
  
-   适配器客户端和适配器之间的 WCF 跟踪
  
-   适配器中的 WCF 跟踪
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a>Oracle 服务器端跟踪使用客户端标识符  
 Oracle 允许你对 Oracle 数据库的客户端应用程序执行的操作执行服务器端跟踪。 由于可以将从客户端应用程序请求路由到不同的数据库会话，它将成为难以跟踪该请求的源。 但是，Oracle 便于端到端应用程序跟踪使用客户端标识符。 
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开`OracleConnectionClientId`绑定属性，它允许你在该适配器用于连接到 Oracle 的连接的设计时指定的客户端标识符。 适配器客户端标识符可帮助你在选择性跟踪中的适配器上的客户端 Oracle，执行的操作，还允许你筛选和查看 Oracle 服务器跟踪基于客户端标识符。 有关如何启用 Oracle 中的客户端标识符的跟踪的信息，请参阅[http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746)。  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>适配器客户端和适配器之间的 WCF 跟踪  
 适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。 WCF 跟踪用于跟踪的输入的 XML，来自适配器客户端，通过使用 WCF 服务模型，而在诊断序列化问题非常有用。 WCF 跟踪不用于 WCF 通道模型或从适配器到适配器客户端的输出消息。 可以通过将一段摘录添加到各自的配置文件来激活对 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。 此外，您可以启用跟踪，同时在设计时和运行时。  
  
-   **在设计时跟踪**。 对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。  
  
-   **在运行时跟踪**。 对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。  
  
    -   有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。  
  
    -   WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。  
  
 若要启用 WCF 跟踪，添加以下摘录内容中的`<configuration>`标记：  
  
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
  
 这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。 [WCF 跟踪](https://msdn.microsoft.com/library/ms730342.aspx)提供了详细信息。  
  
> [!IMPORTANT]
>  请确保减轻暴露敏感业务数据，可以启用跟踪时导致的潜在安全威胁。 有关建议，请参阅[消息和实例数据跟踪的最佳做法](../../core/best-practices-for-message-and-instance-data-tracking.md)。  
  
## <a name="wcf-tracing-within-the-adapter"></a>适配器中的 WCF 跟踪  
 适配器登录到跟踪文件，如错误、 警告和信息性消息的不同类别的有用信息。 此类信息可用于了解在适配器中的处理流程和与适配器诊断问题。 你可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，BizTalk 应用程序和 WCF 服务模型应用程序通过将一段摘录添加到各自的配置文件。 此外，您可以启用跟踪，同时在设计时和运行时。  
  
-   **在设计时跟踪**。 对于设计时体验，你可能使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 因此，若要启用跟踪的设计时体验，你必须添加摘录 devenv.exe.config 文件位于*\<安装驱动器\>*: files\microsoft Visual Studio *\<版本\>*\Common7\IDE。  
  
-   **在运行时跟踪**。 对于运行时跟踪，必须添加具体取决于你使用的应用程序的摘要。  
  
    -   有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，你必须添加到 BizTalk 配置文件，通常 BTSNTSvc.exe.config 摘录。有关[!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)]，此文件位于通常下\<安装驱动器\>: files\microsoft [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]。 BizTalk Server 中，为此文件位于通常下\<安装驱动器\>: files\microsoft BizTalk Server。  
  
    -   WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。  
  
 若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录内容中的`<configuration>`标记：  
  
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
  
 这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。  
  
## <a name="viewing-the-traces"></a>查看跟踪内容  
 Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。 [使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)提供有关此工具的更多详细信息。  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>配置 BizTalk 应用程序的跟踪  
 BizTalk Server 管理控制台允许你配置的项目例如发送端口的各种跟踪选项，并接收端口。 跟踪配置设置，您可以跟踪入站和出站事件数据、 消息属性，消息正文和业务流程。 有关配置 BizTalk 应用程序的跟踪的详细信息，请参阅[管理和跟踪你的项目](../../core/managing-artifacts.md)。  
  
 你还可以使用组中心数据库到[查看跟踪的消息和实例数据](../../core/viewing-tracked-message-and-instance-data.md)，包括最佳实践，保存跟踪查询，和的详细信息。
  
## <a name="see-also"></a>另请参阅  
[故障排除适配器](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)