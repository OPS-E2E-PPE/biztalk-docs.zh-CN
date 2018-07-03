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
ms.openlocfilehash: 618d5475842a9e5844f289a7ca77e4d9a725b130
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990214"
---
# <a name="nested-positional-records"></a>嵌套位置记录
如果允许嵌套位置记录**Max Occurs**的子记录的属性设置为一个正整数。 字段自动计算应能够处理新的深度。 但是，此行为方式已修改。 具体而言，由于可能存在空分隔符，所以仅在满足以下条件之一时，字段位置的自动计算才能进行：  
  
- 选定节点具有以中缀分隔的父节点。  
  
- 选定节点具有指定的起始位置。  
  
  请注意，嵌套位置记录和其父记录为分隔容器（其中分隔符为空）的位置记录不同。 对于真正按位置嵌套的结构，确定其长度时不能有任何多义性。 例如，分隔的循环节点可以包含出现 0 到 N 次的重复的位置记录。 但是，对于本身为位置记录的循环节点，可能还包含与重复位置记录对等的字段，重复位置记录的出现次数必须是确定的（正整数）。  
  
## <a name="see-also"></a>请参阅  
 [位置记录注意事项](../core/positional-record-considerations.md)