---
title: SOAP 适配器的安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, security
- security, SOAP adapters
ms.assetid: f869bd82-df93-45e1-b747-b538820253fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f61b68ce0fd174dfbb766889e544c9b1005468d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985310"
---
# <a name="soap-adapter-security-recommendations"></a><span data-ttu-id="ad482-102">SOAP 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="ad482-102">SOAP Adapter Security Recommendations</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ad482-103"> 使用 SOAP 适配器来发布（接收）和使用（发送）Web Services。</span><span class="sxs-lookup"><span data-stu-id="ad482-103"> uses the SOAP adapter to publish (receive) and consume (send) Web services.</span></span> <span data-ttu-id="ad482-104">有关 SOAP 适配器的详细信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ad482-104">For more information about the SOAP adapter, see [SOAP Adapter](../core/soap-adapter.md).</span></span> <span data-ttu-id="ad482-105">有关 Web 服务的详细信息，请参阅[使用 Web 服务的](../core/using-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ad482-105">For more information about Web services, see [Using Web Services](../core/using-web-services.md).</span></span> <span data-ttu-id="ad482-106">建议你遵循这些准则以确保你的环境中的 SOAP 适配器的安全并对其进行部署。</span><span class="sxs-lookup"><span data-stu-id="ad482-106">It is recommended you follow these guidelines for securing and deploying the SOAP adapter in your environment.</span></span>  
  
- <span data-ttu-id="ad482-107">有关针对发布 Web 服务的安全建议，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ad482-107">For security recommendations for publishing Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
- <span data-ttu-id="ad482-108">SOAP 适配器利用超文本传输协议 (HTTP) 来向 BizTalk Server 发送消息或从其接收消息。</span><span class="sxs-lookup"><span data-stu-id="ad482-108">The SOAP adapter leverages the Hypertext Transfer Protocol (HTTP) to send and receive messages to and from BizTalk Server.</span></span> <span data-ttu-id="ad482-109">因此，你必须遵循安全建议以确保 Internet 信息服务 (IIS) 的安全。</span><span class="sxs-lookup"><span data-stu-id="ad482-109">Therefore, you must follow the security recommendations for securing Internet Information Services (IIS).</span></span> <span data-ttu-id="ad482-110">如果使用 IIS 7.0，请确保你遵循 IIS 7.0 建议以配置应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="ad482-110">If you use IIS 7.0, ensure you follow the IIS 7.0 recommendations for configuring application isolation.</span></span> <span data-ttu-id="ad482-111">有关详细信息，请参阅[创建应用程序池 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=196674)。</span><span class="sxs-lookup"><span data-stu-id="ad482-111">For more information, see [Create an Application Pool (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=196674).</span></span>  
  
- <span data-ttu-id="ad482-112">在为 SOAP 接收位置创建应用程序池时，你必须将其配置为使用满足以下条件的帐户运行：该帐户是运行 SOAP 接收适配器的独立主机的 Windows 组以及 Internet 信息服务工作进程组（IIS_WPG 组）的成员。</span><span class="sxs-lookup"><span data-stu-id="ad482-112">When you create an application pool for a SOAP receive location, you must configure it to run under an account that is a member of the Windows group for the isolated host running the SOAP receive adapter and the Internet Information Services Worker Process group (IIS_WPG group).</span></span> <span data-ttu-id="ad482-113">随后，必须将 SOAP 接收适配器的主机实例配置为使用此帐户。</span><span class="sxs-lookup"><span data-stu-id="ad482-113">You must then configure the host instance for the SOAP receive adapter to use this account.</span></span> <span data-ttu-id="ad482-114">如果你更改了 IIS_WPG 组帐户，则必须确保也更新为新帐户下运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="ad482-114">If you change the account for the IIS_WPG group, you must ensure you also update the host instance to run under the new account.</span></span>  
  
- <span data-ttu-id="ad482-115">如果将安全套接字层 (SSL) 客户端证书与 SOAP 发送适配器一起使用，则必须手动配置这些证书。</span><span class="sxs-lookup"><span data-stu-id="ad482-115">When you use Secure Sockets Layer (SSL) client certificates with the SOAP send adapter, you must manually configure these certificates.</span></span>  
  
- <span data-ttu-id="ad482-116">在使用 Web Services 时，可以通过匿名、基本、摘要、Windows 集成或客户端证书方式来进行验证。</span><span class="sxs-lookup"><span data-stu-id="ad482-116">When consuming Web services, you can use anonymous, basic, digest, Windows integrated, or client certificates for authentication.</span></span> <span data-ttu-id="ad482-117">如果通过基本验证来使用 Web Services，建议你使用 SSL 来确保未经授权的人员无法从消息中读取用户凭据。</span><span class="sxs-lookup"><span data-stu-id="ad482-117">When consuming Web services by using basic authentication, it is recommended to use SSL to ensure that an unauthorized person cannot read the user credentials from the message.</span></span>  
  
- <span data-ttu-id="ad482-118">如果需要将前端用户的内容映射到后端系统中的凭据，则可以使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="ad482-118">You can use Enterprise Single Sign-On (SSO) in scenarios where you need to map the content of the front-end user to credentials in a back-end system.</span></span> <span data-ttu-id="ad482-119">有关详细信息，请参阅[如何映射单个登录凭据](../core/how-to-map-single-sign-on-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="ad482-119">For more information, see [How to Map Single Sign-On Credentials](../core/how-to-map-single-sign-on-credentials.md).</span></span>  
  
- <span data-ttu-id="ad482-120">如果使用基本验证或在消息级别未使用加密，则建议你使用 SSL 来接收和发送消息，以确保未经授权的人员无法读取用户凭据。</span><span class="sxs-lookup"><span data-stu-id="ad482-120">When using basic authentication, or when you do not use encryption at the message level, it is recommended to use SSL for both receiving and sending messages to ensure that an unauthorized person cannot read the user credentials.</span></span>  
  
- <span data-ttu-id="ad482-121">建议使用 Windows 集成身份验证来发送消息和接收消息。</span><span class="sxs-lookup"><span data-stu-id="ad482-121">It is recommended to use Windows integrated authentication for both sending and receiving messages.</span></span>  
  
- <span data-ttu-id="ad482-122">运行 SOAP 适配器的计算机还具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时。</span><span class="sxs-lookup"><span data-stu-id="ad482-122">The computer running the SOAP adapter also has the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime.</span></span> <span data-ttu-id="ad482-123">建议不要将 SOAP 适配器放置在外围网络中。</span><span class="sxs-lookup"><span data-stu-id="ad482-123">It is recommended you do not put the SOAP adapter in the perimeter network.</span></span> <span data-ttu-id="ad482-124">如果将其置于外围网络中，则必须打开从外围网络到数据域的端口才能使 SQL Server 与 MessageBox 数据库进行通信，这样 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时可能会受到攻击。</span><span class="sxs-lookup"><span data-stu-id="ad482-124">If you do, you have to open ports from the perimeter network to the data domain for SQL Server traffic to the MessageBox database, and you are exposing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime to potential attacks.</span></span> <span data-ttu-id="ad482-125">建议你在处理域（而不是外围网络）中配置 SOAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ad482-125">It is recommended you configure the SOAP adapter in the processing domain (that is, not the perimeter network).</span></span> <span data-ttu-id="ad482-126">然后，可以将最外层防火墙配置为通过处理域中的防火墙转发 SOAP 请求。</span><span class="sxs-lookup"><span data-stu-id="ad482-126">You can then configure the outermost firewall to forward SOAP requests through the firewall in the processing domain.</span></span> <span data-ttu-id="ad482-127">此机制称为反向代理。</span><span class="sxs-lookup"><span data-stu-id="ad482-127">This mechanism is called reverse proxy.</span></span> <span data-ttu-id="ad482-128">（Forefront Threat Management Gateway (TMG) 2010 服务器实施被称为 Web 发布。）</span><span class="sxs-lookup"><span data-stu-id="ad482-128">(The Forefront Threat Management Gateway (TMG) 2010 server implementation is called Web Publishing.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad482-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad482-129">See Also</span></span>  
 <span data-ttu-id="ad482-130">[用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="ad482-130">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="ad482-131">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="ad482-131">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)