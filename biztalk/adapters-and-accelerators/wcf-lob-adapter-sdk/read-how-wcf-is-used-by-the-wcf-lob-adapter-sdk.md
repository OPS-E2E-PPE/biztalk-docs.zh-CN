---
title: "读取 WCF LOB 适配器 SDK 如何使用 WCF |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 183dd134-7273-4767-bad0-c42ae125985e
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb84124213df8cf1bd401ab80db25586f5ca4534
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="ffee0-102">读取 WCF LOB 适配器 SDK 如何使用 WCF</span><span class="sxs-lookup"><span data-stu-id="ffee0-102">Read how WCF is used by the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="ffee0-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构，并依赖于[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]运行时能够提供公开适配器功能和交换信息所需的基本消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="ffee0-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extends the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel architecture and depends on the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] runtime to provide the basic messaging services required to expose adapter functionality and exchange information.</span></span> 
  
 <span data-ttu-id="ffee0-104">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供一个用于编写适配器，公开它们在框架[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，并使用公共适配器元素，如元数据和连接池对它们进行补充。</span><span class="sxs-lookup"><span data-stu-id="ffee0-104">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a framework for writing adapters, surfacing them in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], and complementing them with common adapter elements such as metadata and connection pooling.</span></span> <span data-ttu-id="ffee0-105">它也包括支持工具来增强体验，如[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]为.NET 应用程序和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序和[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ffee0-105">It also consists of support tools to enhance the experience such as the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] for .NET applications and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] for [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications and the [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)].</span></span>  
  
 <span data-ttu-id="ffee0-106">它负责[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开到广泛的消费应用程序，以管理不同的终结点之间的消息流并提供 SDK 和工具要自定义，服务配置和监视消息流。</span><span class="sxs-lookup"><span data-stu-id="ffee0-106">It is the responsibility of the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] to expose services to a wide array of consuming applications, to manage the flow of messages between different endpoints, and to provide an SDK and tools to customize, configure, and monitor message flow.</span></span> <span data-ttu-id="ffee0-107">例如，开发人员可以自定义的行为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过扩展其通道使用自定义消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="ffee0-107">For example, a developer can customize the behavior of a [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] by extending its channel with custom message handlers.</span></span>  
  
 <span data-ttu-id="ffee0-108">之间的关系[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]以下高级体系结构的图所示。</span><span class="sxs-lookup"><span data-stu-id="ffee0-108">The relationship between the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] is shown in the following high-level architectural figure.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/asdk-wcf.gif "ASDK_WCF")  
  
 <span data-ttu-id="ffee0-109">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]之上生成[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]作为的扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型。</span><span class="sxs-lookup"><span data-stu-id="ffee0-109">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is built on top of [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] as an extension to the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model.</span></span> <span data-ttu-id="ffee0-110">它提供了特定于域和简化的对象模型和工具用于为自定义构建适配器设置[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。</span><span class="sxs-lookup"><span data-stu-id="ffee0-110">It provides a domain-specific and simplified object model and tool set for building adapters as custom [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channels.</span></span> <span data-ttu-id="ffee0-111">使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以自定义方式展现[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="ffee0-111">Adapters built using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] are surfaced as custom [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] bindings.</span></span>  
  
 <span data-ttu-id="ffee0-112">下图显示使用给定的适配器绑定的出站消息交换。</span><span class="sxs-lookup"><span data-stu-id="ffee0-112">The following figure shows the outbound message exchange using a given adapter binding.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/58609452-d09e-4dbd-b470-c92a29977858.gif "58609452-d09e-4dbd-b470-c92a29977858")  
  
 <span data-ttu-id="ffee0-113">下图显示使用给定的适配器绑定的入站的消息交换。</span><span class="sxs-lookup"><span data-stu-id="ffee0-113">The following figure shows the inbound message exchange using a given adapter binding.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b62d5040-7e40-4edd-ac7b-69768131c51b.gif "b62d5040-7e40-4edd-ac7b-69768131c51b")  
  
 <span data-ttu-id="ffee0-114">有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型，请参见[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ffee0-114">For more information about the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model, see [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>  
  
## <a name="wcf-services-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="ffee0-115">WCF 服务和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="ffee0-115">WCF Services and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="ffee0-116">当开发典型[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，第一步是创建与外部世界，介绍如何与服务通信共享服务的协定。</span><span class="sxs-lookup"><span data-stu-id="ffee0-116">When developing a typical [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the first step is to create the contract for the service that is shared with the outside world that describes how to communicate with the service.</span></span> <span data-ttu-id="ffee0-117">此协定实质上是指定的集合和访问服务提供的操作所必需的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="ffee0-117">This contract essentially specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
 <span data-ttu-id="ffee0-118">一旦此协定将公开为服务，[服务模型元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)可以用于创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端能够使用它。</span><span class="sxs-lookup"><span data-stu-id="ffee0-118">Once this contract is exposed as a service, the [Service Model Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx) can be used to create a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client to consume it.</span></span> <span data-ttu-id="ffee0-119">该协定提供一组静态有关的操作和不得更改的消息的信息。</span><span class="sxs-lookup"><span data-stu-id="ffee0-119">The contract provides information about a static set of operations and messages that must not change.</span></span> 
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a410af83-ee3b-46d0-9afd-d32970f5ba0a.gif "a410af83-ee3b-46d0-9afd-d32970f5ba0a")  
  
 <span data-ttu-id="ffee0-120">适配器与此相反，使用生成[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供一组动态的有关集合的操作和业务线系统中可用的数据的元数据。</span><span class="sxs-lookup"><span data-stu-id="ffee0-120">In contrast, adapters built using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provide a dynamic set of metadata about the collection of operations and data that are available within a line-of-business system.</span></span> <span data-ttu-id="ffee0-121">业务线系统通常具有一个协定中描述的操作过多，可能有新操作添加到响应新兴的业务需求。</span><span class="sxs-lookup"><span data-stu-id="ffee0-121">The line-of-business system often has too many operations to be described in one contract and may have new operations added to respond to emerging business needs.</span></span>  
  
 <span data-ttu-id="ffee0-122">例如，业务线系统可能提供帐户管理操作。</span><span class="sxs-lookup"><span data-stu-id="ffee0-122">For example, a line-of-business system may provide account management operations.</span></span> <span data-ttu-id="ffee0-123">识别需要优化新客户帐户的创建后, 公司更新业务线系统，以包括新的操作。</span><span class="sxs-lookup"><span data-stu-id="ffee0-123">After identifying a need to streamline the creation of new customer accounts, the company updates the line-of-business system to include the new operation.</span></span> <span data-ttu-id="ffee0-124">使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公开它向客户端提供的元数据中此操作。</span><span class="sxs-lookup"><span data-stu-id="ffee0-124">An adapter built using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes this operation in the metadata it provides to clients.</span></span>  
  
 <span data-ttu-id="ffee0-125">在设计时， [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-基于的适配器生成动态以满足业务线系统的需求的协定。</span><span class="sxs-lookup"><span data-stu-id="ffee0-125">At design time, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-based adapter generates contracts dynamically to meet the needs of the line-of-business system.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2f4d896a-14d9-43f4-8cdc-f816c5eab46d.gif "2f4d896a-14d9-43f4-8cdc-f816c5eab46d")  
  
 <span data-ttu-id="ffee0-126">ASDK 提供[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]的适配器使用者，来在设计时生成动态协定的工具。</span><span class="sxs-lookup"><span data-stu-id="ffee0-126">The ASDK provides [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools for the adapter consumer to generate dynamic contracts at design time.</span></span>  
  
 <span data-ttu-id="ffee0-127">在运行时，当消息流入使用编写适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，适配器通常必须对其执行的一系列操作接收消息。</span><span class="sxs-lookup"><span data-stu-id="ffee0-127">At runtime, when the message flows into the adapter written using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the adapter often must take a series of actions on the receive message.</span></span> <span data-ttu-id="ffee0-128">这些操作包括：</span><span class="sxs-lookup"><span data-stu-id="ffee0-128">These actions include:</span></span>  
  
-   <span data-ttu-id="ffee0-129">查找与消息相关的元数据</span><span class="sxs-lookup"><span data-stu-id="ffee0-129">Looking up metadata pertaining to the message</span></span>  
  
-   <span data-ttu-id="ffee0-130">打开消息</span><span class="sxs-lookup"><span data-stu-id="ffee0-130">Opening the message</span></span>  
  
-   <span data-ttu-id="ffee0-131">解释消息</span><span class="sxs-lookup"><span data-stu-id="ffee0-131">Interpreting the message</span></span>  
  
-   <span data-ttu-id="ffee0-132">业务线系统中调用适当的函数</span><span class="sxs-lookup"><span data-stu-id="ffee0-132">Calling the appropriate functions in the line-of-business system</span></span>  
  
 <span data-ttu-id="ffee0-133">情况下[!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)]服务，消息只传递而无需正在通过元数据解析。</span><span class="sxs-lookup"><span data-stu-id="ffee0-133">In the case of a [!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)] service, messages simply pass through without being resolved through metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffee0-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffee0-134">See Also</span></span>  
 [<span data-ttu-id="ffee0-135">用于 Oracle 数据库和 WCF LOB 适配器 SDK 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="ffee0-135">BizTalk Adapter for Oracle Database and the WCF LOB Adapter SDK</span></span>](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)