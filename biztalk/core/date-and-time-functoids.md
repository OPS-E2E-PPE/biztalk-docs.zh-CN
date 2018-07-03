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
ms.openlocfilehash: 5224c409a6d705806cccc493009ce2c32062f0a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010662"
---
# <a name="date-and-time-functoids"></a>“日期和时间”Functoid

## <a name="overview"></a>概述
**日期 / 时间**functoid 可以分为两类。 第一类包含单个 functoid**添加天数**，用于将指定的天数添加到指定的日期和时间值。 如果输出实例消息中的字段应包括对将来某个日期和时间的估计，这一类可能十分有用。 例如，**添加天数**functoid 可用于生成估计发货日期基于固定的增量了收到订单的日期。  

 第二个类别包括所有中的剩余 functoid**日期和时间**类别。 这些 functoid 用于在运行时提供时间戳，以便输出实例消息中可以包括正在执行的消息转换的日期和时间。  

 **添加天数**functoid 接受两个输入参数，而**日期**，**日期和时间**，以及**时间**functoid 具有任何输入参数。  

## <a name="available-functoids"></a>可用的 functoid  
 **日期 / 时间**functoid 包括： 

* 添加天数
* date
* 日期和时间
* Time

提供了更多详细信息这些 functoid **Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **日期和时间 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
