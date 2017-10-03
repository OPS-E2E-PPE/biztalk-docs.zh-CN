---
title: "BizTalk Adapter for PeopleSoft 企业体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, XML messages
- architecture
- XML, messages
- XML, validating
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377e49af3a20302b92a4214959b534c9d0949a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="87d11-102">PeopleSoft Enterprise 的 BizTalk 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="87d11-102">Architecture of BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="87d11-103">在用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的基本操作过程中，适配器会接收来自 BizTalk Server 的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="87d11-103">During the basic operation of Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter receives an XML message from BizTalk Server.</span></span> <span data-ttu-id="87d11-104">它包含 SOAP 信封中的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="87d11-104">It encloses the XML message in a SOAP envelope.</span></span> <span data-ttu-id="87d11-105">PeopleSoft Enterprise 的 BizTalk 适配器会将 SOAP 请求转发给服务器。</span><span class="sxs-lookup"><span data-stu-id="87d11-105">BizTalk Adapter for PeopleSoft Enterprise forwards the SOAP requests to the server.</span></span> <span data-ttu-id="87d11-106">适配器使用 PeopleSoft psjoa 类与 PeopleSoft 系统进行通信，通过 Jolt 事务协议连接到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="87d11-106">The adapter communicates with the PeopleSoft system using the PeopleSoft psjoa classes, which connect to the PeopleSoft system through Jolt Transaction Protocol.</span></span> <span data-ttu-id="87d11-107">PeopleSoft 系统接收请求，并执行业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="87d11-107">The PeopleSoft system receives the request and executes the business logic.</span></span> <span data-ttu-id="87d11-108">通过一个类似过程发送回复。</span><span class="sxs-lookup"><span data-stu-id="87d11-108">The reply is sent back through a similar process.</span></span>  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  
<span data-ttu-id="87d11-109">适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="87d11-109">Adapter Architecture</span></span>  
  
## <a name="peoplesoft-component-interface-methods"></a><span data-ttu-id="87d11-110">PeopleSoft 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="87d11-110">PeopleSoft Component Interface Methods</span></span>  
 <span data-ttu-id="87d11-111">PeopleSoft 组件接口所提供的基本 API 在性质上是低级的。</span><span class="sxs-lookup"><span data-stu-id="87d11-111">The basic APIs that are provided by the PeopleSoft component interface are low-level in nature.</span></span> <span data-ttu-id="87d11-112">客户端要求这些 API 的多次调用。</span><span class="sxs-lookup"><span data-stu-id="87d11-112">The client requires multiple invocations of these APIs.</span></span> <span data-ttu-id="87d11-113">例如，若要获得组件接口的实例属性，客户端需要一个或多个调用来设置低级别 Get 方法调用后面的项值。</span><span class="sxs-lookup"><span data-stu-id="87d11-113">For example, to obtain the property of an instance of a component interface, the client needs one or more calls to set the key values followed by a low-level Get method call.</span></span> <span data-ttu-id="87d11-114">然后，它必须发送多个调用以获取其属性。</span><span class="sxs-lookup"><span data-stu-id="87d11-114">It must then send multiple calls to get the properties.</span></span> <span data-ttu-id="87d11-115">使用 PeopleSoft Enterprise 的 BizTalk 适配器，使用此方法提供一组新的标准方法（Get、Create、Find 和 Update），以便需要客户端进行单一调用完成相同结果。</span><span class="sxs-lookup"><span data-stu-id="87d11-115">With BizTalk Adapter for PeopleSoft Enterprise, a new set of standard methods (Get, Create, Find, and Update) are provided in such a way that the client is required to make a single call to accomplish the same result.</span></span> <span data-ttu-id="87d11-116">通过代表客户端使 PeopleSoft Enterprise 的 BizTalk 适配器执行多个调用，完成操作。</span><span class="sxs-lookup"><span data-stu-id="87d11-116">You do this by having BizTalk Adapter for PeopleSoft Enterprise perform multiple calls on behalf of the client.</span></span> <span data-ttu-id="87d11-117">有关方法的详细信息，请参阅[附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="87d11-117">For more information about the methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
 <span data-ttu-id="87d11-118">若要创建 PeopleSoft 的架构，则 PeopleSoft Enterprise 的 BizTalk 适配器会检索 PeopleSoft 组件接口定义或元数据。</span><span class="sxs-lookup"><span data-stu-id="87d11-118">To create a schema for PeopleSoft, BizTalk Adapter for PeopleSoft Enterprise retrieves the PeopleSoft component interface definitions or metadata.</span></span>  
  
 <span data-ttu-id="87d11-119">PeopleSoft Enterprise 的 BizTalk 适配器是基于“发送”功能的组件接口，并且不需要 PeopleSoft Integration Broker。</span><span class="sxs-lookup"><span data-stu-id="87d11-119">BizTalk Adapter for PeopleSoft Enterprise is based on component interfaces for the Send functionality and does not require the PeopleSoft Integration Broker.</span></span> <span data-ttu-id="87d11-120">组件接口公开为 Web 服务，可以通过 BizTalk Server 进行访问。</span><span class="sxs-lookup"><span data-stu-id="87d11-120">The component interfaces are exposed as Web services, which can be accessed from BizTalk Server.</span></span>  
  
### <a name="validation"></a><span data-ttu-id="87d11-121">验证</span><span class="sxs-lookup"><span data-stu-id="87d11-121">Validation</span></span>  
 <span data-ttu-id="87d11-122">当 PeopleSoft Enterprise 的 BizTalk 适配器接收来自 BizTalk Server 的 XML 消息时，会执行两个级别的验证：</span><span class="sxs-lookup"><span data-stu-id="87d11-122">When BizTalk Adapter for PeopleSoft Enterprise receives an XML message from BizTalk Server, two levels of validation are performed:</span></span>  
  
-   <span data-ttu-id="87d11-123">根据 XML 规范，XML 消息必须有效。</span><span class="sxs-lookup"><span data-stu-id="87d11-123">The XML message must be valid with regard to XML specification.</span></span>  
  
-   <span data-ttu-id="87d11-124">XML 消息必须与特定 Web 服务要求的内容相匹配（例如，接口与数据类型相匹配）。</span><span class="sxs-lookup"><span data-stu-id="87d11-124">The XML message must match what is required by the specific Web service (for example, interface matching such as data types).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87d11-125">对于业务逻辑（是 PeopleSoft 系统的域，并且对 PeopleSoft Enterprise 的 BizTalk 适配器是透明的）没有验证。</span><span class="sxs-lookup"><span data-stu-id="87d11-125">There is no validation with regard to business logic, which is the domain of the PeopleSoft system, and is transparent to BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d11-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87d11-126">See Also</span></span>  
 <span data-ttu-id="87d11-127">[入门](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="87d11-127">[Getting Started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span></span>  
 [<span data-ttu-id="87d11-128">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="87d11-128">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)