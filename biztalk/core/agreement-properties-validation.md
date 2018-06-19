---
title: 协议属性验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d565c26-37ef-4aee-aebb-3152880242a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c01ec281005cbeaffda6dcd2349c1153a531b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229869"
---
# <a name="agreement-properties-validation"></a>协议属性验证
协议属性包括对交换、组或事务集的重复控制编号的检查。 只有在协议属性中启用这些验证，EDI 接收管道才会执行这些验证。 这些验证包括：  
  
-   检查重复的交换控制编号（X12 中的 ISA13 或 EDIFACT 中的 UNB5）。 可以输入一个时间值（单位：天）来为此检查设置有效的时间范围。  
  
-   检查交换中的重复组控制编号（X12 中的 GS6 或 EDIFACT 中的 UNG5）  
  
-   检查功能组中的重复事务集控制编号（X12 中的 ST2 或 EDIFACT 中的 UNH1）  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)