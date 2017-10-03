---
title: "使用 WCF 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b984bcda798796565113739c6088af6d569f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-wcf-services"></a><span data-ttu-id="e0263-102">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e0263-102">Using WCF Services</span></span>
<span data-ttu-id="e0263-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供内置支持 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="e0263-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Windows Communication Foundation (WCF).</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e0263-104">可重复使用和聚合你业务流程中的所有现有 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e0263-104"> enables you to reuse and aggregate all your existing WCF services within your orchestrations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e0263-105">在 WCF 服务还实现对本机适配器的支持。</span><span class="sxs-lookup"><span data-stu-id="e0263-105"> also implements support for native adapters in WCF services.</span></span> <span data-ttu-id="e0263-106">本地适配器支持为 WCF 服务提供了可伸缩性、容错功能和跟踪功能，且用户无需为此编写代码。</span><span class="sxs-lookup"><span data-stu-id="e0263-106">Native adapter support provides scalability, fault tolerance, and tracking capabilities for WCF services without requiring you to write code.</span></span> <span data-ttu-id="e0263-107">有关 WCF 适配器的信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="e0263-107">For information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
 <span data-ttu-id="e0263-108">WCF 服务中的支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]划分为两个类别： 发布或创建 WCF 服务，或调用或使用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e0263-108">The WCF services support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] falls into two categories: publishing or creating WCF services, or calling or consuming WCF services.</span></span>  
  
 <span data-ttu-id="e0263-109">**发布的 WCF 服务**</span><span class="sxs-lookup"><span data-stu-id="e0263-109">**Publishing WCF services**</span></span>  
  
 <span data-ttu-id="e0263-110">您可以使用 WCF 适配器将您的业务流程和架构发布（公开）为 WCF 服务，以便将 WCF 服务逻辑与业务流程逻辑分开。</span><span class="sxs-lookup"><span data-stu-id="e0263-110">You can publish (expose) your orchestrations and schemas as WCF services with the WCF adapters to separate the WCF service logic from the business process logic.</span></span> <span data-ttu-id="e0263-111">对于独立 WCF 适配器来说，您可以使用 BizTalk WCF 服务发布向导创建在 Internet 信息服务 (IIS) 中运行的 Web 应用程序承载的独立 WCF 接收位置。</span><span class="sxs-lookup"><span data-stu-id="e0263-111">For isolated WCF adapters, you can use the BizTalk WCF Service Publishing Wizard to create isolated WCF receive locations hosted by Web applications running in Internet Information Services (IIS).</span></span> <span data-ttu-id="e0263-112">对于进程内 WCF 适配器来说，您可以使用 BizTalk WCF 服务发布向导为任何 WCF 位置发布服务元数据。</span><span class="sxs-lookup"><span data-stu-id="e0263-112">For the in-process WCF adapters, you can publish service metadata for any WCF locations with the BizTalk WCF Service Publishing Wizard.</span></span>  <span data-ttu-id="e0263-113">发布元数据将允许使用 svcutil.exe 实用程序创建客户端代码。</span><span class="sxs-lookup"><span data-stu-id="e0263-113">The publishing of metadata allows the creation of client code using the svcutil.exe utility.</span></span>  
  
 <span data-ttu-id="e0263-114">**使用 WCF 服务**</span><span class="sxs-lookup"><span data-stu-id="e0263-114">**Consuming WCF services**</span></span>  
  
 <span data-ttu-id="e0263-115">您可以使用 BizTalk WCF 服务使用向导生成 BizTalk 项目（如 BizTalk 业务流程和类型），以便根据 WCF 服务的元数据文档使用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e0263-115">You can use the BizTalk WCF Service Consuming Wizard to generate the BizTalk artifacts, such as BizTalk orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span> <span data-ttu-id="e0263-116">元数据允许发送端口以客户端身份访问外部服务。</span><span class="sxs-lookup"><span data-stu-id="e0263-116">Metadata allows a send port to access an external service as a client.</span></span> <span data-ttu-id="e0263-117">元数据仅用于对终结点地址、绑定和协议进行描述。</span><span class="sxs-lookup"><span data-stu-id="e0263-117">Metadata is used purely for describing the endpoint address, binding, and contract.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0263-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="e0263-118">In This Section</span></span>  
  
-   [<span data-ttu-id="e0263-119">发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e0263-119">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="e0263-120">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e0263-120">Consuming WCF Services</span></span>](../core/consuming-wcf-services.md)  
  
-   [<span data-ttu-id="e0263-121">为 WCF 适配器指定消息正文</span><span class="sxs-lookup"><span data-stu-id="e0263-121">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="e0263-122">WCF 适配器演练</span><span class="sxs-lookup"><span data-stu-id="e0263-122">WCF Adapter Walkthroughs</span></span>](../core/wcf-adapter-walkthroughs.md)