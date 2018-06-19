---
title: 如何登录到非 Windows 应用程序的本地用户 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55957f4-22c4-48b5-827a-ab41d8f846ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3c2e9ffaede20e29987938a436ad2a091920fce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253869"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a>如何登录到非 Windows 应用程序的本地用户
使用关联应用程序设置了用户后，就可以使用单一登录 (SSO) 来访问当前用户的外部用户名和凭据。 然后，可以使用这些凭据将您的用户登录到运行在主机服务器上的关联应用程序。  
  
> [!NOTE]
>  除了为 SSO 设置相应的安全协议外，您还可能需要设置附加的安全性，使您的应用程序可以在正确的安全上下文中调用 SSO。 如果您的应用程序无法在正确的安全上下文中调用 SSO，则 SSO 将拒绝对您的应用程序的访问。  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a>为 SSO 应用程序设置安全上下文  
  
1.  标识您的应用程序成功运行所需的凭据。  
  
     例如，使用 Web 服务或在 IIS 中承载的.NET Framework 远程处理的应用程序需要模拟客户端，以便将传递到 SSO 的相应凭据。  
  
2.  确认相关的安全设置（例如与虚拟目录、应用程序池和 web.config 文件有关的安全设置）设置为向您的应用程序提供这些凭据。  
  
     有关如何设置安全凭据的详细信息，请参阅[生成安全 ASP.NET 应用程序： 身份验证、 授权和安全通信](http://go.microsoft.com/fwlink/?LinkId=193906)。  
  
     有关 ASP.NET Web 服务传递凭据的信息的详细信息，请参阅[HOW TO： 传递到 ASP.NET Web 服务的当前凭据](http://go.microsoft.com/fwlink/?LinkId=193907)。  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a>将本地用户登录到宿主应用程序  
  
1.  接收将当前用户登录到运行在主机服务器上的应用程序的请求。  
  
     您负责确定当前用户如何请求登录到宿主应用程序。  
  
2.  检索当前正在使用的用户的凭据`ISSOLookup1.GetCredentials`或`ISSOLookup2.GetCredentials`。  
  
     必须提供主机应用程序以及任何相关的标志的名称。 `GetCredentials`返回的关联的用户名称和主机应用程序的凭据。  
  
     请注意，你可以使用`ISSOLookup1`或`ISSOLookup2`。 唯一的区别是`ISSOLookup2`还具有日志记录到本地 windows 应用程序的远程用户的方法。  
  
3.  使用外部用户名和凭据登录到宿主应用程序。  
  
     您负责确定如何使用凭据以登录到宿主应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [如何登录到本地的应用程序的远程用户](../core/how-to-log-a-remote-user-on-to-a-local-application.md)