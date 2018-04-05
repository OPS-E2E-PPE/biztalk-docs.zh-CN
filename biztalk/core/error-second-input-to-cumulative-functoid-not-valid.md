---
title: 错误-第二个输入无效的累积 functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputToCumulativeNotValid
ms.assetid: e41a58a7-e0a2-4284-bd19-279578a8915d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0228beda57b961d515471e42760abe3ab92db54
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-to-cumulative-functoid-not-valid"></a>错误-第二个输入无效的累积 functoid
**错误代码**  
  
 btm1031  
  
 **说明**  
  
 指示**的累积**functoid 具有不是有效的第二个输入的参数。 “累计”functoid 的第二个输入参数必须是正整数，用于指示对其执行累计的源架构内部的范围。  
  
 **用户执行任何操作**  
  
 选择指示**的累积**functoid，单击省略号 (**...**) 与关联的按钮**顺序 Functoid 输入**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框框中，确保第二个输入的参数，如果有的话，是一个正整数。