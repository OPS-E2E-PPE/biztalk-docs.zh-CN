---
title: 错误-第二个表提取程序 Functoid 的输入不有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c53e84e62422a70214a4cfd90979de85538e158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388439"
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a>错误-第二个表提取程序 Functoid 的输入不有效
**错误代码**  
  
 btm1073  
  
 **说明**  
  
 第二个输入参数的相关**表提取程序**functoid 不是有效。 此参数必须是一个正整数常量，它指示表循环网格为配置中的有效列**表循环**由第一个输入参数指示的 functoid。  
  
 **用户执行任何操作**  
  
 确保相关的输入的参数**表提取程序**functoid，在通过访问其**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。  
  
|表提取程序 functoid 输入参数编号|Description|  
|-----------------------------------------------------|-----------------|  
|1|从链接**表循环**functoid 从中**表提取程序**functoid 将提取列数据，由其第二个参数。|  
|2|通过配置的数据表中的有效列数**表循环网格**的属性**表循环**functoid 指定的第一个输入参数。|