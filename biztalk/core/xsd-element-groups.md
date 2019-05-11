---
title: XSD 元素组 |Microsoft Docs
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
ms.openlocfilehash: e2090d300259949b8d5e26f2fa48cc416beba3ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401546"
---
# <a name="xsd-element-groups"></a>XSD 元素组
使用的架构中某些结构，创建变体中可扩展样式表语言转换 (XSLT) 的 BizTalk 映射器生成。  
  
 定义 sequence、 choice 或所有元素组在映射中包括的架构时会发生该错误。 例如，如果您使用的架构，包括**选择组**节点，它是您可以创建一个映射，需要两个或更多的子级**选择组**节点可出现在输出实例消息。 在这种情况下，BizTalk 映射器将在编译映射时显示警告。 警告将提示您只有一个必填字段已映射可能在运行时的同一个父循环迭代填充。 BizTalk 映射器不授予您一条错误消息，指出映射逻辑不正确。  
  
 可能会在其中生成变体，则 XSLT 中的另一种情况是当满足以下条件：  
  
- **记录 A**具有子级**字段元素 B**。  
  
- **记录 A**和子**字段元素 B**出现一次。  
  
- **记录 A**属于**选择组**重复执行。  
  
  在此情况下，BizTalk 映射器将生成包含迭代逻辑，以便处理许多不同的源记录的可能性的 XSLT。  
  
> [!NOTE]
>  您必须是明确地加以指定涉及组的映射。 例如，如果目标架构包含**选择组**具有子节点 A 和 B 节点，不有效 a 和 B 同时在其父组的同一个迭代。 BizTalk 映射器不会阻止你创建有效的映射。 因此，必须使用判断 functoid 设置映射，其中 A 和 B 可以永远不会出现在同一时间。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)