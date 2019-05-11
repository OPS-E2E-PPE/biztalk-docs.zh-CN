---
title: 业务流程的持久性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, persistence
- persistence
- BizTalk Server Orchestration Engine
ms.assetid: 2f79d294-f7df-4d84-ba76-50618506b6c6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee984e3dab85cf9a1efb7a28864c85c9abac918
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395799"
---
# <a name="persistence-in-orchestrations"></a><span data-ttu-id="513d9-102">业务流程的持久性</span><span class="sxs-lookup"><span data-stu-id="513d9-102">Persistence in Orchestrations</span></span>
<span data-ttu-id="513d9-103">业务流程引擎将保存在不同持久化点，以便可以解除冻结的业务流程实例的业务流程实例的整个状态。</span><span class="sxs-lookup"><span data-stu-id="513d9-103">The orchestration engine saves the entire state of an orchestration instance at various persistence points to allow rehydration of the orchestration instance.</span></span> <span data-ttu-id="513d9-104">状态包括任何。可以用于在业务流程，此外消息和变量的基于网络的组件。</span><span class="sxs-lookup"><span data-stu-id="513d9-104">The state includes any .NET-based components that may be used in the orchestration, in addition to messages and variables.</span></span> <span data-ttu-id="513d9-105">该引擎存储在以下持久化点的状态：</span><span class="sxs-lookup"><span data-stu-id="513d9-105">The engine stores state at the following persistence points:</span></span>  
  
- <span data-ttu-id="513d9-106">事务作用域 （原子或长时间运行） 的末尾</span><span class="sxs-lookup"><span data-stu-id="513d9-106">End of a transactional scope (atomic or long running)</span></span>  
  
- <span data-ttu-id="513d9-107">在调试断点</span><span class="sxs-lookup"><span data-stu-id="513d9-107">At debugging breakpoints</span></span>  
  
- <span data-ttu-id="513d9-108">在执行其他业务流程通过启动业务流程形状</span><span class="sxs-lookup"><span data-stu-id="513d9-108">At the execution of other orchestrations through the Start Orchestration shape</span></span>  
  
- <span data-ttu-id="513d9-109">在发送形状 （原子事务中除外）</span><span class="sxs-lookup"><span data-stu-id="513d9-109">At the Send shape (except in an atomic transaction)</span></span>  
  
- <span data-ttu-id="513d9-110">挂起业务流程实例时</span><span class="sxs-lookup"><span data-stu-id="513d9-110">When an Orchestration Instance is suspended</span></span>  
  
- <span data-ttu-id="513d9-111">当系统关闭以受控的方式</span><span class="sxs-lookup"><span data-stu-id="513d9-111">When the system shutdowns in a controlled manner</span></span>  
  
- <span data-ttu-id="513d9-112">在引擎确定它要解除冻结</span><span class="sxs-lookup"><span data-stu-id="513d9-112">When the engine determines it wants to dehydrate</span></span>  
  
- <span data-ttu-id="513d9-113">完成业务流程实例</span><span class="sxs-lookup"><span data-stu-id="513d9-113">When an orchestration instance is finished</span></span>  
  
  <span data-ttu-id="513d9-114">引擎会暂留点的数量进行优化，因为它们是开销很大，尤其是在处理大消息大小。</span><span class="sxs-lookup"><span data-stu-id="513d9-114">The engine optimizes the number of persistence points as they are expensive, especially when dealing with large message sizes.</span></span> <span data-ttu-id="513d9-115">下面，使用原子作用域中的发送形状在业务流程中的两个业务流程实例中所示，引擎确定事务作用域结束和业务流程结束之间的单个持久化点。</span><span class="sxs-lookup"><span data-stu-id="513d9-115">As shown in the two orchestration instances below, in the orchestration with the Send Shapes in an atomic scope, the engine determines a single persistence point between the end of the transaction scope and the end of the orchestration.</span></span> <span data-ttu-id="513d9-116">在另一个业务流程，将有两个持久化点，一个用于第一个发送形状，第二个用于发送形状外加业务流程结束。</span><span class="sxs-lookup"><span data-stu-id="513d9-116">In the other orchestration, there will be two persistence points, one for the first Send shape and the second for the Send shape plus end of the orchestration.</span></span>  
  
  <span data-ttu-id="513d9-117">**业务流程持久化**</span><span class="sxs-lookup"><span data-stu-id="513d9-117">**Orchestration persistence**</span></span>  
  
  <span data-ttu-id="513d9-118">![业务流程持久化](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span><span class="sxs-lookup"><span data-stu-id="513d9-118">![Orchestration persistence](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span></span>  
  
  <span data-ttu-id="513d9-119">任何。在业务流程中使用的基于网络的对象直接或间接必须标记为可序列化除非在原子作用域中调用它们，或如果对象是无状态，并且只通过静态方法调用。</span><span class="sxs-lookup"><span data-stu-id="513d9-119">Any .NET-based objects you use in orchestrations, either directly or indirectly, must be marked as serializable unless they are invoked in atomic scopes, or if the objects are stateless and are invoked only through static methods.</span></span> <span data-ttu-id="513d9-120">**System.Xml.XmlDocument**是一种特殊情况，不需要将标记为可序列化而不考虑作用域的事务属性。</span><span class="sxs-lookup"><span data-stu-id="513d9-120">**System.Xml.XmlDocument** is a special case and does not need to be marked as serializable regardless of the transaction property for a scope.</span></span>  
  
  <span data-ttu-id="513d9-121">如何进行特殊处理**System.Xml.XmlDocument**工作：</span><span class="sxs-lookup"><span data-stu-id="513d9-121">How does the special handling for **System.Xml.XmlDocument** work:</span></span>  
  
  <span data-ttu-id="513d9-122">当用户定义的变量**X**类型的**T**，其中**T**是**System.Xml.XmlDocument**派生一个类或**System.Xml.XmlDocument**然后，编译器会将**X**作为可序列化对象。</span><span class="sxs-lookup"><span data-stu-id="513d9-122">When the user defines a variable **X** of type **T**, where **T** is **System.Xml.XmlDocument** or a class derived from **System.Xml.XmlDocument** then the compiler will treat **X** as a serializable object.</span></span>  
  
  <span data-ttu-id="513d9-123">序列化时**X**，运行时将保留以下几部分信息: （a） 的实际类型**Tr**对象的**X**引用的 （b) **OuterXml**文档的字符串。</span><span class="sxs-lookup"><span data-stu-id="513d9-123">When serializing **X**, the runtime will keep the following pieces of information: (a) the actual type **Tr** of the object **X** is referring to (b) the **OuterXml** string of the document.</span></span>  
  
  <span data-ttu-id="513d9-124">当反序列化**X**，在运行时将创建的一个实例**Tr** （假设不采用任何参数的构造函数），并将调用**LoadXml**提供使用已保存的实例**OuterXml。X**然后将设置为指向新创建的实例**Tr**。</span><span class="sxs-lookup"><span data-stu-id="513d9-124">When de-serializing **X**, the runtime will create an instance of **Tr** (this assumes a constructor that does not take any parameters) and will call **LoadXml** providing the instance with the saved **OuterXml.  X** will then be set to point to the newly created instance of **Tr**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="513d9-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="513d9-125">See Also</span></span>  
 [<span data-ttu-id="513d9-126">中的</span><span class="sxs-lookup"><span data-stu-id="513d9-126">Transactions</span></span>](../core/transactions.md)