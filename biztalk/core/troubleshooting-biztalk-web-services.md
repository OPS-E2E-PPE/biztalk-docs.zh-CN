---
title: BizTalk Web Services 疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdc86de8-e41e-4878-a66e-e242bcf3b705
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e208d7050abf75043edc03d85d1b18340fc42b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398662"
---
# <a name="troubleshooting-biztalk-web-services"></a>BizTalk Web Services 疑难解答
本部分提供有关如何确定和解决常见的 Web 服务问题的建议。  
  
## <a name="general-troubleshooting"></a>常规故障排除  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a>启用 Web Services 发布向导跟踪  
 可以启用跟踪来调试 BizTalk Web Services 发布向导通过取消注释\<添加\>BTSWebSvcWiz.exe.config 文件中的节点。 有关从 Web Services 发布向导获取跟踪信息的详细信息，请参阅[如何修改 BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md)。  
  
### <a name="enabling-soap-message-tracing"></a>启用 SOAP 消息跟踪  
 可以启用 SOAP 消息跟踪，以帮助你调试使用 SOAP 扩展发布应用程序的 Web 服务。 有关 SOAP 扩展的详细信息，请参阅[如何：实现 SOAP 扩展](http://go.microsoft.com/fwlink/?LinkId=62314)。  
  
### <a name="using-the-throwdetailederror-switch"></a>使用 ThrowDetailedError 开关  
 如果发生错误，Web 客户端会收到一个一般**SoapException**。  
  
 若要调试已发布的 Web 服务，可以向 web.config 文件以控制从已发布的 Web 服务返回的异常详细信息级别添加一个开关。 开关，则**ThrowDetailedError**，并当设置为**True**服务器代理将内部异常信息返回至 Web 客户端，从而可以调试已发布的 Web 服务。  
  
 下面的 XML 代码演示**ThrowDetailedError**下的 web.config 文件中出现的交换机\<appSettings\>节点：  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  内部异常可能包含敏感信息。 调试后，应设置**ThrowDetailedError**切换到**False**。  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a>在 Web 服务中使用.NET Framework 跟踪来捕获和记录错误  
 .NET Framework **System.Diagnostics.Trace**类可用于捕获并将错误写入文本文件。  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>若要使用 System.Diagnostics.Trace 类捕获并将错误写入文本文件  
  
1. 更新将 TRACE 编译器指令设置为该 Web 服务的 web.config 文件 **，则返回 true**并添加**TraceSwitch**值：  
  
   ```  
   <?xml version="1.0"?>  
   <configuration>  
     <system.codedom>  
       <compilers>  
         <compiler language="c#;cs;csharp"   
                   extension=".cs"   
                   compilerOptions="/d:TRACE"  
                   type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.3500.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" warningLevel="1" />  
         </compilers>  
     </system.codedom>  
     <system.diagnostics>  
       <switches>  
         <add name="WebSvcTraceSwitch" value="2" />  
         <!-- Set to 0, 1, 2, 3, or 4, which corresponds   
         to TraceLevel.Off, TraceLevel.Error, TraceLevel.Warning  
         TraceLevel.Info, and TraceLevel.Verbose. -->  
       </switches>  
     </system.diagnostics>  
   </configuration>  
   ```  
  
   > [!NOTE]
   >  如果 TRACE 编译器指令没有设置为 **，则返回 true** ，则会不生成任何跟踪输出。 **TraceSwitch**值也可以调用类中设置，但为方便起见在 web.config 文件中设置。 设置**TraceSwitch**值到的相应级别的开发目的，并以减少或禁止跟踪输出，完成开发之后更改的值。  
  
2. 创建的实例**TraceSwitch**并**TextWriterTraceListener**类和使用**尝试...捕获**阻止在 Web 服务 [WebMethod] 调用，以捕获并将错误写入跟踪输出文件中。 例如，下面的代码捕获时尝试将整数变量 s2 设置为对象变量 o2 的空实例，将生成一个错误：  
  
   ```  
   using System;  
   using System.Web;  
   using System.Web.Services;  
   using System.Web.Services.Protocols;  
   using System.Diagnostics;  
  
   [WebService(Namespace = "http://tempuri.org/")]  
   [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
   public class Service : System.Web.Services.WebService  
   {  
       TraceSwitch WebSvcTraceSwitch = new TraceSwitch("WebSvcTraceSwitch", "Web Service Trace");  
       TextWriterTraceListener TestTracer = new TextWriterTraceListener("C:\\traceout.txt");  
   // Note that by default the local ASPNET account(IIS 5.x) or the   
   // local NETWORK SERVICE account(IIS 6.0) needs write access to  
   // this directory so that the instance of the   
   // TextWriterTraceListener can write to the trace output file.  
   );  
  
       public Service () {  
       }  
  
       [WebMethod]  
       public string HelloWorld()   
       {  
       string h2 = "Hello World";  
       //object o2 = 1;  
       object o2 = null;  
           try  
           {  
               int s2 = (int)o2; //Error if o2 set to null   
               return h2;  
           }  
           catch(Exception e)  
           {  
               Trace.Listeners.Add(TestTracer);  
               Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning,"Exception caught: " + e.Message);  
               //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
               TestTracer.Dispose();  
               return "An error occurred in the Web service, please contact the web server administrator.";  
           }  
       }  
   }  
   ```  
  
   > [!NOTE]
   >  此代码是 HelloWorld Web 服务时创建新生成的默认值的修改的版本**ASP.Net Web 服务**项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
   > 
   > [!NOTE]
   >  适用于 Windows Vista，可能需要管理员权限将跟踪输出文件写入到的根文件夹。  
  
3. 重新生成 Web 服务项目。 现在，如果在发生错误**尝试**语句中处理异常**捕获**语句和错误写入跟踪输出文件。  
  
## <a name="general-troubleshooting-questions-and-answers"></a>常见疑难问题与解答  
 本部分包含一系列问题与解答可帮助您解决 Web services 的问题。  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a>使用 Web 服务; 时出现错误如何避免它们？  
 有许多细节需要考虑时使用 Web 服务，其中包括：  
  
- 避免在参数名称中使用两个下划线字符。  
  
- 利用**任何**元素或**anyAttribute** Web 方法中不支持特性。  
  
- 避免使用 XLANG/s 关键字作为 Web 服务名称或 Web 方法名称。  
  
- 避免使用 XLANG/s 不支持的 Web 方法参数类型。  
  
- 不要使用元素名称都是 C# 关键字或将为您的架构中的 C# 标识符无效。  
  
- 避免与多个服务的 Web 服务描述语言 (WSDL) 文件或端口类型定义。  
  
- Web 方法的参数必须是 Xml 可序列化。  
  
- 避免使用包含多根的架构的 Web services 的引用。  
  
- 避免与 Web 方法的基于泛型的参数，如可以为 null 的参数应为引用 Web 服务。  
  
- 不支持 WSDL 导入元素。  
  
  有关这些详细信息和相关的注意事项，请参阅[注意事项使用 Web Services 时](../core/considerations-when-consuming-web-services.md)。  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a>为什么我收到错误发布我使用的架构\<包括\>元素？  
 如果架构包含循环引用，不能发布架构 (包含的架构具有**包括**包含架构的元素) 或具有无法解析**schemaLocation**属性。  
  
 有关限制的详细信息**包括**元素，请参阅[Include 元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=62312)。 Web Services 发布向导已在.NET Framework 2.0; 中的 xsd.exe 具有相同的限制有关详细信息，请参阅[导入元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=119606)。  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a>发布信封架构时，为什么收到错误？  
 如果必须要发布为 Web 服务的信封架构，您需要手动修改生成的 Web 项目。  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>若要修改的信封架构生成的 Web 项目  
  
1.  打开 *\<myWebService\>*。 asmx.cs 文件。  
  
2.  编辑文件，并更改`bodyTypeAssemblyQualifiedName = <dll.name.version>`到 `bodyTypeAssemblyQualifiedName = null`  
  
> [!NOTE]
>  您可能需要重置 Internet 信息服务 (IIS)，如果先前的.dll 文件仍在 ASP.NET 工作进程。  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a>已发布 Web services 的客户端可能未收到服务器脚本超时错误  
 如果使用.NET Framework 的 Web 客户端调用 Web 服务生成具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web Services 发布向导，它是可能在客户端无法收到服务器脚本超时错误，因为通过会首先发生客户端请求超时默认值。 若要解决此问题可以执行下列任一操作：  
  
-   通过增加的值来提高客户端请求超时值大于服务器脚本超时**HttpWebRequest.Timeout**客户端上的属性。  
  
-   降低服务器脚本超时小于客户端请求超时的值的值**HttpServerUtility.ScriptTimeout**在服务器上的属性。  
  
## <a name="common-errors"></a>常见错误  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Web 服务将返回 HTTP 404 （找不到文件） 错误  
  
#### <a name="problem"></a>问题  
 尝试调用 Web 服务返回 HTTP 404 （找不到文件） 错误。  
  
#### <a name="cause"></a>原因  
 如果 ASP.NET 未安装和/或在服务器上启用 IIS 承载的 Web 服务，可以发生此错误。  
  
#### <a name="resolution"></a>解决方法  
 请确保安装并启用 ASP.NET。 如果它是未安装和/或运行位于 IIS 服务器的 %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ 文件夹中的 aspnet_regiis.exe 程序，请安装.NET Framework。  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>处理 web 服务使用 BizTalk Server Web Services 发布向导生成的文档从删除日期字段  
  
#### <a name="problem"></a>问题  
 处理具有 BizTalk Server Web Services 发布向导，在字段中包含的任何数据具有生成的 web 服务的文档时**数据类型**的**xs: date**已从文档。  
  
#### <a name="cause"></a>原因  
 如果发布的业务流程包含一个或多个字段都具有的架构，会出现此问题**数据类型**的**xs: date**和一个**Nillable** 属性**True**。  
  
#### <a name="workaround"></a>解决方法  
 解决此问题，请在已发布的架构中查找字段**数据类型**的**xs: date** ，并验证**Nillable**这些字段的属性设置为**False**。  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>调用 Web 服务时，会出现"System.IO.FileNotFoundException"错误  
  
#### <a name="problem"></a>问题  
 当在 Microsoft ASP.NET Web 应用程序中调用 Web 服务时，可能会收到以下错误：  
  
 System.IO.FileNotFoundException  
  
#### <a name="cause"></a>原因  
 如果以下条件之一为 true，可能发生此错误：  
  
-   工作进程没有读取进程 Temp 目录的权限和工作进程没有写入进程 Temp 目录的权限。  
  
-   XmlSerializer 生成的代码中有编译错误。  
  
#### <a name="resolution"></a>解决方法  
 此错误记录在 Microsoft 知识库文章[823196](http://support.microsoft.com/kb/823196)。 按照此知识库文章以解决此错误的解决方法部分中的步骤。