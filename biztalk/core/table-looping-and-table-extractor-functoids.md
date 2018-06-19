---
title: 表循环和表提取程序 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d4433255ac00d51c88b45bd1a2b5205bd1c735
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278357"
---
# <a name="table-looping-and-table-extractor-functoids"></a>表循环和表提取程序 Functoid

## <a name="overview"></a>概述
在映射中，对于输入实例消息中的每个结构，输出实例消息中通常都会有一个对应的结构。 但是，有时候您需要基于一个输入实例结构生成多个输出实例结构。 通过表驱动循环，可以创建生成多个结构的映射。  
  
 主导表循环使用**表循环**functoid 和**表提取程序**functoid。 **表循环**functoid 具有你配置的内部表。 为每个输入字段或记录**表循环**functoid 输出的表，一次一个地行。 例如，如果有 10 个记录中的输入的实例消息和内部表中的两行**表循环**，functoid 输出二十个行，两个用于每个十个记录的总计。 **表提取程序**functoid 从行提取所需的项目，并将其传递到输出实例消息。  
  
 有关更多详细信息，请参阅**表循环 Functoid 引用**和**表提取程序 Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [表循环 Functoid](../core/table-looping-functoid.md)  
  
-   [表提取程序 Functoid](../core/table-extractor-functoid.md)  
  
-   [表驱动循环配置](../core/table-driven-looping-configuration.md)  
  
-   [表驱动循环示例](../core/table-driven-looping-example.md)