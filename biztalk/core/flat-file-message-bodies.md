---
title: 平面文件消息正文 |Microsoft 文档
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
ms.openlocfilehash: 2de8748d9a36c817f7db8fed96a59c8d2bd7dda2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246781"
---
# <a name="flat-file-message-bodies"></a>平面文件消息正文
平面文件实例消息正文，是必需的是平面文件反汇编程序处理到一个或多个 XML 实例消息。 要知道哪些数据需要入站平面文件实例消息正文中，你必须配置与对应于正文的平面文件架构的平面文件反汇编程序。 你可以通过使用指定的架构**文档架构**的平面文件反汇编程序的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。 由于平面文件实例消息必须有正文部分，你必须配置相应的架构使用这两种方法之一。  
  
 对于出站的平面文件实例消息，平面文件汇编器可以动态确定实例消息的正文的相应的平面文件架构。 平面文件汇编器确定消息类型，这是根元素，这两种必须存在于出站消息的 XML 版本的名称和目标命名空间的组合中的相应架构。 或者，你可以显式配置平面文件架构，用于通过配置**文档架构**的平面文件汇编器的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。  
  
 在入站平面文件实例消息正文中找到的数据可以复制到相应的消息上下文中，通过在平面文件架构的平面文件反汇编程序用于处理入站的实例消息中指定属性提升。 同样，还可以在平面文件架构的平面文件汇编正在使用其来处理该出站消息中指定属性降级回出站的平面文件实例消息复制消息上下文中的数据。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件消息标头](../core/flat-file-message-headers.md)   
 [平面文件消息拖车安排](../core/flat-file-message-trailers.md)   
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何创建平面文件消息架构](../core/how-to-create-schemas-for-flat-file-messages.md)