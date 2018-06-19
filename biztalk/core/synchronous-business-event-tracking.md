---
title: 同步业务事件跟踪 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 302c7918-bc62-46f1-a949-fbf94a7073e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84223714e2e04cec6c079862693a09786cb19a7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277933"
---
# <a name="synchronous-business-event-tracking"></a>同步业务事件跟踪
向 BAM 发送事件数据的最简单方法是使用 DirectEventStream 类的实例。 此类在应用程序的当前事务（如果有）的上下文中将事件数据直接保存到 BAM 主导入数据库中。  
  
 如果在此操作期间发生错误，方法调用将在调用应用程序中引发异常。 例如，如果传入 UpdateActivity 的项的名称与 BAM 活动定义不匹配，或者您还未部署 BAM 定义，将会出现这种情况。 这样，在保存 BAM 数据时调用应用程序能够捕获所有错误并从这些错误中恢复，这使以后的管理工作变得更简单。  
  
 同步保存数据可能会影响性能，这是因为调用应用程序必须等待 BAM 执行完所有存储过程和触发器。  
  
## <a name="see-also"></a>另请参阅  
 [异步业务事件跟踪](../core/asynchronous-business-event-tracking.md)