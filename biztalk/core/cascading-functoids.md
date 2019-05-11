---
title: 级联 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Cascading
- Cascading functoids
ms.assetid: 03c46e7b-be1c-475e-b68b-f9d1d7732fce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020ff5eeb4bed7e5f1c6a09b1757300f2db525e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357610"
---
# <a name="cascading-functoids"></a>级联 Functoid
如果某个 functoid 在链接到目标架构中的记录或字段之前先链接到其他 functoid，此时称为对 Functoid 进行级联。 例如，可以创建如下级联 functoid，其中两个串连的字符串产生第三个字符串来填充到目标架构的字段中。  
  
 在对 functoid 进行级联时，可以在网格页中创建多个连续的转换。 虽然对可以在一页中级联的 functoid 数量没有限制，但仍需谨慎使用级联。 复杂的级联会增加将输入实例消息转换为输出实例消息的时间，从而显著降低运行时的性能。  
  
## <a name="see-also"></a>请参阅  
 [映射中的 Functoid](../core/functoids-in-maps.md)   
 [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)