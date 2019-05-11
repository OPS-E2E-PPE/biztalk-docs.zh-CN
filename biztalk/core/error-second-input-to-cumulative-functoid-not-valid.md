---
title: 错误-第二个输入无效的累计 Functoid |Microsoft Docs
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
ms.openlocfilehash: 3ae68d06fbdadae35cef199215c1e9861b37dd19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388458"
---
# <a name="error---second-input-to-cumulative-functoid-not-valid"></a>错误-第二个输入无效的累计 Functoid
**错误代码**  
  
 btm1031  
  
 **说明**  
  
 所指示**累计**functoid 具有无效的第二个输入的参数。 累计 functoid 的第二个输入的参数必须是一个正整数，用于指示对其执行累计的源架构中的范围。  
  
 **用户执行任何操作**  
  
 选择所指示**累计**functoid，单击省略号 (**...**) 按钮与相关联**顺序 Functoid 输入**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框框中，确保第二个输入的参数，如果有的话，是一个正整数。