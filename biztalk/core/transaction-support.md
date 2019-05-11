---
title: 事务支持 |Microsoft Docs
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
ms.openlocfilehash: 79f078800926852be5dcd24679157b000dab1c19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279695"
---
# <a name="transaction-support"></a>事务支持
规则引擎通常情况下不支持事务。 但是，您可以更新数据库中事务的方式使用**DataConnection**对象中的以下步骤所示：  
  
1. 创建**SqlConnection**对象使用的连接字符串，并打开该连接。  
  
   ```  
   SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
   connection.Open();  
   ```  
  
2. 创建**SqlTransaction**对象通过调用**BeginTransaction**步骤 1 中创建连接对象上的方法。  
  
   ```  
   SqlTransaction transaction = connection.BeginTransaction();  
   ```  
  
3. 创建**DataConnection**通过使用在步骤 1 和 2 中创建的连接和事务对象的对象。  
  
   ```  
   DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
   ```  
  
4. 传递**DataConnection**对象作为事实与其他事实一起你想要传递给策略，并执行策略。  
  
   ```  
   //Passing a .NET object as a fact along with the data connection  
   MyClass obj = new MyClass();  
   object[] facts = new object[2];  
   facts[0] = dc;  
   facts[1] = obj;  
   Policy pol = new Policy(policyName);  
   policy.Execute(facts);    
   ```  
  
5. 调用**更新**数据连接对象上的方法。 执行策略仅在内存中完成时完成的所有更新。 必须调用**更新**要更新数据库的数据连接对象上的方法。  
  
   ```  
   dc.Update();  
   ```  
  
6. 现在，调用**提交**或**回滚**在数据连接对象上基于你自己的逻辑。  
  
   ```  
   //Checking the value of PropertyA in .net object   
   //to decide whether to commit or rollback  
   if (obj.PropertyA == true)  
   transaction.Commit();  
   else  
   transaction.Rollback();  
  
   ```  
  
7. 关闭连接，并释放策略对象。  
  
   ```  
   sqlCon.Close();  
   policy.Dispose();  
   ```  
  
   下面的代码是使用的所有步骤的完整代码：  
  
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
  
-   此外可以使用**OleDbConnection**并**OleDbTransaction**而不是使用对象**SqlConnection**并**SqlTransaction**以事务方式执行数据库更新的对象。  
  
-   通过策略的所有修改都在内存中都完成。 必须调用**更新**方法**DataConnection**对象来更新数据库。  
  
-   您可以提交或回滚该事务通过调用**提交**或**回滚**方法**DataConnection**分别对象。