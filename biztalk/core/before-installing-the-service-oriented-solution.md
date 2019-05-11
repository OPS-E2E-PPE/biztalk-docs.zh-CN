---
title: 安装面向服务的解决方案之前 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, deployment prerequisites
ms.assetid: 865bd21c-e49a-4647-af91-fefee07ee806
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed78cdffeb93f22bb42f3af999608ea01559d7b6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530509"
---
# <a name="before-installing-the-service-oriented-solution"></a><span data-ttu-id="ca608-102">然后再安装面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="ca608-102">Before Installing the Service Oriented Solution</span></span>
<span data-ttu-id="ca608-103">以下系统必备组件必须有可供一台计算机上安装面向服务的解决方案的存根版本：</span><span class="sxs-lookup"><span data-stu-id="ca608-103">The following prerequisites must be available to install the stub version of the service-oriented solution on a single computer:</span></span>  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] <span data-ttu-id="ca608-104">的用户。</span><span class="sxs-lookup"><span data-stu-id="ca608-104">.</span></span>  
  
- <span data-ttu-id="ca608-105">支持的软件[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca608-105">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
- <span data-ttu-id="ca608-106">最新版本的 IBM WebSphere MQ 客户端的 Windows</span><span class="sxs-lookup"><span data-stu-id="ca608-106">The latest version of IBM WebSphere MQ Client for Windows</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ca608-107">MQSeries 服务器不需要为解决方案的存根版本。</span><span class="sxs-lookup"><span data-stu-id="ca608-107">MQSeries Server is not required for the stub version of the solution.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ca608-108">可以从 IBM 网站下载 IBM WebSphere MQ 客户端的 Windows。</span><span class="sxs-lookup"><span data-stu-id="ca608-108">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
  <span data-ttu-id="ca608-109">对于一台计算机上安装面向服务的解决方案的内联和适配器版本：</span><span class="sxs-lookup"><span data-stu-id="ca608-109">For installing the inline and adapter version of the service oriented solution on a single computer:</span></span>  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] <span data-ttu-id="ca608-110">的用户。</span><span class="sxs-lookup"><span data-stu-id="ca608-110">.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ca608-111">所需的域帐户映射的企业单一登录 (SSO) 的凭据。</span><span class="sxs-lookup"><span data-stu-id="ca608-111">A domain account is required to map credentials for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="ca608-112">我们建议为 BizTalk 服务和 ENTSSO 服务帐户使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="ca608-112">We recommend using domain accounts for the BizTalk service and for the ENTSSO service accounts.</span></span>  
  
- <span data-ttu-id="ca608-113">支持的软件[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca608-113">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
- <span data-ttu-id="ca608-114">对运行 MQSeries 服务器的计算机访问的本地计算机上的 MQSeries 服务器。</span><span class="sxs-lookup"><span data-stu-id="ca608-114">MQSeries Server on the local computer or access to the computer running the MQSeries Server.</span></span> <span data-ttu-id="ca608-115">对于内联版本，MQSeries 客户端 Api 必须在运行解决方案的业务流程的 BizTalk 服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="ca608-115">For the inline version, MQSeries client APIs must be available on the BizTalk server running the solution’s orchestrations.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ca608-116">MQSeries 服务器的版本必须与 BizTalk Server MQSeries 适配器所需的版本匹配。</span><span class="sxs-lookup"><span data-stu-id="ca608-116">The version of MQSeries Server must match the version required by the BizTalk Server MQSeries Adapter.</span></span> <span data-ttu-id="ca608-117">这可以包括 IBM WebSphere MQ Fix Pack 10 (CSD10) 或更高版本的 Windows 版本 5.3。</span><span class="sxs-lookup"><span data-stu-id="ca608-117">This can include IBM WebSphere MQ for Windows Version 5.3 with Fix Pack 10 (CSD10) or later.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ca608-118">使用 MQSeries 这样对服务器的分布式组件对象模型 (DCOM) 调用如功能时，请确保你没有启用了-基于网络地址转换 (NAT） 防火墙。</span><span class="sxs-lookup"><span data-stu-id="ca608-118">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="ca608-119">客户端必须能够访问服务器的实际 IP 地址，并基于 NAT 的防火墙将此地址为客户端将无法识别的内容。</span><span class="sxs-lookup"><span data-stu-id="ca608-119">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
- <span data-ttu-id="ca608-120">IBM 大型机使用 CICS 和 Transaction X，如果您使用的解决方案，则需要大型机的变体。</span><span class="sxs-lookup"><span data-stu-id="ca608-120">IBM Mainframe with CICS and Transaction X if you are using a variation of the solution that requires a mainframe.</span></span> <span data-ttu-id="ca608-121">在这种情况下，必须在大型机上安装 CICS 应用程序 （COBOL 代码） 和 Microsoft Host Integration Server (HIS) 所需访问大型机。</span><span class="sxs-lookup"><span data-stu-id="ca608-121">In this case, the CICS application (COBOL code) must be installed on the mainframe and Microsoft Host Integration Server (HIS) is required to access the mainframe.</span></span>  
  
   <span data-ttu-id="ca608-122">如果没有大型机可用于该解决方案，则可以修改要使用存根挂起事务的 Web 服务的端口绑定。</span><span class="sxs-lookup"><span data-stu-id="ca608-122">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="ca608-123">Web 服务生成本地模拟大型机事务的事务。</span><span class="sxs-lookup"><span data-stu-id="ca608-123">The Web service generates transactions locally to emulate the mainframe transactions.</span></span> <span data-ttu-id="ca608-124">有关如何修改为存根挂起事务 Web 服务端口绑定的详细信息，请参阅[如何安装的内联版本和适配器版本的面向服务的解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="ca608-124">For more information about how to modify the port binding for the stub Pending Transactions Web service, see [How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md).</span></span>  
  
- <span data-ttu-id="ca608-125">在 host Integration Server 需要连接到大型机。</span><span class="sxs-lookup"><span data-stu-id="ca608-125">Host Integration Server is required to connect to the mainframe.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ca608-126">在 host Integration Server 是作为 BizTalk Server 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ca608-126">Host Integration Server is included as part of BizTalk Server.</span></span>  
  
- <span data-ttu-id="ca608-127">Web 服务器配置为使用 HTTPS 连接证书。</span><span class="sxs-lookup"><span data-stu-id="ca608-127">Web server configured with a certificate for HTTPS connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca608-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca608-128">See Also</span></span>  
 <span data-ttu-id="ca608-129">[如何安装该服务的存根版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ca608-129">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="ca608-130">[如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ca608-130">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="ca608-131">[如何运行该服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ca608-131">[How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="ca608-132">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="ca608-132">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)