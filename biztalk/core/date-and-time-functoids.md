---
title: 日期和时间 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e2d49f5-1aaf-4e4d-8da1-e8605304dccb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec31607ecefb417fef597b5ba700e6461c71a2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238517"
---
# <a name="date-and-time-functoids"></a>“日期和时间”Functoid

## <a name="overview"></a>概述
**日期 / 时间**functoid 可以划分为两个类别。 第一个类别包含单个 functoid，**添加天**，它用于将指定的天数添加到指定的日期和时间值。 如果输出实例消息中的字段应包括对将来某个日期和时间的估计，这一类可能十分有用。 例如，**添加天**functoid 可以用于生成估计传送日期基于固定的增量从了收到订单的日期。  
  
 第二个类别包括所有在剩余 functoid**日期和时间**类别。 这些 functoid 用于在运行时提供时间戳，以便输出实例消息中可以包括正在执行的消息转换的日期和时间。  
  
 **添加天**functoid 接受两个输入参数，而**日期**，**日期和时间**，和**时间**functoid 产生任何影响参数。  

## <a name="available-functoids"></a>可用的 functoid  
 **日期 / 时间**functoid 均： 

* 添加天数
* 日期
* 日期和时间
* Time

提供了更多详细信息上这些 functoid **Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
-  [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **日期和时间 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]