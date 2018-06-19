---
title: 事务支持 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DataConnection object
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 84faac2f-6229-4692-9d1a-bf62d87d69bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57fc1d7a1edd18663cb21a85037cf3e662948fc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279421"
---
# <a name="transaction-support"></a>事务支持
规则引擎通常不支持事务。 但是，你可以通过更新数据库以事务性方式使用**该组**对象中的以下步骤所示：  
  
1.  创建**SqlConnection**对象使用的连接字符串，然后打开该连接。  
  
    ```  
    SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
    connection.Open();  
    ```  
  
2.  创建**SqlTransaction**对象通过调用**BeginTransaction**步骤 1 中创建连接对象上的方法。  
  
    ```  
    SqlTransaction transaction = connection.BeginTransaction();  
    ```  
  
3.  创建**该组**通过使用你在步骤 1 和 2 中创建的连接和事务对象的对象。  
  
    ```  
    DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
    ```  
  
4.  传递**该组**对象与任何其他的事实数据以及你想要将传递给该策略，然后执行策略的事实。  
  
    ```  
    //Passing a .NET object as a fact along with the data connection  
    MyClass obj = new MyClass();  
    object[] facts = new object[2];  
    facts[0] = dc;  
    facts[1] = obj;  
    Policy pol = new Policy(policyName);  
    policy.Execute(facts);    
    ```  
  
5.  调用**更新**数据连接对象上的方法。 执行策略时，所进行的所有更新都是在内存中完成的。 必须调用**更新**要更新数据库的数据连接对象上的方法。  
  
    ```  
    dc.Update();  
    ```  
  
6.  现在，调用**提交**或**回滚**数据连接对象上基于您自己的逻辑。  
  
    ```  
    //Checking the value of PropertyA in .net object   
    //to decide whether to commit or rollback  
    if (obj.PropertyA == true)  
    transaction.Commit();  
    else  
    transaction.Rollback();  
  
    ```  
  
7.  关闭连接，并释放策略对象。  
  
    ```  
    sqlCon.Close();  
    policy.Dispose();  
    ```  
  
 下列代码是上述所有步骤的完整代码：  
  
```  
SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
connection.Open();  
SqlTransaction transaction = connection.BeginTransaction();  
DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
MyClass obj = new MyClass();  
object[] facts = new object[2];  
facts[0] = dc;  
facts[1] = obj;  
Policy pol = new Policy(policyName);  
policy.Execute(facts);    
dc.Update();  
if (obj.PropertyA == true)  
transaction.Commit();  
else  
transaction.Rollback();  
sqlCon.Close();  
policy.Dispose();  
```  
  
## <a name="comments"></a>注释  
  
-   你还可以使用**OleDbConnection**和**OleDbTransaction**对象而不是使用**SqlConnection**和**SqlTransaction**若要以事务性方式执行数据库更新的对象。  
  
-   所有通过策略进行的修改都是在内存中完成的。 必须调用**更新**方法**该组**要更新数据库对象。  
  
-   你可以提交或回滚事务通过调用**提交**或**回滚**方法**该组**分别对象。