---
title: 示例冻结计算 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 025d83e8a7bd6c5a3c324bd5dae8354ac43321ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393904"
---
# <a name="sample-dehydration-calculation"></a>示例冻结计算
下面是示例计算，使用专用字节数，以确定将冻结 BizTalk 的示例。 它使用默认配置值和一些示例运行时的值。  
  
 假定冻结属性的以下值：  
  
- **TimeBlocked** = 60 （示例时间以秒为单位）  
  
- **WaitingHistory** = 90 （示例等待历史记录以秒为单位）  
  
- **ActualPrivateBytes** = 250 （专用字节数的示例值）  
  
- **OptimalUsage** = 50 （默认配置值）  
  
- **MaximalUsage** = 350 （默认配置值）  
  
  由于**ActualPrivateBytes**之间**OptimalUsage**并**MaximalUsage**，所以 alpha 计算为：  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 然后计算**TestThreshold** ，如下所示：  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 和最后，决定冻结：  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 使用此示例中，可以确定，该业务流程将不会冻结这一次。