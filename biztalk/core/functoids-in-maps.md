---
title: 在映射中的 Functoid |Microsoft 文档
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
ms.openlocfilehash: 976af2faed27e6cae8a57d9c7c83308d0519d81d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246037"
---
# <a name="functoids-in-maps"></a>映射中的 Functoid
BizTalk 映射器支持从源架构中的记录和字段转换至目标架构中的记录和字段的复杂结构性转换。 Functoid 使用预定义的公式和特定值（称为参数）来执行计算。 这些计算是根据指定的记录和字段顺序执行的。  
  
 通过从工具箱中选择 functoid、将其拖至网格页中并将其链接到源架构和目标架构中的节点，可以将数据加到一起、修改日期或时间信息、连接数据或者执行其他操作。 例如，**添加**functoid 添加值和**记录计数**functoid 实例消息中返回的循环记录的总数。 您可以在工具箱中找到的 functoid 的类别包括： 高级，转换，累积，数据库中，日期 / 时间、 逻辑、 数学、 科学记数法和字符串。  
  
> [!NOTE]
>  除数据库 functoid 之外，所有 functoid 均为内联 C#。  
  
> [!NOTE]
>  目标架构节点接受从除外 functoid 只有一个输入**循环**functoid。  
  
 本部分中的主题将介绍如何从以前版本的 BizTalk Server 迁移 functoid、functoid 概述、其功能以及如何使用这些 functoid。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Functoid 类别](../core/functoid-categories.md)  
  
-   [Functoid 输入参数](../core/functoid-input-parameters.md)  
  
-   [基本 Functoid](../core/basic-functoids.md)  
  
-   [高级的 Functoid](../core/advanced-functoids.md)  
  
-   [级联 Functoid](../core/cascading-functoids.md)  
  
-   [Functoid 属性](../core/functoid-properties.md)  
  
-   [迁移 Functoid](../core/migrating-functoids.md)