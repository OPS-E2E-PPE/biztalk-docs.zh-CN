---
title: 错误-表循环数据无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e62678e7dc4e0aceee128cb24bc0ff34129168cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388410"
---
# <a name="error---table-looping-data-not-valid"></a>错误-表循环数据无效
**错误代码**  
  
 btm1065  
  
 **说明**  
  
 关联与相关的数据的表**表循环**functoid 不是有效的很可能是由于该 functoid 或未正确配置的表循环网格的配置不正确第二个输入参数。  
  
 **用户执行任何操作**  
  
 确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。  
  
|表循环 functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。|  
|2|通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。|  
  
 另外，请确保正确配置表循环网格中，通过**表循环网格**属性和**表循环配置**对话框。 必须将访问每个单元格选择一个常数或链接的值由关联**表提取程序**functoid。