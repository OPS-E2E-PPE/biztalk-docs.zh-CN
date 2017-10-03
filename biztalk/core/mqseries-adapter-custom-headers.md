---
title: "MQSeries 适配器自定义标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09a05b8c73cd7be84af01eb4465681816e429bc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-custom-headers"></a>MQSeries 适配器自定义标头
由于在 MQSeries 消息中使用了标头结构，因此必须对要使用的所有自定义标头进行管理。 为了避免影响对 MQSeries 标头的处理，自定义标头必须包含在消息正文中。 应避免对任何自动升级的属性进行降级。 有关自动提升的属性的详细信息，请参阅[MQSeries 适配器属性](../core/mqseries-adapter-properties.md)。  
  
 在消息正文中包含自定义标头需要执行额外的处理任务。 一种解决方案是在应用程序的管道中处理自定义标头。 接收管道提取自定义标头信息并将该信息升级为上下文属性。 同样，发送管道获取与自定义标头对应的上下文属性并在消息正文中对这些属性进行降级。  
  
 有关在管道组件中使用自定义标头的示例，请参阅[MQSSendPipelineComponent （BizTalk Server 示例）](../core/mqssendpipelinecomponent-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)