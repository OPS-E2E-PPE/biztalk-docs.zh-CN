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
ms.openlocfilehash: d9cf7cddd25f3f01b6203c050a4391e16cedc989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-tracing-in-bam"></a>如何在 BAM 中启用跟踪
您可以在 BAM 中启用跟踪，以便帮助解决在以下 5 个 BAM 组件中出现的问题：  
  
-   BAM 管理实用工具  
  
-   BAM 事件总线  
  
-   BAM 门户  
  
-   BAM 警报  
  
-   BAM WCF 侦听器  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a>为 BAM 管理实用程序启用跟踪  
 您可以通过为 BAM 管理实用程序启用跟踪，获取与部署错误有关的信息。 可以采取两种方式启用跟踪： 可以通过特定 BM.exe 命令的命令行启用跟踪，或者可以修改 BAM 管理实用程序配置文件来为所有 BM.exe 命令启用跟踪。  
  
### <a name="using-the-command-line"></a>使用命令行  
 使用激活 BM.exe 命令行跟踪**-跟踪： 在 &#124; 关闭**切换。 使用 Trace 开关将重写配置文件中的设置。  
  
 该开关可与所有标准 BM.exe 命令一起使用。  
  
 例如：  
  
 **bm.exe 部署全部-DefinitionFile:PO.xml – 跟踪： 上**  
  
### <a name="using-the-configuration-file"></a>使用配置文件  
 可以通过修改位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] Tracking 文件夹中的 BM.exe.config 配置文件来启用跟踪。 此文件包含**system.diagnostics**部分，其中包含跟踪元素。 删除注释以便启用跟踪。 默认情况下，不启用跟踪。  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a>为 BAM 事件总线启用跟踪  
 为 BAM 事件总线启用跟踪可帮助您诊断两类的数据库存储错误：  
  
-   源于使用跟踪配置文件编辑器时发生的 BizTalk Server 服务事件的存储错误。  
  
-   在使用缓冲的事件流 API 时生成的存储错误。  
  
 若要为 BAM 事件总线启用跟踪，请编辑或添加 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 文件夹中的 BTSNTSvc.exe.config 文件的以下部分。  
  
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
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a>若要启用 BAM 事件总线跟踪  
  
1.  编辑 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config 文件。  
  
2.  找到\<system.diagnostics > 和\</system.diagnostics > 标记。 如果在该文件中不存在这两个标记，则复制上述代码并将代码粘贴到该配置文件中。  
  
3.  取消注释取消注释系统诊断部分通过移动结束注释分隔符 (-->) 之后来自\</system.diagnostics > 标记添加到之前\<system.diagnostics > 标记。  
  
4.  保存该文件。  
  
## <a name="enabling-tracing-for-the-bam-portal"></a>为 BAM 门户启用跟踪  
 为 BAM 门户启用跟踪允许您排除连接问题。  
  
 BAM 门户是一种 ASP.NET 应用程序，它采用标准协议进行跟踪。 在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件没有名为一节\<跟踪 >，可实现。  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a>为 BAM 门户启用跟踪  
  
1.  编辑 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config 文件。  
  
2.  找到\<system.diagnostics > 和\</system.diagnostics > 标记。  
  
3.  取消的系统诊断部分注释有移动结束注释分隔符 (-->) 之后来自\</system.diagnostics > 标记添加到之前\<system.diagnostics > 标记。  
  
4.  修改 initializeData 属性以便指定将跟踪日志写入的位置。  
  
5.  找到\<.w e b > 标记。  
  
6.  System.web 部分中找到的跟踪标记，并取消跟踪命令注释通过移动分隔符 (-->) 从后到前跟踪标记。  
  
7.  保存该文件。  
  
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
 为 BAM 警报启用跟踪可以帮助您排除警报送达问题。  
  
 BAM 警报基于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Notification Services 基础结构。 若要启用 BAM 警报的跟踪，请参阅故障排除主题 Notification Services [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416)。  
  
## <a name="bam-interceptors"></a>BAM 拦截器  
 若要启用 BAM 拦截器的端到端跟踪，可修改应用程序的配置文件-对于 Web 承载的应用程序或 Appname.config 自承载应用程序，为 Web.config。 下面的示例说明如何修改该文件：  
  
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
  
 用于 Windows Workflow Foundation 和 Windows Communication Foundation 的 BAM 侦听器将写入名为“Microsoft BizTalk Bam Interceptors”的源中。  
  
> [!NOTE]
>  源字符串区分大小写并且必须与所示内容完全一样。 如果您的字符串不同于所示的字符串，您将收不到 BAM 侦听器的跟踪信息。  
  
 您通过设置 switchValue 控制跟踪级别。 下表概括列出了可用的跟踪级别。  
  
|跟踪级别|Description|  
|-----------------|-----------------|  
|严重|记录 Fail-Fast 和事件日志条目以及跟踪相关信息。|  
|错误|记录所有异常。|  
|警告|存在可能在以后导致出现错误或严重问题的情况。|  
|信息|生成有助于监视和诊断系统状态、衡量性能或执行分析的消息。 您可以利用此类信息来规划容量和管理性能。|  
|“详细”|用于用户代码和服务的调试级别跟踪。|  
|全部|所有消息。|  
  
> [!NOTE]
>  跟踪可能会对性能有负面影响。 只在执行故障排除活动时启用跟踪。  
  
### <a name="viewing-the-wcf-trace-file"></a>查看 WCF 跟踪文件  
 若要分析 WCF 跟踪，可以使用 WCF Service Trace Viewer Tool。 有关服务跟踪查看器工具的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM](../core/managing-bam.md)