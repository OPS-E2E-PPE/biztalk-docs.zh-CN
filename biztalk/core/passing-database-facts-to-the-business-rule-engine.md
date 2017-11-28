---
title: "将数据库事实传递到业务规则引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62285bbe-ee64-4c26-b48e-55f666dc1304
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ae35802263b71965698e0bb56d1ddbee9ae0a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="passing-database-facts-to-the-business-rule-engine"></a><span data-ttu-id="e4f21-102">将数据库事实传递到业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="e4f21-102">Passing Database Facts to the Business Rule Engine</span></span>
<span data-ttu-id="e4f21-103">当你使用业务规则编辑器工具测试策略需要将该组/TypedDataTable 对象作为一个事实时，该组/TypedDataTable 对象是自动为你创建和断言到业务规则引擎的工作内存。</span><span class="sxs-lookup"><span data-stu-id="e4f21-103">When you use the Business Rule Composer tool to test a policy that requires a DataConnection/TypedDataTable object as a fact, a DataConnection/TypedDataTable object is automatically created for you and asserted into the Business Rule Engine's working memory.</span></span> <span data-ttu-id="e4f21-104">此外，还将自动提交通过该策略进行的任何数据库更新。</span><span class="sxs-lookup"><span data-stu-id="e4f21-104">Additionally, any database updates by the policy are committed automatically.</span></span>  
  
 <span data-ttu-id="e4f21-105">与此相反，在调用时从业务流程的策略，是通过调用规则形状或以编程方式，该组/TypedDataTable 对象不为你创建，和数据库不会提交更新自动。</span><span class="sxs-lookup"><span data-stu-id="e4f21-105">In contrast, when you invoke the policy from an orchestration, either by using the Call Rules shape or programmatically, the DataConnection/TypedDataTable object is not created for you and the database updates are not committed automatically.</span></span> <span data-ttu-id="e4f21-106">在这种情况下，应创建数据连接/TypedDataTable 对象、 将其与的事实数据传递给规则引擎，并通过使用以下方法之一，以编程方式提交的数据库更改。</span><span class="sxs-lookup"><span data-stu-id="e4f21-106">In this case, you should create a DataConnection/TypedDataTable object, pass it as a fact to the rule engine, and commit the database changes programmatically by using one of the following methods.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a><span data-ttu-id="e4f21-107">通过业务流程传递 DataConnection 对象</span><span class="sxs-lookup"><span data-stu-id="e4f21-107">Passing a DataConnection Object from an Orchestration</span></span>  
 <span data-ttu-id="e4f21-108">下面的示例代码演示如何在业务流程中创建一个 DataConnection 对象、配置调用规则形状以将该 DataConnection 对象作为参数传递，并在执行策略后提交任何数据库更新。</span><span class="sxs-lookup"><span data-stu-id="e4f21-108">The following sample code demonstrates how to create a DataConnection object in the orchestration, configure the Call Rules shape to pass the DataConnection object as a parameter, and commit any database updates after the policy is executed.</span></span>  
  
1.  <span data-ttu-id="e4f21-109">在业务流程设计器中打开业务流程，使用“业务流程视图”选项卡，创建以下变量。</span><span class="sxs-lookup"><span data-stu-id="e4f21-109">Create the following variables using the Orchestration View tab with the orchestration open in the Orchestration Designer.</span></span>  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  <span data-ttu-id="e4f21-110">之前调用规则形状的表达式形状，在创建数据连接对象。</span><span class="sxs-lookup"><span data-stu-id="e4f21-110">In an Expression shape before the Call Rules shape, create a DataConnection object.</span></span> <span data-ttu-id="e4f21-111">下面的代码示例演示如何创建数据连接对象。</span><span class="sxs-lookup"><span data-stu-id="e4f21-111">The following code example demonstrates how to create a DataConnection object.</span></span>  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  <span data-ttu-id="e4f21-112">配置调用规则形状以将 DataCon 变量作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="e4f21-112">Configure the Call Rules shape to pass the DataCon variable as a parameter.</span></span> <span data-ttu-id="e4f21-113">有关详细信息，请参阅[如何使用调用规则形状](../core/how-to-use-the-call-rules-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="e4f21-113">For more information, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
4.  <span data-ttu-id="e4f21-114">在调用规则形状后的表达式形状中，提交策略所做的数据库更改。</span><span class="sxs-lookup"><span data-stu-id="e4f21-114">In an Expression shape after the Call Rules shape, commit the database changes made by the policy.</span></span> <span data-ttu-id="e4f21-115">下面的代码示例演示如何提交策略所做的数据库更改。</span><span class="sxs-lookup"><span data-stu-id="e4f21-115">The following code example demonstrates how to commit the database changes made by the policy.</span></span>  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="e4f21-116">你需要使用[SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)仅对象策略如果更新数据库。</span><span class="sxs-lookup"><span data-stu-id="e4f21-116">You need to use a [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx) object only if the policy updates the database.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a><span data-ttu-id="e4f21-117">从事实检索器传递 DataConnection 对象</span><span class="sxs-lookup"><span data-stu-id="e4f21-117">Passing a DataConnection Object from a Fact Retriever</span></span>  
 <span data-ttu-id="e4f21-118">以下是从事实检索器组件传递 DataConnection 对象所需实施的典型步骤。</span><span class="sxs-lookup"><span data-stu-id="e4f21-118">Here are the typical steps you need to implement to pass a DataConnection object from a fact retriever component.</span></span>  
  
1.  <span data-ttu-id="e4f21-119">创建一个事实检索器组件，用于创建 DataConnection 对象并将其添加到规则引擎的工作内存中。</span><span class="sxs-lookup"><span data-stu-id="e4f21-119">Create a fact retriever component that creates and asserts a DataConnection object into the rule engine's working memory.</span></span> <span data-ttu-id="e4f21-120">有关如何创建事实检索器组件的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。</span><span class="sxs-lookup"><span data-stu-id="e4f21-120">For more information about how to create a fact retriever component, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
2.  <span data-ttu-id="e4f21-121">实现[IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)接口事实检索器组件，并提交中的数据库更改[UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="e4f21-121">Implement the [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx) interface on fact retriever component, and commit the database changes from the [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx) method.</span></span> <span data-ttu-id="e4f21-122">执行完策略后，规则引擎将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="e4f21-122">This method is called by the rule engine after it is done with executing the policy.</span></span>  
  
3.  <span data-ttu-id="e4f21-123">使用“业务规则编辑器”工具，将策略配置为使用事实检索器组件。</span><span class="sxs-lookup"><span data-stu-id="e4f21-123">Configure the policy to use the fact retriever component by using the Business Rule Composer tool.</span></span> <span data-ttu-id="e4f21-124">有关详细信息，请参阅[如何为策略配置事实检索器](../core/how-to-configure-a-fact-retriever-for-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="e4f21-124">For more information, see [How to Configure a Fact Retriever for a Policy](../core/how-to-configure-a-fact-retriever-for-a-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f21-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4f21-125">See Also</span></span>  
 <span data-ttu-id="e4f21-126">[业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e4f21-126">[Data Access in the Business Rule Engine](../core/data-access-in-the-business-rule-engine.md) </span></span>  
 <span data-ttu-id="e4f21-127">[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md) </span><span class="sxs-lookup"><span data-stu-id="e4f21-127">[How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md) </span></span>  
 [<span data-ttu-id="e4f21-128">如何为策略配置事实检索器</span><span class="sxs-lookup"><span data-stu-id="e4f21-128">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)