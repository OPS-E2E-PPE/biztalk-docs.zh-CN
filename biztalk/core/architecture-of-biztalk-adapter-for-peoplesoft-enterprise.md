---
title: 用于 PeopleSoft Enterprise 的 BizTalk 适配器的体系结构 |Microsoft Docs
description: 介绍如何接收消息，消息是如何验证，并使用 PeopleSoft 适配器与 BizTalk Server 时，提供了组件接口方法上的信息
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d65bfed5d76d4cb78a476ee56c863247a92a7ae
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528804"
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a><span data-ttu-id="13496-103">PeopleSoft Enterprise 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="13496-103">PeopleSoft Enterprise adapter architecture</span></span>
<span data-ttu-id="13496-104">在 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的基本操作，适配器从 BizTalk Server 接收一条 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="13496-104">During the basic operation of Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter receives an XML message from BizTalk Server.</span></span> <span data-ttu-id="13496-105">它包含在 SOAP 信封的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="13496-105">It encloses the XML message in a SOAP envelope.</span></span> <span data-ttu-id="13496-106">用于 PeopleSoft Enterprise 的 BizTalk 适配器将转发到服务器的 SOAP 请求。</span><span class="sxs-lookup"><span data-stu-id="13496-106">BizTalk Adapter for PeopleSoft Enterprise forwards the SOAP requests to the server.</span></span> <span data-ttu-id="13496-107">适配器与使用 PeopleSoft psjoa 类，它连接到 PeopleSoft 系统通过 Jolt 事务协议的 PeopleSoft 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="13496-107">The adapter communicates with the PeopleSoft system using the PeopleSoft psjoa classes, which connect to the PeopleSoft system through Jolt Transaction Protocol.</span></span> <span data-ttu-id="13496-108">PeopleSoft 系统接收请求并执行业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="13496-108">The PeopleSoft system receives the request and executes the business logic.</span></span> <span data-ttu-id="13496-109">通过一个类似过程发送回复。</span><span class="sxs-lookup"><span data-stu-id="13496-109">The reply is sent back through a similar process.</span></span>  
  
 <span data-ttu-id="13496-110">![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")</span><span class="sxs-lookup"><span data-stu-id="13496-110">![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")</span></span>  

  
## <a name="component-interface-methods"></a><span data-ttu-id="13496-111">组件接口方法</span><span class="sxs-lookup"><span data-stu-id="13496-111">Component Interface Methods</span></span>  
 <span data-ttu-id="13496-112">提供的 PeopleSoft 组件接口的基本 Api 是低级别在本质上。</span><span class="sxs-lookup"><span data-stu-id="13496-112">The basic APIs that are provided by the PeopleSoft component interface are low-level in nature.</span></span> <span data-ttu-id="13496-113">客户端需要这些 Api 的多个调用。</span><span class="sxs-lookup"><span data-stu-id="13496-113">The client requires multiple invocations of these APIs.</span></span> <span data-ttu-id="13496-114">例如，若要获得组件接口的实例的属性，客户端需要一个或多个调用来设置项的值和低级别的 Get 方法调用。</span><span class="sxs-lookup"><span data-stu-id="13496-114">For example, to obtain the property of an instance of a component interface, the client needs one or more calls to set the key values followed by a low-level Get method call.</span></span> <span data-ttu-id="13496-115">然后，它必须发送多个调用以获取的属性。</span><span class="sxs-lookup"><span data-stu-id="13496-115">It must then send multiple calls to get the properties.</span></span> <span data-ttu-id="13496-116">使用用于 PeopleSoft Enterprise 的 BizTalk 适配器，这样客户端所需执行一次调用来完成相同的结果中提供了一组新的标准方法 （Get、 创建、 查找和更新）。</span><span class="sxs-lookup"><span data-stu-id="13496-116">With BizTalk Adapter for PeopleSoft Enterprise, a new set of standard methods (Get, Create, Find, and Update) are provided in such a way that the client is required to make a single call to accomplish the same result.</span></span> <span data-ttu-id="13496-117">通过让执行多个代表客户端调用用于 PeopleSoft Enterprise 的 BizTalk 适配器来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="13496-117">You do this by having BizTalk Adapter for PeopleSoft Enterprise perform multiple calls on behalf of the client.</span></span> <span data-ttu-id="13496-118">有关方法的详细信息，请参阅[附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="13496-118">For more information about the methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
 <span data-ttu-id="13496-119">若要创建 PeopleSoft 的架构，用于 PeopleSoft Enterprise 的 BizTalk 适配器会检索 PeopleSoft 组件接口定义或元数据。</span><span class="sxs-lookup"><span data-stu-id="13496-119">To create a schema for PeopleSoft, BizTalk Adapter for PeopleSoft Enterprise retrieves the PeopleSoft component interface definitions or metadata.</span></span>  
  
 <span data-ttu-id="13496-120">用于 PeopleSoft Enterprise 的 BizTalk 适配器基于发送功能的组件接口，并不需要 PeopleSoft Integration Broker。</span><span class="sxs-lookup"><span data-stu-id="13496-120">BizTalk Adapter for PeopleSoft Enterprise is based on component interfaces for the Send functionality and does not require the PeopleSoft Integration Broker.</span></span> <span data-ttu-id="13496-121">组件接口公开为 Web 服务，可以从 BizTalk Server 进行访问。</span><span class="sxs-lookup"><span data-stu-id="13496-121">The component interfaces are exposed as Web services, which can be accessed from BizTalk Server.</span></span>  
  
### <a name="validation"></a><span data-ttu-id="13496-122">验证</span><span class="sxs-lookup"><span data-stu-id="13496-122">Validation</span></span>  
 <span data-ttu-id="13496-123">当用于 PeopleSoft Enterprise 的 BizTalk 适配器从 BizTalk Server 收到一条 XML 消息时，将执行两个级别的验证：</span><span class="sxs-lookup"><span data-stu-id="13496-123">When BizTalk Adapter for PeopleSoft Enterprise receives an XML message from BizTalk Server, two levels of validation are performed:</span></span>  
  
-   <span data-ttu-id="13496-124">XML 消息必须是有效根据 XML 规范。</span><span class="sxs-lookup"><span data-stu-id="13496-124">The XML message must be valid with regard to XML specification.</span></span>  
  
-   <span data-ttu-id="13496-125">XML 消息必须与匹配内容所需的特定 Web 服务 （例如，与数据类型的接口）。</span><span class="sxs-lookup"><span data-stu-id="13496-125">The XML message must match what is required by the specific Web service (for example, interface matching such as data types).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13496-126">不会验证对于业务逻辑，这是 PeopleSoft 系统的域，对用于 PeopleSoft Enterprise 的 BizTalk 适配器是透明的。</span><span class="sxs-lookup"><span data-stu-id="13496-126">There is no validation with regard to business logic, which is the domain of the PeopleSoft system, and is transparent to BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13496-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="13496-127">See Also</span></span>  
 [<span data-ttu-id="13496-128">入门</span><span class="sxs-lookup"><span data-stu-id="13496-128">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   