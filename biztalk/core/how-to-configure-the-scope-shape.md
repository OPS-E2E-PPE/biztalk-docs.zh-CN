---
title: 如何配置作用域形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], about Scope shape
- Scope shape [Orchestration Designer], configuring
- Scope shape [Orchestration Designer], variables
- Scope shape [Orchestration Designer]
- configuring [Orchestration Designer], Scope shape
- Scope shape [Orchestration Designer], transactions
ms.assetid: 3c518db0-d68c-4f72-9d5c-48540811e289
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef17f5d1ab94875af118d17551da4334525535fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249445"
---
# <a name="how-to-configure-the-scope-shape"></a><span data-ttu-id="2ea34-102">如何配置作用域形状</span><span class="sxs-lookup"><span data-stu-id="2ea34-102">How to Configure the Scope Shape</span></span>
<span data-ttu-id="2ea34-103">**作用域**形状提供其内容的上下文的框架。</span><span class="sxs-lookup"><span data-stu-id="2ea34-103">The **Scope** shape provides a contextual framework for its contents.</span></span> <span data-ttu-id="2ea34-104">第一个块**作用域**形状是上下文块或正文中，作用域的基本操作发生; 它是类似于在 try/catch 语句的 try 块。</span><span class="sxs-lookup"><span data-stu-id="2ea34-104">The first block of a **Scope** shape is the context block, or body, in which the basic actions of the scope take place; it is analogous to the try block in a try/catch statement.</span></span> <span data-ttu-id="2ea34-105">以下正文，**作用域**形状可能还包含一个或多个异常处理程序块和补偿块。</span><span class="sxs-lookup"><span data-stu-id="2ea34-105">Following the body, the **Scope** shape may also include one or more exception-handler blocks and a compensation block.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ea34-106">在多个机环境中其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和协调世界时 (UTC) 是否在两台计算机上的不同，SQL Server 位于不同计算机上则**超时**为配置的属性**作用域**可能早于由于 UTC 时间应在触发形状[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 计算机不同步。</span><span class="sxs-lookup"><span data-stu-id="2ea34-106">In a multiple machine environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are located on different machines, if the Coordinated Universal Time (UTC) is different on the two machines then the **Timeout** property you configure for the **Scope** shape may get triggered earlier than expected because of the UTC time on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server machines is unsynchronized.</span></span> <span data-ttu-id="2ea34-107">请注意，这不是一个时区问题，因为世界时不受时区影响。</span><span class="sxs-lookup"><span data-stu-id="2ea34-107">Note that this is not a time zones issue as Coordinated Universal Time is unaffected by time zones.</span></span>  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a><span data-ttu-id="2ea34-108">将作用域形状配置为事务边界</span><span class="sxs-lookup"><span data-stu-id="2ea34-108">To configure a Scope shape as a transaction boundary</span></span>  
  
1.  <span data-ttu-id="2ea34-109">在属性窗口中，设置**事务类型**属性**原子**或**运行长时间**。</span><span class="sxs-lookup"><span data-stu-id="2ea34-109">In the Properties window, set the **Transaction Type** property to **Atomic** or **Long Running**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ea34-110">业务流程本身必须为长期事务，这样您才能将“事务类型”设置为“原子”或“长期”。</span><span class="sxs-lookup"><span data-stu-id="2ea34-110">The orchestration must itself be a long-running transaction in order for you to set the Transaction Type to Atomic or Long Running.</span></span>  
  
2.  <span data-ttu-id="2ea34-111">如果**事务类型**设置为**原子**，然后在属性窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="2ea34-111">If the **Transaction Type** is set to **Atomic**, then in the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="2ea34-112">属性</span><span class="sxs-lookup"><span data-stu-id="2ea34-112">Property</span></span>|<span data-ttu-id="2ea34-113">Description</span><span class="sxs-lookup"><span data-stu-id="2ea34-113">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="2ea34-114">批处理</span><span class="sxs-lookup"><span data-stu-id="2ea34-114">Batch</span></span>|<span data-ttu-id="2ea34-115">布尔值，确定此事务是否可与多个业务流程实例中的其他事务一起成批处理。</span><span class="sxs-lookup"><span data-stu-id="2ea34-115">Boolean value that determines if this transaction can be batched with other transactions across multiple instances of the orchestration.</span></span> <span data-ttu-id="2ea34-116">由于 BizTalk Server 不支持对多个业务流程实例中的原子事务进行成批处理，所以 BizTalk Server 中从不使用此属性。</span><span class="sxs-lookup"><span data-stu-id="2ea34-116">This property is never used in BizTalk Server because BizTalk Server does not support batching atomic transactions across multiple instances of orchestrations.</span></span> <span data-ttu-id="2ea34-117">在将来版本中将弃用此属性。</span><span class="sxs-lookup"><span data-stu-id="2ea34-117">This property will be deprecated in the future release.</span></span>|  
    |<span data-ttu-id="2ea34-118">隔离级别</span><span class="sxs-lookup"><span data-stu-id="2ea34-118">Isolation Level</span></span>|<span data-ttu-id="2ea34-119">确定并发事务中数据可访问的程度：</span><span class="sxs-lookup"><span data-stu-id="2ea34-119">Determines the degree to which data is accessible among concurrent transactions:</span></span><br /><br /> <span data-ttu-id="2ea34-120">读提交-若要阻止访问在并发事务中的数据进行修改，直到提交所选的事务。</span><span class="sxs-lookup"><span data-stu-id="2ea34-120">-   Read Committed—To prevent the selected transaction from accessing data modifications in concurrent transactions until they are committed.</span></span> <span data-ttu-id="2ea34-121">此选项是 Microsoft SQL Server 的默认设置。</span><span class="sxs-lookup"><span data-stu-id="2ea34-121">This option is the Microsoft SQL Server default setting.</span></span><br /><span data-ttu-id="2ea34-122">可重复的读取-所选的事务完成之前需要读取的锁。</span><span class="sxs-lookup"><span data-stu-id="2ea34-122">-   Repeatable Read—To require read locks until the selected transaction is complete.</span></span><br /><span data-ttu-id="2ea34-123">序列化-以防止并发事务完成所选的事务之前进行数据修改。</span><span class="sxs-lookup"><span data-stu-id="2ea34-123">-   Serializable—To prevent concurrent transactions from making data modifications until the selected transaction is complete.</span></span> <span data-ttu-id="2ea34-124">此选项是最严格的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="2ea34-124">This option is the most restrictive isolation level.</span></span>|  
    |<span data-ttu-id="2ea34-125">重试</span><span class="sxs-lookup"><span data-stu-id="2ea34-125">Retry</span></span>|<span data-ttu-id="2ea34-126">布尔值，确定是否在出错时重试此事务。</span><span class="sxs-lookup"><span data-stu-id="2ea34-126">Boolean value that determines whether this transaction is retried when an error occurs.</span></span> <span data-ttu-id="2ea34-127">默认值是 **True**秒。</span><span class="sxs-lookup"><span data-stu-id="2ea34-127">The default value is **True**.</span></span> <span data-ttu-id="2ea34-128">**注意：** 原子事务将重试，如果引发了 Microsoft.XLANG.BaseTypes.RetryTransactionException，或如果业务流程引擎不能存储其状态或提交该事务。</span><span class="sxs-lookup"><span data-stu-id="2ea34-128">**Note:**  An atomic transaction will be retried if you throw Microsoft.XLANG.BaseTypes.RetryTransactionException, or if the orchestration engine is unable to store its state or commit the transaction.</span></span>|  
    |<span data-ttu-id="2ea34-129">超时</span><span class="sxs-lookup"><span data-stu-id="2ea34-129">Timeout</span></span>|<span data-ttu-id="2ea34-130">确定事务失败之前处于非活动状态的时间（以秒计）。</span><span class="sxs-lookup"><span data-stu-id="2ea34-130">Determines the time in seconds until the transaction fails due to inactivity.</span></span> <span data-ttu-id="2ea34-131">如果不想使用超时，可将此属性值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="2ea34-131">If you do not want to use a timeout, set the value of this property to 0.</span></span> <span data-ttu-id="2ea34-132">**注意：** 这的 DTC 超时，且不强制通过业务流程引擎。</span><span class="sxs-lookup"><span data-stu-id="2ea34-132">**Note:**  This is a DTC timeout, and is not enforced by the orchestration engine.</span></span> <span data-ttu-id="2ea34-133">仅对于原子事务，该引擎不会中断事务。</span><span class="sxs-lookup"><span data-stu-id="2ea34-133">For atomic transactions only, the engine will not interrupt the transaction.</span></span> <span data-ttu-id="2ea34-134">该引擎会在提交前正常运行，只有在通过 DTC 事务中的某一对象参与该事务时，该引擎才会在提交时失败。</span><span class="sxs-lookup"><span data-stu-id="2ea34-134">It proceeds normally until commitment, at which point it fails to commit only if participating in a DTC transaction through one of the objects inside it.</span></span>|  
  
3.  <span data-ttu-id="2ea34-135">如果**事务类型**设置为**运行长时间**，然后在属性窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="2ea34-135">If the **Transaction Type** is set to **Long Running**, then in the Properties window, specify the following property:</span></span>  
  
    |<span data-ttu-id="2ea34-136">属性</span><span class="sxs-lookup"><span data-stu-id="2ea34-136">Property</span></span>|<span data-ttu-id="2ea34-137">Description</span><span class="sxs-lookup"><span data-stu-id="2ea34-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="2ea34-138">超时</span><span class="sxs-lookup"><span data-stu-id="2ea34-138">Timeout</span></span>|<span data-ttu-id="2ea34-139">确定事务超时并被视为失败事务之前经过的时间（以秒计）。</span><span class="sxs-lookup"><span data-stu-id="2ea34-139">Determines the time in seconds until the transaction times out and is considered a failed transaction.</span></span> <span data-ttu-id="2ea34-140">如果不想使用超时，可将此属性值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="2ea34-140">If you do not want to use a timeout, set the value of this property to 0.</span></span>|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a><span data-ttu-id="2ea34-141">配置作用域形状以包含局部变量</span><span class="sxs-lookup"><span data-stu-id="2ea34-141">To configure a Scope shape to contain local variables</span></span>  
  
1.  <span data-ttu-id="2ea34-142">在“业务流程视图”窗口中，双击作用域。</span><span class="sxs-lookup"><span data-stu-id="2ea34-142">Double-click the scope in the Orchestration View window.</span></span>  
  
2.  <span data-ttu-id="2ea34-143">右键单击作用域下的变量文件夹，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="2ea34-143">Right-click the Variables folder under the scope and then click **New Variable**.</span></span>  
  
3.  <span data-ttu-id="2ea34-144">请在"要添加变量"步骤 2 中按[如何添加业务流程变量](../core/how-to-add-orchestration-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="2ea34-144">Proceed from step 2 in "To add a variable" in [How to Add Orchestration Variables](../core/how-to-add-orchestration-variables.md).</span></span>