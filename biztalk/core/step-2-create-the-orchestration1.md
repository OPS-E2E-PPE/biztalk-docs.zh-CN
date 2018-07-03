---
title: 步骤 2： 创建 Orchestration1 |Microsoft Docs
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
ms.openlocfilehash: 9802b7c75b704ec34c399df8ecc432ed22d342e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982206"
---
# <a name="step-2-create-the-orchestration"></a>步骤 2： 创建业务流程
使用名为 BeginDocTest 的项目时，业务流程的设置如下所示：  
  
- 端口  
  
- 消息  
  
- 发送和接收  
  
- 构造消息  
  
- 转换  
  
  业务流程不处理任何异常。 如果连接超时， 如果连接超时，Edwards OneWorld 会执行它将回滚的隐式事务内的 BeginDoc 和随后操作。这样，BizTalk 业务流程无需执行任何操作来回滚 J.D.Edwards EnterpriseOne Edwards OneWorld 所做的更改。 不过，超时会导致 BizTalk 业务流程中出现异常。 BizTalk 将异常记录在事件日志中。 如果你要向业务流程添加异常处理，请参阅 Microsoft BizTalk Server 帮助中的“如何添加捕获异常块”和“如何添加补偿块”。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [任务 1：创建端口](../core/task-1-create-the-ports2.md)  
  
-   [任务 2：创建消息](../core/task-2-create-the-messages1.md)  
  
-   [任务 3：配置“发送和接收”形状](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [任务 4：配置“构造消息”形状](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [任务 5：配置“转换”形状](../core/task-5-configure-the-transform-shape1.md)