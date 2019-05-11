---
title: 消息传送事件流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae51bce79ca06edc8874100648b1b3002f917f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324971"
---
# <a name="messaging-event-streams"></a>消息传送事件流
在其安装 BizTalk Server，并且您的计算机上运行应用程序正在跟踪属于 BizTalk 管道事务的项时使用消息传送事件流 (MES)。 使用 MES 可确保在 BAM 事件持久化保持与 BizTalk 管道事务同步。  
  
 消息传送事件流是由返回的 EventStream 对象的实例[Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)方法。  
  
 消息传送事件流是异步的首先在 BizTalk MessageBox 数据库中存储的跟踪数据。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
 在中找到 IPipelineContext [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)命名空间。 若要使用 API 必须将 Microsoft.BizTalk.Pipeline （在 microsoft.biztalk.pipeline.dll 中） 添加添加到你的项目中。  
  
## <a name="see-also"></a>请参阅  
 [OrchestrationEventStream](../core/orchestrationeventstream.md)   
 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx)   
 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)