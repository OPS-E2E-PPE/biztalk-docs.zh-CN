---
title: "WCF 服务发布 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f72f2b300738f2e9a1a643e152048b64cf8f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-wcf-services"></a><span data-ttu-id="f45f2-102">发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="f45f2-102">Publishing WCF Services</span></span>
<span data-ttu-id="f45f2-103">业务流程可以发布为中的 WCF 服务[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由 WCF 客户端调用。</span><span class="sxs-lookup"><span data-stu-id="f45f2-103">An orchestration can be published as a WCF service in [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be called by WCF clients.</span></span>  
  
 <span data-ttu-id="f45f2-104">**具有独立的 WCF 适配器的 WCF 服务发布**</span><span class="sxs-lookup"><span data-stu-id="f45f2-104">**Publishing WCF services with the isolated WCF adapters**</span></span>  
  
 <span data-ttu-id="f45f2-105">通过使用针对独立 WCF 适配器（WCF-BasicHttp 适配器、WCF-WSHttp 适配器和 WCF-CustomIsolated 适配器）的 BizTalk WCF 服务发布向导，可以创建并发布 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="f45f2-105">You create and publish WCF services by using the BizTalk WCF Service Publishing Wizard for the isolated WCF adapters such as the WCF-BasicHttp adapter, the WCF-WSHttp adapter, and the WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="f45f2-106">这将创建一个接收位置，作为 IIS 中进程外应用程序存在。</span><span class="sxs-lookup"><span data-stu-id="f45f2-106">This creates a receive location which exists as an out of process application in IIS.</span></span>  
  
 <span data-ttu-id="f45f2-107">在使用独立 WCF 适配器发布 WCF 服务之前，您应当了解如何在 Internet 信息服务 (IIS) 中承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="f45f2-107">Before you publish a WCF service with the isolated WCF adapters, you should have an understanding of how to host WCF services in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="f45f2-108">**为 WCF 接收位置发布服务元数据**</span><span class="sxs-lookup"><span data-stu-id="f45f2-108">**Publishing service metadata for the WCF receive locations**</span></span>  
  
 <span data-ttu-id="f45f2-109">通过使用 BizTalk WCF 服务发布向导，可以为已发布的 WCF 接收位置创建服务元数据。</span><span class="sxs-lookup"><span data-stu-id="f45f2-109">You create service metadata for published WCF receive locations by using the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="f45f2-110">若要从已发布的元数据文档生成服务模型客户端代码可以使用服务模型元数据实用工具 (SvcUtil.exe) 中包含[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]软件开发工具包 (SDK)，为[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]和[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]运行时组件。</span><span class="sxs-lookup"><span data-stu-id="f45f2-110">To generate service model client code from the published metadata documents you can use the Service Model Metadata Utility tool (SvcUtil.exe) included in the [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Software Development Kit (SDK) for [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] and [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Runtime Components.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f45f2-111">在运行 BizTalk WCF 服务发布向导之前，必须先启用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="f45f2-111">Before running the BizTalk WCF Service Publishing Wizard, you must enable WCF services.</span></span> <span data-ttu-id="f45f2-112">有关启用你的系统的 WCF 服务的详细信息，请参阅[将 IIS 配置为独立的 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="f45f2-112">For more information about enabling WCF services for your system, see [Configuring IIS for the Isolated WCF Receive Adapters](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f45f2-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="f45f2-113">In This Section</span></span>  
  
-   [<span data-ttu-id="f45f2-114">使用独立的 WCF 发布 WCF 服务接收适配器</span><span class="sxs-lookup"><span data-stu-id="f45f2-114">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="f45f2-115">为 WCF 发布服务元数据接收适配器</span><span class="sxs-lookup"><span data-stu-id="f45f2-115">Publishing Service Metadata for the WCF Receive Adapters</span></span>](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="f45f2-116">发布使用 WCF 的 WCF 服务时的注意事项接收适配器</span><span class="sxs-lookup"><span data-stu-id="f45f2-116">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="f45f2-117">与已发布的 WCF 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="f45f2-117">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)  
  
-   [<span data-ttu-id="f45f2-118">如何从作为 WCF 服务发布的业务流程引发错误异常</span><span class="sxs-lookup"><span data-stu-id="f45f2-118">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)