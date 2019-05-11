---
title: 映射中的链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba3da2b4bebcb559616aa583fd24fd183fd085c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329655"
---
# <a name="links-in-maps"></a>映射中的链接
链接指定将数据从复制的元素或属性的输入的实例消息中的元素或属性在输出实例中的基本功能。 您在设计时在源和目标架构中创建记录和字段之间的链接。 这样可以创建在运行时，输出实例消息从符合源架构的输入的实例消息符合目标架构。  
  
 BizTalk 映射器支持一对一链接和一个多链接。 例如，链接可以连接的单个记录或字段从源架构到单个记录或目标架构中的字段。 链接可以还连接的单个记录或字段从源架构到多个记录或目标架构中的字段。  
  
 链接还可以连接多个记录或字段从源架构到 functoid，然后连接到单个 （或多个） 记录和/或目标架构中的字段。 一般情况下，直接从多个源记录的链接或者到单个目标记录或字段的字段不是有效并生成一条警告。 是一个例外**循环**functoid。 有关详细信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。  
  
 在本部分中的主题介绍与创建和使用 BizTalk 映射器中的链接相关的概念。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [链接类型](../core/types-of-links.md)  
  
-   [创建链接](../core/creating-links.md)  
  
-   [配置链接](../core/configuring-links.md)  
  
-   [记录到记录链接](../core/record-to-record-linking.md)  
  
-   [与“任何元素”和“任何属性”节点相关的链接](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [编译器指令和链接](../core/compiler-directives-and-links.md)