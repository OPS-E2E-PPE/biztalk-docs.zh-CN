---
title: 条件循环 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, conditional
- Equal functoids
- maps, conditional looping
ms.assetid: eb16efb8-b12c-47d6-afc9-579fc85ea59c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a29aa5c1835b37f1b268c1aca9b87cc688c291b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391623"
---
# <a name="conditional-looping"></a>循环的条件
您可以添加到条件**循环**通过链接的输出的 functoid**循环**functoid 和**逻辑**functoid 到相同的目标记录。 目标记录只有在符合逻辑条件时才会创建。  
  
## <a name="conditional-looping-map"></a>条件循环映射  
 ![映射来说明条件循环 functoid。](../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")  
  
 在前面的图中，第一个**相等**functoid 比较**名称**字段**FoodSurvey**到"Wendy Wheeler"。 第二个**相等**functoid 比较**名称**字段**FlowerSurvey**到"李伟"。 因此，地图创建目标**地址**仅为两个名称的记录。 使用中的示例数据**循环**functoid 的示例中，输出实例消息将出现，如下所示。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://ConditionalLoop.MasterAddresses">  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290">  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406">  
</ns0:MasterAddresses>  
```  
  
## <a name="see-also"></a>另请参阅  
 [如何添加循环到图 Functoid](../core/how-to-add-looping-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)