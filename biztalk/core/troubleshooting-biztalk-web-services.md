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
# <a name="troubleshooting-biztalk-web-services"></a><span data-ttu-id="55523-102">BizTalk Web Services 疑难解答</span><span class="sxs-lookup"><span data-stu-id="55523-102">Troubleshooting BizTalk Web Services</span></span>
<span data-ttu-id="55523-103">本部分提供有关如何确定和解决常见的 Web 服务问题的建议。</span><span class="sxs-lookup"><span data-stu-id="55523-103">This section offers advice on how to identify and resolve common Web service issues.</span></span>  
  
## <a name="general-troubleshooting"></a><span data-ttu-id="55523-104">常规故障排除</span><span class="sxs-lookup"><span data-stu-id="55523-104">General Troubleshooting</span></span>  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a><span data-ttu-id="55523-105">启用 Web Services 发布向导跟踪</span><span class="sxs-lookup"><span data-stu-id="55523-105">Enabling Web Services Publishing Wizard tracing</span></span>  
 <span data-ttu-id="55523-106">可以启用跟踪来调试 BizTalk Web Services 发布向导通过取消注释\<添加\>BTSWebSvcWiz.exe.config 文件中的节点。</span><span class="sxs-lookup"><span data-stu-id="55523-106">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add\> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="55523-107">有关从 Web Services 发布向导获取跟踪信息的详细信息，请参阅[如何修改 BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md)。</span><span class="sxs-lookup"><span data-stu-id="55523-107">For more information about obtaining trace information from the Web Services Publishing Wizard, see [How to Modify BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md).</span></span>  
  
### <a name="enabling-soap-message-tracing"></a><span data-ttu-id="55523-108">启用 SOAP 消息跟踪</span><span class="sxs-lookup"><span data-stu-id="55523-108">Enabling SOAP message tracing</span></span>  
 <span data-ttu-id="55523-109">可以启用 SOAP 消息跟踪，以帮助你调试使用 SOAP 扩展发布应用程序的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="55523-109">You can enable SOAP message tracing to help you debug the Web services publishing application by using a SOAP extension.</span></span> <span data-ttu-id="55523-110">有关 SOAP 扩展的详细信息，请参阅[如何：实现 SOAP 扩展](http://go.microsoft.com/fwlink/?LinkId=62314)。</span><span class="sxs-lookup"><span data-stu-id="55523-110">For more information about SOAP extensions, see [How to: Implement a SOAP Extension](http://go.microsoft.com/fwlink/?LinkId=62314).</span></span>  
  
### <a name="using-the-throwdetailederror-switch"></a><span data-ttu-id="55523-111">使用 ThrowDetailedError 开关</span><span class="sxs-lookup"><span data-stu-id="55523-111">Using the ThrowDetailedError switch</span></span>  
 <span data-ttu-id="55523-112">如果发生错误，Web 客户端会收到一个一般**SoapException**。</span><span class="sxs-lookup"><span data-stu-id="55523-112">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="55523-113">若要调试已发布的 Web 服务，可以向 web.config 文件以控制从已发布的 Web 服务返回的异常详细信息级别添加一个开关。</span><span class="sxs-lookup"><span data-stu-id="55523-113">To debug your published Web service, you can add a switch to the web.config file to control the level of the exception details returned from the published Web service.</span></span> <span data-ttu-id="55523-114">开关，则**ThrowDetailedError**，并当设置为**True**服务器代理将内部异常信息返回至 Web 客户端，从而可以调试已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="55523-114">The switch is **ThrowDetailedError**, and when it is set to **True** the server proxy returns inner exception information to the Web client, enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="55523-115">下面的 XML 代码演示**ThrowDetailedError**下的 web.config 文件中出现的交换机\<appSettings\>节点：</span><span class="sxs-lookup"><span data-stu-id="55523-115">The following XML code shows the **ThrowDetailedError** switch that appears in the web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  <span data-ttu-id="55523-116">内部异常可能包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="55523-116">The inner exception may contain sensitive information.</span></span> <span data-ttu-id="55523-117">调试后，应设置**ThrowDetailedError**切换到**False**。</span><span class="sxs-lookup"><span data-stu-id="55523-117">After debugging, you should set the **ThrowDetailedError** switch to **False**.</span></span>  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a><span data-ttu-id="55523-118">在 Web 服务中使用.NET Framework 跟踪来捕获和记录错误</span><span class="sxs-lookup"><span data-stu-id="55523-118">Using .NET Framework tracing to capture and log errors in the Web service</span></span>  
 <span data-ttu-id="55523-119">.NET Framework **System.Diagnostics.Trace**类可用于捕获并将错误写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="55523-119">The .NET Framework **System.Diagnostics.Trace** class can be used to capture and write errors to a text file.</span></span>  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a><span data-ttu-id="55523-120">若要使用 System.Diagnostics.Trace 类捕获并将错误写入文本文件</span><span class="sxs-lookup"><span data-stu-id="55523-120">To use the System.Diagnostics.Trace class to capture and write errors to a text file</span></span>  
  
1. <span data-ttu-id="55523-121">更新将 TRACE 编译器指令设置为该 Web 服务的 web.config 文件 **，则返回 true**并添加**TraceSwitch**值：</span><span class="sxs-lookup"><span data-stu-id="55523-121">Update the web.config file for the Web service to set the TRACE compiler directive to **true** and add a **TraceSwitch** value:</span></span>  
  
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
   >  <span data-ttu-id="55523-122">如果 TRACE 编译器指令没有设置为 **，则返回 true** ，则会不生成任何跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="55523-122">If the TRACE compiler directive is not set to **true** then no trace output will be generated.</span></span> <span data-ttu-id="55523-123">**TraceSwitch**值也可以调用类中设置，但为方便起见在 web.config 文件中设置。</span><span class="sxs-lookup"><span data-stu-id="55523-123">The **TraceSwitch** value can also be set in the calling class but is set here in the web.config file for convenience.</span></span> <span data-ttu-id="55523-124">设置**TraceSwitch**值到的相应级别的开发目的，并以减少或禁止跟踪输出，完成开发之后更改的值。</span><span class="sxs-lookup"><span data-stu-id="55523-124">Set the **TraceSwitch** value to the appropriate level for development purposes and change the value after development is complete to reduce or inhibit trace output.</span></span>  
  
2. <span data-ttu-id="55523-125">创建的实例**TraceSwitch**并**TextWriterTraceListener**类和使用**尝试...捕获**阻止在 Web 服务 [WebMethod] 调用，以捕获并将错误写入跟踪输出文件中。</span><span class="sxs-lookup"><span data-stu-id="55523-125">Create an instance of the **TraceSwitch** and **TextWriterTraceListener** classes and use a **try…catch** block in the Web service [WebMethod] call to trap and write errors to a trace output file.</span></span> <span data-ttu-id="55523-126">例如，下面的代码捕获时尝试将整数变量 s2 设置为对象变量 o2 的空实例，将生成一个错误：</span><span class="sxs-lookup"><span data-stu-id="55523-126">For example, the following code traps an error that is generated when attempting to set the integer variable s2 to a null instance of the object variable o2:</span></span>  
  
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
   >  <span data-ttu-id="55523-127">此代码是 HelloWorld Web 服务时创建新生成的默认值的修改的版本**ASP.Net Web 服务**项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55523-127">This code is a modified version of the HelloWorld Web service that is generated by default when you create a new **ASP.Net Web Service** project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="55523-128">适用于 Windows Vista，可能需要管理员权限将跟踪输出文件写入到的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="55523-128">For Windows Vista, Administrator privileges may be required to write the trace output file to the root folder.</span></span>  
  
3. <span data-ttu-id="55523-129">重新生成 Web 服务项目。</span><span class="sxs-lookup"><span data-stu-id="55523-129">Rebuild the Web service project.</span></span> <span data-ttu-id="55523-130">现在，如果在发生错误**尝试**语句中处理异常**捕获**语句和错误写入跟踪输出文件。</span><span class="sxs-lookup"><span data-stu-id="55523-130">Now, if an error occurs in the **Try** statement the exception is handled in the **Catch** statement and an error is written to the trace output file.</span></span>  
  
## <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="55523-131">常见疑难问题与解答</span><span class="sxs-lookup"><span data-stu-id="55523-131">General Troubleshooting Questions and Answers</span></span>  
 <span data-ttu-id="55523-132">本部分包含一系列问题与解答可帮助您解决 Web services 的问题。</span><span class="sxs-lookup"><span data-stu-id="55523-132">This section contains a set of questions and answers designed to help you resolve issues with Web services.</span></span>  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a><span data-ttu-id="55523-133">使用 Web 服务; 时出现错误如何避免它们？</span><span class="sxs-lookup"><span data-stu-id="55523-133">I am receiving errors when consuming a Web service; how can I avoid them?</span></span>  
 <span data-ttu-id="55523-134">有许多细节需要考虑时使用 Web 服务，其中包括：</span><span class="sxs-lookup"><span data-stu-id="55523-134">There are many details to consider when consuming a Web service, including the following:</span></span>  
  
- <span data-ttu-id="55523-135">避免在参数名称中使用两个下划线字符。</span><span class="sxs-lookup"><span data-stu-id="55523-135">Avoid using two underscore characters in a parameter name.</span></span>  
  
- <span data-ttu-id="55523-136">利用**任何**元素或**anyAttribute** Web 方法中不支持特性。</span><span class="sxs-lookup"><span data-stu-id="55523-136">Use of the **any** element or the **anyAttribute** attribute is not supported in Web methods.</span></span>  
  
- <span data-ttu-id="55523-137">避免使用 XLANG/s 关键字作为 Web 服务名称或 Web 方法名称。</span><span class="sxs-lookup"><span data-stu-id="55523-137">Avoid using XLANG/s keywords as a Web service name or Web method name.</span></span>  
  
- <span data-ttu-id="55523-138">避免使用 XLANG/s 不支持的 Web 方法参数类型。</span><span class="sxs-lookup"><span data-stu-id="55523-138">Avoid using Web method parameter types that are not supported by XLANG/s.</span></span>  
  
- <span data-ttu-id="55523-139">不要使用元素名称都是 C# 关键字或将为您的架构中的 C# 标识符无效。</span><span class="sxs-lookup"><span data-stu-id="55523-139">Do not use element names that are C# keywords or will be invalid as a C# identifier in your schemas.</span></span>  
  
- <span data-ttu-id="55523-140">避免与多个服务的 Web 服务描述语言 (WSDL) 文件或端口类型定义。</span><span class="sxs-lookup"><span data-stu-id="55523-140">Avoid Web Services Description Language (WSDL) files with multiple service or port type definitions.</span></span>  
  
- <span data-ttu-id="55523-141">Web 方法的参数必须是 Xml 可序列化。</span><span class="sxs-lookup"><span data-stu-id="55523-141">Web method parameters must be Xml Serializable.</span></span>  
  
- <span data-ttu-id="55523-142">避免使用包含多根的架构的 Web services 的引用。</span><span class="sxs-lookup"><span data-stu-id="55523-142">Avoid references to consumed Web services that contain multi-rooted schemas.</span></span>  
  
- <span data-ttu-id="55523-143">避免与 Web 方法的基于泛型的参数，如可以为 null 的参数应为引用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="55523-143">Avoid referencing Web services with Web methods expecting generic-based parameters such as nullable parameters.</span></span>  
  
- <span data-ttu-id="55523-144">不支持 WSDL 导入元素。</span><span class="sxs-lookup"><span data-stu-id="55523-144">The WSDL import element is not supported.</span></span>  
  
  <span data-ttu-id="55523-145">有关这些详细信息和相关的注意事项，请参阅[注意事项使用 Web Services 时](../core/considerations-when-consuming-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="55523-145">For more information about these and related considerations, see [Considerations When Consuming Web Services](../core/considerations-when-consuming-web-services.md).</span></span>  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a><span data-ttu-id="55523-146">为什么我收到错误发布我使用的架构\<包括\>元素？</span><span class="sxs-lookup"><span data-stu-id="55523-146">Why am I getting errors publishing my schema that uses the \<include\> element?</span></span>  
 <span data-ttu-id="55523-147">如果架构包含循环引用，不能发布架构 (包含的架构具有**包括**包含架构的元素) 或具有无法解析**schemaLocation**属性。</span><span class="sxs-lookup"><span data-stu-id="55523-147">Schemas cannot be published if they include circular references (the included schema has an **include** element to the including schema) or have an unresolved **schemaLocation** attribute.</span></span>  
  
 <span data-ttu-id="55523-148">有关限制的详细信息**包括**元素，请参阅[Include 元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=62312)。</span><span class="sxs-lookup"><span data-stu-id="55523-148">For more information about the limitation of the **include** element, see [Include Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span> <span data-ttu-id="55523-149">Web Services 发布向导已在.NET Framework 2.0; 中的 xsd.exe 具有相同的限制有关详细信息，请参阅[导入元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=119606)。</span><span class="sxs-lookup"><span data-stu-id="55523-149">The Web Services Publishing Wizard has the same limitations as XSD.exe in .NET Framework 2.0; for more information, see [Import Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=119606).</span></span>  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a><span data-ttu-id="55523-150">发布信封架构时，为什么收到错误？</span><span class="sxs-lookup"><span data-stu-id="55523-150">Why do I receive errors when publishing my envelope schema?</span></span>  
 <span data-ttu-id="55523-151">如果必须要发布为 Web 服务的信封架构，您需要手动修改生成的 Web 项目。</span><span class="sxs-lookup"><span data-stu-id="55523-151">If you have an envelope schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="55523-152">若要修改的信封架构生成的 Web 项目</span><span class="sxs-lookup"><span data-stu-id="55523-152">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="55523-153">打开 *\<myWebService\>*。 asmx.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="55523-153">Open the *\<myWebService\>*.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="55523-154">编辑文件，并更改`bodyTypeAssemblyQualifiedName = <dll.name.version>`到 `bodyTypeAssemblyQualifiedName = null`</span><span class="sxs-lookup"><span data-stu-id="55523-154">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version>` to `bodyTypeAssemblyQualifiedName = null`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55523-155">您可能需要重置 Internet 信息服务 (IIS)，如果先前的.dll 文件仍在 ASP.NET 工作进程。</span><span class="sxs-lookup"><span data-stu-id="55523-155">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASP.NET worker process.</span></span>  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a><span data-ttu-id="55523-156">已发布 Web services 的客户端可能未收到服务器脚本超时错误</span><span class="sxs-lookup"><span data-stu-id="55523-156">Clients of published Web services may not receive server script time-out errors</span></span>  
 <span data-ttu-id="55523-157">如果使用.NET Framework 的 Web 客户端调用 Web 服务生成具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web Services 发布向导，它是可能在客户端无法收到服务器脚本超时错误，因为通过会首先发生客户端请求超时默认值。</span><span class="sxs-lookup"><span data-stu-id="55523-157">If Web clients that use .NET Framework are calling a Web service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script time-out errors because the client request time-out occurs first by default.</span></span> <span data-ttu-id="55523-158">若要解决此问题可以执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="55523-158">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="55523-159">通过增加的值来提高客户端请求超时值大于服务器脚本超时**HttpWebRequest.Timeout**客户端上的属性。</span><span class="sxs-lookup"><span data-stu-id="55523-159">Increase the client request time-out to a value greater than the server script time-out by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="55523-160">降低服务器脚本超时小于客户端请求超时的值的值**HttpServerUtility.ScriptTimeout**在服务器上的属性。</span><span class="sxs-lookup"><span data-stu-id="55523-160">Reduce the server script time-out to a value less than the client request time-out by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="common-errors"></a><span data-ttu-id="55523-161">常见错误</span><span class="sxs-lookup"><span data-stu-id="55523-161">Common Errors</span></span>  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a><span data-ttu-id="55523-162">Web 服务将返回 HTTP 404 （找不到文件） 错误</span><span class="sxs-lookup"><span data-stu-id="55523-162">A Web service returns an HTTP 404 (File Not Found) error</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="55523-163">问题</span><span class="sxs-lookup"><span data-stu-id="55523-163">Problem</span></span>  
 <span data-ttu-id="55523-164">尝试调用 Web 服务返回 HTTP 404 （找不到文件） 错误。</span><span class="sxs-lookup"><span data-stu-id="55523-164">Attempts to call a Web service return an HTTP 404 (File Not Found) error.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="55523-165">原因</span><span class="sxs-lookup"><span data-stu-id="55523-165">Cause</span></span>  
 <span data-ttu-id="55523-166">如果 ASP.NET 未安装和/或在服务器上启用 IIS 承载的 Web 服务，可以发生此错误。</span><span class="sxs-lookup"><span data-stu-id="55523-166">This error can occur if ASP.NET is not installed and/or enabled on the IIS server that hosts the Web service.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="55523-167">解决方法</span><span class="sxs-lookup"><span data-stu-id="55523-167">Resolution</span></span>  
 <span data-ttu-id="55523-168">请确保安装并启用 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="55523-168">Ensure that ASP.NET is installed and enabled.</span></span> <span data-ttu-id="55523-169">如果它是未安装和/或运行位于 IIS 服务器的 %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ 文件夹中的 aspnet_regiis.exe 程序，请安装.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="55523-169">Install the .NET Framework if it is not installed and/or run the aspnet_regiis.exe program located in the %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ folder of the IIS server.</span></span>  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a><span data-ttu-id="55523-170">处理 web 服务使用 BizTalk Server Web Services 发布向导生成的文档从删除日期字段</span><span class="sxs-lookup"><span data-stu-id="55523-170">Date fields are removed from documents processed by a web service generated with the BizTalk Server Web Services Publishing Wizard</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="55523-171">问题</span><span class="sxs-lookup"><span data-stu-id="55523-171">Problem</span></span>  
 <span data-ttu-id="55523-172">处理具有 BizTalk Server Web Services 发布向导，在字段中包含的任何数据具有生成的 web 服务的文档时**数据类型**的**xs: date**已从文档。</span><span class="sxs-lookup"><span data-stu-id="55523-172">When you process a document with a web service that was generated with the BizTalk Server Web Services Publishing Wizard, any data contained in a field with a **Data Type** of **xs:date** is removed from the document.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="55523-173">原因</span><span class="sxs-lookup"><span data-stu-id="55523-173">Cause</span></span>  
 <span data-ttu-id="55523-174">如果发布的业务流程包含一个或多个字段都具有的架构，会出现此问题**数据类型**的**xs: date**和一个**Nillable** 属性**True**。</span><span class="sxs-lookup"><span data-stu-id="55523-174">This problem can occur if the published orchestration contains a schema with one or more fields that have a **Data Type** of **xs:date** and a **Nillable** property of **True**.</span></span>  
  
#### <a name="workaround"></a><span data-ttu-id="55523-175">解决方法</span><span class="sxs-lookup"><span data-stu-id="55523-175">Workaround</span></span>  
 <span data-ttu-id="55523-176">解决此问题，请在已发布的架构中查找字段**数据类型**的**xs: date** ，并验证**Nillable**这些字段的属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="55523-176">To workaround this problem, locate the fields in the published schema that have a **Data Type** of **xs:date** and verify that the **Nillable** property of these fields is set to **False**.</span></span>  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a><span data-ttu-id="55523-177">调用 Web 服务时，会出现"System.IO.FileNotFoundException"错误</span><span class="sxs-lookup"><span data-stu-id="55523-177">A "System.IO.FileNotFoundException" error occurs when a Web service is called</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="55523-178">问题</span><span class="sxs-lookup"><span data-stu-id="55523-178">Problem</span></span>  
 <span data-ttu-id="55523-179">当在 Microsoft ASP.NET Web 应用程序中调用 Web 服务时，可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="55523-179">When you call a Web service in a Microsoft ASP.NET Web application, you may receive the following error:</span></span>  
  
 <span data-ttu-id="55523-180">System.IO.FileNotFoundException</span><span class="sxs-lookup"><span data-stu-id="55523-180">System.IO.FileNotFoundException</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="55523-181">原因</span><span class="sxs-lookup"><span data-stu-id="55523-181">Cause</span></span>  
 <span data-ttu-id="55523-182">如果以下条件之一为 true，可能发生此错误：</span><span class="sxs-lookup"><span data-stu-id="55523-182">This error can occur if either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="55523-183">工作进程没有读取进程 Temp 目录的权限和工作进程没有写入进程 Temp 目录的权限。</span><span class="sxs-lookup"><span data-stu-id="55523-183">The worker process does not have permissions to read to the process Temp directory, and the worker process does not have permissions to write to the process Temp directory.</span></span>  
  
-   <span data-ttu-id="55523-184">XmlSerializer 生成的代码中有编译错误。</span><span class="sxs-lookup"><span data-stu-id="55523-184">There are compilation errors in the code that XmlSerializer generated.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="55523-185">解决方法</span><span class="sxs-lookup"><span data-stu-id="55523-185">Resolution</span></span>  
 <span data-ttu-id="55523-186">此错误记录在 Microsoft 知识库文章[823196](http://support.microsoft.com/kb/823196)。</span><span class="sxs-lookup"><span data-stu-id="55523-186">This error is documented in Microsoft Knowledge Base article [823196](http://support.microsoft.com/kb/823196).</span></span> <span data-ttu-id="55523-187">按照此知识库文章以解决此错误的解决方法部分中的步骤。</span><span class="sxs-lookup"><span data-stu-id="55523-187">Follow the steps in the Resolution section of this Knowledge Base article to resolve this error.</span></span>