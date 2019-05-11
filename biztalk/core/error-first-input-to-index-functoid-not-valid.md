---
title: 错误-第一个输入无效的索引 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToIndexNotValid
ms.assetid: f7dbe9cc-9cfa-4fc7-af3e-1241cb2b50a9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6746912273d72df958c7df5e8f092aeb8f490ecb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388880"
---
# <a name="error---first-input-to-index-functoid-not-valid"></a>错误-第一个输入无效的索引 Functoid
**错误代码**  
  
 btm1015  
  
 **说明**  
  
 所指示的第一个输入的参数**索引**functoid 不是来自**字段**中的循环节点**记录**源架构中的节点。  
  
 **用户执行任何操作**  
  
 创建相应的输入的链接： 将之间**字段**节点内的循环**记录**中的源架构和所指示的节点**索引**functoid。 可能有必要，打开**配置\<Functoid\> Functoid**通过选择所指示的对话框**索引**functoid，然后单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]为了确保新创建的链接是所指示的第一个输入的参数属性窗口**索引**functoid。