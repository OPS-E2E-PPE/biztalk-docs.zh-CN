---
title: 科学 Functoid |Microsoft 文档
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
ms.openlocfilehash: 2b23f65ecede9082ec93041ddab45fa92029851a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269501"
---
# <a name="scientific-functoids"></a>科学 Functoid

## <a name="overview"></a>概述
**科学**functoid 用于执行各种标准三角函数、 对数和指数计算。  
  
 除**Base-Specified 对数**和**X ^ Y** functoid，其中的每个采用两个输入的参数，**科学记数法**functoid 所有采用单个参数。  
  
 四个三角**科学记数法**functoid (**反正切值**，**余弦**，**正弦值**，和**正切**) 所有使用弧度表示，而不是度为单位为其相关的输入或输出参数。 弧度是一种角度度量单位，如一个整圆的弧度为 2π。 下述：  
  
-   2π 弧度 = 360 度  
  
-   1 弧度 = 180/π 度  
  
-   1 度 = π/180 弧度  
  
 如果你输入或输出实例消息使用度角度作为其所在部门的度量值，你将需要使用**数学**结合三角 functoid**科学记数法**到 functoid实现正确的结果。  

## <a name="available-functoids"></a>可用的 functoid  
 **科学记数法**functoid 均： 

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
  
## <a name="see-also"></a>另请参阅  
-  [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **科学 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]