---
title: 协议属性验证 |Microsoft Docs
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
ms.openlocfilehash: 38f03d5d504210d270e8892965bffa238ee49496
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359381"
---
# <a name="agreement-properties-validation"></a>协议属性验证
协议属性包括对交换、组或事务集的重复控制编号的检查。 只有在协议属性中启用这些验证，EDI 接收管道才会执行这些验证。 这些验证包括：  
  
-   检查重复的交换控制编号（X12 中的 ISA13 或 EDIFACT 中的 UNB5）。 可以输入一个时间值（单位：天）来为此检查设置有效的时间范围。  
  
-   检查交换中的重复组控制编号（X12 中的 GS6 或 EDIFACT 中的 UNG5）  
  
-   检查功能组中的重复事务集控制编号（X12 中的 ST2 或 EDIFACT 中的 UNH1）  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)