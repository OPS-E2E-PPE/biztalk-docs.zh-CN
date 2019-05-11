---
title: 错误-索引 Functoid 具有任何索引 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74355e4593d542d394cf5408842ed22f37da099f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388817"
---
# <a name="error---index-functoid-has-no-index"></a>错误-索引 Functoid 具有没有索引
**错误代码**  
  
 btm1014  
  
 **说明**  
  
 提供了无索引值为所指示**索引**functoid。  
  
 **用户执行任何操作**  
  
 为所指示提供适当数量的索引输入参数**索引**functoid，其中的循环数确定适当数量**记录**在其中的节点**字段**嵌套源架构中的节点。 若要创建的索引输入的参数，选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口，然后使用![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")按钮**配置\<Functoid\> Functoid**对话框可以添加一个或多个常数输入的参数，其中第一个代表直接父级中的索引循环**记录**节点，并随后的索引输入参数代表较远的祖先循环**记录**节点。