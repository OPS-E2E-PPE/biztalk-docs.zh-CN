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
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a><span data-ttu-id="8a151-102">如何登录的本地用户身份登录到非 Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="8a151-102">How to Log a Local User on to a Non-Windows Application</span></span>
<span data-ttu-id="8a151-103">设置你的用户与关联应用程序后，可以使用单一登录 (SSO) 访问的外部用户名称和当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="8a151-103">After you set up your user with an affiliate application, you can use Single Sign-On (SSO) to access the external user name and credentials of the current user.</span></span> <span data-ttu-id="8a151-104">使用这些凭据，然后可以记录在用户登录到主机服务器运行的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a151-104">Using these credentials, you can then log your user on to the affiliate application that is running on a host server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a151-105">除了为 SSO 设置相应的安全协议，你可能还需要设置附加的安全性以允许应用程序以正确的安全上下文中调用 SSO。</span><span class="sxs-lookup"><span data-stu-id="8a151-105">In addition to setting the appropriate security protocols for SSO, you might also need to set additional security to allow your application to call SSO in the correct security context.</span></span> <span data-ttu-id="8a151-106">如果你的应用程序不能在正确的安全上下文中调用 SSO，SSO 将拒绝对你的应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="8a151-106">If your application cannot call SSO in the correct security context, SSO will deny access to your application.</span></span>  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a><span data-ttu-id="8a151-107">若要设置 SSO 应用程序的安全上下文</span><span class="sxs-lookup"><span data-stu-id="8a151-107">To set the security context for an SSO application</span></span>  
  
1.  <span data-ttu-id="8a151-108">确定将哪些凭据来成功地运行应用程序需求。</span><span class="sxs-lookup"><span data-stu-id="8a151-108">Identify what credentials your application needs to run successfully.</span></span>  
  
     <span data-ttu-id="8a151-109">例如，使用 Web 服务或在 IIS 中承载的.NET Framework 远程处理的应用程序需要模拟客户端，以便将传递到 SSO 的相应凭据。</span><span class="sxs-lookup"><span data-stu-id="8a151-109">For example, an application that uses Web services or .NET Framework remoting hosted in IIS needs to impersonate the client in order to pass the appropriate credentials on to SSO.</span></span>  
  
2.  <span data-ttu-id="8a151-110">确认相关的安全设置，例如与虚拟目录、 应用程序池和 web.config 文件中，已设置为你应用程序提供这些凭据。</span><span class="sxs-lookup"><span data-stu-id="8a151-110">Confirm that the relevant security settings, such as those on virtual directories, application pools, and web.config files, are set to provide your application with those credentials.</span></span>  
  
     <span data-ttu-id="8a151-111">有关如何设置安全凭据的详细信息，请参阅[Building Secure ASP.NET Applications:身份验证、 授权和安全通信](http://go.microsoft.com/fwlink/?LinkId=193906)。</span><span class="sxs-lookup"><span data-stu-id="8a151-111">For more information about how to set security credentials, see [Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](http://go.microsoft.com/fwlink/?LinkId=193906).</span></span>  
  
     <span data-ttu-id="8a151-112">ASP.NET Web 服务传递凭据的详细信息，请参阅[HOW TO:将当前凭据传递给 ASP.NET Web 服务](http://go.microsoft.com/fwlink/?LinkId=193907)。</span><span class="sxs-lookup"><span data-stu-id="8a151-112">For more information about passing credentials for an ASP.NET Web service, see [HOW TO: Pass Current Credentials to an ASP.NET Web Service](http://go.microsoft.com/fwlink/?LinkId=193907).</span></span>  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a><span data-ttu-id="8a151-113">若要本地用户登录到主机应用程序</span><span class="sxs-lookup"><span data-stu-id="8a151-113">To log a local user on to a host application</span></span>  
  
1.  <span data-ttu-id="8a151-114">接收到主机服务器上运行的应用程序将当前用户的请求。</span><span class="sxs-lookup"><span data-stu-id="8a151-114">Receive the request to log the current user on to an application running on the host server.</span></span>  
  
     <span data-ttu-id="8a151-115">它由你负责确定当前用户请求如何登录到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a151-115">It is your responsibility to determine how the current user requests to be logged on to a host application.</span></span>  
  
2.  <span data-ttu-id="8a151-116">检索当前使用的用户的凭据`ISSOLookup1.GetCredentials`或`ISSOLookup2.GetCredentials`。</span><span class="sxs-lookup"><span data-stu-id="8a151-116">Retrieve the credentials for the current user who is using `ISSOLookup1.GetCredentials` or `ISSOLookup2.GetCredentials`.</span></span>  
  
     <span data-ttu-id="8a151-117">必须提供主机应用程序以及所有相关标志的名称。</span><span class="sxs-lookup"><span data-stu-id="8a151-117">You must supply the name of the host application together with any relevant flags.</span></span> <span data-ttu-id="8a151-118">`GetCredentials` 返回相关联的用户名和主机应用程序的凭据。</span><span class="sxs-lookup"><span data-stu-id="8a151-118">`GetCredentials` returns the associated user name and credentials for the host application.</span></span>  
  
     <span data-ttu-id="8a151-119">请注意，可以使用`ISSOLookup1`或`ISSOLookup2`。</span><span class="sxs-lookup"><span data-stu-id="8a151-119">Note that you can use either `ISSOLookup1` or `ISSOLookup2`.</span></span> <span data-ttu-id="8a151-120">唯一的区别是`ISSOLookup2`还具有将远程用户登录到本地 windows 应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="8a151-120">The only difference is that `ISSOLookup2` also has a method for logging a remote user on to a local windows application.</span></span>  
  
3.  <span data-ttu-id="8a151-121">使用的外部用户名称和凭据登录到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a151-121">Use the external user name and credentials to log on to the host application.</span></span>  
  
     <span data-ttu-id="8a151-122">它由你负责确定如何使用凭据登录到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a151-122">It is your responsibility to determine how to use the credentials to log on to the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a151-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a151-123">See Also</span></span>  
 [<span data-ttu-id="8a151-124">如何远程用户登录到本地应用程序</span><span class="sxs-lookup"><span data-stu-id="8a151-124">How to Log a Remote User on to a Local Application</span></span>](../core/how-to-log-a-remote-user-on-to-a-local-application.md)