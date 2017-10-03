---
title: "循环路径 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Looping functoids, paths
- maps, conditional looping
ms.assetid: 4612dc2d-2c39-427d-88ac-65f9e85873c7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69e7d1c092ee5ca34b8c2ef3f309eff6c44b271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="loop-paths"></a>循环路径
如果其最大出现次数属性大于 1 就循环架构中的元素。 源架构中的循环元素和目标架构中的循环元素之间绘制的链接时发生循环路径。  
  
## <a name="configuring-a-loop-path"></a>配置循环路径  
 创建循环路径时，BizTalk 映射程序自动处理循环记录。  
  
 通过将源架构的循环记录中的字段链接到目标架构的循环记录中的字段，可以在映射中配置循环路径。 下图显示的是仅将食品调查记录复制到主地址列表的映射。  
  
 ![映射用法循环路径。] (../core/media/correct-loop-path-map.gif "correct_loop_path_map")  
循环路径映射  
  
## <a name="multiple-loop-paths"></a>多个循环路径  
 如果将包含于两个或多个循环记录中的字段链接到包含于单个循环记录中的字段，则会形成多个循环路径。 下图显示的是尝试将两个不同调查中收集的地址合并为单个主地址列表。  
  
 ![具有多个循环路径映射](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")  
具有多个循环路径的映射（不正确）  
  
 此映射将不会产生预期的结果。 当映射器在编译过程中遇到多个循环路径时，它将生成一条警告，并默认选择第一个循环路径。 若要将两个不同地址组合到单个主地址列表中，使用**循环**functoid 以下地图中所示。  
  
 ![映射的循环 functoid 用法。] (../core/media/loopingfunctoid.gif "loopingfunctoid")  
“循环”Functoid 映射（正确）  
  
 **循环**functoid 应使用而不是在以下情况中的多个循环路径：  
  
1.  当映射器在多个循环路径方案中未产生所期望的输出结果时。  
  
2.  要将输入实例消息中的多个重复结构合并为输出实例消息中的单个重复结构。  
  
3.  要通过将单个记录映射到多个记录将平面架构转换为分层架构。 将平面架构转换为 Microsoft Commerce Server 目录时通常会执行此操作。  
  
## <a name="see-also"></a>另请参阅  
 [如何添加循环到图 Functoid](../core/how-to-add-looping-functoids-to-a-map.md)   
 [循环 Functoid](../core/looping-functoid.md)