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
ms.openlocfilehash: c9bcb513704753363e054d689d2409925ffcd483
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995382"
---
# <a name="how-to-diagnose-problems-with-the-wcf-adapters"></a><span data-ttu-id="e0c32-102">如何诊断 WCF 适配器问题</span><span class="sxs-lookup"><span data-stu-id="e0c32-102">How to Diagnose Problems with the WCF Adapters</span></span>
<span data-ttu-id="e0c32-103">本部分提供诊断 WCF 适配器问题所需遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="e0c32-103">This section contains steps that you can follow to help diagnose problems with the WCF adapters.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="e0c32-104">检查 IIS 日志和 HTTPERR 日志中的 IIS 服务器有错误</span><span class="sxs-lookup"><span data-stu-id="e0c32-104">Check the IIS log and HTTPERR log of the IIS server for errors</span></span>  
  
- <span data-ttu-id="e0c32-105">源或目标 IIS 服务器日志文件中可能包含有助于排除独立 WCF 适配器的故障的信息。</span><span class="sxs-lookup"><span data-stu-id="e0c32-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the isolated WCF adapters.</span></span> <span data-ttu-id="e0c32-106">默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e0c32-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="e0c32-107"><em>%Windir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="e0c32-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e0c32-108">*%Windir%* 是一个占位符的位置[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]目录在 IIS 服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0c32-108">*%WinDir%* is a placeholder for the location of the [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directory on the IIS server.</span></span>  
  
   <span data-ttu-id="e0c32-109">默认情况下，在基于 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的计算机上，HTTPERR 日志文件位于下面的目录中：</span><span class="sxs-lookup"><span data-stu-id="e0c32-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] based computers are located in the following directory:</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e0c32-110">只有基于 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的计算机上才有 HTTPERR 日志文件。</span><span class="sxs-lookup"><span data-stu-id="e0c32-110">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] based computers.</span></span>  
  
   <span data-ttu-id="e0c32-111"><em>%Windir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="e0c32-111"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
### <a name="use-wcf-message-logging-for-fault-monitoring-and-diagnosis-of-problems-from-the-wcf-adapters"></a><span data-ttu-id="e0c32-112">使用 WCF 消息记录从 WCF 适配器进行故障监视和问题诊断</span><span class="sxs-lookup"><span data-stu-id="e0c32-112">Use WCF message logging for fault monitoring and diagnosis of problems from the WCF adapters</span></span>  
  
1. <span data-ttu-id="e0c32-113">WCF 提供记录传入消息和传出消息以便脱机使用这一功能。</span><span class="sxs-lookup"><span data-stu-id="e0c32-113">WCF provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="e0c32-114">可以使用消息记录来查看通过 WCF 适配器传入和传出的是什么消息。</span><span class="sxs-lookup"><span data-stu-id="e0c32-114">You can use message logging to see what the messages incoming and outgoing through the WCF adapters look like.</span></span> <span data-ttu-id="e0c32-115">默认情况下，WCF 不记录消息。</span><span class="sxs-lookup"><span data-stu-id="e0c32-115">WCF does not log messages by default.</span></span> <span data-ttu-id="e0c32-116">若要激活消息记录，您必须修改 WCF 适配器使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="e0c32-116">To activate message logging, you have to modify the configuration files that the WCF adapters use.</span></span> <span data-ttu-id="e0c32-117">有关 WCF 消息日志记录的详细信息，请参阅"消息日志记录"网址[ http://go.microsoft.com/fwlink/?LinkId=89003 ](http://go.microsoft.com/fwlink/?LinkId=89003)。</span><span class="sxs-lookup"><span data-stu-id="e0c32-117">For more information about WCF message logging, see "Message Logging" at [http://go.microsoft.com/fwlink/?LinkId=89003](http://go.microsoft.com/fwlink/?LinkId=89003).</span></span>  
  
2. <span data-ttu-id="e0c32-118">对于进程内 WCF 适配器，可以通过修改应用程序配置文件中，启用 WCF 消息日志记录**BTSNtSvc.exe.config**，对于**BTSNtSvc.exe**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-118">For the in-process WCF adapters, you can enable WCF message logging by modifying the application configuration file, **BTSNtSvc.exe.config**, for **BTSNtSvc.exe**.</span></span> <span data-ttu-id="e0c32-119">此配置文件位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装路径中。</span><span class="sxs-lookup"><span data-stu-id="e0c32-119">The configuration file can be found in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation path.</span></span> <span data-ttu-id="e0c32-120">如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装在默认位置，则 BtsNtSvc.exe 将在目录 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 中。</span><span class="sxs-lookup"><span data-stu-id="e0c32-120">If you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3. <span data-ttu-id="e0c32-121">对于独立 WCF 适配器，可以通过修改启用 WCF 消息日志记录**Web.config** BizTalk WCF 服务发布向导创建 Web 应用程序文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="e0c32-121">For the isolated WCF adapters, you can enable WCF message logging by modifying the **Web.config** file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder.</span></span>  
  
4. <span data-ttu-id="e0c32-122">若要修改**BTSNtSvc.exe.config**或**Web.config**使用记事本，打开配置文件，然后配置 WCF 消息日志记录，如下面的配置示例中所示：</span><span class="sxs-lookup"><span data-stu-id="e0c32-122">To modify **BTSNtSvc.exe.config** or **Web.config**, open the configuration file by using Notepad, and then configure WCF message logging, as indicated in the following configuration example:</span></span>  
  
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
  
5. <span data-ttu-id="e0c32-123">您可以使用 Windows Communication Foundation (WCF) Service Trace Viewer Tool 来分析 WCF 记录的消息。</span><span class="sxs-lookup"><span data-stu-id="e0c32-123">You can use the Windows Communication Foundation (WCF) Service Trace Viewer Tool to analyze messages logged by WCF.</span></span> <span data-ttu-id="e0c32-124">Service Trace Viewer 包含在 Windows Vista 和 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 运行时组件的 Microsoft Windows 软件开发工具包 (SDK) 中。</span><span class="sxs-lookup"><span data-stu-id="e0c32-124">Service Trace Viewer is included in the Microsoft Windows Software Development Kit (SDK) for Windows Vista and [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Runtime Components.</span></span> <span data-ttu-id="e0c32-125">你可以从 Microsoft 下载中心下载 Windows SDK [ http://go.microsoft.com/fwlink/?LinkID=75636 ](http://go.microsoft.com/fwlink/?LinkID=75636)。</span><span class="sxs-lookup"><span data-stu-id="e0c32-125">You can download the Windows SDK from the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=75636](http://go.microsoft.com/fwlink/?LinkID=75636).</span></span> <span data-ttu-id="e0c32-126">有关使用此工具的详细信息，请参阅"Service Trace Viewer Tool (SvcTraceViewer.exe)"at [ http://go.microsoft.com/fwlink/?LinkId=88991 ](http://go.microsoft.com/fwlink/?LinkId=88991)。</span><span class="sxs-lookup"><span data-stu-id="e0c32-126">For more information about using this tool, see "Service Trace Viewer Tool (SvcTraceViewer.exe)"at [http://go.microsoft.com/fwlink/?LinkId=88991](http://go.microsoft.com/fwlink/?LinkId=88991).</span></span>  
  
### <a name="return-managed-exception-information-to-the-client-in-a-soap-fault-to-ease-debugging"></a><span data-ttu-id="e0c32-127">将托管异常信息包括在 SOAP 错误中返回给客户端以便进行调试</span><span class="sxs-lookup"><span data-stu-id="e0c32-127">Return managed exception information to the client in a SOAP fault to ease debugging</span></span>  
  
1. <span data-ttu-id="e0c32-128">可以选择**错误中包括异常**选项为标准 WCF 接收位置将托管的异常信息返回到 SOAP 错误中的客户端以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="e0c32-128">You can select the **Include exception in faults** option for the standard WCF receive location to return managed exception information to the client in SOAP faults to ease debugging.</span></span> <span data-ttu-id="e0c32-129">使用以下步骤选择**错误中包括异常**选项。</span><span class="sxs-lookup"><span data-stu-id="e0c32-129">Use the following steps to select the **Include exception in faults** option.</span></span>  
  
   1. <span data-ttu-id="e0c32-130">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开**接收位置**，右键单击使用标准 WCF 适配器的接收位置，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand **Receive Locations**, right-click a receive location using a standard WCF adapter, and then click **Properties**.</span></span>  
  
   2. <span data-ttu-id="e0c32-131">在中**接收位置属性**对话框中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-131">In the **Receive Location Properties** dialog box, click **Configure**.</span></span>  
  
   3. <span data-ttu-id="e0c32-132">在传输对话框中，在**消息**选项卡上，选择**错误中包括异常**选项。</span><span class="sxs-lookup"><span data-stu-id="e0c32-132">In the transport dialog box, on the **Messages** tab, select the **Include exception in faults** option.</span></span>  
  
2. <span data-ttu-id="e0c32-133">如果使用 Wcf-custom 或 Wcf-customisolated 适配器，则可以设置**IncludeExceptionDetailInFaults**的属性[ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004)返回托管的异常信息客户端。</span><span class="sxs-lookup"><span data-stu-id="e0c32-133">If you use the WCF-Custom or the WCF-CustomIsolated adapter, you can set the **IncludeExceptionDetailInFaults** property of the [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004) to return managed exception information to the client.</span></span> <span data-ttu-id="e0c32-134">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e0c32-134">To do so, use the following steps:</span></span>  
  
   1. <span data-ttu-id="e0c32-135">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开**接收位置**，右键单击使用 Wcf-custom 或 Wcf-customisolated 适配器的接收位置，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-135">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand **Receive Locations**, right-click a receive location using the WCF-Custom or the WCF-CustomIsolated adapter, and then click **Properties**.</span></span>  
  
   2. <span data-ttu-id="e0c32-136">在中**接收位置属性**对话框中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-136">In the **Receive Location Properties** dialog box, click **Configure**.</span></span>  
  
   3. <span data-ttu-id="e0c32-137">在传输对话框中，在**行为**选项卡上，右键单击**ServiceBehavior**节点，，然后单击**将扩展添加**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-137">In the transport dialog box, on the **Behavior** tab, right-click the **ServiceBehavior** node, and then click **Add extension**.</span></span>  
  
   4. <span data-ttu-id="e0c32-138">在中**选择行为扩展**对话框中，选择**serviceDebug**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e0c32-138">In the **Select Behavior Extension** dialog box, select **serviceDebug**, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="e0c32-139">在传输对话框中，在**行为**选项卡上，单击**serviceDebug**节点，并选择**True**为**includeExceptionDetail**中的属性**配置**列表视图。</span><span class="sxs-lookup"><span data-stu-id="e0c32-139">In the transport dialog box, on the **Behavior** tab, click the **serviceDebug** node, and then select **True** for the **includeExceptionDetail** property in the **Configuration** list view.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e0c32-140">将托管异常信息返回给客户端可能会带来安全风险，原因是异常详细信息会公开有关内部服务实现的信息，而这些信息可能会被未经授权客户端使用。</span><span class="sxs-lookup"><span data-stu-id="e0c32-140">Returning managed exception information to clients can be a security risk because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c32-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0c32-141">See Also</span></span>  
 <span data-ttu-id="e0c32-142">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="e0c32-142">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 <span data-ttu-id="e0c32-143">[WCF 适配器疑难解答](../core/troubleshooting-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e0c32-143">[Troubleshooting the WCF Adapters](../core/troubleshooting-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="e0c32-144">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="e0c32-144">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)