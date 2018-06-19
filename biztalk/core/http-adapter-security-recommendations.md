---
title: HTTP 适配器安全建议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, HTTP adapters
- configuring [HTTP adapters], security
- HTTP adapters, security
ms.assetid: ef6043c2-c62a-40e5-b2e1-53e60f87a761
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb4e5909a61040a2bcd2dd84a81f81077d25a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256757"
---
# <a name="http-adapter-security-recommendations"></a><span data-ttu-id="ae979-102">HTTP 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="ae979-102">HTTP Adapter Security Recommendations</span></span>
<span data-ttu-id="ae979-103">使用 HTTP 适配器可以通过超文本传输协议 (HTTP) 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与应用程序之间交换信息。</span><span class="sxs-lookup"><span data-stu-id="ae979-103">You use the HTTP adapter to exchange information between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and an application by means of the Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="ae979-104">通过向指定的 HTTP URL 发送 HTTP POST 或 HTTP GET 请求，应用程序可以向服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="ae979-104">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="ae979-105">有关 HTTP 适配器的详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ae979-105">For more information about the HTTP adapter, see [HTTP Adapter](../core/http-adapter.md).</span></span> <span data-ttu-id="ae979-106">建议你使用以下准则以确保你的环境中的 HTTP 适配器的安全并对其进行部署：</span><span class="sxs-lookup"><span data-stu-id="ae979-106">It is recommended that you use the following guidelines for securing and deploying the HTTP adapter in your environment:</span></span>  
  
-   <span data-ttu-id="ae979-107">确保为 HTTP 适配器配置了 Internet 信息服务 (IIS) 设置。</span><span class="sxs-lookup"><span data-stu-id="ae979-107">Ensure you configure the Internet Information Services (IIS) settings for the HTTP adapter.</span></span> <span data-ttu-id="ae979-108">有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ae979-108">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
-   <span data-ttu-id="ae979-109">如果使用 7.0，请确保你遵循 IIS 7.0 建议以配置应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="ae979-109">If you use 7.0, ensure you follow the IIS 7.0 recommendations for configuring application isolation.</span></span>  
  
-   <span data-ttu-id="ae979-110">如果使用基本验证或在消息级别未使用加密，则建议你使用安全套接字层 (SSL) 来接收和发送消息，以确保未经授权的人员无法探查用户凭据。</span><span class="sxs-lookup"><span data-stu-id="ae979-110">When you use Basic Authentication, or when you do not use encryption at the message level, it is recommended to use Secure Sockets Layer (SSL) for both receiving and sending messages to ensure that an unauthorized person cannot sniff the user credentials.</span></span>  
  
-   <span data-ttu-id="ae979-111">建议使用 Windows 集成身份验证来发送消息和接收消息。</span><span class="sxs-lookup"><span data-stu-id="ae979-111">It is recommended to use Windows integrated authentication for both sending and receiving messages.</span></span>  
  
-   <span data-ttu-id="ae979-112">建议不要对 ISAPI 扩展文件进行重命名、复制或移动。</span><span class="sxs-lookup"><span data-stu-id="ae979-112">It is recommended that you do not rename, copy, or move the ISAPI extension file.</span></span> <span data-ttu-id="ae979-113">这样可确保安全更新安装程序能够正确地应用任何与此文件有关的可能的安全更新。</span><span class="sxs-lookup"><span data-stu-id="ae979-113">This ensures that the security update installers can correctly apply any potential security updates pertinent to this file.</span></span>  
  
-   <span data-ttu-id="ae979-114">应对包含 ISAPI 扩展文件的目录以及为接收消息创建的虚拟目录使用加强的任意访问控制列表 (DACL)。</span><span class="sxs-lookup"><span data-stu-id="ae979-114">You should use strong discretionary access control lists (DACLs) for the directory containing the ISAPI extension file and for the virtual directory that you create for receiving messages.</span></span> <span data-ttu-id="ae979-115">运行 HTTP 适配器的主机的 BizTalk Isolated Host Users 组成员需要对这些目录具有读取和执行权限，而 HTTP 适配器对其进行验证的用户需要对这些目录具有读取权限。</span><span class="sxs-lookup"><span data-stu-id="ae979-115">Members of the BizTalk Isolated Host group for the host running the HTTP adapter need read and execute permissions, and the users that the HTTP adapter authenticates need read permissions on these directories.</span></span>  
  
-   <span data-ttu-id="ae979-116">如果将 SSL 客户端证书与 HTTP 发送适配器一起使用，则必须手动配置这些证书。</span><span class="sxs-lookup"><span data-stu-id="ae979-116">When you use SSL client certificates with the HTTP send adapter, you must manually configure these certificates.</span></span>  
  
-   <span data-ttu-id="ae979-117">与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件一样，建议你不要将 HTTP 适配器置于外围网络中。</span><span class="sxs-lookup"><span data-stu-id="ae979-117">Just like other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components, it is recommended you do not put the HTTP adapter in the perimeter network.</span></span> <span data-ttu-id="ae979-118">如果将其置于外围网络中，则必须打开从外围网络到数据域的端口才能使 SQL Server 与 MessageBox 数据库进行通信，这样容易引起风险。</span><span class="sxs-lookup"><span data-stu-id="ae979-118">If you do, you have to open ports from the perimeter network to the data domain for SQL Server traffic to the MessageBox database, which is risk-prone.</span></span> <span data-ttu-id="ae979-119">建议在处理域（而不是外围网络）中配置 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ae979-119">It is recommended you configure the HTTP adapter in the processing domain (that is, not the perimeter network).</span></span> <span data-ttu-id="ae979-120">然后，可以将最外层防火墙 (FW4) 配置为通过处理域中的防火墙 (FW3) 转发 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="ae979-120">You can then configure the outmost firewall (FW4) to forward HTTP requests through the firewall in the processing domain (FW3).</span></span> <span data-ttu-id="ae979-121">在这种情况下，外围网络中不需要 IIS。</span><span class="sxs-lookup"><span data-stu-id="ae979-121">In this case, you do not need IIS in the perimeter network.</span></span> <span data-ttu-id="ae979-122">此机制称为反向代理。</span><span class="sxs-lookup"><span data-stu-id="ae979-122">This mechanism is called reverse proxy.</span></span> <span data-ttu-id="ae979-123">（Forefront Threat Management Gateway (TMG) 2010 服务器实施被称为 Web 发布。）</span><span class="sxs-lookup"><span data-stu-id="ae979-123">(The Forefront Threat Management Gateway (TMG) 2010 server implementation is called Web Publishing.)</span></span>  
  
-   <span data-ttu-id="ae979-124">在为 HTTP 接收位置创建应用程序池时，你必须将其配置为使用满足以下条件的帐户运行：该帐户是运行 HTTP 接收适配器的独立主机的 Windows 组以及 Internet 信息服务工作进程组（IIS_WPG 组）的成员。</span><span class="sxs-lookup"><span data-stu-id="ae979-124">When you create an application pool for an HTTP receive location, you must configure it to run under an account that is a member of the Windows group for the isolated host running the HTTP receive adapter and the Internet Information Services Worker Process group (IIS_WPG group).</span></span> <span data-ttu-id="ae979-125">随后，必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将 HTTP 接收适配器的主机实例配置为使用此帐户。</span><span class="sxs-lookup"><span data-stu-id="ae979-125">You must then use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the host instance for the HTTP receive adapter to use this account.</span></span> <span data-ttu-id="ae979-126">如果你更改 IIS_WPG 组的帐户，则必须确保也更新要在新的帐户下运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="ae979-126">If you change the account for the IIS_WPG group, you must ensure you also update the host instance to run under the new account.</span></span> <span data-ttu-id="ae979-127">有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ae979-127">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae979-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae979-128">See Also</span></span>  
 <span data-ttu-id="ae979-129">[用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="ae979-129">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="ae979-130">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="ae979-130">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)