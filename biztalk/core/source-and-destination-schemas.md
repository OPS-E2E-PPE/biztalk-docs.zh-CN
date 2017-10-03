---
title: "源和目标架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- destination schemas
- source schemas, maps
- XML schemas, defining
- destination schemas, about destination schemas
- schemas, destination
- destination schemas, maps
- maps, source schemas
- schemas, Root Reference property
- Root Reference property, modifying
- source schemas
- modifying, Root Reference property
- maps, Root Reference property
- source schemas, about source schemas
- schemas, maps
- maps, schema requirements
- schemas, requirements
- schemas, source schemas
- maps, destination schemas
- Root Reference property
ms.assetid: 8c805854-9fa1-4ce3-938d-a2e61ba17fa1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82fb8445260b505fbd04b648c251b99fe896dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="source-and-destination-schemas"></a>源和目标架构
每个 BizTalk 映射都使用两个架构：一个源架构和一个目标架构。 源架构定义了要从中获取数据的实例消息的结构。 目标架构则定义了映射生成的实例消息的结构。 例如，若要将采购订单的发货地址信息和帐单邮寄地址信息映射到发票，则需要一个定义采购订单的架构用作源架构，一个定义发票的架构用作目标架构。  
  
 BizTalk 映射中使用的架构必须符合以下条件：  
  
-   源架构和目标架构必须是当前 BizTalk 项目的一部分，或者必须在程序集中包括指向这两个架构的引用以便在运行时访问它们。  
  
-   BizTalk 映射器中使用的架构必须基于 XML 架构定义 (XSD) 语言。 使用 BizTalk 编辑器可以便捷地创建此类架构。 有关创建使用 BizTalk 编辑器的架构的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。 另请参阅[创建架构](../core/creating-schemas.md)。  
  
 在 BizTalk 编辑器中，可以创建带多个根节点的架构。 但是，如果在 BizTalk 映射中使用带有多个根节点的架构，则必须选择要在映射中使用的根节点（以及相应的子结构）。 架构具有**根引用**属性标识的根是主。 如果某个架构具有多个根和**根引用**属性设置的架构是首次打开时作为源或目标架构、 BizTalk 映射程序使用指定的根。 如果某个架构具有多个根和**根引用**未设置属性，BizTalk 映射程序将提示你选择的根。  
  
 如果你更改**根引用**属性已在地图中，BizTalk 映射程序中使用的架构不到更改，并继续使用最初指定的根。 如果你想要生成不同的映射使用不同的相同的架构的根，则最好不要设置**根引用**属性。 这样，在架构用于新的映射时，您就必须明确地选择根。  
  
 如果在映射包含架构之后再编辑该架构，则映射中的链接可能会断开。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)