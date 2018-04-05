---
title: 错误-为第二个输入表不是有效循环 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb321a26300a514357225713db1b197fb828851
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a>错误-为第二个输入表不是有效循环 Functoid
**错误代码**  
  
 btm1072  
  
 **说明**  
  
 第二个输入参数相关**表循环**functoid 无效。 此参数必须是正整数，用于指示相关联的表循环网格中的列数。  
  
 **用户执行任何操作**  
  
 确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid\>Functoid**对话框中，是下表中所示。  
  
|“表循环”functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。|  
|2|通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。|