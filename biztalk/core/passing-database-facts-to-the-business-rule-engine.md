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
# <a name="passing-database-facts-to-the-business-rule-engine"></a>将数据库事实传递到业务规则引擎
当你使用业务规则编辑器工具测试策略需要将该组/TypedDataTable 对象作为一个事实时，该组/TypedDataTable 对象是自动为你创建和断言到业务规则引擎的工作内存。 此外，还将自动提交通过该策略进行的任何数据库更新。  
  
 与此相反，在调用时从业务流程的策略，是通过调用规则形状或以编程方式，该组/TypedDataTable 对象不为你创建，和数据库不会提交更新自动。 在这种情况下，应创建数据连接/TypedDataTable 对象、 将其与的事实数据传递给规则引擎，并通过使用以下方法之一，以编程方式提交的数据库更改。  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a>通过业务流程传递 DataConnection 对象  
 下面的示例代码演示如何在业务流程中创建一个 DataConnection 对象、配置调用规则形状以将该 DataConnection 对象作为参数传递，并在执行策略后提交任何数据库更新。  
  
1.  在业务流程设计器中打开业务流程，使用“业务流程视图”选项卡，创建以下变量。  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  之前调用规则形状的表达式形状，在创建数据连接对象。 下面的代码示例演示如何创建数据连接对象。  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  配置调用规则形状以将 DataCon 变量作为参数传递。 有关详细信息，请参阅[如何使用调用规则形状](../core/how-to-use-the-call-rules-shape.md)。  
  
4.  在调用规则形状后的表达式形状中，提交策略所做的数据库更改。 下面的代码示例演示如何提交策略所做的数据库更改。  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  你需要使用[SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)仅对象策略如果更新数据库。  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a>从事实检索器传递 DataConnection 对象  
 以下是从事实检索器组件传递 DataConnection 对象所需实施的典型步骤。  
  
1.  创建一个事实检索器组件，用于创建 DataConnection 对象并将其添加到规则引擎的工作内存中。 有关如何创建事实检索器组件的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。  
  
2.  实现[IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)接口事实检索器组件，并提交中的数据库更改[UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)方法。 执行完策略后，规则引擎将调用此方法。  
  
3.  使用“业务规则编辑器”工具，将策略配置为使用事实检索器组件。 有关详细信息，请参阅[如何为策略配置事实检索器](../core/how-to-configure-a-fact-retriever-for-a-policy.md)。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)   
 [如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)   
 [如何为策略配置事实检索器](../core/how-to-configure-a-fact-retriever-for-a-policy.md)