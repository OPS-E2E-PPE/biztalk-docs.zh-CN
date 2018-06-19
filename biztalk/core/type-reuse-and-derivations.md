---
title: 键入重用和派生 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 240145ea-be41-40ce-8edd-3d4d00e2baec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2982fdf5e46f813669ff74b513615637aa699bd4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286613"
---
# <a name="type-reuse-and-derivations"></a>类型重用和派生
在 XML 架构定义 (XSD) 语言中，复杂的全局类型提供了定义可在架构中各个位置重用并可能进行重新定义的结构化数据类型的机制。 例如，最传统的示例之一是包含姓名、街道、城市、省/自治区等信息的地址结构。 此外，姓名本身可能是包含名字、中名和姓氏字符串的结构。 如果对此复杂结构进行全局定义，则可以在架构中的多个位置使用该结构，例如用于发货地址和帐单邮寄地址。  
  
 XSD 还提供了从一个类型派生另一个类型的机制。 此机制既包括简单内容类型，也包括复杂内容类型。 例如，可以从简单字符串类型（例如，xs:string）派生新的类型，以便该新类型只允许将几个特定字符串作为合法值。 此类派生在 XSD 中称为通过限制派生，因为所派生类型的允许值比基本类型的允许值具有更高的限制性。  
  
 在上述建议的地址类型中，可以提供涉及复杂类型的派生示例。 假设该地址类型被设计为包含特定国家/地区内的地址，该地址中已假定了国家/地区本身。 若要扩展此类地址类型，以便能够处理国际地址，则可以从原始地址类型派生新的类型，然后在所派生的类型中包括诸如国家/地区之类的其他信息。 此类派生在 XSD 中称为通过扩展派生，因为所派生的类型已扩展了基本类型。  
  
 本部分介绍了类型重用以及在重用类型时使用派生对其进行重新定义的方式。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [复杂全局类型定义和命名](../core/complex-global-type-definition-and-naming.md)  
  
-   [如何使用复杂全局类型](../core/ways-to-use-complex-global-types.md)  
  
-   [简单类型派生](../core/simple-type-derivation.md)