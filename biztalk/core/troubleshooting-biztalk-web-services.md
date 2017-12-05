---
title: "BizTalk Web 服务疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdc86de8-e41e-4878-a66e-e242bcf3b705
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1b768bf667969c4adc8119b6d9d89c0ed79fc32
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-biztalk-web-services"></a>BizTalk Web Services 疑难解答
本部分提供如何找出和解决常见 Web Services 问题的建议。  
  
## <a name="general-troubleshooting"></a>常规疑难解答  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a>启用 Web Services 发布向导跟踪  
 你可以启用跟踪来调试 BizTalk Web 服务发布向导通过对取消注释\<添加\>BTSWebSvcWiz.exe.config 文件中的节点。 有关从 Web 服务发布向导获取跟踪信息的详细信息，请参阅[如何修改 BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md)。  
  
### <a name="enabling-soap-message-tracing"></a>启用 SOAP 消息跟踪  
 通过使用 SOAP 扩展，您可以启用有助于调试 Web Services 发布应用程序的 SOAP 消息跟踪。 有关 SOAP 扩展的详细信息，请参阅[如何： 实现 SOAP 扩展](http://go.microsoft.com/fwlink/?LinkId=62314)。  
  
### <a name="using-the-throwdetailederror-switch"></a>使用 ThrowDetailedError 开关  
 如果发生错误，Web 客户端接收泛型**SoapException**。  
  
 若要调试已发布 Web Services，您可以向 web.config 文件添加一个开关来控制由已发布 Web Services 返回的异常详细信息的级别。 该交换机是否**ThrowDetailedError**，并且当设置为**True**服务器代理到 Web 客户端，使你能够调试已发布的 Web 服务返回内部异常信息。  
  
 下面的 XML 代码演示**ThrowDetailedError**下 web.config 文件中出现的交换机\<appSettings\>节点：  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  内部异常可能包含敏感信息。 调试后，应设置**ThrowDetailedError**切换到**False**。  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a>使用 .NET Framework 跟踪来捕获和记录 Web Services 中的错误  
 .NET Framework **System.Diagnostics.Trace**类可以用于捕获并将错误写入文本文件。  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>使用 System.Diagnostics.Trace 类捕获错误并将其写入文本文件  
  
1.  更新要设置为跟踪编译器指令的 Web 服务的 web.config 文件**true**并添加**TraceSwitch**值：  
  
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
    >  如果跟踪编译器指令未设置为**true** ，则将不生成任何 trace 输出。 **TraceSwitch**值还可以调用类中设置，但为方便起见 web.config 文件中未在此处设置。 设置**TraceSwitch**到出于开发目的的适当级别值，并在开发完成以减少或避免降低跟踪输出之后更改值。  
  
2.  创建的实例**TraceSwitch**和**TextWriterTraceListener**类和使用**try … catch**块中，在 Web 服务 [WebMethod] 调用，以捕获并写入到的错误跟踪输出文件。 例如，以下代码捕捉尝试将整数变量 s2 设置为对象变量 o2 的空实例时生成的错误：  
  
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
    >  此代码是在创建一个新时，默认情况下生成 HelloWorld Web 服务的修改的版本**ASP.Net Web 服务**项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
    > [!NOTE]
    >  适用于 Windows Vista，可能需要管理员权限将跟踪输出文件写入到的根文件夹。  
  
3.  重新生成 Web Services 项目。 现在，如果在发生错误**重**在中处理异常的语句**捕获**语句和错误写入到跟踪输出文件。  
  
## <a name="general-troubleshooting-questions-and-answers"></a>常见疑难问题与解答  
 本部分包含可帮助您解决 Web Services 问题的一系列问题与解答。  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a>在使用 Web Services 时出现错误；如何避免？  
 使用 Web Services 时需要考虑诸多细节，包括：  
  
-   避免在参数名称中使用两条下划线。  
  
-   利用**任何**元素或**anyAttribute** Web 方法中不支持属性。  
  
-   避免使用 XLANG/s 关键字作为 Web Services 名称或 Web 方法名称。  
  
-   避免使用 XLANG/s 不支持的 Web 方法参数类型。  
  
-   不要在架构中使用作为 C# 关键字或将作为无效 C# 标识符使用的元素名称。  
  
-   避免使用具有多个服务或端口类型定义的 Web Services 描述语言 (WSDL) 文件。  
  
-   Web 方法参数必须执行 Xml 序列化。  
  
-   避免引用包含多根架构的已使用 Web Services。  
  
-   对于需要基于泛型参数（如空参数）的 Web 方法，避免引用带有此种方法的 Web Services。  
  
-   不支持 WSDL 导入元素。  
  
 有关这些详细信息和相关的注意事项，请参阅[注意事项使用 Web 服务时](../core/considerations-when-consuming-web-services.md)。  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a>为什么我收到发布我使用的架构的错误\<包括\>元素？  
 如果它们包括循环引用，无法发布架构 (包括的架构具有**包括**到包括架构元素) 或具有无法解析**schemaLocation**属性。  
  
 有关限制的详细信息**包括**元素，请参阅[包括元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=62312)。 Web 服务发布向导在.NET Framework 2.0; 中具有与 XSD.exe 相同的限制有关详细信息，请参阅[导入元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=119606)。  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a>为什么在发布信封架构时出现错误？  
 如果您有一个要发布为 Web Services 的信封架构，则需要手动修改生成的 Web 项目。  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>为信封架构修改生成的 Web 项目  
  
1.  打开 *\<myWebService\>*。 asmx.cs 文件。  
  
2.  编辑文件，并更改`bodyTypeAssemblyQualifiedName = <dll.name.version>`到`bodyTypeAssemblyQualifiedName = null`  
  
> [!NOTE]
>  如果先前的 .dll 文件仍然在 ASP.NET 工作进程中，您可能需要重置 Internet 信息服务 (IIS)。  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a>已发布 Web Services 的客户端可能不会出现服务器脚本超时错误。  
 如果使用 .NET framework 的 Web 客户端调用某个使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services 发布向导生成的 Web Service，则客户端可能无法收到服务器脚本超时错误，因为默认情况下会首先发生客户端请求超时。 若要解决该问题，可执行以下操作之一：  
  
-   通过增加的值增加到大于服务器脚本超时的值的客户端请求超时**HttpWebRequest.Timeout**客户端上的属性。  
  
-   通过减少的值减小为小于客户端请求超时的值的服务器脚本超时**HttpServerUtility.ScriptTimeout**服务器上的属性。  
  
## <a name="common-errors"></a>常见错误  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Web Services 返回 HTTP 404（找不到文件）错误  
  
#### <a name="problem"></a>问题  
 尝试调用 Web Services 时返回 HTTP 404（找不到文件）错误。  
  
#### <a name="cause"></a>原因  
 如果承载 Web Services 的 IIS 服务器没有安装和/或启用 ASP.NET，可能出现此错误。  
  
#### <a name="resolution"></a>解决方法  
 确保安装并启用了 ASP.NET。 安装 .NET Framework（如果尚未安装），并且/或运行位于 IIS 服务器的 %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ 文件夹中的 aspnet_regiis.exe 程序。  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>数据字段从 Web Services 处理的文档中删除，该 Web Services 是通过 BizTalk Server Web Services 发布向导生成的。  
  
#### <a name="problem"></a>问题  
 处理具有 BizTalk Server Web 服务发布向导中，包含的字段中的任何数据具有生成的 web 服务的文档时**数据类型**的**xs: date**从删除文档。  
  
#### <a name="cause"></a>原因  
 如果已发布的业务流程包含具有一个或多个字段具有的架构，则会出现此问题**数据类型**的**xs: date**和**Nillable** 属性**True**。  
  
#### <a name="workaround"></a>解决方法  
 解决此问题，在具有已发布的架构中查找字段**数据类型**的**xs: date**并确认**Nillable**这些字段的属性设置为**False**。  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>调用 Web Services 时出现“System.IO.FileNotFoundException”错误。  
  
#### <a name="problem"></a>问题  
 在 Microsoft ASP.NET Web 应用程序中调用 Web Services 时，可能出现以下错误：  
  
 System.IO.FileNotFoundException  
  
#### <a name="cause"></a>原因  
 如果满足以下条件之一，就可能出现此错误：  
  
-   工作进程没有读取进程 Temp 目录的权限，并且工作进程没有写入进程 Temp 目录的权限。  
  
-   在 XmlSerializer 生成的代码中有编译错误。  
  
#### <a name="resolution"></a>解决方法  
 此错误记录在 Microsoft 知识库文章[823196](http://support.microsoft.com/kb/823196)。 请按照此知识库文章解决方法部分的步骤纠正此错误。