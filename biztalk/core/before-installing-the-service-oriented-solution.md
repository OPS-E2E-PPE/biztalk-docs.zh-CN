---
title: 安装服务面向解决方案之前 |Microsoft 文档
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
ms.openlocfilehash: 23f326a6fe028c5b7ea5edf60216c1933eccbdb6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006222"
---
# <a name="before-installing-the-service-oriented-solution"></a><span data-ttu-id="83cb8-102">在安装面向服务的解决方案之前</span><span class="sxs-lookup"><span data-stu-id="83cb8-102">Before Installing the Service Oriented Solution</span></span>
<span data-ttu-id="83cb8-103">若要在单台计算机上安装面向服务的解决方案的存根版本，必须具备以下必备组件：</span><span class="sxs-lookup"><span data-stu-id="83cb8-103">The following prerequisites must be available to install the stub version of the service-oriented solution on a single computer:</span></span>  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]<span data-ttu-id="83cb8-104">。</span><span class="sxs-lookup"><span data-stu-id="83cb8-104">.</span></span>  
  
-   <span data-ttu-id="83cb8-105">[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 支持的软件。</span><span class="sxs-lookup"><span data-stu-id="83cb8-105">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
-   <span data-ttu-id="83cb8-106">IBM WebSphere MQ Client for Windows 的最新版本</span><span class="sxs-lookup"><span data-stu-id="83cb8-106">The latest version of IBM WebSphere MQ Client for Windows</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83cb8-107">对于解决方案的存根版本，MQSeries 服务器不是必需的。</span><span class="sxs-lookup"><span data-stu-id="83cb8-107">MQSeries Server is not required for the stub version of the solution.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83cb8-108">你可以从 IBM 网站下载 IBM WebSphere MQ Client for Windows。</span><span class="sxs-lookup"><span data-stu-id="83cb8-108">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
 <span data-ttu-id="83cb8-109">对于在单台计算机上安装面向服务的解决方案的内联版本和适配器版本：</span><span class="sxs-lookup"><span data-stu-id="83cb8-109">For installing the inline and adapter version of the service oriented solution on a single computer:</span></span>  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]<span data-ttu-id="83cb8-110">。</span><span class="sxs-lookup"><span data-stu-id="83cb8-110">.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83cb8-111">必须具备域帐户以为企业单一登录 (SSO) 映射凭据。</span><span class="sxs-lookup"><span data-stu-id="83cb8-111">A domain account is required to map credentials for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="83cb8-112">建议为 BizTalk 服务和 ENTSSO 服务帐户使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="83cb8-112">We recommend using domain accounts for the BizTalk service and for the ENTSSO service accounts.</span></span>  
  
-   <span data-ttu-id="83cb8-113">[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 支持的软件。</span><span class="sxs-lookup"><span data-stu-id="83cb8-113">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
-   <span data-ttu-id="83cb8-114">安装在本地计算机上的 MQSeries 服务器，或具有对运行 MQSeries 服务器的计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="83cb8-114">MQSeries Server on the local computer or access to the computer running the MQSeries Server.</span></span> <span data-ttu-id="83cb8-115">对于内联版本，在运行解决方案的业务流程的 BizTalk 服务器上，MQSeries 客户端 API 必须可用。</span><span class="sxs-lookup"><span data-stu-id="83cb8-115">For the inline version, MQSeries client APIs must be available on the BizTalk server running the solution’s orchestrations.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83cb8-116">MQSeries 服务器的版本必须与 BizTalk Server MQSeries 适配器所需的版本。</span><span class="sxs-lookup"><span data-stu-id="83cb8-116">The version of MQSeries Server must match the version required by the BizTalk Server MQSeries Adapter.</span></span> <span data-ttu-id="83cb8-117">这可以包括带有 Fix Pack 10 (CSD10) 或更高版本的 IBM WebSphere MQ Windows 版本 5.3。</span><span class="sxs-lookup"><span data-stu-id="83cb8-117">This can include IBM WebSphere MQ for Windows Version 5.3 with Fix Pack 10 (CSD10) or later.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83cb8-118">当使用诸如 MQSeries 这样对服务器调用分布式组件对象模型 (DCOM) 的功能时，请确保未启用基于网络地址转换 (NAT) 的防火墙。</span><span class="sxs-lookup"><span data-stu-id="83cb8-118">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="83cb8-119">客户端必须能够通过其实际 IP 地址访问该服务器，并且基于 NAT 的防火墙将此地址翻译为客户端不能识别的地址。</span><span class="sxs-lookup"><span data-stu-id="83cb8-119">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
-   <span data-ttu-id="83cb8-120">如果使用的是需要大型机的变体解决方案，则需要带有 CICS 和 Transaction X 的 IBM 大型机。</span><span class="sxs-lookup"><span data-stu-id="83cb8-120">IBM Mainframe with CICS and Transaction X if you are using a variation of the solution that requires a mainframe.</span></span> <span data-ttu-id="83cb8-121">在这种情况下，必须在大型机上安装 CICS 应用程序（COBOL 代码），并且必须具备 Microsoft Host Integration Server (HIS) 以访问大型机。</span><span class="sxs-lookup"><span data-stu-id="83cb8-121">In this case, the CICS application (COBOL code) must be installed on the mainframe and Microsoft Host Integration Server (HIS) is required to access the mainframe.</span></span>  
  
     <span data-ttu-id="83cb8-122">如果没有大型机可用于该解决方案，则可以修改端口绑定以使用存根 Web Services 来模拟挂起事务。</span><span class="sxs-lookup"><span data-stu-id="83cb8-122">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="83cb8-123">该 Web Services 将在本地生成事务以模拟大型机事务。</span><span class="sxs-lookup"><span data-stu-id="83cb8-123">The Web service generates transactions locally to emulate the mainframe transactions.</span></span> <span data-ttu-id="83cb8-124">有关如何修改存根 （stub） 挂起的事务 Web 服务的端口绑定的详细信息，请参阅[如何安装在内联和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="83cb8-124">For more information about how to modify the port binding for the stub Pending Transactions Web service, see [How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md).</span></span>  
  
-   <span data-ttu-id="83cb8-125">必须具备 Host Integration Server 才能连接到大型机。</span><span class="sxs-lookup"><span data-stu-id="83cb8-125">Host Integration Server is required to connect to the mainframe.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83cb8-126">Host Integration Server 是 BizTalk Server 的一部分包括。</span><span class="sxs-lookup"><span data-stu-id="83cb8-126">Host Integration Server is included as part of BizTalk Server.</span></span>  
  
-   <span data-ttu-id="83cb8-127">配置有 HTTPS 连接证书的 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="83cb8-127">Web server configured with a certificate for HTTPS connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cb8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83cb8-128">See Also</span></span>  
 <span data-ttu-id="83cb8-129">[如何安装服务的存根 （stub） 版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="83cb8-129">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="83cb8-130">[如何安装内联和服务的适配器版本面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="83cb8-130">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="83cb8-131">[如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="83cb8-131">[How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="83cb8-132">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="83cb8-132">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)