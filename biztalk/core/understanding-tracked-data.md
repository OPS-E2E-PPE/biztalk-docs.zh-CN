---
title: 了解跟踪的数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, viewing
- service instances, viewing
- viewing, suspended instances
- messages, viewing
- viewing, service details
- viewing, orchestration details
- viewing, message details
- orchestrations, viewing
- suspended instances
- instances, suspended
ms.assetid: dcc3fbd5-cd2c-4780-a577-0ccd521cf5eb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed30934ca154c8b6921682112b12d016c57f92be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286581"
---
# <a name="understanding-tracked-data"></a>了解跟踪数据
跟踪查询运行时，在结果列表底部的查询结果窗口会显示跟踪的信息。  
  
## <a name="viewing-message-details"></a>查看消息详细信息  
 您可以跟踪消息属性。 也可以将跟踪消息正文保存到文件中，然后使用非 Microsoft 工具查看它们。  
  
-   可以右键单击服务实例所引用的任何消息，然后选择消息详细信息。  
  
-   如果消息已处理但被跟踪（因为启用了跟踪功能），则可以将其保存到硬盘并对其进行检查。  
  
-   可以附加到业务流程实例，然后使用业务流程调试器。  
  
## <a name="viewing-service-events"></a>查看服务事件  
 当挂起的服务出现在事件日志时，则可以通过使用调查服务**消息流**，**业务流程调试器**，**显示跟踪消息事件**，**显示实时服务实例**，选项从**上下文**菜单。  
  
## <a name="viewing-orchestration-events"></a>查看业务流程事件  
 使用业务流程调试器可以查看消息实例在通过业务流程时所经过的路径。 在逐步执行时，业务流程的呈现图像将显示消息的进度，您可以在业务流程中放置断点，以便进行调试。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [什么是邮件跟踪？](../core/what-is-message-tracking.md)  
  
-   [什么是事件跟踪？](../core/what-is-event-tracking.md)