---
title: 测试 BizTalk web 服务 |Microsoft Docs
description: 配置接收位置和 web.config 以在 web 浏览器中测试 BizTalk web 服务
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4aa96e84003b27f9e65aa282cf157314ec5f852f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383340"
---
# <a name="test-a-biztalk-web-service"></a><span data-ttu-id="5bf8f-103">测试 BizTalk Web 服务</span><span class="sxs-lookup"><span data-stu-id="5bf8f-103">Test a BizTalk Web Service</span></span>

## <a name="overview"></a><span data-ttu-id="5bf8f-104">概述</span><span class="sxs-lookup"><span data-stu-id="5bf8f-104">Overview</span></span>
<span data-ttu-id="5bf8f-105">而无需编写 Web 客户端应用程序，可以测试已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-105">You can test your published Web service without writing a Web client application.</span></span> <span data-ttu-id="5bf8f-106">可以使用 Web 浏览器中的，如 Internet Explorer 测试已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-106">You can use a Web browser, such as Internet Explorer, to test your published Web service.</span></span> <span data-ttu-id="5bf8f-107">虽然可以访问任何已发布的 Web 服务使用 Web 浏览器，你可以仅用含有简单类型参数的 Web 方法测试 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-107">Although you can access any published Web service using a Web browser, you can only test Web services with Web methods that contain simple type parameters.</span></span> <span data-ttu-id="5bf8f-108">若要在 Web 浏览器中测试您的 Web 方法，在接收端口中使用的请求和响应消息应用消息部分只能是简单类型，如**System.String**或**System.Int32**。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-108">To test your Web method in a Web browser, your message parts for the request and response messages that are used in the receive port can only be a simple type, such as **System.String** or **System.Int32**.</span></span> <span data-ttu-id="5bf8f-109">如果有消息部分使用架构作为消息类型，不能测试的浏览器的 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-109">If any message part uses a schema as a message type, you cannot test the Web method with a browser.</span></span>  
  
 <span data-ttu-id="5bf8f-110">如果你想要测试已发布的 Web 服务使用 HTTP GET 或 HTTP POST，则必须配置 BizTalk SOAP 适配器的接收位置和修改已发布的 Web 服务的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-110">If you want to test your published Web services using HTTP-GET or HTTP-POST, you must configure your BizTalk receive location for the SOAP adapter and modify the Web.config file for your published Web service.</span></span>  
  
 <span data-ttu-id="5bf8f-111">**修改接收位置**</span><span class="sxs-lookup"><span data-stu-id="5bf8f-111">**Modifying the Receive Locations**</span></span>  
  
 <span data-ttu-id="5bf8f-112">当 SOAP 适配器配置接收位置时，SOAP 适配器通常情况下的虚拟目录和 Web 服务.asmx 文件名称，从而设置接收位置的 URI:</span><span class="sxs-lookup"><span data-stu-id="5bf8f-112">When the SOAP adapter configures receive locations, the SOAP adapter normally sets the URI of the receive location by giving the virtual directory and the Web service .asmx file name:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 <span data-ttu-id="5bf8f-113">这样，SOAP 适配器来接收 Web 服务请求使用 HTTP SOAP 协议。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-113">This allows the SOAP adapter to receive Web service requests using the HTTP-SOAP protocol.</span></span> <span data-ttu-id="5bf8f-114">若要配置接收位置以使用 HTTP-GET 或 HTTP-POST 协议，必须将方法名称追加到 URI:</span><span class="sxs-lookup"><span data-stu-id="5bf8f-114">To configure the receive location to use the HTTP-GET or HTTP-POST protocol, you must append the method name to the URI:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 <span data-ttu-id="5bf8f-115">方法名称是在业务流程中的端口操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-115">The method name is the same as the port operation name in the orchestration.</span></span>  
  
 <span data-ttu-id="5bf8f-116">**修改 Web.config 文件**</span><span class="sxs-lookup"><span data-stu-id="5bf8f-116">**Modifying the Web.config file**</span></span>  
  
 <span data-ttu-id="5bf8f-117">默认情况下，向导将配置为使用 HTTP SOAP 协议的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-117">By default, the wizard configures the Web services to use the HTTP-SOAP protocol.</span></span> <span data-ttu-id="5bf8f-118">HTTP-GET 和 HTTP-POST 均被显式禁用。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-118">HTTP-GET and HTTP-POST are explicitly disabled.</span></span> <span data-ttu-id="5bf8f-119">若要测试的 Web 浏览器的 Web 服务，必须启用 HTTP GET。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-119">To test a Web service with a Web browser, you must enable HTTP-GET.</span></span>  
  
## <a name="update-the-webconfig"></a><span data-ttu-id="5bf8f-120">更新 Web.config</span><span class="sxs-lookup"><span data-stu-id="5bf8f-120">Update the Web.config</span></span>
  
1. <span data-ttu-id="5bf8f-121">打开已发布的 Web 服务的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-121">Open the Web.config file for the published Web service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5bf8f-122">可以在你配置的目录中找到 Web.config 文件，包含 Web 服务的 IIS 虚拟根。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-122">You can find the Web.config file in the directory that you configured for the IIS virtual root that contains the Web service.</span></span>  
  
2. <span data-ttu-id="5bf8f-123">查找\<协议\>部分：</span><span class="sxs-lookup"><span data-stu-id="5bf8f-123">Find the \<protocols\> section:</span></span>  
  
   ```  
   <webServices>  
      <protocols>  
        <remove name="HttpPost" />  
        <remove name="HttpGet" />  
        <remove name="HttpPostLocalhost" />  
      </protocols>  
  
   </webServices>  
   ```  
  
3. <span data-ttu-id="5bf8f-124">用于测试 HTTP GET，HTTP POST 或 HTTP POST 从本地计算机上，删除从相应的行\<协议\>部分。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-124">For testing HTTP-GET, HTTP-POST, or HTTP-POST from the local computer, remove the corresponding line from the \<protocols\> section.</span></span>  
  
   <span data-ttu-id="5bf8f-125">有关配置选项的详细信息，请参阅[XML Web 服务使用 ASP.NET 创建的配置选项](https://msdn.microsoft.com/library/b2c0ew36.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-125">For more information about the configuration options, see [Configuration Options for XML Web Services Created Using ASP.NET](https://msdn.microsoft.com/library/b2c0ew36.aspx).</span></span> 
  
#### <a name="access-a-web-service-with-internet-explorer"></a><span data-ttu-id="5bf8f-126">访问使用 Internet Explorer 的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5bf8f-126">Access a Web service with Internet Explorer</span></span>  
  
- <span data-ttu-id="5bf8f-127">在 Internet Explorer 中，在 **地址** 框中，键入使用以下格式的 Web 服务 URL **http://<em>servername</em>/*apppath*/*webservicename*.asmx** 。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-127">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format **http://<em>servername</em>/*apppath*/*webservicename*.asmx**.</span></span>  
  
  |<span data-ttu-id="5bf8f-128">参数</span><span class="sxs-lookup"><span data-stu-id="5bf8f-128">Parameter</span></span>|<span data-ttu-id="5bf8f-129">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="5bf8f-129">Value</span></span>|  
  |---------------|-----------|  
  |<span data-ttu-id="5bf8f-130">***servername***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-130">***servername***</span></span>|<span data-ttu-id="5bf8f-131">部署 XML Web 服务的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-131">The name of the server that you have deployed your XML Web service.</span></span>|  
  |<span data-ttu-id="5bf8f-132">***Apppath***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-132">***Apppath***</span></span>|<span data-ttu-id="5bf8f-133">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-133">The name of your virtual directory and the Web application path.</span></span>|  
  |<span data-ttu-id="5bf8f-134">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-134">***webservicename.asmx***</span></span>|<span data-ttu-id="5bf8f-135">XML Web 服务.asmx 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-135">The name of the XML Web service .asmx file.</span></span>|  
  
  <span data-ttu-id="5bf8f-136">Web 服务的说明介绍了特定的 Web 服务支持的所有 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-136">The description for the Web service shows you all the Web service methods that the particular Web service supports.</span></span> <span data-ttu-id="5bf8f-137">Web 服务描述页包含每个可用的 Web 方法和 Web 服务的服务说明的链接。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-137">The Web service description page contains links for each available Web method and the service description of the Web service.</span></span>  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get"></a><span data-ttu-id="5bf8f-138">通过 Internet Explorer 用 HTTP-GET 测试 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5bf8f-138">Test a Web service with Internet Explorer using HTTP-GET</span></span>  
  
1.  <span data-ttu-id="5bf8f-139">在访问 Web 服务描述页之后, 单击 Web 服务说明页中列出的 Web 方法之一。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-139">After accessing the Web service description page, click one of the Web methods listed in the Web service description page.</span></span>  
  
2.  <span data-ttu-id="5bf8f-140">键入对于 Web 方法中，所需的参数，然后单击**Invoke**。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-140">Type the necessary parameters for the Web method, and then click **Invoke**.</span></span>  
  
3.  <span data-ttu-id="5bf8f-141">服务器将在浏览器中返回 XML 响应。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-141">The server returns an XML response in the browser.</span></span> <span data-ttu-id="5bf8f-142">如果 Web 服务的返回数据类型为双精度浮点数，结果可能类似以下形式：</span><span class="sxs-lookup"><span data-stu-id="5bf8f-142">If the return data type for the Web service is a double-precision floating-point number, the result might look like the following:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a><span data-ttu-id="5bf8f-143">通过使用 HTTP GET （备选方法） 的 Internet Explorer 测试 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5bf8f-143">Test a Web service with Internet Explorer using HTTP-GET (alternate method)</span></span>  
  
1.  <span data-ttu-id="5bf8f-144">在 Internet Explorer 中，在**地址**框中，键入使用以下格式的 Web 服务 URL ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-144">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.</span></span>  
  
    |<span data-ttu-id="5bf8f-145">参数</span><span class="sxs-lookup"><span data-stu-id="5bf8f-145">Parameter</span></span>|<span data-ttu-id="5bf8f-146">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="5bf8f-146">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="5bf8f-147">***servername***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-147">***servername***</span></span>|<span data-ttu-id="5bf8f-148">部署 XML Web 服务的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-148">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="5bf8f-149">***Apppath***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-149">***Apppath***</span></span>|<span data-ttu-id="5bf8f-150">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-150">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="5bf8f-151">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-151">***webservicename.asmx***</span></span>|<span data-ttu-id="5bf8f-152">XML Web 服务.asmx 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-152">The name of the XML Web service .asmx file.</span></span>|  
    |<span data-ttu-id="5bf8f-153">***方法名称***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-153">***Methodname***</span></span>|<span data-ttu-id="5bf8f-154">XML Web 服务公开一个公共方法的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-154">The name of a public method that the XML Web service exposes.</span></span> <span data-ttu-id="5bf8f-155">如果留空，则会显示 XML Web 服务的说明页，其中列出在.asmx 文件中的每个公共方法。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-155">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="5bf8f-156">（可选）</span><span class="sxs-lookup"><span data-stu-id="5bf8f-156">(Optional)</span></span>|  
    |<span data-ttu-id="5bf8f-157">***parameter***</span><span class="sxs-lookup"><span data-stu-id="5bf8f-157">***parameter***</span></span>|<span data-ttu-id="5bf8f-158">适当的参数名称和任何所需的方法的参数的值。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-158">The appropriate parameter name and value for any parameters required by your method.</span></span> <span data-ttu-id="5bf8f-159">如果留空，则会显示 XML Web 服务的说明页，其中列出在.asmx 文件中的每个公共方法。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-159">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="5bf8f-160">（可选）</span><span class="sxs-lookup"><span data-stu-id="5bf8f-160">(Optional)</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="5bf8f-161">此语法中的 XML Web 服务方法名称区分大小写，但服务器、 项目和 XML Web 服务名称不是。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-161">The XML Web service method name in this syntax is case sensitive, but the server, project, and XML Web service names are not.</span></span>  
  
2.  <span data-ttu-id="5bf8f-162">按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-162">Press Enter.</span></span> <span data-ttu-id="5bf8f-163">Web 浏览器显示来自服务器的 XML 响应。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-163">The Web browser displays an XML response from the server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bf8f-164">此外可以使用 HTTP POST 来调用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-164">You can also use HTTP-POST to call the Web service.</span></span> <span data-ttu-id="5bf8f-165">有关信息和有关从 Web 浏览器调用 XML Web 服务的示例，请参阅[从浏览器访问 XML Web Services](https://msdn.microsoft.com/library/45fez2a8.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5bf8f-165">For information and samples about calling XML Web services from a Web browser, see [Access XML Web Services from a Browser](https://msdn.microsoft.com/library/45fez2a8.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf8f-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bf8f-166">See Also</span></span>  
 [<span data-ttu-id="5bf8f-167">测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5bf8f-167">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)