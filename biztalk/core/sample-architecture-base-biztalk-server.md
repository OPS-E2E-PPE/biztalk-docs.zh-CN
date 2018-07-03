---
title: 示例体系结构： 基本 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- IPSec
- BizTalk Server, examples
- security, examples
- security, architecture
- IPSec, about IPSec
- BizTalk Server, architecture
- architecture, security
ms.assetid: 7ccc1ef3-670f-423f-b6ca-3d56b9bbeabf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47a6464f34cb523df28cfc0fa1bd481ae09a5b4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969502"
---
# <a name="sample-architecture-base-biztalk-server"></a><span data-ttu-id="6445f-102">示例结构：基本 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6445f-102">Sample Architecture: Base BizTalk Server</span></span>
<span data-ttu-id="6445f-103">本主题将介绍基本示例结构。</span><span class="sxs-lookup"><span data-stu-id="6445f-103">This topic discusses the base sample architecture.</span></span> <span data-ttu-id="6445f-104">其中介绍了 BizTalk Server 部署中与适配器无关的组件。</span><span class="sxs-lookup"><span data-stu-id="6445f-104">It describes the components in a BizTalk Server deployment that are adapter-independent.</span></span> <span data-ttu-id="6445f-105">建议所有 BizTalk Server 部署都至少包含这些组件。</span><span class="sxs-lookup"><span data-stu-id="6445f-105">We recommend that any BizTalk Server deployment have at least these components.</span></span>  
  
 <span data-ttu-id="6445f-106">下图显示了 BizTalk Server 基本示例结构的组件。</span><span class="sxs-lookup"><span data-stu-id="6445f-106">The following figure shows the components of the base BizTalk Server sample architecture.</span></span> <span data-ttu-id="6445f-107">所有针对适配器的 BizTalk Server 结构中都包含这些组件，我们将在稍后部分中讨论这些结构。</span><span class="sxs-lookup"><span data-stu-id="6445f-107">These components appear in all the adapter-specific BizTalk Server architectures that we discuss in later sections.</span></span>  
  
 <span data-ttu-id="6445f-108">**图 1 基本结构组件**</span><span class="sxs-lookup"><span data-stu-id="6445f-108">**Figure 1 Base architecture components**</span></span>  
  
 <span data-ttu-id="6445f-109">![基本结构组件](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span><span class="sxs-lookup"><span data-stu-id="6445f-109">![Base architecture components](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span></span>  
  
 <span data-ttu-id="6445f-110">此示例结构包含以下部分中介绍的各项。</span><span class="sxs-lookup"><span data-stu-id="6445f-110">This sample architecture contains the items discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="6445f-111">外围网络 ― internet</span><span class="sxs-lookup"><span data-stu-id="6445f-111">Perimeter network―internet</span></span>  
  
-   <span data-ttu-id="6445f-112">此外围网络（也称为 DMZ、外围安全区域和外围子网）包含提供 Internet 相关服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="6445f-112">This perimeter network (also known as DMZ, demilitarized zone, and screened subnet) contains servers that provide Internet-related services.</span></span> <span data-ttu-id="6445f-113">此域中没有 BizTalk Server、BizTalk 接收位置或企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="6445f-113">There are no BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers in this domain.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="6445f-114">外围网络 ― Intranet</span><span class="sxs-lookup"><span data-stu-id="6445f-114">Perimeter network―intranet</span></span>  
 <span data-ttu-id="6445f-115">此外围网络包含提供 Intranet 相关服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="6445f-115">This perimeter network contains servers that provide intranet-related services.</span></span> <span data-ttu-id="6445f-116">该网络在 Intranet（例如公司网络）与运行应用程序的服务器之间提供附加的安全防护层。</span><span class="sxs-lookup"><span data-stu-id="6445f-116">It provides an additional layer of security between your intranet (for example, a corporate network) and the servers that run the application.</span></span> <span data-ttu-id="6445f-117">与 Internet 外围网络一样，Intranet 外围网络不包含 BizTalk Server、BizTalk 接收位置或企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="6445f-117">Like the Internet perimeter network, the intranet perimeter network does not contain BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="6445f-118">电子商务域</span><span class="sxs-lookup"><span data-stu-id="6445f-118">E-Business Domain</span></span>  
 <span data-ttu-id="6445f-119">此域包含 BizTalk Server 实现使用的所有基础结构和应用程序。</span><span class="sxs-lookup"><span data-stu-id="6445f-119">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="6445f-120">此域中的服务器如下：</span><span class="sxs-lookup"><span data-stu-id="6445f-120">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="6445f-121">**BizTalk Server。**</span><span class="sxs-lookup"><span data-stu-id="6445f-121">**BizTalk Server.**</span></span> <span data-ttu-id="6445f-122">此服务器安装有 BizTalk Server 运行时以及各种 BizTalk 主机的实例。</span><span class="sxs-lookup"><span data-stu-id="6445f-122">This server has an installation of the BizTalk Server runtime and instances of various BizTalk Hosts.</span></span> <span data-ttu-id="6445f-123">环境中 BizTalk Server 的数目取决于其运行的主机类型和所需的性能。</span><span class="sxs-lookup"><span data-stu-id="6445f-123">The number of BizTalk Servers in the environment depends on the type of hosts they run and the performance needs.</span></span> <span data-ttu-id="6445f-124">当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6445f-124">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="6445f-125">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="6445f-125">**Master secret server.**</span></span> <span data-ttu-id="6445f-126">此服务器是企业单一登录 (SSO) 主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="6445f-126">This server is the Enterprise Single Sign-On (SSO) master secret server.</span></span> <span data-ttu-id="6445f-127">该服务器保存有 SSO 系统用于对 SSO 数据库中的数据进行加密的主密钥（加密密钥）。</span><span class="sxs-lookup"><span data-stu-id="6445f-127">It holds the master secret (encryption key) that the SSO system uses to encrypt the data in the SSO database.</span></span>  
  
-   <span data-ttu-id="6445f-128">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="6445f-128">**SQL Server.**</span></span> <span data-ttu-id="6445f-129">此服务器包含 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="6445f-129">This server contains the BizTalk databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6445f-130">为了进行故障转移保护，建议你对每个 BizTalk 数据库进行群集。</span><span class="sxs-lookup"><span data-stu-id="6445f-130">For failover protection, we recommend that you cluster each BizTalk database.</span></span> <span data-ttu-id="6445f-131">有关 Microsoft SQL Server 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkID=190216 ](http://go.microsoft.com/fwlink/?LinkID=190216)。</span><span class="sxs-lookup"><span data-stu-id="6445f-131">For more information about Microsoft SQL Server failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6445f-132">根据所需的性能，你可能必须将 BizTalk 数据库分别放在多台运行 SQL Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="6445f-132">Depending on your performance needs, you might have to separate the BizTalk databases into multiple computers that run SQL Server.</span></span>  
  
-   <span data-ttu-id="6445f-133">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="6445f-133">**Domain controller.**</span></span> <span data-ttu-id="6445f-134">此服务器用作电子商务 Active Directory 域的宿主。</span><span class="sxs-lookup"><span data-stu-id="6445f-134">This server hosts the E-Business Active Directory domain.</span></span> <span data-ttu-id="6445f-135">其中包含有关需要访问 BizTalk Server 的所有组帐户和个人帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="6445f-135">It contains information about all the groups and individual accounts that need access to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="6445f-136">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="6445f-136">**Administration tools.**</span></span> <span data-ttu-id="6445f-137">在这个域中的服务器之一承载管理工具： BizTalk 管理控制台和企业单一登录 (SSO) 管理实用程序。</span><span class="sxs-lookup"><span data-stu-id="6445f-137">One of the servers in this domain hosts the administration tools: BizTalk Administration console and Enterprise Single Sign-On (SSO) administration utility.</span></span>  
  
## <a name="firewalls-and-domains"></a><span data-ttu-id="6445f-138">防火墙和域</span><span class="sxs-lookup"><span data-stu-id="6445f-138">Firewalls and Domains</span></span>  
 <span data-ttu-id="6445f-139">图 1 中，Forefront Threat Management Gateway (TMG) 2010 服务器用作软件防火墙，以保护和包含每个域。</span><span class="sxs-lookup"><span data-stu-id="6445f-139">In Figure 1, Forefront Threat Management Gateway (TMG) 2010 server acts as a software firewall to help protect and contain each of these domains.</span></span> <span data-ttu-id="6445f-140">此外，电子商务域具有自己的域控制器，并且此域不信任其他任何域。</span><span class="sxs-lookup"><span data-stu-id="6445f-140">Additionally, the E-Business domain has its own domain controller, and this domain does not trust any other domain.</span></span> <span data-ttu-id="6445f-141">有关如何为域和信任关系配置防火墙的详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=25230 ](http://go.microsoft.com/fwlink/?LinkId=25230)。</span><span class="sxs-lookup"><span data-stu-id="6445f-141">For more information about how to configure a firewall for domains and trusts, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).</span></span>  
  
 <span data-ttu-id="6445f-142">该示例结构具有两个防火墙：</span><span class="sxs-lookup"><span data-stu-id="6445f-142">The sample architecture has two firewalls:</span></span>  
  
- <span data-ttu-id="6445f-143">**防火墙 1。**</span><span class="sxs-lookup"><span data-stu-id="6445f-143">**Firewall 1.**</span></span> <span data-ttu-id="6445f-144">此防火墙具有三个网络接口： 它路由来自 Internet、 intranet 和外围网络的流量。</span><span class="sxs-lookup"><span data-stu-id="6445f-144">This firewall has three network interfaces: It routes traffic from the Internet, the intranet, and the perimeter networks.</span></span>  
  
- <span data-ttu-id="6445f-145">**防火墙 2。**</span><span class="sxs-lookup"><span data-stu-id="6445f-145">**Firewall 2.**</span></span> <span data-ttu-id="6445f-146">此防火墙是双宿主： 它将路由来自外围网络 （Internet 和 intranet） 和电子商务域的流量。</span><span class="sxs-lookup"><span data-stu-id="6445f-146">This firewall is dual-homed: It routes traffic from the perimeter networks (both Internet and intranet) and the E-Business domain.</span></span>  
  
  <span data-ttu-id="6445f-147">外围网络中的计算机不是任何域的成员，并且这些计算机互不通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-147">The computers in the perimeter networks are not members of any domain, and they do not communicate with each other.</span></span>  
  
## <a name="ipsec"></a><span data-ttu-id="6445f-148">IPsec</span><span class="sxs-lookup"><span data-stu-id="6445f-148">IPsec</span></span>  
 <span data-ttu-id="6445f-149">建议你使用 Internet 协议安全性 (IPSec) 来帮助确保电子商务域中所有服务器之间通信的安全。</span><span class="sxs-lookup"><span data-stu-id="6445f-149">We recommend that you use Internet Protocol security (IPSec) to help secure the communication between all the servers in the E-Business domain.</span></span> <span data-ttu-id="6445f-150">IPsec 规则如下所述：</span><span class="sxs-lookup"><span data-stu-id="6445f-150">The IPsec rules are as follows:</span></span>  
  
- <span data-ttu-id="6445f-151">允许 BizTalk Server 与域控制器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-151">Allow authenticated traffic between BizTalk Server and the domain controller.</span></span>  
  
- <span data-ttu-id="6445f-152">允许 BizTalk Server 与管理工具服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-152">Allow authenticated traffic between BizTalk Server and the administration tools server.</span></span>  
  
- <span data-ttu-id="6445f-153">允许 BizTalk Server 与主密钥服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-153">Allow authenticated traffic between BizTalk Server and the master secret server.</span></span>  
  
- <span data-ttu-id="6445f-154">允许 BizTalk Server 与 SQL Server 之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-154">Allow authenticated traffic between BizTalk Server and the SQL Server.</span></span>  
  
- <span data-ttu-id="6445f-155">允许主密钥服务器与域控制器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-155">Allow authenticated traffic between the master secret server and the domain controller.</span></span>  
  
- <span data-ttu-id="6445f-156">允许主密钥服务器与 BizTalk Server（独立、处理、进程内和跟踪主机）之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-156">Allow authenticated traffic between the master secret server and the BizTalk Server (isolated, processing, in-process, and tracking hosts.)</span></span>  
  
- <span data-ttu-id="6445f-157">允许主密钥服务器与 SQL Server（SSO 数据库）之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-157">Allow authenticated traffic between the master secret server and the SQL Server (SSO databases).</span></span>  
  
- <span data-ttu-id="6445f-158">允许域控制器与域中所有服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-158">Allow authenticated traffic between the domain controller and all the servers in the domain.</span></span>  
  
- <span data-ttu-id="6445f-159">允许管理工具服务器与域中所有服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-159">Allow authenticated traffic between the administration tools server and all the servers in the domain.</span></span>  
  
  <span data-ttu-id="6445f-160">如果域中存在不需要访问 BizTalk Server、SQL Server、主密钥服务器或管理工具服务器的其他应用程序，则阻止这些应用程序与相应服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="6445f-160">If you have other applications in the domain that do not need access to the BizTalk Server, SQL Server, master secret server, or administration tools server, block traffic between those applications and the appropriate servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6445f-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="6445f-161">See Also</span></span>  
 <span data-ttu-id="6445f-162">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="6445f-162">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="6445f-163">[对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="6445f-163">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="6445f-164">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="6445f-164">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)