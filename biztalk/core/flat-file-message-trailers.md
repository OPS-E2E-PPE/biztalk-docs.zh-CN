---
title: 平面文件消息拖车安排 |Microsoft 文档
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
ms.openlocfilehash: 7cbeaef3f23de3cb89d873413964cd331ec23f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246285"
---
# <a name="flat-file-message-trailers"></a>平面文件消息尾部
使用平面文件实例消息标头，在由已在中配置的平面文件架构控制通过平面文件反汇编程序的可选的平面文件实例消息尾部的分析**尾部架构**设计时平面文件反汇编程序的属性或**XMLNORM。TrailerSpecName**消息上下文属性。 如果未使用上述两种方法之一来指定架构，则平面文件拆装器将假设平面文件实例消息不包含尾部。  
  
 与平面文件实例消息头不同，平面文件实例消息尾部既不能作为单独的单元进行保存和还原，也不能使用属性升级来将各个数据项复制到与该平面文件实例消息正文相关联的消息上下文中。 但是，尾部可以添加到出站的平面文件实例消息通过指定中的相应架构**尾部架构**的平面文件汇编器的设计时属性或**XMLNORM。TrailerSpecName**消息上下文属性。 通过在平面文件实例消息正文的消息上下文中使用属性降级，或在相应的架构中指定默认值或固定值，可以指定构成尾部的可变部分的数据。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件消息标头](../core/flat-file-message-headers.md)   
 [平面文件消息正文](../core/flat-file-message-bodies.md)   
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何创建平面文件消息架构](../core/how-to-create-schemas-for-flat-file-messages.md)