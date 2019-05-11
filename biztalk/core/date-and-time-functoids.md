---
title: 日期和时间 Functoid |Microsoft Docs
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
ms.openlocfilehash: 1bcf2352177c56292007af7d639437b801b278d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352552"
---
# <a name="date-and-time-functoids"></a>日期和时间 Functoid

## <a name="overview"></a>概述
**日期 / 时间**functoid 可以分为两类。 第一类包含单个 functoid**添加天数**，用于将指定的天数添加到指定的日期和时间值。 当输出实例消息中的字段应包含在将来的日期和时间的估计值时，这很有用。 例如，**添加天数**functoid 可用于生成估计发货日期基于固定的增量了收到订单的日期。  

 第二个类别包括所有中的剩余 functoid**日期和时间**类别。 它们用于在运行时，提供一个时间戳，以便可以在输出实例消息中包含的日期和时间消息执行转换。  

 **添加天数**functoid 接受两个输入参数，而**日期**，**日期和时间**，以及**时间**functoid 具有任何输入参数。  

## <a name="available-functoids"></a>可用的 functoid  
 **日期 / 时间**functoid 包括： 

* 添加天数
* Date
* 日期和时间
* Time

提供了更多详细信息这些 functoid **Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **日期和时间 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
