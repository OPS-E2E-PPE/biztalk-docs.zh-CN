---
title: 使用 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81082cacafb1f04d54920648d8f588a4b2ccc50a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396738"
---
# <a name="using-wcf-services"></a><span data-ttu-id="1e96d-102">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="1e96d-102">Using WCF Services</span></span>
<span data-ttu-id="1e96d-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供内置支持为 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="1e96d-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Windows Communication Foundation (WCF).</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1e96d-104">使您可以重用和聚合业务流程中的所有现有 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="1e96d-104">enables you to reuse and aggregate all your existing WCF services within your orchestrations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1e96d-105">此外实现 WCF 服务中的本地适配器的支持。</span><span class="sxs-lookup"><span data-stu-id="1e96d-105">also implements support for native adapters in WCF services.</span></span> <span data-ttu-id="1e96d-106">本机适配器支持提供了可伸缩性、 容错能力和跟踪功能为 WCF 服务，而无需编写代码。</span><span class="sxs-lookup"><span data-stu-id="1e96d-106">Native adapter support provides scalability, fault tolerance, and tracking capabilities for WCF services without requiring you to write code.</span></span> <span data-ttu-id="1e96d-107">有关 WCF 适配器的信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1e96d-107">For information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
 <span data-ttu-id="1e96d-108">WCF 中的服务支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]划分为两个类别： 发布或创建 WCF 服务时，或调用或使用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="1e96d-108">The WCF services support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] falls into two categories: publishing or creating WCF services, or calling or consuming WCF services.</span></span>  
  
 <span data-ttu-id="1e96d-109">**发布 WCF 服务**</span><span class="sxs-lookup"><span data-stu-id="1e96d-109">**Publishing WCF services**</span></span>  
  
 <span data-ttu-id="1e96d-110">您可以发布 （公开） 您的业务流程和架构作为 WCF 服务与 WCF 适配器，以便单独的 WCF 服务逻辑与业务流程逻辑。</span><span class="sxs-lookup"><span data-stu-id="1e96d-110">You can publish (expose) your orchestrations and schemas as WCF services with the WCF adapters to separate the WCF service logic from the business process logic.</span></span> <span data-ttu-id="1e96d-111">对于独立 WCF 适配器，可以使用 BizTalk WCF 服务发布向导创建独立 WCF 接收位置由运行在 Internet 信息服务 (IIS) Web 应用程序承载。</span><span class="sxs-lookup"><span data-stu-id="1e96d-111">For isolated WCF adapters, you can use the BizTalk WCF Service Publishing Wizard to create isolated WCF receive locations hosted by Web applications running in Internet Information Services (IIS).</span></span> <span data-ttu-id="1e96d-112">对于进程内 WCF 适配器，可以将发布为 BizTalk WCF 服务发布向导与任何 WCF 位置的服务元数据。</span><span class="sxs-lookup"><span data-stu-id="1e96d-112">For the in-process WCF adapters, you can publish service metadata for any WCF locations with the BizTalk WCF Service Publishing Wizard.</span></span>  <span data-ttu-id="1e96d-113">元数据的发布允许使用 svcutil.exe 实用程序的客户端代码的创建。</span><span class="sxs-lookup"><span data-stu-id="1e96d-113">The publishing of metadata allows the creation of client code using the svcutil.exe utility.</span></span>  
  
 <span data-ttu-id="1e96d-114">**使用 WCF 服务**</span><span class="sxs-lookup"><span data-stu-id="1e96d-114">**Consuming WCF services**</span></span>  
  
 <span data-ttu-id="1e96d-115">可以使用 BizTalk WCF 服务使用向导生成 BizTalk 项目，如 BizTalk 业务流程和类型，以便使用基于 WCF 服务的元数据文档的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="1e96d-115">You can use the BizTalk WCF Service Consuming Wizard to generate the BizTalk artifacts, such as BizTalk orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span> <span data-ttu-id="1e96d-116">元数据，用于访问外部服务作为客户端的发送端口。</span><span class="sxs-lookup"><span data-stu-id="1e96d-116">Metadata allows a send port to access an external service as a client.</span></span> <span data-ttu-id="1e96d-117">元数据纯粹用于描述终结点地址、 绑定和协定。</span><span class="sxs-lookup"><span data-stu-id="1e96d-117">Metadata is used purely for describing the endpoint address, binding, and contract.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e96d-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="1e96d-118">In This Section</span></span>  
  
-   [<span data-ttu-id="1e96d-119">发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="1e96d-119">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="1e96d-120">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="1e96d-120">Consuming WCF Services</span></span>](../core/consuming-wcf-services.md)  
  
-   [<span data-ttu-id="1e96d-121">指定 WCF 适配器的消息正文</span><span class="sxs-lookup"><span data-stu-id="1e96d-121">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="1e96d-122">WCF 适配器演练</span><span class="sxs-lookup"><span data-stu-id="1e96d-122">WCF Adapter Walkthroughs</span></span>](../core/wcf-adapter-walkthroughs.md)