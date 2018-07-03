---
title: 如何计算冻结 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db413cfef1e49f1f3177d8a9f578c94f5a2a1a28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998142"
---
# <a name="how-to-calculate-dehydration"></a>如何计算冻结
若要计算冻结，则需要使用已配置的属性和某些运行时值。 下面的示例演示如何计算假设的冻结方案。  
  
### <a name="to-calculate-dehydration"></a>计算冻结  
  
1. 让 alpha 表示一个介于 0 和 1 之间的因子，以测量内存使用状况。  在实际操作中，alpha 有 3 个不同的部分分别与 3 个内存阻止标准（冻结属性）对应；在本示例中，我们将它们分别表示为 alpha(virtual)、alpha(private) 和 alpha(physical)。 定义以下内容：  
  
   ```  
   IF ActualPrivateBytes < OptimalUsage  
      alpha(private) = 1  
   ELSE IF ActualPrivateBytes > MaximalUsage  
      alpha(private) = 0  
   ELSE  
      alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
   ```  
  
   > [!NOTE]
   >  OptimalUsage 和 MaximalUsage 具有每个冻结属性的默认值。 可以在 BTSNTSvc.exe.config 文件中更改这些值。 有关详细信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。  
  
2. 用同样的方法定义其他 alpha 成分。 定义以下内容：  
  
   ```  
   alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
   where alpha(…) = 1 whenever IsActive=false for that given memory unit  
   ```  
  
3. 然后定义 TestThreshold（以秒为单位定义 TestThreshold、MinThreshold、MaxThreshold）：  
  
   ```  
   TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
   ```  
  
   > [!NOTE]
   >  MinThreshold 默认值 = 1。 MaxThreshold 默认值 = 1800年。 可以在 BTSNTSvc.exe.config 文件中更改这些值。 有关详细信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。  
  
4. 然后定义 TimeBlocked 和 EstimatedTime：  
  
   -   TimeBlocked = 我们等待满足此订阅的实际时间  
  
   -   EstimatedTime = 此业务流程保持空闲的估计时间（例如，侦听的剩余超时）  
  
   是否冻结取决于下面布尔值条件的结果（true = 冻结）：  
  
-   冻结 = (EstimatedTime > TestThreshold OR TimeBlocked > (2* TestThreshold))  
  
> [!NOTE]
>  估计时间是至延迟结束的剩余时间（如果延迟 5 分钟，过去了 2 分钟，则 TimeBlocked=120 秒，EstimatedTime=180 秒）。  
  
## <a name="see-also"></a>请参阅  
 [冻结默认属性](../core/dehydration-default-properties.md)   
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)