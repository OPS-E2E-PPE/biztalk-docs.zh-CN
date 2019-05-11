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
ms.openlocfilehash: 78b3a3d59619df42070fdbed3508fbafb2b37c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369836"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a>诊断跟踪和消息日志记录中的 SQL 适配器
诊断跟踪有助于有效地诊断使用适配器时可能遇到的问题。 适配器客户端可以激活在两个级别的诊断跟踪：  
  
- 适配器客户端和适配器之间  
  
- 适配器内  
  
  本部分提供有关激活在以下级别的跟踪信息。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>适配器客户端和适配器之间的跟踪  
 适配器客户端可以启用 WCF 跟踪适配器客户端和适配器之间的跟踪问题。 WCF 跟踪用于跟踪来自适配器客户端使用 WCF 服务模型，并且可在诊断序列化问题的输入的 XML。 WCF 通道模型或从适配器到适配器客户端的输出消息，不使用 WCF 跟踪。 通过将一段摘录添加到各自的配置文件，可以激活 BizTalk 应用程序和 WCF 服务模型应用程序的 WCF 跟踪。 此外，可以启用跟踪都在设计时和运行时。  
  
- **在设计时跟踪**。 为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。  
  
- **在运行时跟踪**。 对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。  
  
  - 有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。  
  
  - 为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。  
  
  若要启用 WCF 跟踪，请添加以下摘录中的`<configuration>`标记。  
  
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
  
 这将 WCF 跟踪保存到 C:\log\WCFTrace.svclog。 有关 WCF 跟踪的详细信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。  
  
> [!IMPORTANT]
>  请确保减轻暴露敏感业务数据通过启用跟踪的潜在安全威胁。 有关建议，请参阅[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)。
  
## <a name="tracing-within-the-adapter"></a>在适配器跟踪  
 适配器记录到跟踪文件，例如错误、 警告和信息性消息的不同类别的有用信息。 此类信息可了解该适配器中的过程流和诊断适配器的问题。 可以激活[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪的 BizTalk 应用程序和 WCF 服务模型应用程序通过向各自的配置文件添加一段摘录。 此外，可以启用跟踪都在设计时和运行时。  
  
- **在设计时跟踪**。 为设计时体验，你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 所有这些工具可以从使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 因此，若要启用跟踪的设计时体验，您必须添加摘录到 devenv.exe.config 文件位于*\<安装驱动器\>*: \Program Files\Microsoft Visual Studio *\<版本\>* \Common7\IDE。  
  
- **在运行时跟踪**。 对于运行时跟踪，必须添加具体取决于您使用的应用程序的摘录。  
  
  - 有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，必须将摘录内容添加到 BizTalk 配置文件中，BTSNTSvc.exe.config 通常。对于 BizTalk Server 中，此文件将出现通常下\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。  
  
  - 为 WCF 服务模型.NET 应用程序，必须将摘录内容添加到你的项目的 app.config 文件。  
  
  若要启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和适配器跟踪，添加以下摘录中的`<configuration>`标记。  
  
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
  
 这将 WCF 跟踪保存到 C:\log\AdapterTrace.svclog。  
  
## <a name="viewing-the-traces"></a>查看跟踪内容  
 Windows Communication Foundation (WCF) 服务跟踪查看器工具可用于查看跟踪。 有关工具的详细信息，请参阅[使用服务跟踪查看器查看相关跟踪和时遇到问题](https://msdn.microsoft.com/library/aa751795.aspx)。
  
## <a name="configuring-tracking-for-biztalk-applications"></a>为 BizTalk 应用程序配置跟踪  
 在 BizTalk Server 管理控制台，可以配置各种跟踪选项的项，如发送端口和接收端口。 跟踪配置设置，可跟踪入站和出站事件数据、 消息属性、 消息正文和业务流程。 有关为 BizTalk 应用程序配置跟踪的详细信息，请参阅[管理项目](../../core/managing-artifacts.md)。
  
 此外可以使用运行状况与活动跟踪 (HAT) 来查看历史记录或跟踪数据。 有关详细信息，请参阅[查看历史记录和跟踪数据](../../core/viewing-historical-and-tracked-data.md)。
  
## <a name="see-also"></a>请参阅  
 [SQL 适配器疑难解答](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)