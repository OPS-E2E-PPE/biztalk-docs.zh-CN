---
title: "事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74827beade56e6e54414371c9796454d3b48609e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transactions"></a>中的
BizTalk Server 业务流程引擎可管理复杂流程和/或事务集的状态，对其应用业务逻辑，并调用其支持应用程序。  
  
 业务流程可由使用原子事务的若干分立工作组成，这些原子事务在发生错误或长时间运行时自动回滚所有更改，业务流程可包含嵌套事务，并可使用自定义异常处理从错误中恢复。 这些事务性语义通常由业务流程设计器中的“作用域”构造管理。  
  
 长期流程可持续数天、数周，甚至更长的时间。 长期流程通常利用相关将收到的消息和要发送的消息关联起来。 业务流程引擎通常会冻结这些实例以节省系统资源，并在收到相关消息后解除冻结。 业务流程引擎会在已知检查点处将业务流程状态持久化到 MessageBox 数据库，以便为从任何应用程序异常或系统异常中恢复做好准备。  
  
 提供给 BizTalk 业务流程引擎的事务性编程模型不仅支持异常处理，还支持从失败的事务、在错误发生时自动回滚其操作的原子事务或包含其他事务的长期事务及自定义异常处理中恢复。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [原子事务](../core/atomic-transactions.md)  
  
-   [使用原子事务的方案](../core/scenarios-using-atomic-transactions.md)  
  
-   [长时间运行的事务](../core/long-running-transactions.md)  
  
-   [使用长时间运行事务的方案](../core/scenarios-using-long-running-transactions.md)  
  
-   [在业务流程中的持久性](../core/persistence-in-orchestrations.md)