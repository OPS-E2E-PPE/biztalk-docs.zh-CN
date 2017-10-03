---
title: "错误-为第二个输入表提取程序 Functoid 不有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5970c0bfa23cc7da33b2c041cc326987ec278e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a>错误-为第二个输入表提取程序 Functoid 不有效
**错误代码**  
  
 btm1073  
  
 **说明**  
  
 第二个输入参数相关**表提取程序**functoid 无效。 此参数必须为正整数常量，该值指示表循环为配置的网格中的有效列**表循环**functoid 指示的第一个输入参数。  
  
 **用户执行任何操作**  
  
 确保相关的输入的参数**表提取程序**functoid，如通过访问其**输入参数**属性和**配置\<Functoid >Functoid**对话框中，是下表中所示。  
  
|表提取程序 functoid 输入的参数数|Description|  
|-----------------------------------------------------|-----------------|  
|1|从链接**表循环**从此 functoid**表提取程序**functoid 将拉取列数据，由其第二个参数。|  
|2|通过配置的数据表中的有效列数**表循环网格**属性**表循环**functoid 由第一个输入参数指定。|