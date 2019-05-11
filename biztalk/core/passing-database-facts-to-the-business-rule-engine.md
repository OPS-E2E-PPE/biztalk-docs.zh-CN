---
title: 将数据库事实传递到业务规则引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62285bbe-ee64-4c26-b48e-55f666dc1304
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e3b389b3b606089005fa089604b3ba81452fdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395025"
---
# <a name="passing-database-facts-to-the-business-rule-engine"></a><span data-ttu-id="c7cc8-102">将数据库事实传递到业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="c7cc8-102">Passing Database Facts to the Business Rule Engine</span></span>
<span data-ttu-id="c7cc8-103">当您使用业务规则编辑器工具测试要求 DataConnection/TypedDataTable 对象作为事实的策略时，DataConnection/TypedDataTable 对象自动为您创建并添加到业务规则引擎工作内存。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-103">When you use the Business Rule Composer tool to test a policy that requires a DataConnection/TypedDataTable object as a fact, a DataConnection/TypedDataTable object is automatically created for you and asserted into the Business Rule Engine's working memory.</span></span> <span data-ttu-id="c7cc8-104">此外，通过该策略的任何数据库更新都已提交自动。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-104">Additionally, any database updates by the policy are committed automatically.</span></span>  
  
 <span data-ttu-id="c7cc8-105">与此相反，当您调用从业务流程的策略，是通过使用调用规则形状或以编程方式，DataConnection/TypedDataTable 对象不为你创建，并数据库更新也不会自动提交。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-105">In contrast, when you invoke the policy from an orchestration, either by using the Call Rules shape or programmatically, the DataConnection/TypedDataTable object is not created for you and the database updates are not committed automatically.</span></span> <span data-ttu-id="c7cc8-106">在这种情况下，应创建 DataConnection/TypedDataTable 对象、 将其作为事实传递给规则引擎，并使用以下方法之一以编程方式提交数据库更改。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-106">In this case, you should create a DataConnection/TypedDataTable object, pass it as a fact to the rule engine, and commit the database changes programmatically by using one of the following methods.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a><span data-ttu-id="c7cc8-107">从业务流程传递 DataConnection 对象</span><span class="sxs-lookup"><span data-stu-id="c7cc8-107">Passing a DataConnection Object from an Orchestration</span></span>  
 <span data-ttu-id="c7cc8-108">下面的示例代码演示如何在业务流程中创建一个 DataConnection 对象、 配置调用规则形状以传递 DataConnection 对象作为参数，以及提交任何数据库更新后执行的策略。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-108">The following sample code demonstrates how to create a DataConnection object in the orchestration, configure the Call Rules shape to pass the DataConnection object as a parameter, and commit any database updates after the policy is executed.</span></span>  
  
1.  <span data-ttu-id="c7cc8-109">创建以下变量在业务流程设计器中打开该业务流程中使用业务流程视图选项卡。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-109">Create the following variables using the Orchestration View tab with the orchestration open in the Orchestration Designer.</span></span>  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  <span data-ttu-id="c7cc8-110">在调用规则形状前面的表达式形状，创建一个 DataConnection 对象。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-110">In an Expression shape before the Call Rules shape, create a DataConnection object.</span></span> <span data-ttu-id="c7cc8-111">下面的代码示例演示如何创建一个 DataConnection 对象。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-111">The following code example demonstrates how to create a DataConnection object.</span></span>  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  <span data-ttu-id="c7cc8-112">配置调用规则形状以将 DataCon 变量作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-112">Configure the Call Rules shape to pass the DataCon variable as a parameter.</span></span> <span data-ttu-id="c7cc8-113">有关详细信息，请参阅[如何使用调用规则形状](../core/how-to-use-the-call-rules-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-113">For more information, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
4.  <span data-ttu-id="c7cc8-114">在表达式形状中调用规则形状后，提交策略所做的数据库更改。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-114">In an Expression shape after the Call Rules shape, commit the database changes made by the policy.</span></span> <span data-ttu-id="c7cc8-115">下面的代码示例演示如何提交策略所做的数据库更改。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-115">The following code example demonstrates how to commit the database changes made by the policy.</span></span>  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="c7cc8-116">您需要使用[SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)对象仅当策略更新数据库。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-116">You need to use a [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx) object only if the policy updates the database.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a><span data-ttu-id="c7cc8-117">从事实检索器传递 DataConnection 对象</span><span class="sxs-lookup"><span data-stu-id="c7cc8-117">Passing a DataConnection Object from a Fact Retriever</span></span>  
 <span data-ttu-id="c7cc8-118">下面是您需要实现从事实检索器组件传递 DataConnection 对象的典型步骤。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-118">Here are the typical steps you need to implement to pass a DataConnection object from a fact retriever component.</span></span>  
  
1.  <span data-ttu-id="c7cc8-119">创建一个事实检索器组件，创建一个 DataConnection 对象添加到规则引擎工作内存。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-119">Create a fact retriever component that creates and asserts a DataConnection object into the rule engine's working memory.</span></span> <span data-ttu-id="c7cc8-120">有关如何创建事实检索器组件的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-120">For more information about how to create a fact retriever component, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
2.  <span data-ttu-id="c7cc8-121">实现[IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)接口上事实检索器组件，并提交数据库更改从[UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-121">Implement the [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx) interface on fact retriever component, and commit the database changes from the [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx) method.</span></span> <span data-ttu-id="c7cc8-122">它通过执行策略后，规则引擎通过调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-122">This method is called by the rule engine after it is done with executing the policy.</span></span>  
  
3.  <span data-ttu-id="c7cc8-123">配置要使用业务规则编辑器工具使用事实检索器组件的策略。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-123">Configure the policy to use the fact retriever component by using the Business Rule Composer tool.</span></span> <span data-ttu-id="c7cc8-124">有关详细信息，请参阅[如何为策略配置事实检索器](../core/how-to-configure-a-fact-retriever-for-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cc8-124">For more information, see [How to Configure a Fact Retriever for a Policy](../core/how-to-configure-a-fact-retriever-for-a-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7cc8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7cc8-125">See Also</span></span>  
 <span data-ttu-id="c7cc8-126">[业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md) </span><span class="sxs-lookup"><span data-stu-id="c7cc8-126">[Data Access in the Business Rule Engine](../core/data-access-in-the-business-rule-engine.md) </span></span>  
 <span data-ttu-id="c7cc8-127">[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md) </span><span class="sxs-lookup"><span data-stu-id="c7cc8-127">[How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md) </span></span>  
 [<span data-ttu-id="c7cc8-128">如何为策略配置事实检索器</span><span class="sxs-lookup"><span data-stu-id="c7cc8-128">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)