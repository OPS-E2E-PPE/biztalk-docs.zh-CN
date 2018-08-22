---
title: 错误-索引 Functoid 有太多索引 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a22b49a921b957c0fb36f9e6b6925c991cc3cf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968939"
---
# <a name="error---index-functoid-has-too-many-indexes"></a>错误-索引 Functoid 有太多的索引
**错误代码**  
  
 btm1016  
  
 **说明**  
  
 指示**索引**functoid 有太多索引输入的参数指定。 索引输入参数的数目不能超过的祖先循环数**记录**其中的节点**字段**节点指定为嵌套的第一个输入的参数。  
  
 **用户执行任何操作**  
  
 选择指示**索引**functoid，单击省略号 (**...**) 与关联的按钮**输入参数**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框中，删除多余的索引通过选择并单击输入参数![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。