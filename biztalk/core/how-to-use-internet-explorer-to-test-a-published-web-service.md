---
title: "如何使用 Internet Explorer 的已发布的 Web 服务测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, receive locations
- Web services, Internet Explorer
- testing, Web services
- receive locations, modifying
- Web services, modifying
- modifying, Web.config file
- Web.config file
- Web services, Web.config file
- HTTP-GET
- Web services, testing
- Web services, HTTP-GET
- modifying, Web services
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 687078a14d8cb2163c9795c68f65171e7b82467c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-internet-explorer-to-test-a-published-web-service"></a><span data-ttu-id="0bef9-102">如何使用 Internet Explorer 的已发布的 Web 服务测试</span><span class="sxs-lookup"><span data-stu-id="0bef9-102">How to Use Internet Explorer to Test a Published Web Service</span></span>
<span data-ttu-id="0bef9-103">您无需编写 Web 客户端应用程序即可测试已发布的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="0bef9-103">You can test your published Web service without writing a Web client application.</span></span> <span data-ttu-id="0bef9-104">可以用 Web 浏览器（如 Internet Explorer）测试已发布的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="0bef9-104">You can use a Web browser, such as Internet Explorer, to test your published Web service.</span></span> <span data-ttu-id="0bef9-105">尽管可以用 Web 浏览器访问任意已发布的 Web Services，但只能用含有简单类型参数的 Web 方法来测试 Web Services。</span><span class="sxs-lookup"><span data-stu-id="0bef9-105">Although you can access any published Web service using a Web browser, you can only test Web services with Web methods that contain simple type parameters.</span></span> <span data-ttu-id="0bef9-106">若要在 Web 浏览器中测试您的 Web 方法，你的请求和响应消息的接收端口中使用的消息部分可以只是简单类型，如**System.String**或**System.Int32**。</span><span class="sxs-lookup"><span data-stu-id="0bef9-106">To test your Web method in a Web browser, your message parts for the request and response messages that are used in the receive port can only be a simple type, such as **System.String** or **System.Int32**.</span></span> <span data-ttu-id="0bef9-107">如果有消息部分将架构用作消息类型，则无法用浏览器来测试 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="0bef9-107">If any message part uses a schema as a message type, you cannot test the Web method with a browser.</span></span>  
  
 <span data-ttu-id="0bef9-108">如果想用 HTTP-GET 或 HTTP-POST 来测试已发布的 Web Services，则必须配置用于 SOAP 适配器的 BizTalk 接收位置，并修改用于已发布的 Web Services 的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0bef9-108">If you want to test your published Web services using HTTP-GET or HTTP-POST, you must configure your BizTalk receive location for the SOAP adapter and modify the Web.config file for your published Web service.</span></span>  
  
 <span data-ttu-id="0bef9-109">**修改接收位置**</span><span class="sxs-lookup"><span data-stu-id="0bef9-109">**Modifying the Receive Locations**</span></span>  
  
 <span data-ttu-id="0bef9-110">SOAP 适配器配置接收位置时，通常会通过提供虚拟目录和 Web Services .asmx 文件名来设置接收位置的 URI：</span><span class="sxs-lookup"><span data-stu-id="0bef9-110">When the SOAP adapter configures receive locations, the SOAP adapter normally sets the URI of the receive location by giving the virtual directory and the Web service .asmx file name:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 <span data-ttu-id="0bef9-111">这可以使 SOAP 适配器使用 HTTP-SOAP 协议来接收 Web Services 请求。</span><span class="sxs-lookup"><span data-stu-id="0bef9-111">This allows the SOAP adapter to receive Web service requests using the HTTP-SOAP protocol.</span></span> <span data-ttu-id="0bef9-112">要配置接收位置以使用 HTTP-GET 或 HTTP-POST 协议，必须将方法名称附加到 URI 上：</span><span class="sxs-lookup"><span data-stu-id="0bef9-112">To configure the receive location to use the HTTP-GET or HTTP-POST protocol, you must append the method name to the URI:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 <span data-ttu-id="0bef9-113">方法名称与业务流程中的端口操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="0bef9-113">The method name is the same as the port operation name in the orchestration.</span></span>  
  
 <span data-ttu-id="0bef9-114">**修改 Web.config 文件**</span><span class="sxs-lookup"><span data-stu-id="0bef9-114">**Modifying the Web.config file**</span></span>  
  
 <span data-ttu-id="0bef9-115">默认情况下，向导将 Web Services 配置为使用 HTTP-SOAP 协议。</span><span class="sxs-lookup"><span data-stu-id="0bef9-115">By default, the wizard configures the Web services to use the HTTP-SOAP protocol.</span></span> <span data-ttu-id="0bef9-116">HTTP-GET 和 HTTP-POST 均被显式禁用。</span><span class="sxs-lookup"><span data-stu-id="0bef9-116">HTTP-GET and HTTP-POST are explicitly disabled.</span></span> <span data-ttu-id="0bef9-117">若要用 Web 浏览器来测试 Web Services，则必须启用 HTTP-GET。</span><span class="sxs-lookup"><span data-stu-id="0bef9-117">To test a Web service with a Web browser, you must enable HTTP-GET.</span></span>  
  
### <a name="to-modify-the-webconfig-file-for-the-published-web-service"></a><span data-ttu-id="0bef9-118">为已发布的 Web Services 修改 Web.config 文件</span><span class="sxs-lookup"><span data-stu-id="0bef9-118">To modify the Web.config file for the published Web service</span></span>  
  
1.  <span data-ttu-id="0bef9-119">打开已发布的 Web Services 的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0bef9-119">Open the Web.config file for the published Web service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bef9-120">可在为含有 Web Services 的 IIS 虚拟根目录所配置的目录中找到 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0bef9-120">You can find the Web.config file in the directory that you configured for the IIS virtual root that contains the Web service.</span></span>  
  
2.  <span data-ttu-id="0bef9-121">查找\<协议 > 部分：</span><span class="sxs-lookup"><span data-stu-id="0bef9-121">Find the \<protocols> section:</span></span>  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  <span data-ttu-id="0bef9-122">出于测试 HTTP GET，HTTP POST 或 HTTP POST 从本地计算机上，删除相应行从\<协议 > 部分。</span><span class="sxs-lookup"><span data-stu-id="0bef9-122">For testing HTTP-GET, HTTP-POST, or HTTP-POST from the local computer, remove the corresponding line from the \<protocols> section.</span></span>  
  
 <span data-ttu-id="0bef9-123">有关配置选项的详细信息，请参阅"配置选项的 XML 创建使用 ASP.NET Web 服务"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62264](http://go.microsoft.com/fwlink/?LinkId=62264)。</span><span class="sxs-lookup"><span data-stu-id="0bef9-123">For more information about the configuration options, see "Configuration Options for XML Web Services Created Using ASP.NET" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62264](http://go.microsoft.com/fwlink/?LinkId=62264).</span></span>  
  
#### <a name="to-access-a-web-service-with-internet-explorer"></a><span data-ttu-id="0bef9-124">用 Internet Explorer 浏览器访问 Web Services</span><span class="sxs-lookup"><span data-stu-id="0bef9-124">To access a Web service with Internet Explorer</span></span>  
  
-   <span data-ttu-id="0bef9-125">在 Internet Explorer 中，在**地址**框中，键入 Web 服务使用的格式的 URL  **http://*servername*/*apppath*/ *webservicename*.asmx * *。</span><span class="sxs-lookup"><span data-stu-id="0bef9-125">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format **http://*servername*/*apppath*/*webservicename*.asmx**.</span></span>  
  
    |<span data-ttu-id="0bef9-126">参数</span><span class="sxs-lookup"><span data-stu-id="0bef9-126">Parameter</span></span>|<span data-ttu-id="0bef9-127">值</span><span class="sxs-lookup"><span data-stu-id="0bef9-127">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="0bef9-128">***servername***</span><span class="sxs-lookup"><span data-stu-id="0bef9-128">***servername***</span></span>|<span data-ttu-id="0bef9-129">已部署 XML Web Services 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-129">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="0bef9-130">***Apppath***</span><span class="sxs-lookup"><span data-stu-id="0bef9-130">***Apppath***</span></span>|<span data-ttu-id="0bef9-131">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-131">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="0bef9-132">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="0bef9-132">***webservicename.asmx***</span></span>|<span data-ttu-id="0bef9-133">XML Web 服务的 .asmx 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-133">The name of the XML Web service .asmx file.</span></span>|  
  
 <span data-ttu-id="0bef9-134">Web Services 的说明介绍了特定 Web Services 所支持的所有 Web Services 方法。</span><span class="sxs-lookup"><span data-stu-id="0bef9-134">The description for the Web service shows you all the Web service methods that the particular Web service supports.</span></span> <span data-ttu-id="0bef9-135">Web Services 的说明页含有每个可用 Web 方法的链接以及该 Web Services 的服务说明。</span><span class="sxs-lookup"><span data-stu-id="0bef9-135">The Web service description page contains links for each available Web method and the service description of the Web service.</span></span>  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get"></a><span data-ttu-id="0bef9-136">通过 Internet Explorer 用 HTTP-GET 测试 Web Services</span><span class="sxs-lookup"><span data-stu-id="0bef9-136">To test a Web service with Internet Explorer using HTTP-GET</span></span>  
  
1.  <span data-ttu-id="0bef9-137">访问 Web Services 的说明页后，请单击 Web Services 说明页中列出的一项 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="0bef9-137">After accessing the Web service description page, click one of the Web methods listed in the Web service description page.</span></span>  
  
2.  <span data-ttu-id="0bef9-138">键入 Web 方法的必需参数，然后单击**Invoke**。</span><span class="sxs-lookup"><span data-stu-id="0bef9-138">Type the necessary parameters for the Web method, and then click **Invoke**.</span></span>  
  
3.  <span data-ttu-id="0bef9-139">服务器在浏览器中返回一条 XML 响应。</span><span class="sxs-lookup"><span data-stu-id="0bef9-139">The server returns an XML response in the browser.</span></span> <span data-ttu-id="0bef9-140">如果 Web Services 的返回数据类型为双精度浮点数，则结果可能会类似如下：</span><span class="sxs-lookup"><span data-stu-id="0bef9-140">If the return data type for the Web service is a double-precision floating-point number, the result might look like the following:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a><span data-ttu-id="0bef9-141">通过 Internet Explorer 用 HTTP-GET 测试 Web Services（备选方法）</span><span class="sxs-lookup"><span data-stu-id="0bef9-141">To test a Web service with Internet Explorer using HTTP-GET (alternate method)</span></span>  
  
1.  <span data-ttu-id="0bef9-142">在 Internet Explorer 中，在**地址**框中，键入 Web 服务使用的格式的 URL ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***。</span><span class="sxs-lookup"><span data-stu-id="0bef9-142">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.</span></span>  
  
    |<span data-ttu-id="0bef9-143">参数</span><span class="sxs-lookup"><span data-stu-id="0bef9-143">Parameter</span></span>|<span data-ttu-id="0bef9-144">值</span><span class="sxs-lookup"><span data-stu-id="0bef9-144">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="0bef9-145">***servername***</span><span class="sxs-lookup"><span data-stu-id="0bef9-145">***servername***</span></span>|<span data-ttu-id="0bef9-146">已部署 XML Web Services 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-146">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="0bef9-147">***Apppath***</span><span class="sxs-lookup"><span data-stu-id="0bef9-147">***Apppath***</span></span>|<span data-ttu-id="0bef9-148">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-148">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="0bef9-149">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="0bef9-149">***webservicename.asmx***</span></span>|<span data-ttu-id="0bef9-150">XML Web 服务的 .asmx 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-150">The name of the XML Web service .asmx file.</span></span>|  
    |<span data-ttu-id="0bef9-151">***方法名称***</span><span class="sxs-lookup"><span data-stu-id="0bef9-151">***Methodname***</span></span>|<span data-ttu-id="0bef9-152">XML Web Services 公开的公共方法的名称。</span><span class="sxs-lookup"><span data-stu-id="0bef9-152">The name of a public method that the XML Web service exposes.</span></span> <span data-ttu-id="0bef9-153">如果保留为空，则 XML Web Services 的说明页就会出现，列出在 .asmx 文件中可用的每个公共方法。</span><span class="sxs-lookup"><span data-stu-id="0bef9-153">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="0bef9-154">（可选）</span><span class="sxs-lookup"><span data-stu-id="0bef9-154">(Optional)</span></span>|  
    |<span data-ttu-id="0bef9-155">***参数***</span><span class="sxs-lookup"><span data-stu-id="0bef9-155">***parameter***</span></span>|<span data-ttu-id="0bef9-156">方法所需要的任何参数的相应参数名称和值。</span><span class="sxs-lookup"><span data-stu-id="0bef9-156">The appropriate parameter name and value for any parameters required by your method.</span></span> <span data-ttu-id="0bef9-157">如果保留为空，则 XML Web Services 的说明页就会出现，列出在 .asmx 文件中可用的每个公共方法。</span><span class="sxs-lookup"><span data-stu-id="0bef9-157">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="0bef9-158">（可选）</span><span class="sxs-lookup"><span data-stu-id="0bef9-158">(Optional)</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="0bef9-159">在本语法中，XML Web Services 方法名称区分大小写，但服务器、项目及 XML Web Services 名称都不区分。</span><span class="sxs-lookup"><span data-stu-id="0bef9-159">The XML Web service method name in this syntax is case sensitive, but the server, project, and XML Web service names are not.</span></span>  
  
2.  <span data-ttu-id="0bef9-160">按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="0bef9-160">Press Enter.</span></span> <span data-ttu-id="0bef9-161">Web 浏览器显示一条来自服务器的 XML 响应。</span><span class="sxs-lookup"><span data-stu-id="0bef9-161">The Web browser displays an XML response from the server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bef9-162">也可以用 HTTP-POST 来调用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="0bef9-162">You can also use HTTP-POST to call the Web service.</span></span> <span data-ttu-id="0bef9-163">信息和示例有关调用 XML Web 服务从 Web 浏览器，请参阅"如何为:: 访问 XML Web 服务从浏览器"中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62265](http://go.microsoft.com/fwlink/?LinkId=62265)。</span><span class="sxs-lookup"><span data-stu-id="0bef9-163">For information and samples about calling XML Web services from a Web browser, see "How to: Access XML Web Services from a Browser" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62265](http://go.microsoft.com/fwlink/?LinkId=62265).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bef9-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bef9-164">See Also</span></span>  
 [<span data-ttu-id="0bef9-165">测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0bef9-165">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)