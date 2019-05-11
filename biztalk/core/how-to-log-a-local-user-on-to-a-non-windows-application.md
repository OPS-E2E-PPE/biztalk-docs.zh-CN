---
title: 如何记录的本地用户身份登录到非 Windows 应用程序 |Microsoft Docs
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
ms.openlocfilehash: c3a403ff5e5d31b807e443377b0ca7954dd74efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384755"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a>如何登录的本地用户身份登录到非 Windows 应用程序
设置你的用户与关联应用程序后，可以使用单一登录 (SSO) 访问的外部用户名称和当前用户的凭据。 使用这些凭据，然后可以记录在用户登录到主机服务器运行的关联应用程序。  
  
> [!NOTE]
>  除了为 SSO 设置相应的安全协议，你可能还需要设置附加的安全性以允许应用程序以正确的安全上下文中调用 SSO。 如果你的应用程序不能在正确的安全上下文中调用 SSO，SSO 将拒绝对你的应用程序的访问。  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a>若要设置 SSO 应用程序的安全上下文  
  
1.  确定将哪些凭据来成功地运行应用程序需求。  
  
     例如，使用 Web 服务或在 IIS 中承载的.NET Framework 远程处理的应用程序需要模拟客户端，以便将传递到 SSO 的相应凭据。  
  
2.  确认相关的安全设置，例如与虚拟目录、 应用程序池和 web.config 文件中，已设置为你应用程序提供这些凭据。  
  
     有关如何设置安全凭据的详细信息，请参阅[Building Secure ASP.NET Applications:身份验证、 授权和安全通信](http://go.microsoft.com/fwlink/?LinkId=193906)。  
  
     ASP.NET Web 服务传递凭据的详细信息，请参阅[HOW TO:将当前凭据传递给 ASP.NET Web 服务](http://go.microsoft.com/fwlink/?LinkId=193907)。  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a>若要本地用户登录到主机应用程序  
  
1.  接收到主机服务器上运行的应用程序将当前用户的请求。  
  
     它由你负责确定当前用户请求如何登录到主机应用程序。  
  
2.  检索当前使用的用户的凭据`ISSOLookup1.GetCredentials`或`ISSOLookup2.GetCredentials`。  
  
     必须提供主机应用程序以及所有相关标志的名称。 `GetCredentials` 返回相关联的用户名和主机应用程序的凭据。  
  
     请注意，可以使用`ISSOLookup1`或`ISSOLookup2`。 唯一的区别是`ISSOLookup2`还具有将远程用户登录到本地 windows 应用程序的方法。  
  
3.  使用的外部用户名称和凭据登录到主机应用程序。  
  
     它由你负责确定如何使用凭据登录到主机应用程序。  
  
## <a name="see-also"></a>请参阅  
 [如何远程用户登录到本地应用程序](../core/how-to-log-a-remote-user-on-to-a-local-application.md)