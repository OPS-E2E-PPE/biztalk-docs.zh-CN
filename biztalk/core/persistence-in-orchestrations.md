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
ms.openlocfilehash: 184b4a7dde452902f404a5d6ed5dca5ee611e1e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008910"
---
# <a name="persistence-in-orchestrations"></a><span data-ttu-id="b6919-102">业务流程的持久性</span><span class="sxs-lookup"><span data-stu-id="b6919-102">Persistence in Orchestrations</span></span>
<span data-ttu-id="b6919-103">业务流程引擎将保存业务流程实例在不同持久化点时的整个状态，以便可以解除冻结业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="b6919-103">The orchestration engine saves the entire state of an orchestration instance at various persistence points to allow rehydration of the orchestration instance.</span></span> <span data-ttu-id="b6919-104">该状态包括可在业务流程中使用的所有基于 .NET 的组件以及消息和变量。</span><span class="sxs-lookup"><span data-stu-id="b6919-104">The state includes any .NET-based components that may be used in the orchestration, in addition to messages and variables.</span></span> <span data-ttu-id="b6919-105">该引擎存储处于以下持久化点时的状态：</span><span class="sxs-lookup"><span data-stu-id="b6919-105">The engine stores state at the following persistence points:</span></span>  
  
- <span data-ttu-id="b6919-106">事务作用域（原子事务或长期事务）结束时</span><span class="sxs-lookup"><span data-stu-id="b6919-106">End of a transactional scope (atomic or long running)</span></span>  
  
- <span data-ttu-id="b6919-107">在调试断点时</span><span class="sxs-lookup"><span data-stu-id="b6919-107">At debugging breakpoints</span></span>  
  
- <span data-ttu-id="b6919-108">在通过启动业务流程形状执行其他业务流程时</span><span class="sxs-lookup"><span data-stu-id="b6919-108">At the execution of other orchestrations through the Start Orchestration shape</span></span>  
  
- <span data-ttu-id="b6919-109">在发送形状上（原子事务中除外）</span><span class="sxs-lookup"><span data-stu-id="b6919-109">At the Send shape (except in an atomic transaction)</span></span>  
  
- <span data-ttu-id="b6919-110">在挂起业务流程实例时</span><span class="sxs-lookup"><span data-stu-id="b6919-110">When an Orchestration Instance is suspended</span></span>  
  
- <span data-ttu-id="b6919-111">在系统以可控方式关闭时</span><span class="sxs-lookup"><span data-stu-id="b6919-111">When the system shutdowns in a controlled manner</span></span>  
  
- <span data-ttu-id="b6919-112">在引擎确定它要解除冻结时</span><span class="sxs-lookup"><span data-stu-id="b6919-112">When the engine determines it wants to dehydrate</span></span>  
  
- <span data-ttu-id="b6919-113">在业务流程实例完成时</span><span class="sxs-lookup"><span data-stu-id="b6919-113">When an orchestration instance is finished</span></span>  
  
  <span data-ttu-id="b6919-114">引擎在持久化点占用高昂系统资源（尤其是在处理大消息）时优化持久化点的数目。</span><span class="sxs-lookup"><span data-stu-id="b6919-114">The engine optimizes the number of persistence points as they are expensive, especially when dealing with large message sizes.</span></span> <span data-ttu-id="b6919-115">如下面的两个业务流程实例所示，在原子作用域中含发送形状的业务流程中，引擎确定事务作用域结束和业务流程结束之间的单个持久化点。</span><span class="sxs-lookup"><span data-stu-id="b6919-115">As shown in the two orchestration instances below, in the orchestration with the Send Shapes in an atomic scope, the engine determines a single persistence point between the end of the transaction scope and the end of the orchestration.</span></span> <span data-ttu-id="b6919-116">在其他业务流程中，存在两个持久化点，一个用于第一个发送形状，第二个用于发送形状外加业务流程结束。</span><span class="sxs-lookup"><span data-stu-id="b6919-116">In the other orchestration, there will be two persistence points, one for the first Send shape and the second for the Send shape plus end of the orchestration.</span></span>  
  
  <span data-ttu-id="b6919-117">**业务流程持久化**</span><span class="sxs-lookup"><span data-stu-id="b6919-117">**Orchestration persistence**</span></span>  
  
  <span data-ttu-id="b6919-118">![业务流程持久化](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span><span class="sxs-lookup"><span data-stu-id="b6919-118">![Orchestration persistence](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span></span>  
  
  <span data-ttu-id="b6919-119">在业务流程中使用的任何基于 .NET 的对象（无论是直接的还是间接的）都必须标记为可序列化，但以下情况除外：对象在原子作用域中被调用，或者对象是无状态的并且只通过静态方法调用。</span><span class="sxs-lookup"><span data-stu-id="b6919-119">Any .NET-based objects you use in orchestrations, either directly or indirectly, must be marked as serializable unless they are invoked in atomic scopes, or if the objects are stateless and are invoked only through static methods.</span></span> <span data-ttu-id="b6919-120">**System.Xml.XmlDocument**是一种特殊情况，不需要将标记为可序列化而不考虑作用域的事务属性。</span><span class="sxs-lookup"><span data-stu-id="b6919-120">**System.Xml.XmlDocument** is a special case and does not need to be marked as serializable regardless of the transaction property for a scope.</span></span>  
  
  <span data-ttu-id="b6919-121">如何进行特殊处理**System.Xml.XmlDocument**工作：</span><span class="sxs-lookup"><span data-stu-id="b6919-121">How does the special handling for **System.Xml.XmlDocument** work:</span></span>  
  
  <span data-ttu-id="b6919-122">当用户定义的变量**X**类型的**T**，其中**T**是**System.Xml.XmlDocument**派生一个类或**System.Xml.XmlDocument**然后，编译器会将**X**作为可序列化对象。</span><span class="sxs-lookup"><span data-stu-id="b6919-122">When the user defines a variable **X** of type **T**, where **T** is **System.Xml.XmlDocument** or a class derived from **System.Xml.XmlDocument** then the compiler will treat **X** as a serializable object.</span></span>  
  
  <span data-ttu-id="b6919-123">序列化时**X**，运行时将保留以下几部分信息: （a） 的实际类型**Tr**对象的**X**引用的 （b) **OuterXml**文档的字符串。</span><span class="sxs-lookup"><span data-stu-id="b6919-123">When serializing **X**, the runtime will keep the following pieces of information: (a) the actual type **Tr** of the object **X** is referring to (b) the **OuterXml** string of the document.</span></span>  
  
  <span data-ttu-id="b6919-124">当反序列化**X**，在运行时将创建的一个实例**Tr** （假设不采用任何参数的构造函数），并将调用**LoadXml**提供使用已保存的实例**OuterXml。X**然后将设置为指向新创建的实例**Tr**。</span><span class="sxs-lookup"><span data-stu-id="b6919-124">When de-serializing **X**, the runtime will create an instance of **Tr** (this assumes a constructor that does not take any parameters) and will call **LoadXml** providing the instance with the saved **OuterXml.  X** will then be set to point to the newly created instance of **Tr**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6919-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6919-125">See Also</span></span>  
 [<span data-ttu-id="b6919-126">中的</span><span class="sxs-lookup"><span data-stu-id="b6919-126">Transactions</span></span>](../core/transactions.md)