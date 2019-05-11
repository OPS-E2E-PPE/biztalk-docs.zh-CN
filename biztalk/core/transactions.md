---
title: 事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376d27c4d0371a207cae974c8a9f74da0cd36e9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399207"
---
# <a name="transactions"></a>事务
BizTalk Server 业务流程引擎管理的状态、 应用业务逻辑，并调用复杂流程和/或事务集的支持应用程序。  
  
 业务流程可以组合为不同部分的工作使用自动回滚所有更改发生错误时的原子事务或长时间运行的它可以包含嵌套的事务，使用自定义异常处理从错误中恢复方案。 这些事务性语义通常管理通过业务流程设计器中的作用域构造。  
  
 长时间运行的进程可以跨天、 周和更长时间持续时间。 长时间运行进程通常利用相关将收到可能发送的消息的消息相关联。 通常，业务流程引擎冻结这些实例以节省系统资源，并接收相关消息后解除冻结。 业务流程引擎将保留到 MessageBox 数据库在已知检查点从任何应用程序或系统异常中恢复的业务流程状态。  
  
 为 BizTalk 业务流程引擎支持异常处理和恢复失败的事务从提供的事务性编程模型，会发生自动回滚其操作错误时的原子事务，或可以包含其他事务，以及自定义异常处理的长时间运行事务。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [原子事务](../core/atomic-transactions.md)  
  
-   [使用原子事务的方案](../core/scenarios-using-atomic-transactions.md)  
  
-   [长时间运行的事务](../core/long-running-transactions.md)  
  
-   [使用长期事务的方案](../core/scenarios-using-long-running-transactions.md)  
  
-   [业务流程的持久性](../core/persistence-in-orchestrations.md)