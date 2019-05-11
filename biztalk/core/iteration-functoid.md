---
title: 迭代 Functoid |Microsoft Docs
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
ms.openlocfilehash: 4074e5555a327ab18e1991727d88011b395ae8e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380688"
---
# <a name="iteration-functoid"></a>迭代 Functoid
**迭代**functoid 输出循环中的当前记录的索引结构，从第一条记录，2 表示第二个记录 1 开始，依次类推。  
  
 下图显示**迭代**functoid 结合**大于或等于**functoid**小于或等于**functoid，和一个**和** functoid 创建的等效**为**循环。  
  
 ![说明如何使用迭代 functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")  
迭代 Functoid 映射  
  
 假定**大于或等于**functoid 测试的值大于或等于 2，并且**小于或等于**functoid 测试的值小于或等于 4。 在这种情况下，**并**functoid 将返回**true**仅对记录 2、 3 和 4。 因此，输出实例将包含两个、 3 个或四个输入的实例消息的记录。  
  
## <a name="see-also"></a>请参阅  
 [如何向映射添加迭代 Functoid](../core/how-to-add-iteration-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)