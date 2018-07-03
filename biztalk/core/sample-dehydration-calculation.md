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
ms.openlocfilehash: 77701083272da9e09c21cb05daf3c4e9764b604c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993038"
---
# <a name="sample-dehydration-calculation"></a>示例冻结计算
下面是一个计算示例，它使用专用字节来确定 BizTalk 是否将冻结计算。 它使用默认配置值以及一些示例运行时值。  
  
 假定冻结属性值如下：  
  
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
  
 最终，决定是否冻结：  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 使用此示例，您可以确定在此时将不冻结业务流程。