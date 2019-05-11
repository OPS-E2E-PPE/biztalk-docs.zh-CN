---
title: 错误-第一个输入到循环 Functoid 不是有效的表 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ecfb5402cc4c544acc208654cd7fe7459de985
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389291"
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a>错误-第一个输入到循环 Functoid 不是有效的表
**错误代码**  
  
 btm1071  
  
 **说明**  
  
 第一个输入的参数的相关**表循环**functoid 不是有效。 此参数必须是来自源架构中的节点的链接，输入的实例消息中的相应元素的出现次数将控制的一组关联的次数**表提取程序**functoid将在运行时调用。  
  
 **用户执行任何操作**  
  
 确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。  
  
|表循环 functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。|  
|2|通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。|