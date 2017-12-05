---
title: "如何启用跟踪中 BAM |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da99e74-a41d-4ab1-a07d-e3bee6187216
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084eaf8cd4ba1c251b1c196830f76ef9c6a8e33f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-tracing-in-bam"></a><span data-ttu-id="f07e3-102">如何在 BAM 中启用跟踪</span><span class="sxs-lookup"><span data-stu-id="f07e3-102">How to Enable Tracing in BAM</span></span>
<span data-ttu-id="f07e3-103">您可以在 BAM 中启用跟踪，以便帮助解决在以下 5 个 BAM 组件中出现的问题：</span><span class="sxs-lookup"><span data-stu-id="f07e3-103">You can enable tracing in BAM to help troubleshoot problems within the following five BAM components:</span></span>  
  
-   <span data-ttu-id="f07e3-104">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="f07e3-104">BAM Management utility</span></span>  
  
-   <span data-ttu-id="f07e3-105">BAM 事件总线</span><span class="sxs-lookup"><span data-stu-id="f07e3-105">BAM event bus</span></span>  
  
-   <span data-ttu-id="f07e3-106">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="f07e3-106">BAM portal</span></span>  
  
-   <span data-ttu-id="f07e3-107">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="f07e3-107">BAM alerting</span></span>  
  
-   <span data-ttu-id="f07e3-108">BAM WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="f07e3-108">BAM WCF Interceptor</span></span>  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a><span data-ttu-id="f07e3-109">为 BAM 管理实用程序启用跟踪</span><span class="sxs-lookup"><span data-stu-id="f07e3-109">Enabling Tracing for the BAM Management Utility</span></span>  
 <span data-ttu-id="f07e3-110">您可以通过为 BAM 管理实用程序启用跟踪，获取与部署错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f07e3-110">You can obtain information about deployment failures by enabling tracing for the BAM Management utility.</span></span> <span data-ttu-id="f07e3-111">可以采取两种方式启用跟踪：</span><span class="sxs-lookup"><span data-stu-id="f07e3-111">You can do this in two ways.</span></span> <span data-ttu-id="f07e3-112">可以通过特定 BM.exe 命令的命令行启用跟踪，或者可以修改 BAM 管理实用程序配置文件来为所有 BM.exe 命令启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-112">You can enable tracing via the command line for specific BM.exe commands, or you can modify the BAM Management utility configuration file to enable tracing for all BM.exe commands.</span></span>  
  
### <a name="using-the-command-line"></a><span data-ttu-id="f07e3-113">使用命令行</span><span class="sxs-lookup"><span data-stu-id="f07e3-113">Using the Command Line</span></span>  
 <span data-ttu-id="f07e3-114">使用激活 BM.exe 命令行跟踪**-跟踪： 在 &#124; 关闭**切换。</span><span class="sxs-lookup"><span data-stu-id="f07e3-114">BM.exe command line tracing is activated using the **-Trace:on&#124;off** switch.</span></span> <span data-ttu-id="f07e3-115">使用 Trace 开关将重写配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="f07e3-115">Using the Trace switch overrides the settings in the configuration file.</span></span>  
  
 <span data-ttu-id="f07e3-116">该开关可与所有标准 BM.exe 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="f07e3-116">The switch is used in conjunction with any normal BM.exe command.</span></span>  
  
 <span data-ttu-id="f07e3-117">例如：</span><span class="sxs-lookup"><span data-stu-id="f07e3-117">For example:</span></span>  
  
 <span data-ttu-id="f07e3-118">**bm.exe 部署全部-DefinitionFile:PO.xml – 跟踪： 上**</span><span class="sxs-lookup"><span data-stu-id="f07e3-118">**bm.exe deploy-all -DefinitionFile:PO.xml –Trace:On**</span></span>  
  
### <a name="using-the-configuration-file"></a><span data-ttu-id="f07e3-119">使用配置文件</span><span class="sxs-lookup"><span data-stu-id="f07e3-119">Using the Configuration File</span></span>  
 <span data-ttu-id="f07e3-120">可以通过修改位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] Tracking 文件夹中的 BM.exe.config 配置文件来启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-120">You can enable tracing by modifying the BM.exe.config configuration file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking folder.</span></span> <span data-ttu-id="f07e3-121">此文件包含**system.diagnostics**部分，其中包含跟踪元素。</span><span class="sxs-lookup"><span data-stu-id="f07e3-121">This file contains a **system.diagnostics** section which contains the tracing elements.</span></span> <span data-ttu-id="f07e3-122">删除注释以便启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-122">Remove the comment to enable tracing.</span></span> <span data-ttu-id="f07e3-123">默认情况下，不启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-123">By default, tracing is not enabled.</span></span>  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a><span data-ttu-id="f07e3-124">为 BAM 事件总线启用跟踪</span><span class="sxs-lookup"><span data-stu-id="f07e3-124">Enabling Tracing for the BAM Event Bus</span></span>  
 <span data-ttu-id="f07e3-125">为 BAM 事件总线启用跟踪可帮助您诊断两类的数据库存储错误：</span><span class="sxs-lookup"><span data-stu-id="f07e3-125">Enabling tracing for the BAM event bus can help you diagnose two classes of database storage errors:</span></span>  
  
-   <span data-ttu-id="f07e3-126">源于使用跟踪配置文件编辑器时发生的 BizTalk Server 服务事件的存储错误。</span><span class="sxs-lookup"><span data-stu-id="f07e3-126">Storage errors originating from events from the BizTalk Server service when using the Tracking Profile Editor.</span></span>  
  
-   <span data-ttu-id="f07e3-127">在使用缓冲的事件流 API 时生成的存储错误。</span><span class="sxs-lookup"><span data-stu-id="f07e3-127">Storage errors generated when using the buffered event stream APIs.</span></span>  
  
 <span data-ttu-id="f07e3-128">若要为 BAM 事件总线启用跟踪，请编辑或添加 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 文件夹中的 BTSNTSvc.exe.config 文件的以下部分。</span><span class="sxs-lookup"><span data-stu-id="f07e3-128">To enable tracing for the BAM event bus, edit or add the following section of the BTSNTSvc.exe.config file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] folder.</span></span>  
  
 `<system.diagnostics>`  
  
 `<switches>`  
  
 `<add name="Microsoft.BizTalk.Bam.EventBus" value="1" />`  
  
 `</switches>`  
  
 `<trace autoflush="true" indentsize="4">`  
  
 `<listeners>`  
  
 `<add name="Text" type="System.Diagnostics.TextWriterTraceListener" initializeData="c:\tdds.log"/>`  
  
 `</listeners>`  
  
 `</trace>`  
  
 `</system.diagnostics>`  
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a><span data-ttu-id="f07e3-129">若要启用 BAM 事件总线跟踪</span><span class="sxs-lookup"><span data-stu-id="f07e3-129">To enable tracing for the BAM Event bus</span></span>  
  
1.  <span data-ttu-id="f07e3-130">编辑 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f07e3-130">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config file.</span></span>  
  
2.  <span data-ttu-id="f07e3-131">找到\<system.diagnostics\>和\</system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="f07e3-131">Locate the \<system.diagnostics\> and \</system.diagnostics\> tag.</span></span> <span data-ttu-id="f07e3-132">如果在该文件中不存在这两个标记，则复制上述代码并将代码粘贴到该配置文件中。</span><span class="sxs-lookup"><span data-stu-id="f07e3-132">If they are not present in the file, copy the code listed above and paste it into the configuration file.</span></span>  
  
3.  <span data-ttu-id="f07e3-133">取消注释取消注释系统诊断部分通过移动结束注释分隔符 (-->) 之后来自\</system.diagnostics\>标记添加到之前\<system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="f07e3-133">Uncomment the Uncomment the system diagnostics section by moving the end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4.  <span data-ttu-id="f07e3-134">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="f07e3-134">Save the file.</span></span>  
  
## <a name="enabling-tracing-for-the-bam-portal"></a><span data-ttu-id="f07e3-135">为 BAM 门户启用跟踪</span><span class="sxs-lookup"><span data-stu-id="f07e3-135">Enabling Tracing for the BAM Portal</span></span>  
 <span data-ttu-id="f07e3-136">为 BAM 门户启用跟踪允许您排除连接问题。</span><span class="sxs-lookup"><span data-stu-id="f07e3-136">Enabling tracing for the BAM portal allows you to troubleshoot connectivity issues.</span></span>  
  
 <span data-ttu-id="f07e3-137">BAM 门户是一种 ASP.NET 应用程序，它采用标准协议进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-137">The BAM portal is an ASP.NET application, and follows the standard protocol for tracing.</span></span> <span data-ttu-id="f07e3-138">在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件没有名为一节\<跟踪\>，可实现。</span><span class="sxs-lookup"><span data-stu-id="f07e3-138">Within the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file, there is a section called \<trace\> which you can enable.</span></span>  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a><span data-ttu-id="f07e3-139">为 BAM 门户启用跟踪</span><span class="sxs-lookup"><span data-stu-id="f07e3-139">To enable tracing for the BAM portal</span></span>  
  
1.  <span data-ttu-id="f07e3-140">编辑 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f07e3-140">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file.</span></span>  
  
2.  <span data-ttu-id="f07e3-141">找到\<system.diagnostics\>和\</system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="f07e3-141">Locate the \<system.diagnostics\> and \</system.diagnostics\> tags.</span></span>  
  
3.  <span data-ttu-id="f07e3-142">取消的系统诊断部分注释有移动结束注释分隔符 (-->) 之后来自\</system.diagnostics\>标记添加到之前\<system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="f07e3-142">Uncomment the system diagnostics section by moving end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4.  <span data-ttu-id="f07e3-143">修改 initializeData 属性以便指定将跟踪日志写入的位置。</span><span class="sxs-lookup"><span data-stu-id="f07e3-143">Modify the initializeData attribute to specify the location to write the tracing log.</span></span>  
  
5.  <span data-ttu-id="f07e3-144">找到\<system.web\>标记。</span><span class="sxs-lookup"><span data-stu-id="f07e3-144">Locate \<system.web\> tag.</span></span>  
  
6.  <span data-ttu-id="f07e3-145">System.web 部分中找到的跟踪标记，并取消跟踪命令注释通过移动分隔符 (-->) 从后到前跟踪标记。</span><span class="sxs-lookup"><span data-stu-id="f07e3-145">In the system.web section locate the trace tag and uncomment the trace command by moving the delimiter ('-->') from after the trace tag to before it.</span></span>  
  
7.  <span data-ttu-id="f07e3-146">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="f07e3-146">Save the file.</span></span>  
  
 `<!--`  
  
 `TRACING: To turn tracing on:`  
  
 `1) Uncomment this tag and specify a file path for trace output`  
  
 `2) Uncomment the <trace tag> under <system.web>`  
  
 `The trace will be saved to the file pointed to by "initializeData" below.`  
  
 `Ensure that the target directory exists (C:\temp by default).`  
  
 `Make sure that the IIS worker process user account (usually Network Service or ASPNET)`  
  
 `and the BAM Portal user have write permissions for the trace log file directory (C:\temp below).`  
  
 `To turn tracing on, you will need to uncomment the <trace> tag under <system.web>`  
  
 `<system.diagnostics>`  
  
 `<trace autoflush="true" indentsize="2">`  
  
 `<listeners>`  
  
 `<add name="BAMPortalListener"`  
  
 `type="System.Diagnostics.TextWriterTraceListener"`  
  
 `initializeData="C:\temp\BAMPortalTrace.log" />`  
  
 `</listeners>`  
  
 `</trace>`  
  
 `</system.diagnostics>`  
  
 `-->`  
  
 `<!--`  
  
 `TRACING: To turn tracing on:`  
  
 `1) Uncomment this tag`  
  
 `2) Uncomment the <system.diagnostics> tag above and specify a file path for trace output`  
  
 `<trace enabled="true"`  
  
 `requestLimit="40"`  
  
 `pageOutput="false"`  
  
 `traceMode="SortByTime"`  
  
 `localOnly="true"`  
  
 `writeToDiagnosticsTrace="true" />`  
  
 `-->`  
  
## <a name="bam-alerting"></a><span data-ttu-id="f07e3-147">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="f07e3-147">BAM Alerting</span></span>  
 <span data-ttu-id="f07e3-148">为 BAM 警报启用跟踪可以帮助您排除警报送达问题。</span><span class="sxs-lookup"><span data-stu-id="f07e3-148">Enabling tracing for BAM alerting helps you troubleshoot alert delivery failures.</span></span>  
  
 <span data-ttu-id="f07e3-149">BAM 警报基于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Notification Services 基础结构。</span><span class="sxs-lookup"><span data-stu-id="f07e3-149">BAM alerting is built on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services infrastructure.</span></span> <span data-ttu-id="f07e3-150">若要启用 BAM 警报的跟踪，请参阅故障排除主题 Notification Services [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416)。</span><span class="sxs-lookup"><span data-stu-id="f07e3-150">To enable tracing on BAM alerting, see the Notification Services troubleshooting topics at [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416).</span></span>  
  
## <a name="bam-interceptors"></a><span data-ttu-id="f07e3-151">BAM 拦截器</span><span class="sxs-lookup"><span data-stu-id="f07e3-151">BAM Interceptors</span></span>  
 <span data-ttu-id="f07e3-152">若要启用 BAM 拦截器的端到端跟踪，可修改应用程序的配置文件-对于 Web 承载的应用程序或 Appname.config 自承载应用程序，为 Web.config。</span><span class="sxs-lookup"><span data-stu-id="f07e3-152">To enable end-to-end tracing of the BAM interceptors, you modify the application’s configuration file—either Web.config for Web-hosted applications, or Appname.config for self-hosted applications.</span></span> <span data-ttu-id="f07e3-153">下面的示例说明如何修改该文件：</span><span class="sxs-lookup"><span data-stu-id="f07e3-153">The following is an example of how you can modify the file:</span></span>  
  
```  
<system.diagnostics>  
  </sources>  
    <source name="Microsoft BizTalk Bam Interceptors" switchValue="All">  
      <listeners>  
  
        <add name="myListener"  
             type="System.Diagnostics.TextWriterTraceListener"  
             initializeData="TextWriterOutput.log" />  
      </listeners>  
    </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="f07e3-154">用于 Windows Workflow Foundation 和 Windows Communication Foundation 的 BAM 侦听器将写入名为“Microsoft BizTalk Bam Interceptors”的源中。</span><span class="sxs-lookup"><span data-stu-id="f07e3-154">BAM Interceptor for Windows Workflow Foundation and Windows Communication Foundation are written to the source named "Microsoft BizTalk Bam Interceptors".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f07e3-155">源字符串区分大小写并且必须与所示内容完全一样。</span><span class="sxs-lookup"><span data-stu-id="f07e3-155">The source string is case-sensitive and must appear exactly as shown.</span></span> <span data-ttu-id="f07e3-156">如果您的字符串不同于所示的字符串，您将收不到 BAM 侦听器的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="f07e3-156">If your string is different than the one shown, you will not receive trace information for the BAM interceptors.</span></span>  
  
 <span data-ttu-id="f07e3-157">您通过设置 switchValue 控制跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="f07e3-157">You control the tracing level by setting switchValue.</span></span> <span data-ttu-id="f07e3-158">下表概括列出了可用的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="f07e3-158">The available tracing levels are summarized in the following table.</span></span>  
  
|<span data-ttu-id="f07e3-159">跟踪级别</span><span class="sxs-lookup"><span data-stu-id="f07e3-159">Trace Level</span></span>|<span data-ttu-id="f07e3-160">Description</span><span class="sxs-lookup"><span data-stu-id="f07e3-160">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f07e3-161">严重</span><span class="sxs-lookup"><span data-stu-id="f07e3-161">Critical</span></span>|<span data-ttu-id="f07e3-162">记录 Fail-Fast 和事件日志条目以及跟踪相关信息。</span><span class="sxs-lookup"><span data-stu-id="f07e3-162">Logs Fail-Fast and Event Log entries, and trace correlation information.</span></span>|  
|<span data-ttu-id="f07e3-163">错误</span><span class="sxs-lookup"><span data-stu-id="f07e3-163">Error</span></span>|<span data-ttu-id="f07e3-164">记录所有异常。</span><span class="sxs-lookup"><span data-stu-id="f07e3-164">Logs all exceptions.</span></span>|  
|<span data-ttu-id="f07e3-165">警告</span><span class="sxs-lookup"><span data-stu-id="f07e3-165">Warning</span></span>|<span data-ttu-id="f07e3-166">存在可能在以后导致出现错误或严重问题的情况。</span><span class="sxs-lookup"><span data-stu-id="f07e3-166">A condition exists that may subsequently result in an error or critical failure.</span></span>|  
|<span data-ttu-id="f07e3-167">信息</span><span class="sxs-lookup"><span data-stu-id="f07e3-167">Information</span></span>|<span data-ttu-id="f07e3-168">生成有助于监视和诊断系统状态、衡量性能或执行分析的消息。</span><span class="sxs-lookup"><span data-stu-id="f07e3-168">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="f07e3-169">您可以利用此类信息来规划容量和管理性能。</span><span class="sxs-lookup"><span data-stu-id="f07e3-169">You can utilize such information for capacity planning and performance management.</span></span>|  
|<span data-ttu-id="f07e3-170">“详细”</span><span class="sxs-lookup"><span data-stu-id="f07e3-170">Verbose</span></span>|<span data-ttu-id="f07e3-171">用于用户代码和服务的调试级别跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-171">Debug-level tracing for both user code and servicing.</span></span>|  
|<span data-ttu-id="f07e3-172">全部</span><span class="sxs-lookup"><span data-stu-id="f07e3-172">All</span></span>|<span data-ttu-id="f07e3-173">所有消息。</span><span class="sxs-lookup"><span data-stu-id="f07e3-173">All messages.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f07e3-174">跟踪可能会对性能有负面影响。</span><span class="sxs-lookup"><span data-stu-id="f07e3-174">Tracing can have an adverse affect on performance.</span></span> <span data-ttu-id="f07e3-175">只在执行故障排除活动时启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="f07e3-175">Only enable tracing when you are performing troubleshooting activities.</span></span>  
  
### <a name="viewing-the-wcf-trace-file"></a><span data-ttu-id="f07e3-176">查看 WCF 跟踪文件</span><span class="sxs-lookup"><span data-stu-id="f07e3-176">Viewing the WCF Trace File</span></span>  
 <span data-ttu-id="f07e3-177">若要分析 WCF 跟踪，可以使用 WCF Service Trace Viewer Tool。</span><span class="sxs-lookup"><span data-stu-id="f07e3-177">To analyze the WCF trace you use the WCF Service Trace Viewer Tool.</span></span> <span data-ttu-id="f07e3-178">有关服务跟踪查看器工具的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)。</span><span class="sxs-lookup"><span data-stu-id="f07e3-178">For more information about the Service Trace Viewer Tool, see [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07e3-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f07e3-179">See Also</span></span>  
 [<span data-ttu-id="f07e3-180">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="f07e3-180">Managing BAM</span></span>](../core/managing-bam.md)