---
title: "使用顺序处理程序对象与后端系统进行通信 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d7621c4e5737def0e9fc0682de709ae57f98790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a><span data-ttu-id="121a5-102">使用顺序处理程序对象与后端系统进行通信</span><span class="sxs-lookup"><span data-stu-id="121a5-102">Using the Order Handler Object to Communicate with Backend Systems</span></span>
<span data-ttu-id="121a5-103">业务流程管理解决方案可以采用多种方式与原有后端订单系统进行通信，该系统是接收最终订单的宽带提供系统。</span><span class="sxs-lookup"><span data-stu-id="121a5-103">There are many ways in which the business process management solution could communicate with the legacy back-end order system, the cable provisioning system that receives the final orders.</span></span> <span data-ttu-id="121a5-104">该解决方案使用 Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 中提供的 .NET 远程处理功能与提供系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="121a5-104">The solution uses the .NET remoting facilities found in Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] to communicate with the provisioning system.</span></span>  
  
 <span data-ttu-id="121a5-105">该解决方案采用一项常用技术，即使用接口来定义后端系统的访问对象。</span><span class="sxs-lookup"><span data-stu-id="121a5-105">The solution uses a common technique of using an interface to define the access object to the back-end system.</span></span> <span data-ttu-id="121a5-106">通过将接口放置在单独的程序集中，客户端程序集可以具有访问远程对象的权限，而无需具有访问编译的程序集的权限。</span><span class="sxs-lookup"><span data-stu-id="121a5-106">By putting the interface in a separate assembly the client assembly can have access to the remote object without having to have access to the compiled assembly.</span></span>  
  
 <span data-ttu-id="121a5-107">**IOrderHandler**接口定义的方法与后端订单系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="121a5-107">The **IOrderHandler** interface defines the methods to communicate with the backend order system.</span></span> <span data-ttu-id="121a5-108">该接口包括用于分析、激活、取消和完成订单的方法。</span><span class="sxs-lookup"><span data-stu-id="121a5-108">The interface includes methods for analyzing, activating, canceling, and completing orders.</span></span> <span data-ttu-id="121a5-109">它还提供用于标识服务类型，需要取消订单时的方法的方法。</span><span class="sxs-lookup"><span data-stu-id="121a5-109">It also provides a method for identifying the service type, a method needed when an order is canceled.</span></span>  
  
 <span data-ttu-id="121a5-110">**CableOrder1**， **CableOrder2**，附属业务流程并用**OrderHandlerWrapper**实现对象**IOrderHandler**.</span><span class="sxs-lookup"><span data-stu-id="121a5-110">The **CableOrder1**, **CableOrder2**, and satellite orchestrations use the **OrderHandlerWrapper** object that implements **IOrderHandler**.</span></span> <span data-ttu-id="121a5-111">**OrderHandlerWrapper**对象，反过来，将调用的远程实例**OrderHandler**提供对象**CableProvisioningSystemServer**可执行文件。</span><span class="sxs-lookup"><span data-stu-id="121a5-111">The **OrderHandlerWrapper** object, in turn, invokes a remote instance of an **OrderHandler** object provided by the **CableProvisioningSystemServer** executable.</span></span> <span data-ttu-id="121a5-112">通过使用包装对象，可以满足使用 .NET 远程处理与后端订单系统进行通信的业务需求，同时还允许使用异常处理组件的重试功能。</span><span class="sxs-lookup"><span data-stu-id="121a5-112">Using the wrapper object meets the business requirement of using .NET remoting to communicate with the back-end order system while, at the same time, enabling use of the retry features of the exception handling components.</span></span>  
  
 <span data-ttu-id="121a5-113">因为其中一个必须能序列化中业务流程，引用每个对象**OrderHandlerWrapper**也可序列化。</span><span class="sxs-lookup"><span data-stu-id="121a5-113">Because one must be able to serialize every object referenced in an orchestration, the **OrderHandlerWrapper** can also be serialized.</span></span> <span data-ttu-id="121a5-114">使用**OrderHandlerWrapper**隔离业务流程中的序列化代码。</span><span class="sxs-lookup"><span data-stu-id="121a5-114">Using the **OrderHandlerWrapper** isolates the serialization code from the orchestrations.</span></span>  
  
 <span data-ttu-id="121a5-115">如果你查看代码，你将 se， **OrderHandlerWrapper**对象显式实现**ISerializable**接口。</span><span class="sxs-lookup"><span data-stu-id="121a5-115">If you look at the code, you'll se that the **OrderHandlerWrapper** object explicitly implements the **ISerializable** interface.</span></span> <span data-ttu-id="121a5-116">该对象必须处理其自身的序列化，因为它使用非默认的构造函数。</span><span class="sxs-lookup"><span data-stu-id="121a5-116">The object must handle its own serialization because it uses a non-default constructor.</span></span>  
  
 <span data-ttu-id="121a5-117">与使用消息传送相比，使用 .NET 远程处理可以更有效地与后端系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="121a5-117">Using .NET remoting to communicate with the backend system is more efficient than using messaging.</span></span> <span data-ttu-id="121a5-118">另一方面，与单纯的消息传送解决方案相比，使用 .NET 远程处理可以将业务流程更紧密地绑定到后端系统。</span><span class="sxs-lookup"><span data-stu-id="121a5-118">On the other hand, it binds the orchestrations more tightly to the back-end system than a pure messaging solution might.</span></span> <span data-ttu-id="121a5-119">通过使用 .NET 远程处理，还可以防止该解决方案利用内置的 BizTalk Server 功能来重试请求。</span><span class="sxs-lookup"><span data-stu-id="121a5-119">Using .NET remoting also prevents the solution from taking advantage of the built-in BizTalk Server features for retrying requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="121a5-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="121a5-120">See Also</span></span>  
 <span data-ttu-id="121a5-121">[实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="121a5-121">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="121a5-122">过程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="121a5-122">Process Manager Logic</span></span>](../core/process-manager-logic.md)