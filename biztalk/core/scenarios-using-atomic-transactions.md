---
title: 使用原子事务的方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d959fdb9135a804346a869811072f826906b5876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308161"
---
# <a name="scenarios-using-atomic-transactions"></a>使用原子事务的方案
以下方案说明原子事务的使用。  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a>应用场景 1：具有 COM + ServicedComponent 的原子事务  
 下面的业务流程演示如何使用**RetryTransactionException**具有原子事务。 尽管异常处理程序不能直接包含的原子作用域中，作用域可以包括可以具有异常处理程序的非事务性作用域。 **ServicedComponent**在同一 DTC 事务中登记和捕获组件引发的任何异常并将其作为重新引发**RetryTransactionException**。 (这假定**重试**属性设置为**True**原子作用域)。  
  
 请注意，已挂起业务流程和 MessageAssignment 形状中的操作将都已回退即使**RetryTransactionException**不会引发。 此模式，但是，可构建应用程序中的恢复能力重试会自动执行。  
  
 **具有 COM + ServicedComponent 的原子事务**  
  
 ![原子事务与 COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a>应用场景 2：使用事务性的适配器与原子事务  
 下面的业务流程演示如何使用 SQL 适配器与原子事务。 长时间运行的两个逻辑工作部分的单独原子事务与标记将整个业务流程：客户插入新客户和插入订单详细信息。  
  
 如果由于任何原因而将订单插入失败，客户插入应回滚。 此示例使用 SQL 适配器执行数据库工作。 如前文所述，原子事务与关联的范围完成时将消息发送到 MessageBox 数据库。 这意味着，该引擎在 Scope_InsertCustomer 和 Scope_InsertOrder 作用域中发送该消息成功后，作用域的每个提交。 SQL 适配器为客户或订单的实际插入创建了新事务。  
  
 端口具有一个属性，"送达通知"用于验证它已成功通过发送端口发送消息。 当送达通知属性设置为"已传输"时，在发送操作的事务性提交点之前放置一个接收订阅。 但是，在原子作用域，则封闭的父作用域中放置接收订阅。  
  
 在 InsertOrder SQL 事务失败的方案中，将发送"Nack"后退和提交"Scope_InsertOrder"。 在发送端口用尽配置重试次数后，将引发 DeliveryFailureException。 将运行默认补偿过程的默认异常处理程序将捕获此异常。 这将调用与 Scope_InsertCustomer 和 Scope_InsertOrder，从而导致撤销插入客户信息的操作相关联的补偿处理程序。  
  
> [!NOTE]
>  如上文所述，嵌套的长期作用域中的两个作用域和从长期作用域的异常处理程序中调用补偿形状 （面向长时间运行的事务） 将导致相同的行为。 将整个业务流程可能不会标记原子如原子事务不允许嵌套的事务。  
  
 **具有原子事务的事务性的适配器**  
  
 ![事务性适配器与原子事务一起](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")