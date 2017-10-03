---
title: "平面文件架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8009fba7-85f0-4795-9284-5b4e94b3fc72
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674a862b3966088bb1d75dd17ceacd47c30bdda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-schemas"></a>平面文件架构

## <a name="purpose-of-flat-file-schemas"></a>平面文件架构的用途
平面文件架构有两种用途。 它们可以将所有相同的记录和字段特性（包括结构）定义为 XML 架构，并提供用于定义所有平面文件特性的机制，在将平面文件实例消息翻译为等效的 XML 实例消息（或将 XML 实例消息翻译为等效的平面文件实例消息）时需要使用这些特性。 在 BizTalk 映射器中使用平面文件架构来定义平面文件实例消息向其他目标结构的转换时，前一种用途最为有用。 由 BizTalk 映射器中的目标架构定义的目标结构可以由平面文件消息架构（可以是 XML 架构）控制，也可以不通过该架构控制。  
  
 后一种用途用于文档的平面文件格式与其等效的 XML 格式之间的转换，它使用的信息非常广泛，并通过使用其批注语法将这些信息添加到 XML 架构定义 (XSD) 语言架构中。 在根据控制 XML 实例消息结构的架构对 XML 实例消息进行验证时，就 XSD 而言，在用途方面此信息是多余的。 不过，XSD 批注语法提供一个用于存储内各种不同的作用域，范围从架构范围以中的批注的形式存储的信息中的XSD架构的平面文件结构信息的方便机制**架构**元素的信息的特定于特定记录或字段，以在相应的批注的形式存储**元素**或**属性**元素。  
  
 使平面文件架构与其 XML 等效项不同的另一个特性是实例消息不能与基于其内容的控制架构相匹配。 必须指定静态架构集以供平面文件拆装器在运行时使用。  
  
 若要查看的平面文件的特征与关联的其他节点属性，你需要指定**平面文件扩展名**使用**架构编辑器扩展**属性**架构**节点。 默认情况下这些都不显示。  
  
 有关特定于平面文件架构的节点属性的详细信息，请参阅**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)