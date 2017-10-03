---
title: "消息传送事件流 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d955dbc2b50d1d9c40b54736762fcbaa2bfe536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-event-streams"></a>消息传送事件流
当您的应用程序运行在安装有 BizTalk Server 的计算机上并且您正在跟踪属于 BizTalk 管道事务的项时，使用消息传送事件流 (MES)。 使用 MES 可确保您的 BAM 事件持久化保持与 BizTalk 管道事务同步。  
  
 消息传递的事件流是 EventStream 返回的对象的实例[Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)方法。  
  
 消息传送事件流是异步的，并且将跟踪数据首先存储在 BizTalk MessageBox 数据库中。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
 在中找到 IPipelineContext [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)命名空间。 若要使用该 API，您必须将 Microsoft.BizTalk.Pipeline（在 microsoft.biztalk.pipeline.dll 中）添加到您的项目。  
  
## <a name="see-also"></a>另请参阅  
 [OrchestrationEventStream](../core/orchestrationeventstream.md)   
 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx)   
 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)