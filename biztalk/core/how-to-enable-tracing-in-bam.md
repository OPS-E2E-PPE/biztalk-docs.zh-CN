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
# <a name="how-to-enable-tracing-in-bam"></a>如何在 BAM 中启用跟踪
您可以启用跟踪在 BAM 中以帮助解决以下 5 个 BAM 组件中的问题：  
  
-   BAM 管理实用程序  
  
-   BAM 事件总线  
  
-   BAM 门户  
  
-   BAM 警报  
  
-   BAM WCF 侦听器  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a>为 BAM 管理实用程序启用跟踪  
 可以通过为 BAM 管理实用程序启用跟踪来获取有关部署失败的信息。 可以通过两种方式来执行此操作。 可以启用跟踪通过特定 BM.exe 命令，在命令行，或者可以修改 BAM 管理实用程序配置文件来为所有 BM.exe 命令启用跟踪。  
  
### <a name="using-the-command-line"></a>使用命令行  
 使用激活 BM.exe 命令行跟踪 **-跟踪： 在&#124;关闭**切换。 使用 Trace 开关将重写配置文件中的设置。  
  
 与所有标准 BM.exe 命令一起使用的开关。  
  
 例如：  
  
 **bm.exe deploy-all -DefinitionFile:PO.xml –Trace:On**  
  
### <a name="using-the-configuration-file"></a>使用配置文件  
 可以通过修改位于中的 BM.exe.config 配置文件启用跟踪[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪文件夹。 此文件包含**system.diagnostics**部分，其中包含跟踪元素。 删除注释以便启用跟踪。 默认情况下不启用跟踪。  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a>为 BAM 事件总线启用跟踪  
 为 BAM 事件总线启用跟踪可以帮助您诊断数据库存储错误的两个类：  
  
- 使用跟踪配置文件编辑器时源自来自 BizTalk Server 服务的事件存储错误。  
  
- 使用缓冲的事件流 Api 时生成的存储错误。  
  
  若要启用跟踪的 BAM 事件总线，请编辑或添加以下部分中的 BTSNTSvc.exe.config 文件的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]文件夹。  
  
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
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a>若要为 BAM 事件总线启用跟踪  
  
1. 编辑[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config 文件。  
  
2. 找到\<system.diagnostics\>并\</system.diagnostics\>标记。 如果它们不存在的文件中，复制上面列出的代码，并将其粘贴到配置文件。  
  
3. 取消的注释系统诊断节通过移动结束注释分隔符 (-->) 从后\</system.diagnostics\>标记添加到之前\<system.diagnostics\>标记。  
  
4. 保存该文件。  
  
## <a name="enabling-tracing-for-the-bam-portal"></a>为 BAM 门户启用跟踪  
 为 BAM 门户启用跟踪，可对连接问题进行故障排除。  
  
 BAM 门户是 ASP.NET 应用程序，并遵循标准协议进行跟踪。 内[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件中，还有一个名为部分\<跟踪\>，可实现。  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a>若要为 BAM 门户启用跟踪  
  
1. 编辑[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件。  
  
2. 找到\<system.diagnostics\>并\</system.diagnostics\>标记。  
  
3. 通过移动结束注释分隔符来取消注释系统诊断部分 (-->) 从后\</system.diagnostics\>标记添加到之前\<system.diagnostics\>标记。  
  
4. 修改 initializeData 属性以便指定要写入跟踪日志的位置。  
  
5. 找到\<system.web\>标记。  
  
6. 在 system.web 节中找到跟踪标记并取消注释跟踪命令移动分隔符 (-->) 从后到前的跟踪标记。  
  
7. 保存该文件。  
  
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
  
## <a name="bam-alerting"></a>BAM 警报  
 为 BAM 警报可帮助您排除警报送达问题启用跟踪。  
  
 BAM 警报基于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Notification Services 基础结构。 若要启用对 BAM 警报的跟踪，请参阅通知服务疑难解答主题，网址[ http://go.microsoft.com/fwlink/?LinkId=79416 ](http://go.microsoft.com/fwlink/?LinkId=79416)。  
  
## <a name="bam-interceptors"></a>BAM 侦听器  
 若要启用端到端跟踪的 BAM 侦听器，你修改应用程序的配置文件 — 的 Web 承载的应用程序，appname.config 自承载应用程序的 Web.config。 下面是举例说明如何修改该文件：  
  
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
  
 Windows Workflow Foundation 的 BAM 侦听器和 Windows Communication Foundation 将写入到名为"Microsoft BizTalk Bam Interceptors"的源。  
  
> [!NOTE]
>  源字符串区分大小写，必须严格按所示出现。 如果您的字符串是不同于所示，不会收到 BAM 侦听器跟踪的信息。  
  
 通过设置 switchValue 控制跟踪级别。 下表总结了可用的跟踪级别。  
  
|跟踪级别|Description|  
|-----------------|-----------------|  
|严重|记录 Fail-fast 和事件日志条目，并跟踪相关信息。|  
|错误|记录所有异常。|  
|警告|存在某种情况随后可能会导致错误或严重故障。|  
|信息|生成消息有助于监视和诊断系统状态、 测量性能，或执行分析。 可以使用此类信息规划容量和性能管理。|  
|“详细”|这两个用户代码的调试级别跟踪和服务。|  
|All|所有消息。|  
  
> [!NOTE]
>  跟踪会对性能产生负面影响。 仅当正在执行故障排除活动时启用跟踪。  
  
### <a name="viewing-the-wcf-trace-file"></a>查看 WCF 跟踪文件  
 若要分析 WCF 跟踪您使用 WCF Service Trace Viewer Tool。 有关 Service Trace Viewer Tool 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=75218 ](http://go.microsoft.com/fwlink/?LinkId=75218)。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)