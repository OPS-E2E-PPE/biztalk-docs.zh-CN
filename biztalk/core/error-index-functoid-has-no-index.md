---
title: 错误-索引 Functoid 不具有索引 |Microsoft 文档
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
ms.openlocfilehash: 0159d308c9befc90590d281351409ba571921a53
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968435"
---
# <a name="error---index-functoid-has-no-index"></a>错误-索引 Functoid 不具有索引
**错误代码**  
  
 btm1014  
  
 **说明**  
  
 提供了无索引值的指示**索引**functoid。  
  
 **用户执行任何操作**  
  
 为指示提供适当数量的索引输入参数**索引**functoid，其中的适当数量由的循环数**记录**其中的节点**字段**嵌套源架构中的节点。 若要创建索引输入的参数，选择指定的 functoid，单击省略号 (**...**) 与关联的按钮**输入参数**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口，然后使用![ ] (../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")按钮内**配置\<Functoid\> Functoid**对话框中添加一个或多个常量输入的参数，其中第一个到直接父表示索引循环**记录**节点和后续索引输入参数表示较远的祖先循环**记录**节点。