---
title: "错误-第一个输入表提取程序 functoid 无效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d501c18bf104a0f538ef90d10510e7d9ec0f02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a>错误-第一个输入表提取程序 functoid 无效
**错误代码**  
  
 btm1019  
  
 **说明**  
  
 第一个输入的参数指示**表提取程序**functoid 不是从一个链接**表循环**functoid，根据需要。  
  
 **用户执行任何操作**  
  
 指示之间创建链接**表提取程序**functoid 适当**表循环**通过将其拖放到另 functoid。 在映射网格页中，“表提取程序”functoid 必须位于“表循环”functoid 的右侧。 此外，使用**配置\<Functoid\> Functoid**对话框框中，确保新创建的链接是为指示的第一个输入的参数**表提取程序**functoid。