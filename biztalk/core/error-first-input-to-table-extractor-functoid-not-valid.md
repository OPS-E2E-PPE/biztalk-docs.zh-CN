---
title: 错误-表提取程序 Functoid 不是有效第一个输入 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b96e673f33bfa7478b633c8254a62d81335cd61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348312"
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a>错误-第一个输入无效的表提取程序 Functoid
**错误代码**  
  
 btm1019  
  
 **说明**  
  
 所指示的第一个输入的参数**表提取程序**functoid 不是从链接**表循环**functoid，根据需要。  
  
 **用户执行任何操作**  
  
 创建之间所指示的链接**表提取程序**functoid 和相应**表循环**通过将其拖放到其他 functoid。 以前的 functoid 必须位于右侧的后一种 functoid 在映射网格页。 此外，使用**配置\<Functoid\> Functoid**对话框框中，确保新创建的链接是所指示的第一个输入的参数**表提取程序**functoid。