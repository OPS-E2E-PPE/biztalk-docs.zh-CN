---
title: 错误-第二个表循环 Functoid 的输入无效 |Microsoft Docs
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
ms.openlocfilehash: 24ab38e947667e894445399e1916fe9e0a3b26fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346919"
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a>错误-第二个表循环 Functoid 的输入无效
**错误代码**  
  
 btm1072  
  
 **说明**  
  
 第二个输入参数的相关**表循环**functoid 不是有效。 此参数必须是正整数，用于指示关联表循环网格中的列数。  
  
 **用户执行任何操作**  
  
 确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。  
  
|表循环 functoid 输入参数编号|Description|  
|---------------------------------------------------|-----------------|  
|1|输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。|  
|2|通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。|  
|3 – 100|常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。|