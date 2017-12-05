---
title: "错误-第一个输入到循环 Functoid 不是有效的表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9ebecbd92b43dd25e6ff3dde04d942b936f40d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a>错误-第一个输入到循环 Functoid 不是有效的表
**错误代码**  
  
 btm1071  
  
 **说明**  
  
 到相关的第一个输入的参数**表循环**functoid 无效。 此参数必须是来自源架构中的节点的链接-输入的实例消息中的相应元素的出现次数将控制的组的关联的次数**表提取程序**functoid将在运行时调用。  
  
 **用户执行任何操作**  
  
 确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid\>Functoid**对话框中，是下表中所示。  
  
|“表循环”functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。|  
|2|通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。|