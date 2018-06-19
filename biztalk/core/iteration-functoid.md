---
title: 迭代 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a491b8829f23296e77ba5a89d12985e8ccd32783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261965"
---
# <a name="iteration-functoid"></a>迭代 Functoid
**迭代**functoid 输出中循环的当前记录的索引结构，对于第一个记录，对于第二个记录，2 1 开始，依次类推。  
  
 下图显示**迭代**functoid 结合**大于或等于**functoid，**小于或等于**functoid，和**和** functoid，若要创建的等效形式**为**循环。  
  
 ![映射用法迭代 functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")  
“迭代”Functoid 映射  
  
 假定**大于或等于**functoid 测试值大于或等于 2，和**小于或等于**functoid 测试值小于或等于 4。 在这种情况下，**和**functoid 将返回**true**仅用于记录 2、 3 和 4。 因此，输出实例将包含记录两个、 第三和四个输入的实例消息。  
  
## <a name="see-also"></a>另请参阅  
 [如何在向地图添加迭代 Functoid](../core/how-to-add-iteration-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)