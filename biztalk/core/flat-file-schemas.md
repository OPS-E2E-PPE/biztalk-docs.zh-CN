---
title: 平面文件架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8009fba7-85f0-4795-9284-5b4e94b3fc72
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ccb698a49df3edd6820cca5bb48a8045749bf89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387836"
---
# <a name="flat-file-schemas"></a>平面文件架构

## <a name="purpose-of-flat-file-schemas"></a>平面文件架构的用途
平面文件架构有两种用途。 它们将所有相同的记录和字段特性 （包括结构） 定义为 XML 架构，并提供一种机制，用于定义所有平面文件实例消息转换为等效的 XML 所需的平面文件特性实例消息 （或相反）。 使用 BizTalk 映射器内的平面文件架构定义的平面文件实例消息转换为其他目标结构时前, 一种用途是最有用。 定义 BizTalk 映射器中的目标架构的目标结构可能会或可能不会受到平面文件消息架构 （可以是 XML 架构）。  
  
 后一种用途，使用一组广泛的信息添加到使用其批注语法的 XML 架构定义 (XSD) 语言架构的文档的平面文件格式和其等效的 XML 格式之间的转换。 此信息是多余的 XSD 而言，在验证控制其结构的架构对 XML 实例消息用途方面。 然而，XSD 批注语法提供了方便的机制来存储各种不同的作用域，范围为从架构范围内中以批注形式存储的信息中的XSD架构的平面文件结构信息**架构**元素的信息的特定于特定记录或字段中，存储为内相应的批注**元素**或**属性**元素。  
  
 使其不同于与其 XML 等效项的平面文件架构的另一个特征是不能基于其内容的控制架构匹配的实例消息这一事实。 相反，必须通过在运行时的平面文件拆装器用于指定静态架构集。  
  
 若要查看与平面文件的特征相关联的其他节点属性，您需要指定**平面文件扩展**通过使用**架构编辑器扩展**属性**架构**节点。 默认情况下不显示它们。  
  
 有关特定于平面文件架构的节点属性的详细信息，请参阅**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)