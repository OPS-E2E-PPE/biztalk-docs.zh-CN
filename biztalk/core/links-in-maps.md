---
title: "在映射中的链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32d2a9ef07cf2d79037d7983e49b26c6cfe5e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="links-in-maps"></a>在映射中的链接
链接指定将数据从输入实例消息中的元素或属性复制到输出实例中的元素或属性的基本功能。 设计时在源架构和目标架构中的记录和字段之间创建链接。 这样可以在运行时从符合源架构的输入实例消息创建符合目标架构的输出实例消息。  
  
 BizTalk 映射器支持一对一链接和一对多链接。 例如，通过链接可以将源架构中的单个记录或字段连接到目标架构中的单个记录或字段。 通过链接还可以将源架构中的单个记录或字段连接到目标架构中的多个记录或字段。  
  
 链接还可以连接多个记录或字段源架构中到 functoid，然后连接到单个 （或多个） 记录和/或目标架构中的字段。 通常，从多个源记录或字段到单个目标记录或字段的直接链接是无效的，并会产生警告。 一个例外是**循环**functoid。 有关详细信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。  
  
 本部分中的主题介绍在 BizTalk 映射器中创建和使用链接的相关概念。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [类型的链接](../core/types-of-links.md)  
  
-   [创建链接](../core/creating-links.md)  
  
-   [配置链接](../core/configuring-links.md)  
  
-   [到记录链接](../core/record-to-record-linking.md)  
  
-   [链接到和从任何元素和 anyAttribute 节点](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [编译器指令和链接](../core/compiler-directives-and-links.md)