---
title: 错误-索引 Functoid 具有索引太多 |Microsoft Docs
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
ms.openlocfilehash: 800d8ca920dac64ee2d9c603bfcb949188824764
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348141"
---
# <a name="error---index-functoid-has-too-many-indexes"></a>错误-索引 Functoid 具有索引太多
**错误代码**  
  
 btm1016  
  
 **说明**  
  
 所指示**索引**functoid 具有太多的索引输入的参数指定。 索引输入参数数目不能超过的祖先循环**记录**节点内的**字段**节点指定为嵌套的第一个输入的参数。  
  
 **用户执行任何操作**  
  
 选择所指示**索引**functoid，单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框中，删除多余的索引输入参数，通过选择并单击![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。