---
title: 错误-表循环 Functoid 不是有效的输入参数个数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68cc75282c7dd18925f39b339521d8ecb41911b9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530727"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a>错误-表循环 Functoid 不是有效的输入参数个数
**错误代码**  
  
 btm1070  
  
 **说明**  
  
 指定相关的输入参数的数目**表循环**functoid 不是有效。  
  
 **用户执行任何操作**  
  
 确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。  
  
|表循环 functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。|  
|2|通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。|