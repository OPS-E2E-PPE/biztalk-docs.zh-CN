---
title: 什么是事件跟踪？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e516121a27a1dda41019f99a0e5c2ba0c60c628b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379686"
---
# <a name="what-is-event-tracking"></a>什么是事件跟踪？
跟踪的消息事件数据基于事件 （例如，当服务开始或结束，或发送或接收消息时）。 消息事件跟踪进程返回的事件的发生，这样您可以查看发生的所有基于设置的跟踪筛选器列表。  
  
 你可以跟踪开始和结束的业务流程和端口，发送和接收消息时，以及在业务流程中每个形状的执行。  
  
 BizTalk 跟踪 (BizTalkDTADb) 数据库包含 DTA_Services 审核表。 此表包含所有已部署服务的历史记录 — 管道、 传输和业务流程。 它不会不跟踪的取消部署的服务。  
  
 你可以跟踪消息的内容以及一条消息的升级的属性。 跟踪消息事件将作为这些操作定义**消息正文**跟踪并**消息属性**跟踪。 尽管在消息事件跟踪输出中会出现信封，但不能通过它们跟踪消息属性。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 管理控制台配置跟踪](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)
