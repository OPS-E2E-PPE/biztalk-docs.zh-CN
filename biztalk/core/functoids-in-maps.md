---
title: 映射中的 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids
- functoids, about functoids
- functoid types, Record Count
- functoid types, Looping
- Looping functoids
- functoids, categories
- functoid types, Addition
- Record Count functoids
ms.assetid: 10ee8b62-cb20-4d26-9d86-b6564f30c297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45e066b759db92db1f51db81dc98816c3f757654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387822"
---
# <a name="functoids-in-maps"></a>映射中的 Functoid
BizTalk 映射器支持从源架构到目标架构中的字段和记录中记录和字段的复杂结构性转换。 Functoid 使用预定义的公式和特定值，称为参数执行计算。 根据指定的记录和字段的顺序执行这些计算。  
  
 通过从工具箱中选择 functoid、 将其拖到网格页上，并将其链接到源架构和目标架构中的节点，可以一起添加数据，可以修改日期或时间信息、 连接数据，或可以是其他操作执行。 例如，**加法**functoid 将值相加并**记录计数**functoid 将返回的实例消息中循环记录的总计数。 您可以在工具箱中找到的 functoid 的类别包括：高级、 转换，累计、 数据库、 日期 / 时间、 逻辑、 数学、 科学计数法和字符串。  
  
> [!NOTE]
>  所有 functoid 都均为内联C#除数据库 functoid。  
  
> [!NOTE]
>  目标架构节点接受来自除 functoid 只能有一个输入**循环**functoid。  
  
 在本部分中的主题介绍如何从早期版本的 BizTalk Server 迁移 functoid、 functoid 概述、 其功能和如何使用它们。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Functoid 类别](../core/functoid-categories.md)  
  
-   [Functoid 输入参数](../core/functoid-input-parameters.md)  
  
-   [基本 Functoid](../core/basic-functoids.md)  
  
-   [高级的 Functoid](../core/advanced-functoids.md)  
  
-   [“级联”Functoid](../core/cascading-functoids.md)  
  
-   [Functoid 属性](../core/functoid-properties.md)  
  
-   [“迁移”Functoid](../core/migrating-functoids.md)