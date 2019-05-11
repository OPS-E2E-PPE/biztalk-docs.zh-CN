---
title: 面向 Internet 的 Web 服务和 WCF 服务发布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c16812fc99c6fa38ad55c7e69afb8b6bb256136c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399553"
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a><span data-ttu-id="257a2-102">发布面向 Internet 的 Web 服务和 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="257a2-102">Publishing Internet-facing Web Services and WCF Services</span></span>
<span data-ttu-id="257a2-103">可以使用多种方法进行发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务添加到 Internet:</span><span class="sxs-lookup"><span data-stu-id="257a2-103">You can use multiple approaches for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services and WCF services to the Internet:</span></span>  
  
- <span data-ttu-id="257a2-104">外围网络 （也称为 DMZ、 外围安全区域和外围子网） 中使用反向代理规则。</span><span class="sxs-lookup"><span data-stu-id="257a2-104">Use reverse proxy rules in a perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>  
  
- <span data-ttu-id="257a2-105">将运行计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，将 Web 服务或 WCF 服务发布到外围网络域。</span><span class="sxs-lookup"><span data-stu-id="257a2-105">Put the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that publish the Web services or WCF services into the perimeter network domain.</span></span>  
  
- <span data-ttu-id="257a2-106">使用 BizTalk Server 云推动器功能将 Web 服务或 WCF 服务发布为 Azure AppFabric 服务总线中继终结点。</span><span class="sxs-lookup"><span data-stu-id="257a2-106">Use BizTalk Server cloud enabler functionality to publish the Web services or WCF services as an Azure AppFabric Service Bus relay endpoint.</span></span>  
  
## <a name="using-a-reverse-proxy"></a><span data-ttu-id="257a2-107">使用反向代理</span><span class="sxs-lookup"><span data-stu-id="257a2-107">Using a Reverse Proxy</span></span>  
 <span data-ttu-id="257a2-108">这一直是进行发布的传统方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="257a2-108">This has been the traditional approach for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services and WCF services.</span></span> <span data-ttu-id="257a2-109">在外围网络中使用反向代理规则便无需使用 BizTalk server 将位于外围网络中。</span><span class="sxs-lookup"><span data-stu-id="257a2-109">Using reverse proxy rules in the perimeter network obviates the need to have BizTalk servers located in the perimeter network.</span></span> <span data-ttu-id="257a2-110">反向代理规则只需将转发 HTTP 和 SOAP 请求从外围网络到运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]intranet 域中。</span><span class="sxs-lookup"><span data-stu-id="257a2-110">The reverse proxy rules simply forward the HTTP and SOAP requests from the perimeter network to the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the intranet domain.</span></span>  
  
 <span data-ttu-id="257a2-111">有关使用反向代理的详细信息，请参阅 BizTalk Server 帮助中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="257a2-111">For more information about using a reverse proxy, see the following topics in BizTalk Server Help:</span></span>  
  
-   <span data-ttu-id="257a2-112">["示例体系结构：HTTP 和 SOAP 适配器"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)。</span><span class="sxs-lookup"><span data-stu-id="257a2-112">["Sample Architecture: HTTP and SOAP Adapters"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339).</span></span>  
  
-   <span data-ttu-id="257a2-113">["示例 TMA:HTTP 和 SOAP 适配器"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)。</span><span class="sxs-lookup"><span data-stu-id="257a2-113">["Sample TMA: HTTP and SOAP Adapters"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340).</span></span>  
  
-   <span data-ttu-id="257a2-114">["大型分布式体系结构"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)。</span><span class="sxs-lookup"><span data-stu-id="257a2-114">["Large Distributed Architecture"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341).</span></span>  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a><span data-ttu-id="257a2-115">使用外围网络中运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="257a2-115">Using Computers Running BizTalk Server in the Perimeter Network</span></span>  
 <span data-ttu-id="257a2-116">这不是首选的方法进行发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务或 WCF 服务添加到 Internet，因为它需要运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]位于外围网络中。</span><span class="sxs-lookup"><span data-stu-id="257a2-116">This is not the preferred approach for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services or WCF services to the Internet because it requires computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be located in the perimeter network.</span></span> <span data-ttu-id="257a2-117">但是，不在外围网络中可用的反向代理时，您可以使用此方法。</span><span class="sxs-lookup"><span data-stu-id="257a2-117">However, when a reverse proxy is not available in the perimeter network, you can use this approach.</span></span>  
  
 <span data-ttu-id="257a2-118">此方法要求要在与 intranet 域之间的单向信任中登记的外围网络域 （但 intranet 域不信任的外围网络域）。</span><span class="sxs-lookup"><span data-stu-id="257a2-118">This approach requires the perimeter network domain to enlist in a one-way trust with the intranet domain (but the intranet domain does not trust the perimeter network domain).</span></span> <span data-ttu-id="257a2-119">IIS 应用程序池的 Web 服务或外围网络域中的 WCF 服务必须在"BizTalk Isolated Host Users"域组中的 intranet 域帐户下运行该主机。</span><span class="sxs-lookup"><span data-stu-id="257a2-119">The IIS application pools that host the Web services or WCF services in the perimeter network domain must be running under an intranet domain account that is in the "BizTalk Isolated Host Users" domain group.</span></span> <span data-ttu-id="257a2-120">这使应用程序池所需的权限，才能发布消息到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="257a2-120">This gives the application pool the required rights to publish messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span>  
  
 <span data-ttu-id="257a2-121">必须为解决此问题在防火墙中打开特定端口。</span><span class="sxs-lookup"><span data-stu-id="257a2-121">You must open specific ports in the firewall to accommodate this.</span></span> <span data-ttu-id="257a2-122">有关所需的端口的详细信息，请参阅["端口用于接收和发送服务器"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="257a2-122">For more information about the required ports, see ["Ports for the Receive and Send Servers"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a><span data-ttu-id="257a2-123">公开为服务使用 AppFabric 连接在云上的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="257a2-123">Exposing BizTalk Applications on the Cloud using AppFabric Connect for Services</span></span>  
 <span data-ttu-id="257a2-124">请参阅文章[BizTalk 应用程序公开为服务使用 AppFabric 连接在云中](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700)有关详细信息将 BizTalk 应用程序公开为 WCF 服务在云上。</span><span class="sxs-lookup"><span data-stu-id="257a2-124">See the article [Exposing BizTalk Applications on the Cloud using AppFabric Connect for Services](http://go.microsoft.com/fwlink/?LinkID=204700) (http://go.microsoft.com/fwlink/?LinkID=204700) for more information about expose BizTalk Applications as WCF Services on the cloud.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257a2-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="257a2-125">See Also</span></span>  
 [<span data-ttu-id="257a2-126">规划发布 Web Services1</span><span class="sxs-lookup"><span data-stu-id="257a2-126">Planning for Publishing Web Services1</span></span>](../technical-guides/planning-for-publishing-web-services1.md)