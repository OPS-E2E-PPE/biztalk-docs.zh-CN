---
title: "平面文件消息标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1981daaf-149a-426d-9a2f-5fcf64bce185
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271e9fe74d0a55f4b3ff5271861d24474fffaf37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-message-headers"></a>平面文件消息头部
可选的平面文件实例消息头的平面文件反汇编程序分析已在中配置的平面文件架构由控制**标头架构**的平面文件反汇编程序的设计时属性或**XMLNORM。HeaderSpecName**消息上下文属性。 如果未指定使用这两种方法之一的架构，平面文件反汇编程序假定平面文件实例消息不包含标头。  

## <a name="outbound-messages"></a>出站消息  
 对于出站的平面文件实例消息，你可以配置以通过指定适当的架构中生成一个标头的平面文件汇编其**标头规范名称**设计时属性或**XMLNORM。HeaderSpecName**消息上下文属性。 有关设置消息上下文属性的详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

## <a name="inbound-messages"></a>入站的消息  
 可以保留并使用两个不同的方式在入站平面文件实例消息标头中找到的数据。 首先，平面文件实例消息标头可以保存在整个消息上下文的更高版本还原作为标题对应的出站的平面文件实例消息的正文中。 你可以使用**保留标头**接收管道来指定应保留标头属性。 如果在平面文件汇编器指定一个标头，将对出站消息中使用保留的标头。  
  
 平面文件实例消息标头中的数据的第二个、 单个项可以复制到通过在相应的架构中指定的一个或多个字段的属性提升平面文件消息正文与关联的消息上下文。 有关将升级属性的详细信息，请参阅[提升属性](../core/promoting-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件消息正文](../core/flat-file-message-bodies.md)   
 [平面文件消息拖车安排](../core/flat-file-message-trailers.md)   
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何创建平面文件消息架构](../core/how-to-create-schemas-for-flat-file-messages.md)