---
title: 科学计数法 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf7a181f200948335aab0ffa2a06d43d38408afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977413"
---
# <a name="scientific-functoids"></a>科学计数法 Functoid

## <a name="overview"></a>概述
**科学记数法**functoid 用于执行各种标准的三角、 对数和指数计算。  

 除**指定底的对数**并**X ^ Y**采用两个输入的参数，functoid**科学记数**functoid 均采用单个参数。  

 四个三角**科学记数**functoid (**反正切值**，**余弦**，**正弦**，和**正切**) 所有使用弧度而不是度作为单位为其相关输入或输出参数。 弧度是一种角度度量单位，如一个整圆的弧度为 2π。 它遵循的：  

- 2π 弧度 = 360 度  

- 1 弧度 = 180/π 度  

- 1 度 = π/180 弧度  

  如果你输入或输出实例消息使用度作为的度量单位的角度，你需要使用**数学**结合使用三角 functoid**科学记数**到 functoid获得正确的结果。  

## <a name="available-functoids"></a>可用的 functoid  
 **科学记数**functoid 包括： 

* 10^n
* 反正切值
* 指定底的对数
* 常用对数
* 余弦值
* 自然指数函数
* 自然对数
* 正弦值
* 正切
* X^Y

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **科学计数法 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
