---
title: 如何在 BAM 中启用跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da99e74-a41d-4ab1-a07d-e3bee6187216
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cb5aaa9e1876637a78a36f77aa4cb63aa56ce0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385078"
---
# <a name="how-to-enable-tracing-in-bam"></a><span data-ttu-id="7a42e-102">如何在 BAM 中启用跟踪</span><span class="sxs-lookup"><span data-stu-id="7a42e-102">How to Enable Tracing in BAM</span></span>
<span data-ttu-id="7a42e-103">您可以启用跟踪在 BAM 中以帮助解决以下 5 个 BAM 组件中的问题：</span><span class="sxs-lookup"><span data-stu-id="7a42e-103">You can enable tracing in BAM to help troubleshoot problems within the following five BAM components:</span></span>  
  
-   <span data-ttu-id="7a42e-104">BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="7a42e-104">BAM Management utility</span></span>  
  
-   <span data-ttu-id="7a42e-105">BAM 事件总线</span><span class="sxs-lookup"><span data-stu-id="7a42e-105">BAM event bus</span></span>  
  
-   <span data-ttu-id="7a42e-106">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="7a42e-106">BAM portal</span></span>  
  
-   <span data-ttu-id="7a42e-107">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="7a42e-107">BAM alerting</span></span>  
  
-   <span data-ttu-id="7a42e-108">BAM WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="7a42e-108">BAM WCF Interceptor</span></span>  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a><span data-ttu-id="7a42e-109">为 BAM 管理实用程序启用跟踪</span><span class="sxs-lookup"><span data-stu-id="7a42e-109">Enabling Tracing for the BAM Management Utility</span></span>  
 <span data-ttu-id="7a42e-110">可以通过为 BAM 管理实用程序启用跟踪来获取有关部署失败的信息。</span><span class="sxs-lookup"><span data-stu-id="7a42e-110">You can obtain information about deployment failures by enabling tracing for the BAM Management utility.</span></span> <span data-ttu-id="7a42e-111">可以通过两种方式来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7a42e-111">You can do this in two ways.</span></span> <span data-ttu-id="7a42e-112">可以启用跟踪通过特定 BM.exe 命令，在命令行，或者可以修改 BAM 管理实用程序配置文件来为所有 BM.exe 命令启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a42e-112">You can enable tracing via the command line for specific BM.exe commands, or you can modify the BAM Management utility configuration file to enable tracing for all BM.exe commands.</span></span>  
  
### <a name="using-the-command-line"></a><span data-ttu-id="7a42e-113">使用命令行</span><span class="sxs-lookup"><span data-stu-id="7a42e-113">Using the Command Line</span></span>  
 <span data-ttu-id="7a42e-114">使用激活 BM.exe 命令行跟踪 **-跟踪： 在&#124;关闭**切换。</span><span class="sxs-lookup"><span data-stu-id="7a42e-114">BM.exe command line tracing is activated using the **-Trace:on&#124;off** switch.</span></span> <span data-ttu-id="7a42e-115">使用 Trace 开关将重写配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="7a42e-115">Using the Trace switch overrides the settings in the configuration file.</span></span>  
  
 <span data-ttu-id="7a42e-116">与所有标准 BM.exe 命令一起使用的开关。</span><span class="sxs-lookup"><span data-stu-id="7a42e-116">The switch is used in conjunction with any normal BM.exe command.</span></span>  
  
 <span data-ttu-id="7a42e-117">例如：</span><span class="sxs-lookup"><span data-stu-id="7a42e-117">For example:</span></span>  
  
 <span data-ttu-id="7a42e-118">**bm.exe deploy-all -DefinitionFile:PO.xml –Trace:On**</span><span class="sxs-lookup"><span data-stu-id="7a42e-118">**bm.exe deploy-all -DefinitionFile:PO.xml –Trace:On**</span></span>  
  
### <a name="using-the-configuration-file"></a><span data-ttu-id="7a42e-119">使用配置文件</span><span class="sxs-lookup"><span data-stu-id="7a42e-119">Using the Configuration File</span></span>  
 <span data-ttu-id="7a42e-120">可以通过修改位于中的 BM.exe.config 配置文件启用跟踪[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪文件夹。</span><span class="sxs-lookup"><span data-stu-id="7a42e-120">You can enable tracing by modifying the BM.exe.config configuration file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking folder.</span></span> <span data-ttu-id="7a42e-121">此文件包含**system.diagnostics**部分，其中包含跟踪元素。</span><span class="sxs-lookup"><span data-stu-id="7a42e-121">This file contains a **system.diagnostics** section which contains the tracing elements.</span></span> <span data-ttu-id="7a42e-122">删除注释以便启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a42e-122">Remove the comment to enable tracing.</span></span> <span data-ttu-id="7a42e-123">默认情况下不启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a42e-123">By default, tracing is not enabled.</span></span>  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a><span data-ttu-id="7a42e-124">为 BAM 事件总线启用跟踪</span><span class="sxs-lookup"><span data-stu-id="7a42e-124">Enabling Tracing for the BAM Event Bus</span></span>  
 <span data-ttu-id="7a42e-125">为 BAM 事件总线启用跟踪可以帮助您诊断数据库存储错误的两个类：</span><span class="sxs-lookup"><span data-stu-id="7a42e-125">Enabling tracing for the BAM event bus can help you diagnose two classes of database storage errors:</span></span>  
  
- <span data-ttu-id="7a42e-126">使用跟踪配置文件编辑器时源自来自 BizTalk Server 服务的事件存储错误。</span><span class="sxs-lookup"><span data-stu-id="7a42e-126">Storage errors originating from events from the BizTalk Server service when using the Tracking Profile Editor.</span></span>  
  
- <span data-ttu-id="7a42e-127">使用缓冲的事件流 Api 时生成的存储错误。</span><span class="sxs-lookup"><span data-stu-id="7a42e-127">Storage errors generated when using the buffered event stream APIs.</span></span>  
  
  <span data-ttu-id="7a42e-128">若要启用跟踪的 BAM 事件总线，请编辑或添加以下部分中的 BTSNTSvc.exe.config 文件的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]文件夹。</span><span class="sxs-lookup"><span data-stu-id="7a42e-128">To enable tracing for the BAM event bus, edit or add the following section of the BTSNTSvc.exe.config file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] folder.</span></span>  
  
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
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a><span data-ttu-id="7a42e-129">若要为 BAM 事件总线启用跟踪</span><span class="sxs-lookup"><span data-stu-id="7a42e-129">To enable tracing for the BAM Event bus</span></span>  
  
1. <span data-ttu-id="7a42e-130">编辑[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="7a42e-130">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config file.</span></span>  
  
2. <span data-ttu-id="7a42e-131">找到\<system.diagnostics\>并\</system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="7a42e-131">Locate the \<system.diagnostics\> and \</system.diagnostics\> tag.</span></span> <span data-ttu-id="7a42e-132">如果它们不存在的文件中，复制上面列出的代码，并将其粘贴到配置文件。</span><span class="sxs-lookup"><span data-stu-id="7a42e-132">If they are not present in the file, copy the code listed above and paste it into the configuration file.</span></span>  
  
3. <span data-ttu-id="7a42e-133">取消的注释系统诊断节通过移动结束注释分隔符 (-->) 从后\</system.diagnostics\>标记添加到之前\<system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="7a42e-133">Uncomment the Uncomment the system diagnostics section by moving the end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4. <span data-ttu-id="7a42e-134">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="7a42e-134">Save the file.</span></span>  
  
## <a name="enabling-tracing-for-the-bam-portal"></a><span data-ttu-id="7a42e-135">为 BAM 门户启用跟踪</span><span class="sxs-lookup"><span data-stu-id="7a42e-135">Enabling Tracing for the BAM Portal</span></span>  
 <span data-ttu-id="7a42e-136">为 BAM 门户启用跟踪，可对连接问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="7a42e-136">Enabling tracing for the BAM portal allows you to troubleshoot connectivity issues.</span></span>  
  
 <span data-ttu-id="7a42e-137">BAM 门户是 ASP.NET 应用程序，并遵循标准协议进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a42e-137">The BAM portal is an ASP.NET application, and follows the standard protocol for tracing.</span></span> <span data-ttu-id="7a42e-138">内[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件中，还有一个名为部分\<跟踪\>，可实现。</span><span class="sxs-lookup"><span data-stu-id="7a42e-138">Within the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file, there is a section called \<trace\> which you can enable.</span></span>  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a><span data-ttu-id="7a42e-139">若要为 BAM 门户启用跟踪</span><span class="sxs-lookup"><span data-stu-id="7a42e-139">To enable tracing for the BAM portal</span></span>  
  
1. <span data-ttu-id="7a42e-140">编辑[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="7a42e-140">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file.</span></span>  
  
2. <span data-ttu-id="7a42e-141">找到\<system.diagnostics\>并\</system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="7a42e-141">Locate the \<system.diagnostics\> and \</system.diagnostics\> tags.</span></span>  
  
3. <span data-ttu-id="7a42e-142">通过移动结束注释分隔符来取消注释系统诊断部分 (-->) 从后\</system.diagnostics\>标记添加到之前\<system.diagnostics\>标记。</span><span class="sxs-lookup"><span data-stu-id="7a42e-142">Uncomment the system diagnostics section by moving end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4. <span data-ttu-id="7a42e-143">修改 initializeData 属性以便指定要写入跟踪日志的位置。</span><span class="sxs-lookup"><span data-stu-id="7a42e-143">Modify the initializeData attribute to specify the location to write the tracing log.</span></span>  
  
5. <span data-ttu-id="7a42e-144">找到\<system.web\>标记。</span><span class="sxs-lookup"><span data-stu-id="7a42e-144">Locate \<system.web\> tag.</span></span>  
  
6. <span data-ttu-id="7a42e-145">在 system.web 节中找到跟踪标记并取消注释跟踪命令移动分隔符 (-->) 从后到前的跟踪标记。</span><span class="sxs-lookup"><span data-stu-id="7a42e-145">In the system.web section locate the trace tag and uncomment the trace command by moving the delimiter ('-->') from after the trace tag to before it.</span></span>  
  
7. <span data-ttu-id="7a42e-146">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="7a42e-146">Save the file.</span></span>  
  
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
  
## <a name="bam-alerting"></a><span data-ttu-id="7a42e-147">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="7a42e-147">BAM Alerting</span></span>  
 <span data-ttu-id="7a42e-148">为 BAM 警报可帮助您排除警报送达问题启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a42e-148">Enabling tracing for BAM alerting helps you troubleshoot alert delivery failures.</span></span>  
  
 <span data-ttu-id="7a42e-149">BAM 警报基于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Notification Services 基础结构。</span><span class="sxs-lookup"><span data-stu-id="7a42e-149">BAM alerting is built on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services infrastructure.</span></span> <span data-ttu-id="7a42e-150">若要启用对 BAM 警报的跟踪，请参阅通知服务疑难解答主题，网址[ http://go.microsoft.com/fwlink/?LinkId=79416 ](http://go.microsoft.com/fwlink/?LinkId=79416)。</span><span class="sxs-lookup"><span data-stu-id="7a42e-150">To enable tracing on BAM alerting, see the Notification Services troubleshooting topics at [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416).</span></span>  
  
## <a name="bam-interceptors"></a><span data-ttu-id="7a42e-151">BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="7a42e-151">BAM Interceptors</span></span>  
 <span data-ttu-id="7a42e-152">若要启用端到端跟踪的 BAM 侦听器，你修改应用程序的配置文件 — 的 Web 承载的应用程序，appname.config 自承载应用程序的 Web.config。</span><span class="sxs-lookup"><span data-stu-id="7a42e-152">To enable end-to-end tracing of the BAM interceptors, you modify the application’s configuration file—either Web.config for Web-hosted applications, or Appname.config for self-hosted applications.</span></span> <span data-ttu-id="7a42e-153">下面是举例说明如何修改该文件：</span><span class="sxs-lookup"><span data-stu-id="7a42e-153">The following is an example of how you can modify the file:</span></span>  
  
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
  
 <span data-ttu-id="7a42e-154">Windows Workflow Foundation 的 BAM 侦听器和 Windows Communication Foundation 将写入到名为"Microsoft BizTalk Bam Interceptors"的源。</span><span class="sxs-lookup"><span data-stu-id="7a42e-154">BAM Interceptor for Windows Workflow Foundation and Windows Communication Foundation are written to the source named "Microsoft BizTalk Bam Interceptors".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a42e-155">源字符串区分大小写，必须严格按所示出现。</span><span class="sxs-lookup"><span data-stu-id="7a42e-155">The source string is case-sensitive and must appear exactly as shown.</span></span> <span data-ttu-id="7a42e-156">如果您的字符串是不同于所示，不会收到 BAM 侦听器跟踪的信息。</span><span class="sxs-lookup"><span data-stu-id="7a42e-156">If your string is different than the one shown, you will not receive trace information for the BAM interceptors.</span></span>  
  
 <span data-ttu-id="7a42e-157">通过设置 switchValue 控制跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="7a42e-157">You control the tracing level by setting switchValue.</span></span> <span data-ttu-id="7a42e-158">下表总结了可用的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="7a42e-158">The available tracing levels are summarized in the following table.</span></span>  
  
|<span data-ttu-id="7a42e-159">跟踪级别</span><span class="sxs-lookup"><span data-stu-id="7a42e-159">Trace Level</span></span>|<span data-ttu-id="7a42e-160">Description</span><span class="sxs-lookup"><span data-stu-id="7a42e-160">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7a42e-161">严重</span><span class="sxs-lookup"><span data-stu-id="7a42e-161">Critical</span></span>|<span data-ttu-id="7a42e-162">记录 Fail-fast 和事件日志条目，并跟踪相关信息。</span><span class="sxs-lookup"><span data-stu-id="7a42e-162">Logs Fail-Fast and Event Log entries, and trace correlation information.</span></span>|  
|<span data-ttu-id="7a42e-163">错误</span><span class="sxs-lookup"><span data-stu-id="7a42e-163">Error</span></span>|<span data-ttu-id="7a42e-164">记录所有异常。</span><span class="sxs-lookup"><span data-stu-id="7a42e-164">Logs all exceptions.</span></span>|  
|<span data-ttu-id="7a42e-165">警告</span><span class="sxs-lookup"><span data-stu-id="7a42e-165">Warning</span></span>|<span data-ttu-id="7a42e-166">存在某种情况随后可能会导致错误或严重故障。</span><span class="sxs-lookup"><span data-stu-id="7a42e-166">A condition exists that may subsequently result in an error or critical failure.</span></span>|  
|<span data-ttu-id="7a42e-167">信息</span><span class="sxs-lookup"><span data-stu-id="7a42e-167">Information</span></span>|<span data-ttu-id="7a42e-168">生成消息有助于监视和诊断系统状态、 测量性能，或执行分析。</span><span class="sxs-lookup"><span data-stu-id="7a42e-168">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="7a42e-169">可以使用此类信息规划容量和性能管理。</span><span class="sxs-lookup"><span data-stu-id="7a42e-169">You can utilize such information for capacity planning and performance management.</span></span>|  
|<span data-ttu-id="7a42e-170">“详细”</span><span class="sxs-lookup"><span data-stu-id="7a42e-170">Verbose</span></span>|<span data-ttu-id="7a42e-171">这两个用户代码的调试级别跟踪和服务。</span><span class="sxs-lookup"><span data-stu-id="7a42e-171">Debug-level tracing for both user code and servicing.</span></span>|  
|<span data-ttu-id="7a42e-172">All</span><span class="sxs-lookup"><span data-stu-id="7a42e-172">All</span></span>|<span data-ttu-id="7a42e-173">所有消息。</span><span class="sxs-lookup"><span data-stu-id="7a42e-173">All messages.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7a42e-174">跟踪会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="7a42e-174">Tracing can have an adverse affect on performance.</span></span> <span data-ttu-id="7a42e-175">仅当正在执行故障排除活动时启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a42e-175">Only enable tracing when you are performing troubleshooting activities.</span></span>  
  
### <a name="viewing-the-wcf-trace-file"></a><span data-ttu-id="7a42e-176">查看 WCF 跟踪文件</span><span class="sxs-lookup"><span data-stu-id="7a42e-176">Viewing the WCF Trace File</span></span>  
 <span data-ttu-id="7a42e-177">若要分析 WCF 跟踪您使用 WCF Service Trace Viewer Tool。</span><span class="sxs-lookup"><span data-stu-id="7a42e-177">To analyze the WCF trace you use the WCF Service Trace Viewer Tool.</span></span> <span data-ttu-id="7a42e-178">有关 Service Trace Viewer Tool 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=75218 ](http://go.microsoft.com/fwlink/?LinkId=75218)。</span><span class="sxs-lookup"><span data-stu-id="7a42e-178">For more information about the Service Trace Viewer Tool, see [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a42e-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a42e-179">See Also</span></span>  
 [<span data-ttu-id="7a42e-180">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="7a42e-180">Managing BAM</span></span>](../core/managing-bam.md)