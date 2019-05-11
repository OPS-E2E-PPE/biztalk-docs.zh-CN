---
title: Ops 适配器实现详细信息 |Microsoft Docs
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
ms.openlocfilehash: 37e890b7413726993dd28aa21dec0f13e92f90f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323430"
---
# <a name="ops-adapter-implementation-details"></a><span data-ttu-id="7f127-102">Ops 适配器实现详细信息</span><span class="sxs-lookup"><span data-stu-id="7f127-102">Ops Adapter Implementation Details</span></span>
<span data-ttu-id="7f127-103">你可能会发现可以修改适配器时了解 Ops 适配器的以下方面或以编程方式对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="7f127-103">You may find it useful to understand the following aspects of the Ops adapter when modifying the adapter or configuring it programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f127-104">Ops 适配器是使用适配器框架生成的。</span><span class="sxs-lookup"><span data-stu-id="7f127-104">The Ops Adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="7f127-105">有关构建与框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="7f127-105">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="batch-processing"></a><span data-ttu-id="7f127-106">批处理</span><span class="sxs-lookup"><span data-stu-id="7f127-106">Batch Processing</span></span>  
 <span data-ttu-id="7f127-107">适配器一次处理一条消息，以便分别处理每条消息和一次只有一个订单执行回滚操作。</span><span class="sxs-lookup"><span data-stu-id="7f127-107">The adapter processes one message at a time so that each message is processed separately, and rollback operations are done on only one order at a time.</span></span> <span data-ttu-id="7f127-108">尽管适配器一次处理一条消息，但它是通过使用批处理大小为一个批处理。</span><span class="sxs-lookup"><span data-stu-id="7f127-108">Although the adapter processes one message at a time, it does so using batching with a batch size of one.</span></span> <span data-ttu-id="7f127-109">这使得更轻松地修改适配器处理批中的消息。</span><span class="sxs-lookup"><span data-stu-id="7f127-109">This makes it easier to modify the adapter to handle messages in batches.</span></span>  
  
## <a name="transaction-handling"></a><span data-ttu-id="7f127-110">事务处理</span><span class="sxs-lookup"><span data-stu-id="7f127-110">Transaction Handling</span></span>  
 <span data-ttu-id="7f127-111">适配器使用由 Microsoft 提供的交易设备[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**设施。</span><span class="sxs-lookup"><span data-stu-id="7f127-111">The adapter uses the transaction facilities provided by the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]**System.Transactions** facilities.</span></span> <span data-ttu-id="7f127-112">适配器创建一个新**CommittableTransaction**并将其与**TransactionScope**。</span><span class="sxs-lookup"><span data-stu-id="7f127-112">The adapter creates a new **CommittableTransaction** and uses it with a **TransactionScope**.</span></span> <span data-ttu-id="7f127-113">适配器调用**初始化**并**Execute**此事务的上下文中的方法。</span><span class="sxs-lookup"><span data-stu-id="7f127-113">The adapter calls the **Initialize** and **Execute** methods within the context of this transaction.</span></span> <span data-ttu-id="7f127-114">被调用的程序集中的代码可以参与该事务通过**Transaction.Current**静态方法，用于获取事务上下文。</span><span class="sxs-lookup"><span data-stu-id="7f127-114">Code in the called assembly can participate in the transaction by using **Transaction.Current** static method to get the transaction context.</span></span> <span data-ttu-id="7f127-115">示例错误处理程序不会使此工具的使用。</span><span class="sxs-lookup"><span data-stu-id="7f127-115">The sample error handler does not make use of this facility.</span></span> <span data-ttu-id="7f127-116">有关详细信息**System.Transactions**，在.NET Framework 类库版本中看到"System.Transactions Namespace"。</span><span class="sxs-lookup"><span data-stu-id="7f127-116">For more information about **System.Transactions**, see "System.Transactions Namespace" in the .NET Framework Class Library version.</span></span>  
  
## <a name="handling-data-other-than-error-reports"></a><span data-ttu-id="7f127-117">处理数据的非错误报告</span><span class="sxs-lookup"><span data-stu-id="7f127-117">Handling Data Other Than Error Reports</span></span>  
 <span data-ttu-id="7f127-118">在解决方案中，适配器处理错误报告消息从新的错误报告功能。</span><span class="sxs-lookup"><span data-stu-id="7f127-118">In the solution, the adapter handles error report messages from the new error reporting feature.</span></span> <span data-ttu-id="7f127-119">但是，由于**Execute**方法将获取作为其唯一参数的字节数组，则不执行任何专门限制什么可以传递给**Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="7f127-119">However, because the **Execute** method takes a byte array as its only argument, there is nothing that specifically limits what can be passed to the **Execute** method.</span></span>  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a><span data-ttu-id="7f127-120">以编程方式创建端口时使用的适配器</span><span class="sxs-lookup"><span data-stu-id="7f127-120">Using the Adapter When Creating Ports Programmatically</span></span>  
 <span data-ttu-id="7f127-121">从代码创建端口时，可以指定适配器。</span><span class="sxs-lookup"><span data-stu-id="7f127-121">You can specify the adapter when creating ports from code.</span></span> <span data-ttu-id="7f127-122">下表显示了自定义属性名称并与它们对应的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7f127-122">The following table shows the custom property names and how they correspond to the display names.</span></span>  
  
|<span data-ttu-id="7f127-123">发送自定义属性名称</span><span class="sxs-lookup"><span data-stu-id="7f127-123">Send Custom Property Name</span></span>|<span data-ttu-id="7f127-124">显示名称</span><span class="sxs-lookup"><span data-stu-id="7f127-124">Display Name</span></span>|  
|-------------------------------|------------------|  
|<span data-ttu-id="7f127-125">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="7f127-125">**DotNetAssemblyStrongName**</span></span>|<span data-ttu-id="7f127-126">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="7f127-126">**DotNetAssemblyStrongName**</span></span>|  
|<span data-ttu-id="7f127-127">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="7f127-127">**DotNetClassName**</span></span>|<span data-ttu-id="7f127-128">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="7f127-128">**DotNetClassName**</span></span>|  
|<span data-ttu-id="7f127-129">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="7f127-129">**InitializationData**</span></span>|<span data-ttu-id="7f127-130">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="7f127-130">**InitializationData**</span></span>|  
|<span data-ttu-id="7f127-131">**TransportLocationUri**</span><span class="sxs-lookup"><span data-stu-id="7f127-131">**TransportLocationUri**</span></span>|<span data-ttu-id="7f127-132">不适用。</span><span class="sxs-lookup"><span data-stu-id="7f127-132">Not applicable.</span></span>|  
  
 <span data-ttu-id="7f127-133">所有属性都是字符串值。</span><span class="sxs-lookup"><span data-stu-id="7f127-133">All of the properties are string values.</span></span> <span data-ttu-id="7f127-134">您构造从程序集名称和类名 TransportLocationUri 属性的值。</span><span class="sxs-lookup"><span data-stu-id="7f127-134">You construct the value of the TransportLocationUri property from the assembly name and the class name.</span></span> <span data-ttu-id="7f127-135">URI 具有值 OPS: / /\<DotNetAssemblyStrongName\>/\<DotNetClassName\>其中占位符将替换为相应的自定义属性的值。</span><span class="sxs-lookup"><span data-stu-id="7f127-135">The URI has the value OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\> where the placeholders are replaced by the values of the corresponding custom property.</span></span>  
  
 <span data-ttu-id="7f127-136">有关从代码创建端口的信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。</span><span class="sxs-lookup"><span data-stu-id="7f127-136">For information about creating ports from code, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f127-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f127-137">See Also</span></span>  
 [<span data-ttu-id="7f127-138">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="7f127-138">The Ops Adapter</span></span>](../core/the-ops-adapter.md)