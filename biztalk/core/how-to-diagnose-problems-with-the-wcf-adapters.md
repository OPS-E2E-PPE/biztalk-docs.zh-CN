---
title: 如何诊断 WCF 适配器问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 997a4ecd-6077-45d6-82d3-3f658ca62fd4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab36d7f5873237a3fb895e3ab378b9d637896027
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338221"
---
# <a name="how-to-diagnose-problems-with-the-wcf-adapters"></a>如何诊断 WCF 适配器问题
本部分包含你可以按照可帮助您诊断 WCF 适配器问题的步骤。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>检查 IIS 日志和 HTTPERR 日志中的 IIS 服务器有错误  
  
- 源或目标 IIS 服务器日志文件可以包含有助于解决问题的独立 WCF 适配器的信息。 默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是一个占位符的位置[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]目录在 IIS 服务器上。  
  
   默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]基于的计算机位于以下目录中：  
  
  > [!NOTE]
  >  仅适用于才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]基于计算机。  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
### <a name="use-wcf-message-logging-for-fault-monitoring-and-diagnosis-of-problems-from-the-wcf-adapters"></a>为错误监视和诊断问题从 WCF 适配器使用 WCF 消息日志记录  
  
1. WCF 提供记录传入和传出消息以便脱机使用的功能。 可以使用消息日志记录以查看传入和传出通过 WCF 适配器的消息的外观。 默认情况下，WCF 不记录消息。 若要激活消息日志记录，你必须修改 WCF 适配器使用的配置文件。 有关 WCF 消息日志记录的详细信息，请参阅"消息日志记录"网址[ http://go.microsoft.com/fwlink/?LinkId=89003 ](http://go.microsoft.com/fwlink/?LinkId=89003)。  
  
2. 对于进程内 WCF 适配器，可以通过修改应用程序配置文件中，启用 WCF 消息日志记录**BTSNtSvc.exe.config**，对于**BTSNtSvc.exe**。 配置文件可在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装路径。 如果您安装了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到默认位置，则 BtsNtSvc.exe 将在目录中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
3. 对于独立 WCF 适配器，可以通过修改启用 WCF 消息日志记录**Web.config** BizTalk WCF 服务发布向导创建 Web 应用程序文件夹中的文件。  
  
4. 若要修改**BTSNtSvc.exe.config**或**Web.config**使用记事本，打开配置文件，然后配置 WCF 消息日志记录，如下面的配置示例中所示：  
  
   ```  
   <configuration>  
     <system.serviceModel>  
       <diagnostics>  
         <messageLogging   
              logEntireMessage="true"   
              logMalformedMessages="false"  
              logMessagesAtServiceLevel="true"   
              logMessagesAtTransportLevel="true"  
              maxMessagesToLog="300000"  
              maxSizeOfMessageToLog="200000"   
       />  
       </diagnostics>  
     </system.serviceModel>  
  
     <system.diagnostics>  
       <sources>  
         <source name="System.ServiceModel.MessageLogging">  
           <listeners>  
             <add name="messages"  
             type="System.Diagnostics.XmlWriterTraceListener"  
             initializeData="c:\wcfTrace.e2e" />  
           </listeners>  
         </source>  
       </sources>  
     </system.diagnostics>  
   </configuration>  
   ```  
  
5. 可以使用 Windows Communication Foundation (WCF) 服务跟踪查看器工具来分析 WCF 记录的消息。 服务跟踪查看器包含在 Microsoft Windows 软件开发工具包 (SDK) 适用于 Windows Vista 和[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]运行时组件。 你可以从 Microsoft 下载中心下载 Windows SDK [ http://go.microsoft.com/fwlink/?LinkID=75636 ](http://go.microsoft.com/fwlink/?LinkID=75636)。 有关使用此工具的详细信息，请参阅"Service Trace Viewer Tool (SvcTraceViewer.exe)"at [ http://go.microsoft.com/fwlink/?LinkId=88991 ](http://go.microsoft.com/fwlink/?LinkId=88991)。  
  
### <a name="return-managed-exception-information-to-the-client-in-a-soap-fault-to-ease-debugging"></a>托管的异常信息返回到 SOAP 错误中的客户端以便进行调试  
  
1. 可以选择**错误中包括异常**选项为标准 WCF 接收位置将托管的异常信息返回到 SOAP 错误中的客户端以便进行调试。 使用以下步骤选择**错误中包括异常**选项。  
  
   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开**接收位置**，右键单击使用标准 WCF 适配器的接收位置，然后单击**属性**。  
  
   2. 在中**接收位置属性**对话框中，单击**配置**。  
  
   3. 在传输对话框中，在**消息**选项卡上，选择**错误中包括异常**选项。  
  
2. 如果使用 Wcf-custom 或 Wcf-customisolated 适配器，则可以设置**IncludeExceptionDetailInFaults**的属性[ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004)返回托管的异常信息客户端。 为此，请使用以下步骤：  
  
   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开**接收位置**，右键单击使用 Wcf-custom 或 Wcf-customisolated 适配器的接收位置，然后单击**属性**。  
  
   2. 在中**接收位置属性**对话框中，单击**配置**。  
  
   3. 在传输对话框中，在**行为**选项卡上，右键单击**ServiceBehavior**节点，，然后单击**将扩展添加**。  
  
   4. 在中**选择行为扩展**对话框中，选择**serviceDebug**，然后单击**确定**。  
  
   5. 在传输对话框中，在**行为**选项卡上，单击**serviceDebug**节点，并选择**True**为**includeExceptionDetail**中的属性**配置**列表视图。  
  
   > [!NOTE]
   >  将托管的异常信息返回到客户端可能存在安全风险，因为异常详细信息公开有关内部服务实现可能被未经授权的客户端使用的信息。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [WCF 适配器疑难解答](../core/troubleshooting-the-wcf-adapters.md)   
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)