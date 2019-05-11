---
title: 平面文件消息标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1981daaf-149a-426d-9a2f-5fcf64bce185
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4914bb5efa806cc16072b6beb96c4d53f6e7ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387922"
---
# <a name="flat-file-message-headers"></a>平面文件消息标头
可选的平面文件实例消息标头的平面文件拆装器的分析已在中配置的平面文件架构控制**标头架构**平面文件拆装器的设计时属性或**XMLNORM。HeaderSpecName**消息上下文属性。 如果未指定的架构使用这两种方法之一，平面文件拆装器将假设平面文件实例消息不包含标头。  

## <a name="outbound-messages"></a>出站消息  
 对于出站平面文件实例消息中，你可以配置平面文件组装器，以便通过指定适当的架构中生成标头及其**头部规范名称**设计时属性或**XMLNORM。HeaderSpecName**消息上下文属性。 有关设置消息上下文属性的详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

## <a name="inbound-messages"></a>入站的消息  
 可以保留和利用两个不同的方式在入站平面文件实例消息标头中找到的数据。 首先，平面文件实例消息标头可以保存在更高版本还原作为标头的相应的出站平面文件实例消息的正文的消息上下文中完整地。 可以使用**保留标头**的接收管道，以指定应当保留头部的属性。 而如果平面文件组装器中指定一个标头，将出站消息上使用保留的头部。  
  
 可以将数据从平面文件实例消息标头的第二个，其中的个别项复制到平面文件消息正文与通过在相应的架构中指定的属性升级的一个或多个字段关联的消息上下文。 有关升级属性的详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [平面文件消息正文](../core/flat-file-message-bodies.md)   
 [平面文件消息尾部](../core/flat-file-message-trailers.md)   
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md)