---
title: 平面文件消息尾部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe115a5-4fdc-4779-94f3-437b5a06fbd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0f609ee7e4770fdc6f34bcd2ff8c11e5f10b6e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345364"
---
# <a name="flat-file-message-trailers"></a>平面文件消息尾部
使用平面文件实例消息标头，在已在中配置的平面文件架构控制的可选的平面文件实例消息尾部的平面文件拆装器分析**尾部架构**设计时平面文件拆装器的属性或**XMLNORM。TrailerSpecName**消息上下文属性。 如果未指定的架构使用这两种方法之一，平面文件拆装器将假设平面文件实例消息不包含尾部。  
  
 不同于与平面文件实例消息头，平面文件实例消息尾部可既不保存和还原作为单个单元，也可以使用属性升级将各个数据项复制到与平面文件实例关联的消息上下文消息正文。 但是，尾部可以添加到出站平面文件实例消息的指定相应的架构中**尾部架构**平面文件组装器的设计时属性或**XMLNORM。TrailerSpecName**消息上下文属性。 可以使用从消息上下文的属性降级的平面文件实例消息正文，或通过在相应的架构中指定默认值或固定的值指定构成尾部的可变部分的数据。  
  
## <a name="see-also"></a>请参阅  
 [平面文件消息标头](../core/flat-file-message-headers.md)   
 [平面文件消息正文](../core/flat-file-message-bodies.md)   
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md)