---
title: 源和目标架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f873c9dcd38c476ea47ea57e412aeec51e239b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243270"
---
# <a name="source-and-destination-schemas"></a>源和目标架构
每个 BizTalk 映射使用两个架构： 源架构和目标架构。 源架构定义从中获取数据的实例消息的结构。 目标架构定义了映射生成的实例消息的结构。 例如，如果你想要映射的装运和帐单信息从采购订单到发票，需要定义采购订单的源架构和定义发票的架构的目标架构的架构。  
  
 BizTalk 映射中使用的架构必须满足以下条件：  
  
- 源和目标架构需要属于当前 BizTalk 项目中，或者必须在程序集中包括对架构的引用，以便可以在运行时访问这些架构。  
  
- 在 BizTalk 映射器中使用的架构必须基于 XML 架构定义 (XSD) 语言。 BizTalk 编辑器提供了创建此类架构的简单方法。 有关使用 BizTalk 编辑器创建架构的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。 另请参阅[创建架构](../core/creating-schemas.md)。  
  
  在 BizTalk 编辑器中，可以使用多个根节点创建架构。 但是，如果在 BizTalk 映射中的多个根节点使用一个架构，您必须选择哪个根节点 （和相应的子结构），在映射中使用。 架构必须具有**根引用**属性确定哪个根是主要的。 如果架构具有多个根和**根引用**属性设置该架构是首次打开时作为源或目标架构，BizTalk 映射器将使用指定的根。 如果架构具有多个根和**根引用**属性未设置，则 BizTalk 映射器会提示你选择的根。  
  
  如果您更改**根引用**属性已在映射中，BizTalk 映射器中使用的架构不会忽略该更改而继续使用最初指定的根。 如果你想要构建不同的映射使用同一架构的不同根，则最好不要设置**根引用**属性。 这样一来，只要该架构用于新的映射，您必须显式选择根。  
  
  如果它包含在映射中之后编辑架构，可能会破坏内映射的链接。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)