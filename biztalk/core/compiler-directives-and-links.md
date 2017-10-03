---
title: "编译器指令和链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compilier directives
- maps, compiling
- BizTalk Mapper, compiler directives
- links [maps], compiling
ms.assetid: 1655e10c-af98-4100-849d-b8214f93cfe9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b598638072d59e635fd75c8e00836829d9459078
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="compiler-directives-and-links"></a>编译器指令和链接
您可以按每个链接配置以下两条编译器指令：  
  
-   从输入实例消息中检索哪些数据并将其复制为输出实例消息中相关的元素或属性值。  
  
    > [!NOTE]
    >  此处的数据包括用于复制元素或属性的自身名称的选项，而不包括与元素或属性关联的任何值。 元素名称和属性名称并不像通常一样视为 XML 实例消息中所传递数据的一部分。  
  
-   如何在源架构和目标架构之间实现节点匹配。  
  
 本部分详细说明了可用于这些指令的选项。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [数据转换配置](../core/data-transformation-configuration.md)  
  
-   [节点层次结构级别匹配](../core/node-hierarchy-level-matching.md)