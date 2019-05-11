---
title: 第 2 步：创建 Orchestration1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a88cafbb-3b6f-4d27-8516-79a2391b4e31
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738dc5e784087b559cde9ffb82d3706f568fe160
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392744"
---
# <a name="step-2-create-the-orchestration"></a>第 2 步：创建业务流程
业务流程的设置是使用名为 BeginDocTest 的项目按如下所示：  
  
- 端口  
  
- 消息  
  
- 发送和接收  
  
- 构造消息  
  
- 转换  
  
  业务流程不处理任何异常。 J.D. Edwards OneWorld 会执行的 BeginDoc 和后续操作，它将回滚，如果连接超时的隐式事务内。BizTalk 业务流程因此不需要执行任何操作来回滚更改 j.d. Edwards OneWorld 使。 但是，超时时间将 BizTalk 业务流程中导致异常。 BizTalk 将异常记录在事件日志中。 如果你想要向业务流程添加异常处理，请参阅"如何添加捕获异常块"和"如何添加补偿块"中的 Microsoft BizTalk Server 帮助。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [任务 1:创建端口](../core/task-1-create-the-ports2.md)  
  
-   [任务 2:创建消息](../core/task-2-create-the-messages1.md)  
  
-   [任务 3:配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [任务 4:配置构造消息形状](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [任务 5:配置转换形状](../core/task-5-configure-the-transform-shape1.md)