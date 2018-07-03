---
title: Web 服务的故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c32bf542-dcc6-4727-b31f-52bb19d4b89d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5166616600fd0748e6f49650f0f462ca2c678e2c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024475"
---
# <a name="troubleshooting-web-services"></a>Web Services 疑难解答
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可广泛使用的 Web 服务使用 SOAP 适配器和业务流程发布为 Web 服务。 本主题提供了一些用于对 Web Services 进行故障排除的操作步骤，还有一些常见的 Web Services 问题以及如何解决这些问题的说明。  
  
## <a name="use-net-framework-tracing-to-capture-and-log-errors-in-a-web-service"></a>使用.NET Framework 跟踪来捕获和记录的 Web 服务中的错误  
 .NET Framework **System.Diagnostics.Trace**类可用于捕获并将错误写入文本文件。  
  
#### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>使用 System.Diagnostics.Trace 类捕获错误并将其写入文本文件  
  
1. 更新 Web 服务，将设置的 web.config 文件**跟踪**编译器指令**true** ，并添加**TraceSwitch**值：  
  
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
   >  如果**跟踪**编译器指令未设置为**true** ，则会不生成任何跟踪输出。 **TraceSwitch**值还可以设置在调用类中，但为方便起见在 web.config 文件中设置。 设置**TraceSwitch**值到的相应级别的开发目的，并以减少或禁止跟踪输出，完成开发之后更改的值。  
  
2. 创建的实例**TraceSwitch**并**TextWriterTraceListener**类并使用**try...catch**中 Web 服务 [WebMethod] 调用，以捕获并写入到的错误阻止跟踪输出文件。 例如，以下代码捕捉尝试将整数变量 s2 设置为对象变量 o2 的空实例时生成的错误：  
  
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
               Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning, "Exception caught: " + e.Message);  
               //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
               TestTracer.Dispose();  
               return "An error occurred in the Web service, please contact the web server administrator.";  
           }  
       }  
   }  
   ```  
  
   > [!NOTE]
   >  此代码是默认值时创建新生成的 HelloWorld Web 服务的修改的版本**ASP.Net Web 服务**项目中 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
   > 
   > [!NOTE]
   >  适用于 Windows Vista，可能需要管理员权限将跟踪输出文件写入到的根文件夹。  
  
3. 重新生成 Web Services 项目。 现在，如果在发生错误**尝试**语句中处理异常**捕获**语句和错误写入跟踪输出文件。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Web Services 返回 HTTP 404（找不到文件）错误  
  
##### <a name="problem"></a>问题  
 尝试调用 Web Services 时返回 HTTP 404（找不到文件）错误。  
  
##### <a name="cause"></a>原因  
 如果承载 Web Services 的 IIS 服务器没有安装和/或启用 ASP.NET，可能出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 确保安装并启用了 ASP.NET。 安装[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]如果它是未安装和/或运行**aspnet_regiis.exe**程序位于 %WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ IIS 服务器的文件夹。  
  
#### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>调用 Web Services 时出现“System.IO.FileNotFoundException”错误。  
  
##### <a name="problem"></a>问题  
 在 Microsoft ASP.NET Web 应用程序中调用 Web Services 时，可能出现以下错误：  
  
 **System.IO.FileNotFoundException**  
  
##### <a name="cause"></a>原因  
 如果满足以下条件之一，就可能出现此错误：  
  
-   工作进程没有读取进程 Temp 目录的权限，并且工作进程没有写入进程 Temp 目录的权限。  
  
-   在 XmlSerializer 生成的代码中有编译错误。  
  
##### <a name="resolution"></a>解决方法  
 此错误记录在 Microsoft 知识库文章 823196 中， [PRB： 收到 'System.IO.FileNotFoundException' 错误时在客户端应用程序调用 Web 服务](http://go.microsoft.com/fwlink/?LinkID=84694)"。 请按照此知识库文章解决方法部分的步骤纠正此错误。  
  
#### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>数据字段从 Web Services 处理的文档中删除，该 Web Services 是通过 BizTalk Server Web Services 发布向导生成的。  
  
##### <a name="problem"></a>问题  
 处理具有 BizTalk Server Web Services 发布向导，在字段中包含的任何数据具有生成的 web 服务的文档时**数据类型**的**xs: date**和**Nillable**的属性**True**从文档中删除。  
  
##### <a name="cause"></a>原因  
 出现此问题的原因是随 Microsoft .NET Framework 类库命名空间 System.Xml.Serialization 提供的 XmlSerializer 类的已知问题。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请安装.NET Framework 2.0 修补程序记录在 Microsoft 知识库文章 925272"[修复： XML 序列化可能会丢失在.NET Framework 2.0 中的 XSD 架构中的某些可选元素](http://go.microsoft.com/fwlink/?LinkId=84696)"。  
  
## <a name="see-also"></a>请参阅  
 [解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)   
 [解决 Web Services 权限问题的准则](../core/guidelines-for-resolving-web-services-permissions-problems.md)