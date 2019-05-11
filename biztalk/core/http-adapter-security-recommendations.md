---
title: HTTP 适配器的安全建议 |Microsoft Docs
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
ms.openlocfilehash: 89b0a18ae91a9fd8c37baf2aa04f7a16c09c4409
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332613"
---
# <a name="http-adapter-security-recommendations"></a><span data-ttu-id="e39dc-102">HTTP 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="e39dc-102">HTTP Adapter Security Recommendations</span></span>
<span data-ttu-id="e39dc-103">使用 HTTP 适配器之间交换信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和应用程序通过超文本传输协议 (HTTP)。</span><span class="sxs-lookup"><span data-stu-id="e39dc-103">You use the HTTP adapter to exchange information between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and an application by means of the Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="e39dc-104">应用程序可以通过将 HTTP POST 或 HTTP GET 请求发送到指定的 HTTP URL 向服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="e39dc-104">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="e39dc-105">有关 HTTP 适配器的详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="e39dc-105">For more information about the HTTP adapter, see [HTTP Adapter](../core/http-adapter.md).</span></span> <span data-ttu-id="e39dc-106">建议用于保护和部署你的环境中的 HTTP 适配器的以下准则：</span><span class="sxs-lookup"><span data-stu-id="e39dc-106">It is recommended that you use the following guidelines for securing and deploying the HTTP adapter in your environment:</span></span>  
  
- <span data-ttu-id="e39dc-107">请确保配置 HTTP 适配器的 Internet 信息服务 (IIS) 设置。</span><span class="sxs-lookup"><span data-stu-id="e39dc-107">Ensure you configure the Internet Information Services (IIS) settings for the HTTP adapter.</span></span> <span data-ttu-id="e39dc-108">有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="e39dc-108">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
- <span data-ttu-id="e39dc-109">如果使用 7.0，请确保您遵循 IIS 7.0 建议以配置应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="e39dc-109">If you use 7.0, ensure you follow the IIS 7.0 recommendations for configuring application isolation.</span></span>  
  
- <span data-ttu-id="e39dc-110">当您使用基本身份验证，或在消息级别未使用加密时，建议使用安全套接字层 (SSL) 来接收和发送消息，以确保未经授权的人员无法探查用户凭据。</span><span class="sxs-lookup"><span data-stu-id="e39dc-110">When you use Basic Authentication, or when you do not use encryption at the message level, it is recommended to use Secure Sockets Layer (SSL) for both receiving and sending messages to ensure that an unauthorized person cannot sniff the user credentials.</span></span>  
  
- <span data-ttu-id="e39dc-111">建议使用 Windows 集成身份验证来发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="e39dc-111">It is recommended to use Windows integrated authentication for both sending and receiving messages.</span></span>  
  
- <span data-ttu-id="e39dc-112">建议，则执行不重命名、 复制或移动 ISAPI 扩展文件。</span><span class="sxs-lookup"><span data-stu-id="e39dc-112">It is recommended that you do not rename, copy, or move the ISAPI extension file.</span></span> <span data-ttu-id="e39dc-113">这可确保安全更新安装程序能够正确地应用任何潜在的安全更新与此文件有关。</span><span class="sxs-lookup"><span data-stu-id="e39dc-113">This ensures that the security update installers can correctly apply any potential security updates pertinent to this file.</span></span>  
  
- <span data-ttu-id="e39dc-114">您应使用加强的任意访问控制列表 (Dacl) 包含 ISAPI 扩展文件的目录和虚拟目录创建用于接收消息。</span><span class="sxs-lookup"><span data-stu-id="e39dc-114">You should use strong discretionary access control lists (DACLs) for the directory containing the ISAPI extension file and for the virtual directory that you create for receiving messages.</span></span> <span data-ttu-id="e39dc-115">运行 HTTP 适配器的主机的 BizTalk Isolated Host 组的成员需要读取和执行权限，而 HTTP 适配器进行身份验证的用户需要拥有读取这些目录的权限。</span><span class="sxs-lookup"><span data-stu-id="e39dc-115">Members of the BizTalk Isolated Host group for the host running the HTTP adapter need read and execute permissions, and the users that the HTTP adapter authenticates need read permissions on these directories.</span></span>  
  
- <span data-ttu-id="e39dc-116">当你使用 SSL 客户端证书与 HTTP 发送适配器，则必须手动配置这些证书。</span><span class="sxs-lookup"><span data-stu-id="e39dc-116">When you use SSL client certificates with the HTTP send adapter, you must manually configure these certificates.</span></span>  
  
- <span data-ttu-id="e39dc-117">就像其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件，则建议您不要将 HTTP 适配器放在外围网络中。</span><span class="sxs-lookup"><span data-stu-id="e39dc-117">Just like other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components, it is recommended you do not put the HTTP adapter in the perimeter network.</span></span> <span data-ttu-id="e39dc-118">如果这样做，您必须打开从外围网络到 SQL Server 流量发送到 MessageBox 数据库，这容易引起风险数据域的端口。</span><span class="sxs-lookup"><span data-stu-id="e39dc-118">If you do, you have to open ports from the perimeter network to the data domain for SQL Server traffic to the MessageBox database, which is risk-prone.</span></span> <span data-ttu-id="e39dc-119">建议在处理域 （即，不是外围网络） 中配置 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="e39dc-119">It is recommended you configure the HTTP adapter in the processing domain (that is, not the perimeter network).</span></span> <span data-ttu-id="e39dc-120">然后可以配置最外层防火墙 (FW4) 转发 HTTP 请求通过处理域 (FW3) 中的防火墙。</span><span class="sxs-lookup"><span data-stu-id="e39dc-120">You can then configure the outmost firewall (FW4) to forward HTTP requests through the firewall in the processing domain (FW3).</span></span> <span data-ttu-id="e39dc-121">在这种情况下，不需要 IIS 的外围网络中。</span><span class="sxs-lookup"><span data-stu-id="e39dc-121">In this case, you do not need IIS in the perimeter network.</span></span> <span data-ttu-id="e39dc-122">此机制称为反向代理。</span><span class="sxs-lookup"><span data-stu-id="e39dc-122">This mechanism is called reverse proxy.</span></span> <span data-ttu-id="e39dc-123">（Forefront Threat Management Gateway (TMG) 2010年服务器实施被称为 Web 发布。）</span><span class="sxs-lookup"><span data-stu-id="e39dc-123">(The Forefront Threat Management Gateway (TMG) 2010 server implementation is called Web Publishing.)</span></span>  
  
- <span data-ttu-id="e39dc-124">当 HTTP 接收位置创建应用程序池时，您必须将其配置为是独立主机运行 HTTP 接收适配器和 Internet 信息服务工作进程组 (IIS_ Windows 组的成员的帐户下运行WPG 组）。</span><span class="sxs-lookup"><span data-stu-id="e39dc-124">When you create an application pool for an HTTP receive location, you must configure it to run under an account that is a member of the Windows group for the isolated host running the HTTP receive adapter and the Internet Information Services Worker Process group (IIS_WPG group).</span></span> <span data-ttu-id="e39dc-125">然后，您必须使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的主机实例配置 http 接收适配器以使用此帐户。</span><span class="sxs-lookup"><span data-stu-id="e39dc-125">You must then use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the host instance for the HTTP receive adapter to use this account.</span></span> <span data-ttu-id="e39dc-126">如果你更改了 IIS_WPG 组帐户，则必须确保也更新为新帐户下运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="e39dc-126">If you change the account for the IIS_WPG group, you must ensure you also update the host instance to run under the new account.</span></span> <span data-ttu-id="e39dc-127">有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="e39dc-127">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39dc-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e39dc-128">See Also</span></span>  
 <span data-ttu-id="e39dc-129">[用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="e39dc-129">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="e39dc-130">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="e39dc-130">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)