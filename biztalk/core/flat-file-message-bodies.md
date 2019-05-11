---
title: 平面文件消息正文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097e49a1-75d2-44a4-9372-d78de7b7597c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef973fca636f4e75f05e26638a841e9e51d39b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387952"
---
# <a name="flat-file-message-bodies"></a>平面文件消息正文
平面文件实例消息正文，是必需的是平面文件拆装器处理成一个或多个 XML 实例消息。 若要了解哪些数据需要入站平面文件实例消息正文中，必须使用对应于正文的平面文件架构配置平面文件拆装器。 可以通过使用指定的架构**文档架构**平面文件拆装器的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。 因为平面文件实例消息必须有一个正文部分，则必须配置相应的架构使用这两种方法之一。  
  
 对于出站平面文件实例消息，平面文件组装器可以动态地确定适当的平面文件架构的实例消息的正文。 平面文件组装器确定消息类型，这是根元素，这两种必须位于出站消息的 XML 版本的名称和目标命名空间的组合中的相应架构。 或者，您可以显式配置要使用通过配置的平面文件架构**文档架构**平面文件组装器的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。  
  
 可在平面文件拆装器会用其来处理入站的实例消息的平面文件架构中指定属性升级在入站平面文件实例消息正文中找到的数据复制到相应的消息上下文中。 同样，可以通过在平面文件组装器会用其来处理出站消息的平面文件架构中指定的属性降级回出站平面文件实例消息复制消息上下文中的数据。  
  
## <a name="see-also"></a>请参阅  
 [平面文件消息标头](../core/flat-file-message-headers.md)   
 [平面文件消息尾部](../core/flat-file-message-trailers.md)   
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md)