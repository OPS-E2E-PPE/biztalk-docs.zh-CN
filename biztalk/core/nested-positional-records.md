---
title: 嵌套位置记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e205e9d-f740-4177-b45a-5e1baadae99a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eddb7925a34e79c1da45a6ec6e2670f9632695
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323617"
---
# <a name="nested-positional-records"></a>嵌套位置记录
如果允许嵌套位置记录**Max Occurs**的子记录的属性设置为一个正整数。 字段自动计算应能够处理新的深度。 但是，没有对此行为的方式的修改。 具体而言，由于可能存在空分隔符，自动计算的字段位置将函数仅当满足以下条件之一：  
  
- 所选的节点具有中缀分隔的父级。  
  
- 所选的节点具有指定的起始位置。  
  
  请注意，嵌套位置记录和位置记录的父级是分隔符为空的分隔的容器之间的区别。 对于真正按位置嵌套的结构不能有任何多义性确定其长度。 例如，分隔的循环节点可以包含出现 0 到 N 次的重复位置记录。 但是，该循环节点本身为位置，并且可能还包含字段作为对等互连到重复的位置记录重复位置记录必须具有确定性的匹配项 （正整数）。  
  
## <a name="see-also"></a>请参阅  
 [位置记录注意事项](../core/positional-record-considerations.md)