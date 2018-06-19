---
title: XSD 元素组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT, XSLT variations
- BizTalk Mapper, XSLT variations
- maps, groups
- Choice Group node
- XSD element groups
- XSLT, warnings
ms.assetid: a6ea22cb-6066-480e-8a2a-75fade3e5970
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b850841819ce844a10e407827d02993ce3559bad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289533"
---
# <a name="xsd-element-groups"></a>XSD 元素组
通过在架构中使用某些结构，可以在 BizTalk 映射器生成的可扩展样式表语言转换 (XSLT) 中创建变体。  
  
 当映射中包括定义序列、所选项或所有元素组的架构时，可能会出现上述情况。 例如，如果你使用包含的架构**选项组**节点，它是你可以创建一个映射，需要两个或多个的子级**选项组**节点显示在输出实例消息。 在这种情况下，BizTalk 映射器将在编译映射时显示警告。 警告将提示您，所映射的必填字段中只有一个字段能在运行时通过父循环的同一个迭代填充。 BizTalk 映射器将不显示表明映射逻辑不正确的错误消息。  
  
 另一种可以在 XSLT 中生成变体情况需要满足以下条件：  
  
-   **记录一个**中有一个子**字段元素 B**。  
  
-   **记录一个**和子**字段元素 B**出现一次。  
  
-   **记录一个**属于**选项组**重复。  
  
 在这种情况下，BizTalk 映射器将生成包含迭代逻辑的 XSLT，以处理可能会有许多源记录变体的情形。  
  
> [!NOTE]
>  对于涉及组的映射，必须明确地加以指定。 例如，如果目标架构包含**选项组**与 A 和 B 的子节点的节点，所以不能具有 A 和 B 同时对其父组的同一迭代。 BizTalk 映射器不会阻止您创建无效的映射。 因此，必须使用判断 functoid 设置映射，以便 A 和 B 永远不会同时出现。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)