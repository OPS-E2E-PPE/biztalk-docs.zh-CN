---
title: "解析程序 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916181431686ca729c0751d9362570afb7dddeee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-web-service"></a><span data-ttu-id="5ba96-102">解析程序 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5ba96-102">The Resolver Web Service</span></span>
<span data-ttu-id="5ba96-103">冲突解决程序 Web 服务是网关置于 ESB 动态解决机制。</span><span class="sxs-lookup"><span data-stu-id="5ba96-103">The Resolver Web service is a gateway into the ESB dynamic resolution mechanism.</span></span> [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="5ba96-104">包括此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。</span><span class="sxs-lookup"><span data-stu-id="5ba96-104"> includes two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="5ba96-105">服务名称**ESB。ResolverServices**和**ESB。ResolverServices.WCF**分别和服务公开以下方法：</span><span class="sxs-lookup"><span data-stu-id="5ba96-105">The service names are **ESB.ResolverServices** and **ESB.ResolverServices.WCF**, respectively, and the services expose the following methods:</span></span>  
  
-   <span data-ttu-id="5ba96-106">**解决。**</span><span class="sxs-lookup"><span data-stu-id="5ba96-106">**Resolve.**</span></span> <span data-ttu-id="5ba96-107">此方法将作为其单个参数**字符串**，其中包含该请求，这符合标准连接字符串的已注册的解析程序如冲突解决程序连接字符串**静态、 BRE、 UDDI，XPATH、 路线，路线静态、 BRI，**或**LDAP。**</span><span class="sxs-lookup"><span data-stu-id="5ba96-107">This method takes as its single parameter a **String** that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP.**</span></span>  
  
-   <span data-ttu-id="5ba96-108">**ResolveMessage。**</span><span class="sxs-lookup"><span data-stu-id="5ba96-108">**ResolveMessage.**</span></span> <span data-ttu-id="5ba96-109">此方法将其第一个参数作为一个字符串，包含该请求，这符合标准连接字符串的已注册的解析程序如的冲突解决程序连接字符串**静态、 BRE、 UDDI、 XPATH、 路线，路线静态、 BRI，**或**LDAP**。</span><span class="sxs-lookup"><span data-stu-id="5ba96-109">This method takes as its first parameter a String that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as  **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP**.</span></span> <span data-ttu-id="5ba96-110">此外，该方法将接受可选的第二个参数，作为**字符串**，其中包含此服务可以使用作为可选的事实数据以帮助解决问题的 XML 消息文档; 例如，BRE 冲突解决程序可能需要消息正文封装事实。</span><span class="sxs-lookup"><span data-stu-id="5ba96-110">In addition, the method accepts an optional second parameter as a **String** that contains an XML message document that the service can use as optional facts to assist in a resolution; for example, the BRE resolver may require a message body that encapsulates facts.</span></span>  
  
 <span data-ttu-id="5ba96-111">有关的冲突解决程序和 ResolverDictionary 类和其用法的详细信息，请参阅[使用帮助器类](../esb-toolkit/using-the-helper-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="5ba96-111">For more information about the Resolver and ResolverDictionary classes and their usage, see [Using the Helper Classes](../esb-toolkit/using-the-helper-classes.md).</span></span>  
  
## <a name="resolver-connection-strings"></a><span data-ttu-id="5ba96-112">冲突解决程序连接字符串</span><span class="sxs-lookup"><span data-stu-id="5ba96-112">Resolver Connection Strings</span></span>  
 <span data-ttu-id="5ba96-113">ESB 动态解决机制使用前面是名字对象，该值指示可执行的解决方法的类型的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="5ba96-113">The ESB dynamic resolution mechanism uses a connection string preceded by a moniker that indicates the type of resolution to perform.</span></span> <span data-ttu-id="5ba96-114">支持的名字对象包括**静态、 BRE、 UDDI、 UDDI3、 XPATH、 路线，路线静态、 BRI，**和**LDAP**。</span><span class="sxs-lookup"><span data-stu-id="5ba96-114">The supported monikers include **STATIC, BRE, UDDI, UDDI3, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** and **LDAP**.</span></span> <span data-ttu-id="5ba96-115">以下连接字符串举例说明**UDDI**名字对象：</span><span class="sxs-lookup"><span data-stu-id="5ba96-115">The following connection string shows an example of a **UDDI** moniker:</span></span>  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="5ba96-116">有关支持的动态解决机制的连接字符串的类型的信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5ba96-116">For information about the types of connections strings supported by the dynamic resolution mechanism, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ba96-117">你必须配置此服务以使用任一 Windows 集成安全性和内置的网络服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="5ba96-117">You must configure this service to use either Windows Integrated Security and to run under the built-in NETWORK SERVICE account.</span></span>  
>   
>  <span data-ttu-id="5ba96-118">默认情况下，冲突解决程序 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。</span><span class="sxs-lookup"><span data-stu-id="5ba96-118">By default, the Resolver Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="5ba96-119">你应配置服务，因此需要 SSL 的客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问你 BizTalk Server 之间的连接控制列表 (ACL) 权限。</span><span class="sxs-lookup"><span data-stu-id="5ba96-119">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span> <span data-ttu-id="5ba96-120">若要避免安全风险，建议不要公开此服务的受信任的子系统的边界之外。</span><span class="sxs-lookup"><span data-stu-id="5ba96-120">To avoid security risks, it is not recommended to expose this service outside the boundary of the trusted subsystem.</span></span>