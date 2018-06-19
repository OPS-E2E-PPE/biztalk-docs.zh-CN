---
title: Ops 适配器实现详细信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3172759541f46ec6c3c8c2b3e684086747036f37
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970779"
---
# <a name="ops-adapter-implementation-details"></a><span data-ttu-id="15595-102">Ops 适配器实现详细信息</span><span class="sxs-lookup"><span data-stu-id="15595-102">Ops Adapter Implementation Details</span></span>
<span data-ttu-id="15595-103">你可能会发现有助于了解 Ops 适配器的以下方面，修改适配器时或以编程方式配置。</span><span class="sxs-lookup"><span data-stu-id="15595-103">You may find it useful to understand the following aspects of the Ops adapter when modifying the adapter or configuring it programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15595-104">Ops 适配器使用适配器框架进行构建。</span><span class="sxs-lookup"><span data-stu-id="15595-104">The Ops Adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="15595-105">有关生成的框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="15595-105">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="batch-processing"></a><span data-ttu-id="15595-106">批处理</span><span class="sxs-lookup"><span data-stu-id="15595-106">Batch Processing</span></span>  
 <span data-ttu-id="15595-107">适配器一次处理一条消息，以便分别处理每条消息，并一次只能有一个按顺序完成回滚操作。</span><span class="sxs-lookup"><span data-stu-id="15595-107">The adapter processes one message at a time so that each message is processed separately, and rollback operations are done on only one order at a time.</span></span> <span data-ttu-id="15595-108">尽管适配器一次处理一条消息，它都使用批处理的一个批次大小。</span><span class="sxs-lookup"><span data-stu-id="15595-108">Although the adapter processes one message at a time, it does so using batching with a batch size of one.</span></span> <span data-ttu-id="15595-109">这样会更容易，若要修改的适配器来处理批中的消息。</span><span class="sxs-lookup"><span data-stu-id="15595-109">This makes it easier to modify the adapter to handle messages in batches.</span></span>  
  
## <a name="transaction-handling"></a><span data-ttu-id="15595-110">事务处理</span><span class="sxs-lookup"><span data-stu-id="15595-110">Transaction Handling</span></span>  
 <span data-ttu-id="15595-111">适配器使用由 Microsoft 提供的事务功能[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**设施。</span><span class="sxs-lookup"><span data-stu-id="15595-111">The adapter uses the transaction facilities provided by the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]**System.Transactions** facilities.</span></span> <span data-ttu-id="15595-112">适配器创建一个新**CommittableTransaction**并使用它与**TransactionScope**。</span><span class="sxs-lookup"><span data-stu-id="15595-112">The adapter creates a new **CommittableTransaction** and uses it with a **TransactionScope**.</span></span> <span data-ttu-id="15595-113">适配器调用**初始化**和**执行**此事务的上下文中的方法。</span><span class="sxs-lookup"><span data-stu-id="15595-113">The adapter calls the **Initialize** and **Execute** methods within the context of this transaction.</span></span> <span data-ttu-id="15595-114">调用程序集中的代码可以参与事务使用**Transaction.Current**静态方法，用于获取事务上下文。</span><span class="sxs-lookup"><span data-stu-id="15595-114">Code in the called assembly can participate in the transaction by using **Transaction.Current** static method to get the transaction context.</span></span> <span data-ttu-id="15595-115">示例错误处理程序不会进行此工具的使用。</span><span class="sxs-lookup"><span data-stu-id="15595-115">The sample error handler does not make use of this facility.</span></span> <span data-ttu-id="15595-116">有关详细信息**System.Transactions**，请参阅.NET Framework 类库版本中的"System.Transactions Namespace"。</span><span class="sxs-lookup"><span data-stu-id="15595-116">For more information about **System.Transactions**, see "System.Transactions Namespace" in the .NET Framework Class Library version.</span></span>  
  
## <a name="handling-data-other-than-error-reports"></a><span data-ttu-id="15595-117">处理错误报告之外的数据</span><span class="sxs-lookup"><span data-stu-id="15595-117">Handling Data Other Than Error Reports</span></span>  
 <span data-ttu-id="15595-118">在解决方案中，适配器处理从新的错误报告功能的错误报告消息。</span><span class="sxs-lookup"><span data-stu-id="15595-118">In the solution, the adapter handles error report messages from the new error reporting feature.</span></span> <span data-ttu-id="15595-119">但是，因为**执行**方法采用一个字节数组作为其唯一的自变量，无需进行任何专门限制可传递给内容**执行**方法。</span><span class="sxs-lookup"><span data-stu-id="15595-119">However, because the **Execute** method takes a byte array as its only argument, there is nothing that specifically limits what can be passed to the **Execute** method.</span></span>  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a><span data-ttu-id="15595-120">当以编程方式创建端口使用适配器</span><span class="sxs-lookup"><span data-stu-id="15595-120">Using the Adapter When Creating Ports Programmatically</span></span>  
 <span data-ttu-id="15595-121">从代码中创建端口时，你可以指定适配器。</span><span class="sxs-lookup"><span data-stu-id="15595-121">You can specify the adapter when creating ports from code.</span></span> <span data-ttu-id="15595-122">下表显示了自定义属性名称和它们对应的显示名称。</span><span class="sxs-lookup"><span data-stu-id="15595-122">The following table shows the custom property names and how they correspond to the display names.</span></span>  
  
|<span data-ttu-id="15595-123">发送自定义属性名称</span><span class="sxs-lookup"><span data-stu-id="15595-123">Send Custom Property Name</span></span>|<span data-ttu-id="15595-124">显示名称</span><span class="sxs-lookup"><span data-stu-id="15595-124">Display Name</span></span>|  
|-------------------------------|------------------|  
|<span data-ttu-id="15595-125">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="15595-125">**DotNetAssemblyStrongName**</span></span>|<span data-ttu-id="15595-126">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="15595-126">**DotNetAssemblyStrongName**</span></span>|  
|<span data-ttu-id="15595-127">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="15595-127">**DotNetClassName**</span></span>|<span data-ttu-id="15595-128">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="15595-128">**DotNetClassName**</span></span>|  
|<span data-ttu-id="15595-129">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="15595-129">**InitializationData**</span></span>|<span data-ttu-id="15595-130">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="15595-130">**InitializationData**</span></span>|  
|<span data-ttu-id="15595-131">**TransportLocationUri**</span><span class="sxs-lookup"><span data-stu-id="15595-131">**TransportLocationUri**</span></span>|<span data-ttu-id="15595-132">不适用。</span><span class="sxs-lookup"><span data-stu-id="15595-132">Not applicable.</span></span>|  
  
 <span data-ttu-id="15595-133">所有属性都是字符串值。</span><span class="sxs-lookup"><span data-stu-id="15595-133">All of the properties are string values.</span></span> <span data-ttu-id="15595-134">构造从程序集名称和类名称 TransportLocationUri 属性的值。</span><span class="sxs-lookup"><span data-stu-id="15595-134">You construct the value of the TransportLocationUri property from the assembly name and the class name.</span></span> <span data-ttu-id="15595-135">URI 包含值 OPS: / /\<DotNetAssemblyStrongName\>/\<DotNetClassName\>其中将占位符替换为相应的自定义属性的值。</span><span class="sxs-lookup"><span data-stu-id="15595-135">The URI has the value OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\> where the placeholders are replaced by the values of the corresponding custom property.</span></span>  
  
 <span data-ttu-id="15595-136">有关创建端口在代码中的信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。</span><span class="sxs-lookup"><span data-stu-id="15595-136">For information about creating ports from code, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15595-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15595-137">See Also</span></span>  
 [<span data-ttu-id="15595-138">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="15595-138">The Ops Adapter</span></span>](../core/the-ops-adapter.md)