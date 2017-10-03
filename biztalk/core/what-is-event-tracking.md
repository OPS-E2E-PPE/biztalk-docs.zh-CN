---
title: "什么是事件跟踪？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [HAT tracking], events
- DTA_Services audit table [HAT]
- HAT, events
- events, tracking
- tracking, events
- Tracking database, DTA_Services audit table
- events, HAT
ms.assetid: dd211752-d1af-4287-967a-908b8d067ebb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa53881cf42ae2769621e10ce21e1160f9b7be0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-event-tracking"></a>什么是事件跟踪？
跟踪消息事件数据是基于事件（例如，服务开始或结束时，或发送或接收消息时）进行的。 消息事件跟踪过程会返回一个已发生事件的列表，这样您就可以查看基于所设置的跟踪筛选器发生的所有事件。  
  
 可以跟踪业务流程和端口的开始和结束、发送和接收消息的时间以及业务流程中每个形状的执行情况。  
  
 BizTalk 跟踪 (BizTalkDTADb) 数据库包含 DTA_Services 审核表。 此表包含所有已部署服务（管道、传输和业务流程）的历史记录。 HAT 不跟踪取消部署的服务。  
  
 可以跟踪消息的内容以及消息的升级属性。 跟踪消息事件定义这些操作，如**消息正文**跟踪和**消息属性**跟踪。 尽管在消息事件跟踪输出中会显示信封，但无法通过这些信封跟踪消息属性。  
  
## <a name="see-also"></a>另请参阅  
 [配置使用 BizTalk Server 管理控制台的跟踪](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)