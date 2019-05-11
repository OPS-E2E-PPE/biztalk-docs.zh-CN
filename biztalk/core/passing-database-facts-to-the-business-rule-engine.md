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
# <a name="passing-database-facts-to-the-business-rule-engine"></a>将数据库事实传递到业务规则引擎
当您使用业务规则编辑器工具测试要求 DataConnection/TypedDataTable 对象作为事实的策略时，DataConnection/TypedDataTable 对象自动为您创建并添加到业务规则引擎工作内存。 此外，通过该策略的任何数据库更新都已提交自动。  
  
 与此相反，当您调用从业务流程的策略，是通过使用调用规则形状或以编程方式，DataConnection/TypedDataTable 对象不为你创建，并数据库更新也不会自动提交。 在这种情况下，应创建 DataConnection/TypedDataTable 对象、 将其作为事实传递给规则引擎，并使用以下方法之一以编程方式提交数据库更改。  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a>从业务流程传递 DataConnection 对象  
 下面的示例代码演示如何在业务流程中创建一个 DataConnection 对象、 配置调用规则形状以传递 DataConnection 对象作为参数，以及提交任何数据库更新后执行的策略。  
  
1.  创建以下变量在业务流程设计器中打开该业务流程中使用业务流程视图选项卡。  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  在调用规则形状前面的表达式形状，创建一个 DataConnection 对象。 下面的代码示例演示如何创建一个 DataConnection 对象。  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  配置调用规则形状以将 DataCon 变量作为参数传递。 有关详细信息，请参阅[如何使用调用规则形状](../core/how-to-use-the-call-rules-shape.md)。  
  
4.  在表达式形状中调用规则形状后，提交策略所做的数据库更改。 下面的代码示例演示如何提交策略所做的数据库更改。  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  您需要使用[SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)对象仅当策略更新数据库。  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a>从事实检索器传递 DataConnection 对象  
 下面是您需要实现从事实检索器组件传递 DataConnection 对象的典型步骤。  
  
1.  创建一个事实检索器组件，创建一个 DataConnection 对象添加到规则引擎工作内存。 有关如何创建事实检索器组件的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。  
  
2.  实现[IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)接口上事实检索器组件，并提交数据库更改从[UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)方法。 它通过执行策略后，规则引擎通过调用此方法。  
  
3.  配置要使用业务规则编辑器工具使用事实检索器组件的策略。 有关详细信息，请参阅[如何为策略配置事实检索器](../core/how-to-configure-a-fact-retriever-for-a-policy.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)   
 [如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)   
 [如何为策略配置事实检索器](../core/how-to-configure-a-fact-retriever-for-a-policy.md)