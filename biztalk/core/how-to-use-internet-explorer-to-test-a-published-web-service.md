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
# <a name="how-to-use-internet-explorer-to-test-a-published-web-service"></a>如何使用 Internet Explorer 的已发布的 Web 服务测试
您无需编写 Web 客户端应用程序即可测试已发布的 Web Services。 可以用 Web 浏览器（如 Internet Explorer）测试已发布的 Web Services。 尽管可以用 Web 浏览器访问任意已发布的 Web Services，但只能用含有简单类型参数的 Web 方法来测试 Web Services。 若要在 Web 浏览器中测试您的 Web 方法，你的请求和响应消息的接收端口中使用的消息部分可以只是简单类型，如**System.String**或**System.Int32**。 如果有消息部分将架构用作消息类型，则无法用浏览器来测试 Web 方法。  
  
 如果想用 HTTP-GET 或 HTTP-POST 来测试已发布的 Web Services，则必须配置用于 SOAP 适配器的 BizTalk 接收位置，并修改用于已发布的 Web Services 的 Web.config 文件。  
  
 **修改接收位置**  
  
 SOAP 适配器配置接收位置时，通常会通过提供虚拟目录和 Web Services .asmx 文件名来设置接收位置的 URI：  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 这可以使 SOAP 适配器使用 HTTP-SOAP 协议来接收 Web Services 请求。 要配置接收位置以使用 HTTP-GET 或 HTTP-POST 协议，必须将方法名称附加到 URI 上：  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 方法名称与业务流程中的端口操作名称相同。  
  
 **修改 Web.config 文件**  
  
 默认情况下，向导将 Web Services 配置为使用 HTTP-SOAP 协议。 HTTP-GET 和 HTTP-POST 均被显式禁用。 若要用 Web 浏览器来测试 Web Services，则必须启用 HTTP-GET。  
  
### <a name="to-modify-the-webconfig-file-for-the-published-web-service"></a>为已发布的 Web Services 修改 Web.config 文件  
  
1.  打开已发布的 Web Services 的 Web.config 文件。  
  
    > [!NOTE]
    >  可在为含有 Web Services 的 IIS 虚拟根目录所配置的目录中找到 Web.config 文件。  
  
2.  查找\<协议 > 部分：  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  出于测试 HTTP GET，HTTP POST 或 HTTP POST 从本地计算机上，删除相应行从\<协议 > 部分。  
  
 有关配置选项的详细信息，请参阅"配置选项的 XML 创建使用 ASP.NET Web 服务"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62264](http://go.microsoft.com/fwlink/?LinkId=62264)。  
  
#### <a name="to-access-a-web-service-with-internet-explorer"></a>用 Internet Explorer 浏览器访问 Web Services  
  
-   在 Internet Explorer 中，在**地址**框中，键入 Web 服务使用的格式的 URL  **http://*servername*/*apppath*/ *webservicename*.asmx * *。  
  
    |参数|值|  
    |---------------|-----------|  
    |***servername***|已部署 XML Web Services 的服务器的名称。|  
    |***Apppath***|虚拟目录和 Web 应用程序路径的名称。|  
    |***webservicename.asmx***|XML Web 服务的 .asmx 文件的名称。|  
  
 Web Services 的说明介绍了特定 Web Services 所支持的所有 Web Services 方法。 Web Services 的说明页含有每个可用 Web 方法的链接以及该 Web Services 的服务说明。  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get"></a>通过 Internet Explorer 用 HTTP-GET 测试 Web Services  
  
1.  访问 Web Services 的说明页后，请单击 Web Services 说明页中列出的一项 Web 方法。  
  
2.  键入 Web 方法的必需参数，然后单击**Invoke**。  
  
3.  服务器在浏览器中返回一条 XML 响应。 如果 Web Services 的返回数据类型为双精度浮点数，则结果可能会类似如下：  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a>通过 Internet Explorer 用 HTTP-GET 测试 Web Services（备选方法）  
  
1.  在 Internet Explorer 中，在**地址**框中，键入 Web 服务使用的格式的 URL ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***。  
  
    |参数|值|  
    |---------------|-----------|  
    |***servername***|已部署 XML Web Services 的服务器的名称。|  
    |***Apppath***|虚拟目录和 Web 应用程序路径的名称。|  
    |***webservicename.asmx***|XML Web 服务的 .asmx 文件的名称。|  
    |***方法名称***|XML Web Services 公开的公共方法的名称。 如果保留为空，则 XML Web Services 的说明页就会出现，列出在 .asmx 文件中可用的每个公共方法。 （可选）|  
    |***参数***|方法所需要的任何参数的相应参数名称和值。 如果保留为空，则 XML Web Services 的说明页就会出现，列出在 .asmx 文件中可用的每个公共方法。 （可选）|  
  
    > [!NOTE]
    >  在本语法中，XML Web Services 方法名称区分大小写，但服务器、项目及 XML Web Services 名称都不区分。  
  
2.  按 Enter 键。 Web 浏览器显示一条来自服务器的 XML 响应。  
  
    > [!NOTE]
    >  也可以用 HTTP-POST 来调用 Web Services。 信息和示例有关调用 XML Web 服务从 Web 浏览器，请参阅"如何为:: 访问 XML Web 服务从浏览器"中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62265](http://go.microsoft.com/fwlink/?LinkId=62265)。  
  
## <a name="see-also"></a>另请参阅  
 [测试已发布的 Web 服务](../core/testing-published-web-services.md)