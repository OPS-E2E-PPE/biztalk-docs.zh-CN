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
ms.openlocfilehash: 666b08e0c7992f8660d005bef51d26c8f51bbed5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-web-services"></a><span data-ttu-id="d39d0-102">BizTalk Web Services 疑难解答</span><span class="sxs-lookup"><span data-stu-id="d39d0-102">Troubleshooting BizTalk Web Services</span></span>
<span data-ttu-id="d39d0-103">本部分提供如何找出和解决常见 Web Services 问题的建议。</span><span class="sxs-lookup"><span data-stu-id="d39d0-103">This section offers advice on how to identify and resolve common Web service issues.</span></span>  
  
## <a name="general-troubleshooting"></a><span data-ttu-id="d39d0-104">常规疑难解答</span><span class="sxs-lookup"><span data-stu-id="d39d0-104">General Troubleshooting</span></span>  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a><span data-ttu-id="d39d0-105">启用 Web Services 发布向导跟踪</span><span class="sxs-lookup"><span data-stu-id="d39d0-105">Enabling Web Services Publishing Wizard tracing</span></span>  
 <span data-ttu-id="d39d0-106">你可以启用跟踪来调试 BizTalk Web 服务发布向导通过对取消注释\<添加 > BTSWebSvcWiz.exe.config 文件中的节点。</span><span class="sxs-lookup"><span data-stu-id="d39d0-106">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="d39d0-107">有关从 Web 服务发布向导获取跟踪信息的详细信息，请参阅[如何修改 BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-107">For more information about obtaining trace information from the Web Services Publishing Wizard, see [How to Modify BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md).</span></span>  
  
### <a name="enabling-soap-message-tracing"></a><span data-ttu-id="d39d0-108">启用 SOAP 消息跟踪</span><span class="sxs-lookup"><span data-stu-id="d39d0-108">Enabling SOAP message tracing</span></span>  
 <span data-ttu-id="d39d0-109">通过使用 SOAP 扩展，您可以启用有助于调试 Web Services 发布应用程序的 SOAP 消息跟踪。</span><span class="sxs-lookup"><span data-stu-id="d39d0-109">You can enable SOAP message tracing to help you debug the Web services publishing application by using a SOAP extension.</span></span> <span data-ttu-id="d39d0-110">有关 SOAP 扩展的详细信息，请参阅[如何： 实现 SOAP 扩展](http://go.microsoft.com/fwlink/?LinkId=62314)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-110">For more information about SOAP extensions, see [How to: Implement a SOAP Extension](http://go.microsoft.com/fwlink/?LinkId=62314).</span></span>  
  
### <a name="using-the-throwdetailederror-switch"></a><span data-ttu-id="d39d0-111">使用 ThrowDetailedError 开关</span><span class="sxs-lookup"><span data-stu-id="d39d0-111">Using the ThrowDetailedError switch</span></span>  
 <span data-ttu-id="d39d0-112">如果发生错误，Web 客户端接收泛型**SoapException**。</span><span class="sxs-lookup"><span data-stu-id="d39d0-112">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="d39d0-113">若要调试已发布 Web Services，您可以向 web.config 文件添加一个开关来控制由已发布 Web Services 返回的异常详细信息的级别。</span><span class="sxs-lookup"><span data-stu-id="d39d0-113">To debug your published Web service, you can add a switch to the web.config file to control the level of the exception details returned from the published Web service.</span></span> <span data-ttu-id="d39d0-114">该交换机是否**ThrowDetailedError**，并且当设置为**True**服务器代理到 Web 客户端，使你能够调试已发布的 Web 服务返回内部异常信息。</span><span class="sxs-lookup"><span data-stu-id="d39d0-114">The switch is **ThrowDetailedError**, and when it is set to **True** the server proxy returns inner exception information to the Web client, enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="d39d0-115">下面的 XML 代码演示**ThrowDetailedError**下 web.config 文件中出现的交换机\<appSettings > 节点：</span><span class="sxs-lookup"><span data-stu-id="d39d0-115">The following XML code shows the **ThrowDetailedError** switch that appears in the web.config file under the \<appSettings> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  <span data-ttu-id="d39d0-116">内部异常可能包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="d39d0-116">The inner exception may contain sensitive information.</span></span> <span data-ttu-id="d39d0-117">调试后，应设置**ThrowDetailedError**切换到**False**。</span><span class="sxs-lookup"><span data-stu-id="d39d0-117">After debugging, you should set the **ThrowDetailedError** switch to **False**.</span></span>  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a><span data-ttu-id="d39d0-118">使用 .NET Framework 跟踪来捕获和记录 Web Services 中的错误</span><span class="sxs-lookup"><span data-stu-id="d39d0-118">Using .NET Framework tracing to capture and log errors in the Web service</span></span>  
 <span data-ttu-id="d39d0-119">.NET Framework **System.Diagnostics.Trace**类可以用于捕获并将错误写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="d39d0-119">The .NET Framework **System.Diagnostics.Trace** class can be used to capture and write errors to a text file.</span></span>  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a><span data-ttu-id="d39d0-120">使用 System.Diagnostics.Trace 类捕获错误并将其写入文本文件</span><span class="sxs-lookup"><span data-stu-id="d39d0-120">To use the System.Diagnostics.Trace class to capture and write errors to a text file</span></span>  
  
1.  <span data-ttu-id="d39d0-121">更新要设置为跟踪编译器指令的 Web 服务的 web.config 文件**true**并添加**TraceSwitch**值：</span><span class="sxs-lookup"><span data-stu-id="d39d0-121">Update the web.config file for the Web service to set the TRACE compiler directive to **true** and add a **TraceSwitch** value:</span></span>  
  
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
    >  <span data-ttu-id="d39d0-122">如果跟踪编译器指令未设置为**true** ，则将不生成任何 trace 输出。</span><span class="sxs-lookup"><span data-stu-id="d39d0-122">If the TRACE compiler directive is not set to **true** then no trace output will be generated.</span></span> <span data-ttu-id="d39d0-123">**TraceSwitch**值还可以调用类中设置，但为方便起见 web.config 文件中未在此处设置。</span><span class="sxs-lookup"><span data-stu-id="d39d0-123">The **TraceSwitch** value can also be set in the calling class but is set here in the web.config file for convenience.</span></span> <span data-ttu-id="d39d0-124">设置**TraceSwitch**到出于开发目的的适当级别值，并在开发完成以减少或避免降低跟踪输出之后更改值。</span><span class="sxs-lookup"><span data-stu-id="d39d0-124">Set the **TraceSwitch** value to the appropriate level for development purposes and change the value after development is complete to reduce or inhibit trace output.</span></span>  
  
2.  <span data-ttu-id="d39d0-125">创建的实例**TraceSwitch**和**TextWriterTraceListener**类和使用**try … catch**块中，在 Web 服务 [WebMethod] 调用，以捕获并写入到的错误跟踪输出文件。</span><span class="sxs-lookup"><span data-stu-id="d39d0-125">Create an instance of the **TraceSwitch** and **TextWriterTraceListener** classes and use a **try…catch** block in the Web service [WebMethod] call to trap and write errors to a trace output file.</span></span> <span data-ttu-id="d39d0-126">例如，以下代码捕捉尝试将整数变量 s2 设置为对象变量 o2 的空实例时生成的错误：</span><span class="sxs-lookup"><span data-stu-id="d39d0-126">For example, the following code traps an error that is generated when attempting to set the integer variable s2 to a null instance of the object variable o2:</span></span>  
  
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
    >  <span data-ttu-id="d39d0-127">此代码是在创建一个新时，默认情况下生成 HelloWorld Web 服务的修改的版本**ASP.Net Web 服务**项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d39d0-127">This code is a modified version of the HelloWorld Web service that is generated by default when you create a new **ASP.Net Web Service** project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d39d0-128">适用于 Windows Vista，可能需要管理员权限将跟踪输出文件写入到的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="d39d0-128">For Windows Vista, Administrator privileges may be required to write the trace output file to the root folder.</span></span>  
  
3.  <span data-ttu-id="d39d0-129">重新生成 Web Services 项目。</span><span class="sxs-lookup"><span data-stu-id="d39d0-129">Rebuild the Web service project.</span></span> <span data-ttu-id="d39d0-130">现在，如果在发生错误**重**在中处理异常的语句**捕获**语句和错误写入到跟踪输出文件。</span><span class="sxs-lookup"><span data-stu-id="d39d0-130">Now, if an error occurs in the **Try** statement the exception is handled in the **Catch** statement and an error is written to the trace output file.</span></span>  
  
## <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="d39d0-131">常见疑难问题与解答</span><span class="sxs-lookup"><span data-stu-id="d39d0-131">General Troubleshooting Questions and Answers</span></span>  
 <span data-ttu-id="d39d0-132">本部分包含可帮助您解决 Web Services 问题的一系列问题与解答。</span><span class="sxs-lookup"><span data-stu-id="d39d0-132">This section contains a set of questions and answers designed to help you resolve issues with Web services.</span></span>  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a><span data-ttu-id="d39d0-133">在使用 Web Services 时出现错误；如何避免？</span><span class="sxs-lookup"><span data-stu-id="d39d0-133">I am receiving errors when consuming a Web service; how can I avoid them?</span></span>  
 <span data-ttu-id="d39d0-134">使用 Web Services 时需要考虑诸多细节，包括：</span><span class="sxs-lookup"><span data-stu-id="d39d0-134">There are many details to consider when consuming a Web service, including the following:</span></span>  
  
-   <span data-ttu-id="d39d0-135">避免在参数名称中使用两条下划线。</span><span class="sxs-lookup"><span data-stu-id="d39d0-135">Avoid using two underscore characters in a parameter name.</span></span>  
  
-   <span data-ttu-id="d39d0-136">利用**任何**元素或**anyAttribute** Web 方法中不支持属性。</span><span class="sxs-lookup"><span data-stu-id="d39d0-136">Use of the **any** element or the **anyAttribute** attribute is not supported in Web methods.</span></span>  
  
-   <span data-ttu-id="d39d0-137">避免使用 XLANG/s 关键字作为 Web Services 名称或 Web 方法名称。</span><span class="sxs-lookup"><span data-stu-id="d39d0-137">Avoid using XLANG/s keywords as a Web service name or Web method name.</span></span>  
  
-   <span data-ttu-id="d39d0-138">避免使用 XLANG/s 不支持的 Web 方法参数类型。</span><span class="sxs-lookup"><span data-stu-id="d39d0-138">Avoid using Web method parameter types that are not supported by XLANG/s.</span></span>  
  
-   <span data-ttu-id="d39d0-139">不要在架构中使用作为 C# 关键字或将作为无效 C# 标识符使用的元素名称。</span><span class="sxs-lookup"><span data-stu-id="d39d0-139">Do not use element names that are C# keywords or will be invalid as a C# identifier in your schemas.</span></span>  
  
-   <span data-ttu-id="d39d0-140">避免使用具有多个服务或端口类型定义的 Web Services 描述语言 (WSDL) 文件。</span><span class="sxs-lookup"><span data-stu-id="d39d0-140">Avoid Web Services Description Language (WSDL) files with multiple service or port type definitions.</span></span>  
  
-   <span data-ttu-id="d39d0-141">Web 方法参数必须执行 Xml 序列化。</span><span class="sxs-lookup"><span data-stu-id="d39d0-141">Web method parameters must be Xml Serializable.</span></span>  
  
-   <span data-ttu-id="d39d0-142">避免引用包含多根架构的已使用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="d39d0-142">Avoid references to consumed Web services that contain multi-rooted schemas.</span></span>  
  
-   <span data-ttu-id="d39d0-143">对于需要基于泛型参数（如空参数）的 Web 方法，避免引用带有此种方法的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="d39d0-143">Avoid referencing Web services with Web methods expecting generic-based parameters such as nullable parameters.</span></span>  
  
-   <span data-ttu-id="d39d0-144">不支持 WSDL 导入元素。</span><span class="sxs-lookup"><span data-stu-id="d39d0-144">The WSDL import element is not supported.</span></span>  
  
 <span data-ttu-id="d39d0-145">有关这些详细信息和相关的注意事项，请参阅[注意事项使用 Web 服务时](../core/considerations-when-consuming-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-145">For more information about these and related considerations, see [Considerations When Consuming Web Services](../core/considerations-when-consuming-web-services.md).</span></span>  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a><span data-ttu-id="d39d0-146">为什么我收到发布我使用的架构的错误\<包括 > 元素？</span><span class="sxs-lookup"><span data-stu-id="d39d0-146">Why am I getting errors publishing my schema that uses the \<include> element?</span></span>  
 <span data-ttu-id="d39d0-147">如果它们包括循环引用，无法发布架构 (包括的架构具有**包括**到包括架构元素) 或具有无法解析**schemaLocation**属性。</span><span class="sxs-lookup"><span data-stu-id="d39d0-147">Schemas cannot be published if they include circular references (the included schema has an **include** element to the including schema) or have an unresolved **schemaLocation** attribute.</span></span>  
  
 <span data-ttu-id="d39d0-148">有关限制的详细信息**包括**元素，请参阅[包括元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=62312)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-148">For more information about the limitation of the **include** element, see [Include Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span> <span data-ttu-id="d39d0-149">Web 服务发布向导在.NET Framework 2.0; 中具有与 XSD.exe 相同的限制有关详细信息，请参阅[导入元素绑定支持](http://go.microsoft.com/fwlink/?LinkId=119606)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-149">The Web Services Publishing Wizard has the same limitations as XSD.exe in .NET Framework 2.0; for more information, see [Import Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=119606).</span></span>  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a><span data-ttu-id="d39d0-150">为什么在发布信封架构时出现错误？</span><span class="sxs-lookup"><span data-stu-id="d39d0-150">Why do I receive errors when publishing my envelope schema?</span></span>  
 <span data-ttu-id="d39d0-151">如果您有一个要发布为 Web Services 的信封架构，则需要手动修改生成的 Web 项目。</span><span class="sxs-lookup"><span data-stu-id="d39d0-151">If you have an envelope schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="d39d0-152">为信封架构修改生成的 Web 项目</span><span class="sxs-lookup"><span data-stu-id="d39d0-152">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="d39d0-153">打开 *\<myWebService >*。 asmx.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="d39d0-153">Open the *\<myWebService>*.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="d39d0-154">编辑文件，并更改`bodyTypeAssemblyQualifiedName = <dll.name.version>`到`bodyTypeAssemblyQualifiedName = null`</span><span class="sxs-lookup"><span data-stu-id="d39d0-154">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version>` to `bodyTypeAssemblyQualifiedName = null`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d39d0-155">如果先前的 .dll 文件仍然在 ASP.NET 工作进程中，您可能需要重置 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-155">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASP.NET worker process.</span></span>  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a><span data-ttu-id="d39d0-156">已发布 Web Services 的客户端可能不会出现服务器脚本超时错误。</span><span class="sxs-lookup"><span data-stu-id="d39d0-156">Clients of published Web services may not receive server script time-out errors</span></span>  
 <span data-ttu-id="d39d0-157">如果使用 .NET framework 的 Web 客户端调用某个使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services 发布向导生成的 Web Service，则客户端可能无法收到服务器脚本超时错误，因为默认情况下会首先发生客户端请求超时。</span><span class="sxs-lookup"><span data-stu-id="d39d0-157">If Web clients that use .NET Framework are calling a Web service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script time-out errors because the client request time-out occurs first by default.</span></span> <span data-ttu-id="d39d0-158">若要解决该问题，可执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="d39d0-158">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="d39d0-159">通过增加的值增加到大于服务器脚本超时的值的客户端请求超时**HttpWebRequest.Timeout**客户端上的属性。</span><span class="sxs-lookup"><span data-stu-id="d39d0-159">Increase the client request time-out to a value greater than the server script time-out by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="d39d0-160">通过减少的值减小为小于客户端请求超时的值的服务器脚本超时**HttpServerUtility.ScriptTimeout**服务器上的属性。</span><span class="sxs-lookup"><span data-stu-id="d39d0-160">Reduce the server script time-out to a value less than the client request time-out by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="common-errors"></a><span data-ttu-id="d39d0-161">常见错误</span><span class="sxs-lookup"><span data-stu-id="d39d0-161">Common Errors</span></span>  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a><span data-ttu-id="d39d0-162">Web Services 返回 HTTP 404（找不到文件）错误</span><span class="sxs-lookup"><span data-stu-id="d39d0-162">A Web service returns an HTTP 404 (File Not Found) error</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="d39d0-163">问题</span><span class="sxs-lookup"><span data-stu-id="d39d0-163">Problem</span></span>  
 <span data-ttu-id="d39d0-164">尝试调用 Web Services 时返回 HTTP 404（找不到文件）错误。</span><span class="sxs-lookup"><span data-stu-id="d39d0-164">Attempts to call a Web service return an HTTP 404 (File Not Found) error.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="d39d0-165">原因</span><span class="sxs-lookup"><span data-stu-id="d39d0-165">Cause</span></span>  
 <span data-ttu-id="d39d0-166">如果承载 Web Services 的 IIS 服务器没有安装和/或启用 ASP.NET，可能出现此错误。</span><span class="sxs-lookup"><span data-stu-id="d39d0-166">This error can occur if ASP.NET is not installed and/or enabled on the IIS server that hosts the Web service.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="d39d0-167">解决方法</span><span class="sxs-lookup"><span data-stu-id="d39d0-167">Resolution</span></span>  
 <span data-ttu-id="d39d0-168">确保安装并启用了 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="d39d0-168">Ensure that ASP.NET is installed and enabled.</span></span> <span data-ttu-id="d39d0-169">安装 .NET Framework（如果尚未安装），并且/或运行位于 IIS 服务器的 %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ 文件夹中的 aspnet_regiis.exe 程序。</span><span class="sxs-lookup"><span data-stu-id="d39d0-169">Install the .NET Framework if it is not installed and/or run the aspnet_regiis.exe program located in the %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ folder of the IIS server.</span></span>  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a><span data-ttu-id="d39d0-170">数据字段从 Web Services 处理的文档中删除，该 Web Services 是通过 BizTalk Server Web Services 发布向导生成的。</span><span class="sxs-lookup"><span data-stu-id="d39d0-170">Date fields are removed from documents processed by a web service generated with the BizTalk Server Web Services Publishing Wizard</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="d39d0-171">问题</span><span class="sxs-lookup"><span data-stu-id="d39d0-171">Problem</span></span>  
 <span data-ttu-id="d39d0-172">处理具有 BizTalk Server Web 服务发布向导中，包含的字段中的任何数据具有生成的 web 服务的文档时**数据类型**的**xs: date**从删除文档。</span><span class="sxs-lookup"><span data-stu-id="d39d0-172">When you process a document with a web service that was generated with the BizTalk Server Web Services Publishing Wizard, any data contained in a field with a **Data Type** of **xs:date** is removed from the document.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="d39d0-173">原因</span><span class="sxs-lookup"><span data-stu-id="d39d0-173">Cause</span></span>  
 <span data-ttu-id="d39d0-174">如果已发布的业务流程包含具有一个或多个字段具有的架构，则会出现此问题**数据类型**的**xs: date**和**Nillable** 属性**True**。</span><span class="sxs-lookup"><span data-stu-id="d39d0-174">This problem can occur if the published orchestration contains a schema with one or more fields that have a **Data Type** of **xs:date** and a **Nillable** property of **True**.</span></span>  
  
#### <a name="workaround"></a><span data-ttu-id="d39d0-175">解决方法</span><span class="sxs-lookup"><span data-stu-id="d39d0-175">Workaround</span></span>  
 <span data-ttu-id="d39d0-176">解决此问题，在具有已发布的架构中查找字段**数据类型**的**xs: date**并确认**Nillable**这些字段的属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="d39d0-176">To workaround this problem, locate the fields in the published schema that have a **Data Type** of **xs:date** and verify that the **Nillable** property of these fields is set to **False**.</span></span>  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a><span data-ttu-id="d39d0-177">调用 Web Services 时出现“System.IO.FileNotFoundException”错误。</span><span class="sxs-lookup"><span data-stu-id="d39d0-177">A "System.IO.FileNotFoundException" error occurs when a Web service is called</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="d39d0-178">问题</span><span class="sxs-lookup"><span data-stu-id="d39d0-178">Problem</span></span>  
 <span data-ttu-id="d39d0-179">在 Microsoft ASP.NET Web 应用程序中调用 Web Services 时，可能出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="d39d0-179">When you call a Web service in a Microsoft ASP.NET Web application, you may receive the following error:</span></span>  
  
 <span data-ttu-id="d39d0-180">System.IO.FileNotFoundException</span><span class="sxs-lookup"><span data-stu-id="d39d0-180">System.IO.FileNotFoundException</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="d39d0-181">原因</span><span class="sxs-lookup"><span data-stu-id="d39d0-181">Cause</span></span>  
 <span data-ttu-id="d39d0-182">如果满足以下条件之一，就可能出现此错误：</span><span class="sxs-lookup"><span data-stu-id="d39d0-182">This error can occur if either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="d39d0-183">工作进程没有读取进程 Temp 目录的权限，并且工作进程没有写入进程 Temp 目录的权限。</span><span class="sxs-lookup"><span data-stu-id="d39d0-183">The worker process does not have permissions to read to the process Temp directory, and the worker process does not have permissions to write to the process Temp directory.</span></span>  
  
-   <span data-ttu-id="d39d0-184">在 XmlSerializer 生成的代码中有编译错误。</span><span class="sxs-lookup"><span data-stu-id="d39d0-184">There are compilation errors in the code that XmlSerializer generated.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="d39d0-185">解决方法</span><span class="sxs-lookup"><span data-stu-id="d39d0-185">Resolution</span></span>  
 <span data-ttu-id="d39d0-186">此错误记录在 Microsoft 知识库文章[823196](http://support.microsoft.com/kb/823196)。</span><span class="sxs-lookup"><span data-stu-id="d39d0-186">This error is documented in Microsoft Knowledge Base article [823196](http://support.microsoft.com/kb/823196).</span></span> <span data-ttu-id="d39d0-187">请按照此知识库文章解决方法部分的步骤纠正此错误。</span><span class="sxs-lookup"><span data-stu-id="d39d0-187">Follow the steps in the Resolution section of this Knowledge Base article to resolve this error.</span></span>