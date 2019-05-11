---
title: 示例体系结构：基本 BizTalk Server |Microsoft Docs
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
ms.openlocfilehash: c4db442ec29ac9185bd1479219db795a9398073f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393961"
---
# <a name="sample-architecture-base-biztalk-server"></a><span data-ttu-id="89ba4-102">示例体系结构：基本 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="89ba4-102">Sample Architecture: Base BizTalk Server</span></span>
<span data-ttu-id="89ba4-103">本主题讨论基本示例结构。</span><span class="sxs-lookup"><span data-stu-id="89ba4-103">This topic discusses the base sample architecture.</span></span> <span data-ttu-id="89ba4-104">它介绍了是独立于适配器的 BizTalk Server 部署中的组件。</span><span class="sxs-lookup"><span data-stu-id="89ba4-104">It describes the components in a BizTalk Server deployment that are adapter-independent.</span></span> <span data-ttu-id="89ba4-105">我们建议所有 BizTalk Server 部署都有至少包含这些组件。</span><span class="sxs-lookup"><span data-stu-id="89ba4-105">We recommend that any BizTalk Server deployment have at least these components.</span></span>  
  
 <span data-ttu-id="89ba4-106">下图显示的基本 BizTalk Server 组件的示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="89ba4-106">The following figure shows the components of the base BizTalk Server sample architecture.</span></span> <span data-ttu-id="89ba4-107">这些组件将出现在我们在后面的章节中介绍的所有特定于适配器的 BizTalk Server 结构。</span><span class="sxs-lookup"><span data-stu-id="89ba4-107">These components appear in all the adapter-specific BizTalk Server architectures that we discuss in later sections.</span></span>  
  
 <span data-ttu-id="89ba4-108">**图 1 基本结构组件**</span><span class="sxs-lookup"><span data-stu-id="89ba4-108">**Figure 1 Base architecture components**</span></span>  
  
 <span data-ttu-id="89ba4-109">![基本结构组件](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span><span class="sxs-lookup"><span data-stu-id="89ba4-109">![Base architecture components](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span></span>  
  
 <span data-ttu-id="89ba4-110">此示例结构包含以下各节所述的项。</span><span class="sxs-lookup"><span data-stu-id="89ba4-110">This sample architecture contains the items discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="89ba4-111">外围网络 ― internet</span><span class="sxs-lookup"><span data-stu-id="89ba4-111">Perimeter network―internet</span></span>  
  
-   <span data-ttu-id="89ba4-112">此外围网络 （也称为 DMZ、 外围安全区域和外围子网） 包含提供 Internet 相关服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="89ba4-112">This perimeter network (also known as DMZ, demilitarized zone, and screened subnet) contains servers that provide Internet-related services.</span></span> <span data-ttu-id="89ba4-113">有没有 BizTalk Server、 BizTalk 在这个域中接收位置或企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="89ba4-113">There are no BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers in this domain.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="89ba4-114">外围网络 ― intranet</span><span class="sxs-lookup"><span data-stu-id="89ba4-114">Perimeter network―intranet</span></span>  
 <span data-ttu-id="89ba4-115">此外围网络包含提供 intranet 相关服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="89ba4-115">This perimeter network contains servers that provide intranet-related services.</span></span> <span data-ttu-id="89ba4-116">它提供了额外的 intranet （例如，公司网络） 和运行应用程序的服务器之间的安全性。</span><span class="sxs-lookup"><span data-stu-id="89ba4-116">It provides an additional layer of security between your intranet (for example, a corporate network) and the servers that run the application.</span></span> <span data-ttu-id="89ba4-117">Internet 外围网络，如 intranet 外围网络不包含 BizTalk Server、 BizTalk 接收位置或企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="89ba4-117">Like the Internet perimeter network, the intranet perimeter network does not contain BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="89ba4-118">电子商务域</span><span class="sxs-lookup"><span data-stu-id="89ba4-118">E-Business Domain</span></span>  
 <span data-ttu-id="89ba4-119">此域包含的所有基础结构和使用您的 BizTalk Server 实施的应用程序。</span><span class="sxs-lookup"><span data-stu-id="89ba4-119">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="89ba4-120">此域中的服务器是：</span><span class="sxs-lookup"><span data-stu-id="89ba4-120">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="89ba4-121">**BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="89ba4-121">**BizTalk Server.**</span></span> <span data-ttu-id="89ba4-122">此服务器已安装了 BizTalk Server 运行时和各种 BizTalk 主机的实例。</span><span class="sxs-lookup"><span data-stu-id="89ba4-122">This server has an installation of the BizTalk Server runtime and instances of various BizTalk Hosts.</span></span> <span data-ttu-id="89ba4-123">在环境中的 BizTalk 服务器数量取决于它们运行的主机和性能需求的类型。</span><span class="sxs-lookup"><span data-stu-id="89ba4-123">The number of BizTalk Servers in the environment depends on the type of hosts they run and the performance needs.</span></span> <span data-ttu-id="89ba4-124">根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="89ba4-124">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="89ba4-125">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="89ba4-125">**Master secret server.**</span></span> <span data-ttu-id="89ba4-126">此服务器是企业单一登录 (SSO) 主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="89ba4-126">This server is the Enterprise Single Sign-On (SSO) master secret server.</span></span> <span data-ttu-id="89ba4-127">它包含主密钥 （加密密钥） SSO 系统用来加密 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="89ba4-127">It holds the master secret (encryption key) that the SSO system uses to encrypt the data in the SSO database.</span></span>  
  
-   <span data-ttu-id="89ba4-128">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="89ba4-128">**SQL Server.**</span></span> <span data-ttu-id="89ba4-129">此服务器包含 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="89ba4-129">This server contains the BizTalk databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="89ba4-130">对于故障转移保护，我们建议您群集每个 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="89ba4-130">For failover protection, we recommend that you cluster each BizTalk database.</span></span> <span data-ttu-id="89ba4-131">有关 Microsoft SQL Server 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkID=190216 ](http://go.microsoft.com/fwlink/?LinkID=190216)。</span><span class="sxs-lookup"><span data-stu-id="89ba4-131">For more information about Microsoft SQL Server failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89ba4-132">根据性能需求，可能需要分离到多台计算机运行 SQL Server 的 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="89ba4-132">Depending on your performance needs, you might have to separate the BizTalk databases into multiple computers that run SQL Server.</span></span>  
  
-   <span data-ttu-id="89ba4-133">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="89ba4-133">**Domain controller.**</span></span> <span data-ttu-id="89ba4-134">此服务器托管的电子商务 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="89ba4-134">This server hosts the E-Business Active Directory domain.</span></span> <span data-ttu-id="89ba4-135">它包含有关所有组和个人帐户需要访问 BizTalk Server 的信息。</span><span class="sxs-lookup"><span data-stu-id="89ba4-135">It contains information about all the groups and individual accounts that need access to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="89ba4-136">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="89ba4-136">**Administration tools.**</span></span> <span data-ttu-id="89ba4-137">在这个域中的服务器之一承载管理工具：BizTalk 管理控制台和企业单一登录 (SSO) 管理实用程序。</span><span class="sxs-lookup"><span data-stu-id="89ba4-137">One of the servers in this domain hosts the administration tools: BizTalk Administration console and Enterprise Single Sign-On (SSO) administration utility.</span></span>  
  
## <a name="firewalls-and-domains"></a><span data-ttu-id="89ba4-138">防火墙和域</span><span class="sxs-lookup"><span data-stu-id="89ba4-138">Firewalls and Domains</span></span>  
 <span data-ttu-id="89ba4-139">在图 1 中，Forefront Threat Management Gateway (TMG) 2010年服务器充当软件防火墙，以帮助保护和包含每个域。</span><span class="sxs-lookup"><span data-stu-id="89ba4-139">In Figure 1, Forefront Threat Management Gateway (TMG) 2010 server acts as a software firewall to help protect and contain each of these domains.</span></span> <span data-ttu-id="89ba4-140">此外，电子商务域具有其自己的域控制器，并且此域不信任其他任何域。</span><span class="sxs-lookup"><span data-stu-id="89ba4-140">Additionally, the E-Business domain has its own domain controller, and this domain does not trust any other domain.</span></span> <span data-ttu-id="89ba4-141">有关如何为域和信任关系配置防火墙的详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=25230 ](http://go.microsoft.com/fwlink/?LinkId=25230)。</span><span class="sxs-lookup"><span data-stu-id="89ba4-141">For more information about how to configure a firewall for domains and trusts, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).</span></span>  
  
 <span data-ttu-id="89ba4-142">示例体系结构具有两个防火墙：</span><span class="sxs-lookup"><span data-stu-id="89ba4-142">The sample architecture has two firewalls:</span></span>  
  
- <span data-ttu-id="89ba4-143">**防火墙 1。**</span><span class="sxs-lookup"><span data-stu-id="89ba4-143">**Firewall 1.**</span></span> <span data-ttu-id="89ba4-144">此防火墙具有三个网络接口：它将从 Internet、 intranet 和外围网络的流量路由。</span><span class="sxs-lookup"><span data-stu-id="89ba4-144">This firewall has three network interfaces: It routes traffic from the Internet, the intranet, and the perimeter networks.</span></span>  
  
- <span data-ttu-id="89ba4-145">**防火墙 2。**</span><span class="sxs-lookup"><span data-stu-id="89ba4-145">**Firewall 2.**</span></span> <span data-ttu-id="89ba4-146">此防火墙是双宿主：它将路由来自外围网络 （Internet 和 intranet） 和电子商务域的流量。</span><span class="sxs-lookup"><span data-stu-id="89ba4-146">This firewall is dual-homed: It routes traffic from the perimeter networks (both Internet and intranet) and the E-Business domain.</span></span>  
  
  <span data-ttu-id="89ba4-147">外围网络中的计算机不是任何域的成员，它们不会彼此进行通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-147">The computers in the perimeter networks are not members of any domain, and they do not communicate with each other.</span></span>  
  
## <a name="ipsec"></a><span data-ttu-id="89ba4-148">IPsec</span><span class="sxs-lookup"><span data-stu-id="89ba4-148">IPsec</span></span>  
 <span data-ttu-id="89ba4-149">我们建议使用 Internet 协议安全 (IPSec) 来帮助保护电子商务域中的所有服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-149">We recommend that you use Internet Protocol security (IPSec) to help secure the communication between all the servers in the E-Business domain.</span></span> <span data-ttu-id="89ba4-150">IPsec 规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="89ba4-150">The IPsec rules are as follows:</span></span>  
  
- <span data-ttu-id="89ba4-151">允许 BizTalk Server 与域控制器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-151">Allow authenticated traffic between BizTalk Server and the domain controller.</span></span>  
  
- <span data-ttu-id="89ba4-152">允许 BizTalk Server 管理工具服务器之间经过身份验证的流量。</span><span class="sxs-lookup"><span data-stu-id="89ba4-152">Allow authenticated traffic between BizTalk Server and the administration tools server.</span></span>  
  
- <span data-ttu-id="89ba4-153">允许 BizTalk Server 与主密钥服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-153">Allow authenticated traffic between BizTalk Server and the master secret server.</span></span>  
  
- <span data-ttu-id="89ba4-154">允许 BizTalk Server 和 SQL Server 之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-154">Allow authenticated traffic between BizTalk Server and the SQL Server.</span></span>  
  
- <span data-ttu-id="89ba4-155">允许主密钥服务器和域控制器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-155">Allow authenticated traffic between the master secret server and the domain controller.</span></span>  
  
- <span data-ttu-id="89ba4-156">允许主密钥服务器与 BizTalk Server （独立、 处理、 在进程和跟踪主机。） 之间经过验证的通信</span><span class="sxs-lookup"><span data-stu-id="89ba4-156">Allow authenticated traffic between the master secret server and the BizTalk Server (isolated, processing, in-process, and tracking hosts.)</span></span>  
  
- <span data-ttu-id="89ba4-157">允许主密钥服务器和 SQL Server （SSO 数据库） 之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-157">Allow authenticated traffic between the master secret server and the SQL Server (SSO databases).</span></span>  
  
- <span data-ttu-id="89ba4-158">允许域控制器和域中的所有服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-158">Allow authenticated traffic between the domain controller and all the servers in the domain.</span></span>  
  
- <span data-ttu-id="89ba4-159">允许管理工具服务器和域中的所有服务器之间经过验证的通信。</span><span class="sxs-lookup"><span data-stu-id="89ba4-159">Allow authenticated traffic between the administration tools server and all the servers in the domain.</span></span>  
  
  <span data-ttu-id="89ba4-160">如果你有其他域中的应用程序不需要访问 BizTalk Server、 SQL Server、 主密钥服务器或管理工具服务器阻止这些应用程序与通信的相应服务器。</span><span class="sxs-lookup"><span data-stu-id="89ba4-160">If you have other applications in the domain that do not need access to the BizTalk Server, SQL Server, master secret server, or administration tools server, block traffic between those applications and the appropriate servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ba4-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="89ba4-161">See Also</span></span>  
 <span data-ttu-id="89ba4-162">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="89ba4-162">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="89ba4-163">[对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="89ba4-163">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="89ba4-164">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="89ba4-164">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)