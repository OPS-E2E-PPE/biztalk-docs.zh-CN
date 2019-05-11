---
title: 如何配置作用域形状 |Microsoft Docs
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
ms.openlocfilehash: 5627f3463b1d2797abe742462cf60e948e8bbb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340418"
---
# <a name="how-to-configure-the-scope-shape"></a><span data-ttu-id="cbc59-102">如何配置作用域形状</span><span class="sxs-lookup"><span data-stu-id="cbc59-102">How to Configure the Scope Shape</span></span>
<span data-ttu-id="cbc59-103">**作用域**形状提供了上下文框架对其内容。</span><span class="sxs-lookup"><span data-stu-id="cbc59-103">The **Scope** shape provides a contextual framework for its contents.</span></span> <span data-ttu-id="cbc59-104">第一个块**作用域**形状是上下文模块或正文中，作用域的基本操作发生; 它类似于 try/catch 语句的 try 块。</span><span class="sxs-lookup"><span data-stu-id="cbc59-104">The first block of a **Scope** shape is the context block, or body, in which the basic actions of the scope take place; it is analogous to the try block in a try/catch statement.</span></span> <span data-ttu-id="cbc59-105">正文的后面，**作用域**形状还可以包含一个或多个异常处理程序模块和补偿模块。</span><span class="sxs-lookup"><span data-stu-id="cbc59-105">Following the body, the **Scope** shape may also include one or more exception-handler blocks and a compensation block.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc59-106">在多台计算机环境中位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和协调世界时 (UTC) 与在两台计算机上，SQL Server 位于不同计算机上则**超时**为配置的属性**作用域**形状可能会早于预期由于 UTC 时间上触发[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 计算机不同步。</span><span class="sxs-lookup"><span data-stu-id="cbc59-106">In a multiple machine environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are located on different machines, if the Coordinated Universal Time (UTC) is different on the two machines then the **Timeout** property you configure for the **Scope** shape may get triggered earlier than expected because of the UTC time on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server machines is unsynchronized.</span></span> <span data-ttu-id="cbc59-107">请注意，这不是一个时区问题如协调世界时是不受时区影响。</span><span class="sxs-lookup"><span data-stu-id="cbc59-107">Note that this is not a time zones issue as Coordinated Universal Time is unaffected by time zones.</span></span>  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a><span data-ttu-id="cbc59-108">若要将作用域形状配置为事务边界</span><span class="sxs-lookup"><span data-stu-id="cbc59-108">To configure a Scope shape as a transaction boundary</span></span>  
  
1.  <span data-ttu-id="cbc59-109">在属性窗口中设置**事务类型**属性设置为**原子**或**长期**。</span><span class="sxs-lookup"><span data-stu-id="cbc59-109">In the Properties window, set the **Transaction Type** property to **Atomic** or **Long Running**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cbc59-110">业务流程本身必须是为了使您可以将事务类型设置为原子或运行时间长时间运行的事务。</span><span class="sxs-lookup"><span data-stu-id="cbc59-110">The orchestration must itself be a long-running transaction in order for you to set the Transaction Type to Atomic or Long Running.</span></span>  
  
2.  <span data-ttu-id="cbc59-111">如果**事务类型**设置为**原子**，然后在属性窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="cbc59-111">If the **Transaction Type** is set to **Atomic**, then in the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="cbc59-112">属性</span><span class="sxs-lookup"><span data-stu-id="cbc59-112">Property</span></span>|<span data-ttu-id="cbc59-113">Description</span><span class="sxs-lookup"><span data-stu-id="cbc59-113">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="cbc59-114">批处理</span><span class="sxs-lookup"><span data-stu-id="cbc59-114">Batch</span></span>|<span data-ttu-id="cbc59-115">布尔值，该值确定是否可以进行此事务与其他事务批处理业务流程的多个实例。</span><span class="sxs-lookup"><span data-stu-id="cbc59-115">Boolean value that determines if this transaction can be batched with other transactions across multiple instances of the orchestration.</span></span> <span data-ttu-id="cbc59-116">在 BizTalk Server 中永远不会使用此属性，因为 BizTalk Server 不支持跨多个实例的业务流程的批处理原子事务。</span><span class="sxs-lookup"><span data-stu-id="cbc59-116">This property is never used in BizTalk Server because BizTalk Server does not support batching atomic transactions across multiple instances of orchestrations.</span></span> <span data-ttu-id="cbc59-117">此属性将在未来版本中弃用。</span><span class="sxs-lookup"><span data-stu-id="cbc59-117">This property will be deprecated in the future release.</span></span>|  
    |<span data-ttu-id="cbc59-118">隔离级别</span><span class="sxs-lookup"><span data-stu-id="cbc59-118">Isolation Level</span></span>|<span data-ttu-id="cbc59-119">确定数据访问并发事务的程度：</span><span class="sxs-lookup"><span data-stu-id="cbc59-119">Determines the degree to which data is accessible among concurrent transactions:</span></span><br /><br /> <span data-ttu-id="cbc59-120">读取已提交，以防止访问并行事务中的数据修改，直到提交所选的事务。</span><span class="sxs-lookup"><span data-stu-id="cbc59-120">-   Read Committed—To prevent the selected transaction from accessing data modifications in concurrent transactions until they are committed.</span></span> <span data-ttu-id="cbc59-121">此选项是 Microsoft SQL Server 默认设置。</span><span class="sxs-lookup"><span data-stu-id="cbc59-121">This option is the Microsoft SQL Server default setting.</span></span><br /><span data-ttu-id="cbc59-122">-可重复读-为所选的事务完成之前要求读的锁定。</span><span class="sxs-lookup"><span data-stu-id="cbc59-122">-   Repeatable Read—To require read locks until the selected transaction is complete.</span></span><br /><span data-ttu-id="cbc59-123">可序列化，以允许并行事务进行数据修改所选的事务完成之前。</span><span class="sxs-lookup"><span data-stu-id="cbc59-123">-   Serializable—To prevent concurrent transactions from making data modifications until the selected transaction is complete.</span></span> <span data-ttu-id="cbc59-124">此选项是限制性最强的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="cbc59-124">This option is the most restrictive isolation level.</span></span>|  
    |<span data-ttu-id="cbc59-125">重试</span><span class="sxs-lookup"><span data-stu-id="cbc59-125">Retry</span></span>|<span data-ttu-id="cbc59-126">布尔值，该值确定发生错误时是否重试此事务。</span><span class="sxs-lookup"><span data-stu-id="cbc59-126">Boolean value that determines whether this transaction is retried when an error occurs.</span></span> <span data-ttu-id="cbc59-127">默认值是 **True**秒。</span><span class="sxs-lookup"><span data-stu-id="cbc59-127">The default value is **True**.</span></span> <span data-ttu-id="cbc59-128">**注意：** 原子事务将重试，如果引发了 Microsoft.XLANG.BaseTypes.RetryTransactionException，或如果业务流程引擎不能存储其状态或提交事务。</span><span class="sxs-lookup"><span data-stu-id="cbc59-128">**Note:**  An atomic transaction will be retried if you throw Microsoft.XLANG.BaseTypes.RetryTransactionException, or if the orchestration engine is unable to store its state or commit the transaction.</span></span>|  
    |<span data-ttu-id="cbc59-129">超时</span><span class="sxs-lookup"><span data-stu-id="cbc59-129">Timeout</span></span>|<span data-ttu-id="cbc59-130">确定以秒为单位由于处于非活动状态的事务失败之前的时间。</span><span class="sxs-lookup"><span data-stu-id="cbc59-130">Determines the time in seconds until the transaction fails due to inactivity.</span></span> <span data-ttu-id="cbc59-131">如果不希望使用超时，则设置此属性的值为 0。</span><span class="sxs-lookup"><span data-stu-id="cbc59-131">If you do not want to use a timeout, set the value of this property to 0.</span></span> <span data-ttu-id="cbc59-132">**注意：** 这是 DTC 超时，并不强制使用业务流程引擎。</span><span class="sxs-lookup"><span data-stu-id="cbc59-132">**Note:**  This is a DTC timeout, and is not enforced by the orchestration engine.</span></span> <span data-ttu-id="cbc59-133">仅对于原子事务，该引擎将不会中断事务。</span><span class="sxs-lookup"><span data-stu-id="cbc59-133">For atomic transactions only, the engine will not interrupt the transaction.</span></span> <span data-ttu-id="cbc59-134">它继续，通常直到做出的承诺，此时它无法提交，仅当参与 DTC 事务通过其内部的对象之一。</span><span class="sxs-lookup"><span data-stu-id="cbc59-134">It proceeds normally until commitment, at which point it fails to commit only if participating in a DTC transaction through one of the objects inside it.</span></span>|  
  
3.  <span data-ttu-id="cbc59-135">如果**事务类型**设置为**长期**，然后在属性窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="cbc59-135">If the **Transaction Type** is set to **Long Running**, then in the Properties window, specify the following property:</span></span>  
  
    |<span data-ttu-id="cbc59-136">属性</span><span class="sxs-lookup"><span data-stu-id="cbc59-136">Property</span></span>|<span data-ttu-id="cbc59-137">Description</span><span class="sxs-lookup"><span data-stu-id="cbc59-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="cbc59-138">超时</span><span class="sxs-lookup"><span data-stu-id="cbc59-138">Timeout</span></span>|<span data-ttu-id="cbc59-139">确定在秒钟，直到事务超时并被视为失败的事务的时间。</span><span class="sxs-lookup"><span data-stu-id="cbc59-139">Determines the time in seconds until the transaction times out and is considered a failed transaction.</span></span> <span data-ttu-id="cbc59-140">如果不希望使用超时，则设置此属性的值为 0。</span><span class="sxs-lookup"><span data-stu-id="cbc59-140">If you do not want to use a timeout, set the value of this property to 0.</span></span>|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a><span data-ttu-id="cbc59-141">若要配置作用域形状以包含本地变量</span><span class="sxs-lookup"><span data-stu-id="cbc59-141">To configure a Scope shape to contain local variables</span></span>  
  
1.  <span data-ttu-id="cbc59-142">双击业务流程视图窗口中的作用域。</span><span class="sxs-lookup"><span data-stu-id="cbc59-142">Double-click the scope in the Orchestration View window.</span></span>  
  
2.  <span data-ttu-id="cbc59-143">右键单击作用域下的变量文件夹，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="cbc59-143">Right-click the Variables folder under the scope and then click **New Variable**.</span></span>  
  
3.  <span data-ttu-id="cbc59-144">在"添加变量"步骤 2 中，然后[如何添加业务流程变量](../core/how-to-add-orchestration-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc59-144">Proceed from step 2 in "To add a variable" in [How to Add Orchestration Variables](../core/how-to-add-orchestration-variables.md).</span></span>