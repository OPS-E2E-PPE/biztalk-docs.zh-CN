---
title: 表循环和表提取程序 Functoid |Microsoft Docs
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
ms.openlocfilehash: fe6660e5fbfb226ff49c394ee83d7205bd6e2dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291642"
---
# <a name="table-looping-and-table-extractor-functoids"></a>表循环和表提取程序 Functoid

## <a name="overview"></a>概述
在映射中，通常都会有一个结构中的输出实例消息的输入的实例消息中的每个结构。 但是，也会出现需要一个输入的实例结构生成多个输出实例结构的情况。 表驱动循环，可创建生成多个结构的映射。  
  
 表驱动循环使用**表循环**functoid 和**表提取程序**functoid。 **表循环**functoid 已配置的内部表。 对于每个输入记录或字段中，**表循环**functoid 会输出表，一次一个的行。 例如，如果有十个记录中的输入的实例消息和内部表中的两个行**表循环**，则 functoid 会输出二十行，两个用于每条记录的总数。 **表提取程序**functoid 从行提取所需的项，并将其传递到输出实例消息。  
  
 有关更多详细信息，请参阅**表循环 Functoid 引用**并**表提取程序 Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [“表循环”Functoid](../core/table-looping-functoid.md)  
  
-   [“表提取程序”functoid](../core/table-extractor-functoid.md)  
  
-   [表驱动循环配置](../core/table-driven-looping-configuration.md)  
  
-   [表驱动循环示例](../core/table-driven-looping-example.md)