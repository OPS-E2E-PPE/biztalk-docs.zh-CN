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
# <a name="test-a-biztalk-web-service"></a>测试 BizTalk Web 服务

## <a name="overview"></a>概述
而无需编写 Web 客户端应用程序，可以测试已发布的 Web 服务。 可以使用 Web 浏览器中的，如 Internet Explorer 测试已发布的 Web 服务。 虽然可以访问任何已发布的 Web 服务使用 Web 浏览器，你可以仅用含有简单类型参数的 Web 方法测试 Web 服务。 若要在 Web 浏览器中测试您的 Web 方法，在接收端口中使用的请求和响应消息应用消息部分只能是简单类型，如**System.String**或**System.Int32**。 如果有消息部分使用架构作为消息类型，不能测试的浏览器的 Web 方法。  
  
 如果你想要测试已发布的 Web 服务使用 HTTP GET 或 HTTP POST，则必须配置 BizTalk SOAP 适配器的接收位置和修改已发布的 Web 服务的 Web.config 文件。  
  
 **修改接收位置**  
  
 当 SOAP 适配器配置接收位置时，SOAP 适配器通常情况下的虚拟目录和 Web 服务.asmx 文件名称，从而设置接收位置的 URI:  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 这样，SOAP 适配器来接收 Web 服务请求使用 HTTP SOAP 协议。 若要配置接收位置以使用 HTTP-GET 或 HTTP-POST 协议，必须将方法名称追加到 URI:  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 方法名称是在业务流程中的端口操作名称相同。  
  
 **修改 Web.config 文件**  
  
 默认情况下，向导将配置为使用 HTTP SOAP 协议的 Web 服务。 HTTP-GET 和 HTTP-POST 均被显式禁用。 若要测试的 Web 浏览器的 Web 服务，必须启用 HTTP GET。  
  
## <a name="update-the-webconfig"></a>更新 Web.config
  
1. 打开已发布的 Web 服务的 Web.config 文件。  
  
   > [!NOTE]
   >  可以在你配置的目录中找到 Web.config 文件，包含 Web 服务的 IIS 虚拟根。  
  
2. 查找\<协议\>部分：  
  
   ```  
   <webServices>  
      <protocols>  
        <remove name="HttpPost" />  
        <remove name="HttpGet" />  
        <remove name="HttpPostLocalhost" />  
      </protocols>  
  
   </webServices>  
   ```  
  
3. 用于测试 HTTP GET，HTTP POST 或 HTTP POST 从本地计算机上，删除从相应的行\<协议\>部分。  
  
   有关配置选项的详细信息，请参阅[XML Web 服务使用 ASP.NET 创建的配置选项](https://msdn.microsoft.com/library/b2c0ew36.aspx)。 
  
#### <a name="access-a-web-service-with-internet-explorer"></a>访问使用 Internet Explorer 的 Web 服务  
  
- 在 Internet Explorer 中，在**地址**框中，键入使用以下格式的 Web 服务 URL **http://<em>servername</em>/*apppath* /*webservicename*.asmx**。  
  
  |参数|ReplTest1|  
  |---------------|-----------|  
  |***servername***|部署 XML Web 服务的服务器的名称。|  
  |***Apppath***|虚拟目录和 Web 应用程序路径的名称。|  
  |***webservicename.asmx***|XML Web 服务.asmx 文件的名称。|  
  
  Web 服务的说明介绍了特定的 Web 服务支持的所有 Web 服务方法。 Web 服务描述页包含每个可用的 Web 方法和 Web 服务的服务说明的链接。  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get"></a>通过 Internet Explorer 用 HTTP-GET 测试 Web 服务  
  
1.  在访问 Web 服务描述页之后, 单击 Web 服务说明页中列出的 Web 方法之一。  
  
2.  键入对于 Web 方法中，所需的参数，然后单击**Invoke**。  
  
3.  服务器将在浏览器中返回 XML 响应。 如果 Web 服务的返回数据类型为双精度浮点数，结果可能类似以下形式：  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a>通过使用 HTTP GET （备选方法） 的 Internet Explorer 测试 Web 服务  
  
1.  在 Internet Explorer 中，在**地址**框中，键入使用以下格式的 Web 服务 URL ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***。  
  
    |参数|ReplTest1|  
    |---------------|-----------|  
    |***servername***|部署 XML Web 服务的服务器的名称。|  
    |***Apppath***|虚拟目录和 Web 应用程序路径的名称。|  
    |***webservicename.asmx***|XML Web 服务.asmx 文件的名称。|  
    |***方法名称***|XML Web 服务公开一个公共方法的名称。 如果留空，则会显示 XML Web 服务的说明页，其中列出在.asmx 文件中的每个公共方法。 （可选）|  
    |***parameter***|适当的参数名称和任何所需的方法的参数的值。 如果留空，则会显示 XML Web 服务的说明页，其中列出在.asmx 文件中的每个公共方法。 （可选）|  
  
    > [!NOTE]
    >  此语法中的 XML Web 服务方法名称区分大小写，但服务器、 项目和 XML Web 服务名称不是。  
  
2.  按 Enter 键。 Web 浏览器显示来自服务器的 XML 响应。  
  
    > [!NOTE]
    >  此外可以使用 HTTP POST 来调用 Web 服务。 有关信息和有关从 Web 浏览器调用 XML Web 服务的示例，请参阅[从浏览器访问 XML Web Services](https://msdn.microsoft.com/library/45fez2a8.aspx)。  
  
## <a name="see-also"></a>请参阅  
 [测试已发布的 Web 服务](../core/testing-published-web-services.md)