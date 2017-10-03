---
title: "步骤 2： 创建 Orchestration2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08d65525-77a9-4be2-a509-40ea60fa7401
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13973edb14fbaed331a33eff429d623a33c3ff71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-orchestration"></a>步骤 2： 创建业务流程
使用名为 BeginDocTest 的项目时，业务流程的设置如下所示：  
  
 • 端口  
  
 • 消息  
  
 • 发送和接收  
  
 • 构造消息  
  
 • 转换  
  
 业务流程不处理任何异常。 如果连接超时， J.D. Edwards EnterpriseOne 执行它将回滚的隐式事务内的 BeginDoc 和随后操作。这样，BizTalk 业务流程无需执行任何操作来回滚 J.D.Edwards EnterpriseOne 所做的更改。 不过，超时会导致 BizTalk 业务流程中出现异常。 BizTalk 将异常记录在事件日志中。 如果您要向业务流程添加异常处理，请参阅 Microsoft BizTalk 2006 主帮助中的“如果添加捕获异常块”和“如何添加补偿块”。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [任务 1： 创建端口](../core/task-1-create-the-ports1.md)  
  
-   [任务 2： 创建消息](../core/task-2-create-the-messages2.md)  
  
-   [任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes2.md)  
  
-   [任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md)  
  
-   [任务 5： 配置转换形状](../core/task-5-configure-the-transform-shape2.md)