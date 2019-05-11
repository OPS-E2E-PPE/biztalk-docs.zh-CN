---
title: 使用订单处理程序对象与后端系统进行通信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 919013bbae989d588033437be54ce705179a44f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302995"
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a><span data-ttu-id="d48b9-102">使用订单处理程序对象与后端系统进行通信</span><span class="sxs-lookup"><span data-stu-id="d48b9-102">Using the Order Handler Object to Communicate with Backend Systems</span></span>
<span data-ttu-id="d48b9-103">有许多方法中的业务流程管理解决方案可以与旧的后端订单系统的宽带提供系统接收最终订单的系统通信。</span><span class="sxs-lookup"><span data-stu-id="d48b9-103">There are many ways in which the business process management solution could communicate with the legacy back-end order system, the cable provisioning system that receives the final orders.</span></span> <span data-ttu-id="d48b9-104">该解决方案使用提供的.NET 远程处理功能在 Microsoft[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]与预配系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="d48b9-104">The solution uses the .NET remoting facilities found in Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] to communicate with the provisioning system.</span></span>  
  
 <span data-ttu-id="d48b9-105">该解决方案使用使用接口来定义后端系统访问对象的常用的技术。</span><span class="sxs-lookup"><span data-stu-id="d48b9-105">The solution uses a common technique of using an interface to define the access object to the back-end system.</span></span> <span data-ttu-id="d48b9-106">通过将接口置于单独的程序集在客户端程序集可以有权访问远程对象，而无需有权访问编译的程序集。</span><span class="sxs-lookup"><span data-stu-id="d48b9-106">By putting the interface in a separate assembly the client assembly can have access to the remote object without having to have access to the compiled assembly.</span></span>  
  
 <span data-ttu-id="d48b9-107">**IOrderHandler**接口定义与后端订单系统进行通信的方法。</span><span class="sxs-lookup"><span data-stu-id="d48b9-107">The **IOrderHandler** interface defines the methods to communicate with the backend order system.</span></span> <span data-ttu-id="d48b9-108">该接口包括用于分析、 激活、 取消和完成订单的方法。</span><span class="sxs-lookup"><span data-stu-id="d48b9-108">The interface includes methods for analyzing, activating, canceling, and completing orders.</span></span> <span data-ttu-id="d48b9-109">它还提供用于标识服务类型，需要取消订单时的方法。</span><span class="sxs-lookup"><span data-stu-id="d48b9-109">It also provides a method for identifying the service type, a method needed when an order is canceled.</span></span>  
  
 <span data-ttu-id="d48b9-110">**CableOrder1**， **CableOrder2**，并使用附属业务流程**OrderHandlerWrapper**对象，它实现**IOrderHandler**.</span><span class="sxs-lookup"><span data-stu-id="d48b9-110">The **CableOrder1**, **CableOrder2**, and satellite orchestrations use the **OrderHandlerWrapper** object that implements **IOrderHandler**.</span></span> <span data-ttu-id="d48b9-111">**OrderHandlerWrapper**对象，进而调用的远程实例**OrderHandler**所提供对象**CableProvisioningSystemServer**可执行文件。</span><span class="sxs-lookup"><span data-stu-id="d48b9-111">The **OrderHandlerWrapper** object, in turn, invokes a remote instance of an **OrderHandler** object provided by the **CableProvisioningSystemServer** executable.</span></span> <span data-ttu-id="d48b9-112">使用包装器对象满足业务要求使用.NET 远程处理进行通信的与后端订单系统时，同时，允许使用异常处理组件的重试功能。</span><span class="sxs-lookup"><span data-stu-id="d48b9-112">Using the wrapper object meets the business requirement of using .NET remoting to communicate with the back-end order system while, at the same time, enabling use of the retry features of the exception handling components.</span></span>  
  
 <span data-ttu-id="d48b9-113">因为其中一个必须能够在业务流程中引用每个对象进行序列化**OrderHandlerWrapper**还可序列化。</span><span class="sxs-lookup"><span data-stu-id="d48b9-113">Because one must be able to serialize every object referenced in an orchestration, the **OrderHandlerWrapper** can also be serialized.</span></span> <span data-ttu-id="d48b9-114">使用**OrderHandlerWrapper**隔离从业务流程的序列化代码。</span><span class="sxs-lookup"><span data-stu-id="d48b9-114">Using the **OrderHandlerWrapper** isolates the serialization code from the orchestrations.</span></span>  
  
 <span data-ttu-id="d48b9-115">如果您看一下代码，您将会**OrderHandlerWrapper**对象显式实现**ISerializable**接口。</span><span class="sxs-lookup"><span data-stu-id="d48b9-115">If you look at the code, you'll se that the **OrderHandlerWrapper** object explicitly implements the **ISerializable** interface.</span></span> <span data-ttu-id="d48b9-116">该对象必须处理其自己的序列化，因为它使用非默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="d48b9-116">The object must handle its own serialization because it uses a non-default constructor.</span></span>  
  
 <span data-ttu-id="d48b9-117">使用.NET 远程处理与后端系统进行通信是使用消息传送相比更高效。</span><span class="sxs-lookup"><span data-stu-id="d48b9-117">Using .NET remoting to communicate with the backend system is more efficient than using messaging.</span></span> <span data-ttu-id="d48b9-118">另一方面，它将绑定业务流程更紧密地到后端系统不是纯消息传递解决方案可能。</span><span class="sxs-lookup"><span data-stu-id="d48b9-118">On the other hand, it binds the orchestrations more tightly to the back-end system than a pure messaging solution might.</span></span> <span data-ttu-id="d48b9-119">使用.NET 远程处理还可防止该解决方案利用内置的 BizTalk Server 功能来重试请求。</span><span class="sxs-lookup"><span data-stu-id="d48b9-119">Using .NET remoting also prevents the solution from taking advantage of the built-in BizTalk Server features for retrying requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48b9-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d48b9-120">See Also</span></span>  
 <span data-ttu-id="d48b9-121">[业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="d48b9-121">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="d48b9-122">进程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="d48b9-122">Process Manager Logic</span></span>](../core/process-manager-logic.md)