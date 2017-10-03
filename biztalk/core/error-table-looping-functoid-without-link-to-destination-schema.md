---
title: "错误-循环 Functoid 而无需链接到目标架构的表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329e6670288f05382acf0ea014ba9ae84c4cb645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a>错误-循环 Functoid 而无需链接到目标架构的表
**错误代码**  
  
 btm1077  
  
 **说明**  
  
 与大多数 functoid 不同**表循环**functoid 具有多个输出。 除这些输出之一必须连接为独立的实例的第一个输入参数**表提取程序**functoid。 剩余的输出必须连接到**记录**目标架构中的节点 （带有适当的重复设置）。 该错误发生时这后者从输出链接**表循环**functoid 没有。  
  
 **用户执行任何操作**  
  
 拖动指示**表循环**记录为相应**记录**目标架构创建缺少链接中的节点。