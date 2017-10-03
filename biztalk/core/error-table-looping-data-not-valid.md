---
title: "错误-循环不是有效的数据的表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2997b4db8b0c1be353d4ff88166716d21059cea6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---table-looping-data-not-valid"></a>错误-循环不是有效的数据的表
**错误代码**  
  
 btm1065  
  
 **说明**  
  
 与相关的数据的表**表循环**functoid 不是有效的可能是由于配置不正确到 functoid 或配置不正确表循环网格第二个输入参数。  
  
 **用户执行任何操作**  
  
 确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid > Functoid**对话框中，是下表中所示。  
  
|“表循环”functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。|  
|2|通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。|  
  
 此外，请确保正确配置表循环网格中，如通过访问**表循环网格**属性和**表循环配置**对话框。 一个常数或链接的值必须为将访问每个单元格选择通过一个关联**表提取程序**functoid。