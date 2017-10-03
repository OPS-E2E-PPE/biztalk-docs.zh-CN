---
title: "使用原子事务的方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e73cfea7a99e2fafbf115a367dbf0840de3369c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenarios-using-atomic-transactions"></a>使用原子事务的方案
下面的方案描述了原子事务的使用。  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a>方案 1： 原子事务与 COM + ServicedComponent  
 以下业务流程演示如何使用**RetryTransactionException**与原子事务。 尽管无法为原子作用域直接包括异常处理程序，但该作用域可以包括可具有异常处理程序的非事务性作用域。 **ServicedComponent**在同一个 DTC 事务中登记和由组件引发任何异常捕获和重新引发作为**RetryTransactionException**。 (此操作假定**重试**属性设置为**True**原子作用域)。  
  
 请注意，已挂起业务流程和 MessageAssignment 形状中的操作将已回滚即使**RetryTransactionException**不会引发。 但是，这种模式能够在自动进行重试的应用程序中提供一定的弹性。  
  
 **与 COM + ServicedComponent 原子事务**  
  
 ![使用 COM &#43; 原子事务ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a>方案 2： 原子事务中使用事务处理的适配器  
 下面的业务流程显示如何将原子事务与 SQL 适配器一起使用。 整个业务流程被标记为长时间运行的两个逻辑部分的工作的单个原子事务： 插入新的客户和插入顺序客户有关的详细信息。  
  
 如果由于某种原因导致插入订单的操作失败，则应回滚插入客户的操作。 该示例使用 SQL 适配器执行数据库工作。 如前所述，消息发送到 MessageBox 数据库时将完成与原子事务相关联的作用域。 这表示引擎在 Scope_InsertCustomer 和 Scope_InsertOrder 作用域中成功发送消息后，将提交每一作用域。 SQL 适配器将为客户或订单的实际插入创建一个新事务。  
  
 这些端口具有“送达通知”属性，用来验证是否通过发送端口成功发送了消息。 将“送达通知”属性设置为“已传输”时，会在发送操作的事务性提交点之前放置一个接收订阅。 但是在原子作用域的情况下，会将接收订阅放在封闭的父作用域中。  
  
 在 InsertOrder SQL 事务失败的情况下，将发送回“Nack”并提交“Scope_InsertOrder”。 发送端口用尽所配置的重试次数后，将引发 DeliveryFailureException。 将运行默认补偿过程的默认异常处理程序会捕获此异常。 这将调用与 Scope_InsertCustomer 和 Scope_InsertOrder 相关联的补偿处理程序，从而导致撤销插入客户信息的操作。  
  
> [!NOTE]
>  将两个作用域嵌套在长期作用域中并从长期作用域的异常处理程序中调用补偿形状（以长期事务为目标），可产生与上述做法相同的行为。 不能将整个业务流程标记为原子的，这是因为原子事务不允许嵌套的事务。  
  
 **与原子事务的事务处理的适配器**  
  
 ![事务处理具有原子事务适配器](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")