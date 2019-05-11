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
ms.openlocfilehash: 19c05eff239a24eeb092f1531691d787fcba67ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387050"
---
# <a name="how-to-calculate-dehydration"></a>如何计算冻结
若要计算冻结，使用已配置的属性和某些运行时的值。 下面的示例演示了如何计算假设的冻结方案。  
  
### <a name="to-calculate-dehydration"></a>若要计算冻结  
  
1. 让 alpha 表示介于 0 和 1 的测量内存使用状况之间的因素。  在实践中，alpha 有一个组件，这三个内存阻止标准 （冻结属性）;在此示例中我们将它们分别表示为 alpha(virtual)、 alpha （private） 和 alpha （physical）。 定义以下：  
  
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
  
2. 类似地定义其他 alpha 组件。 定义以下：  
  
   ```  
   alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
   where alpha(…) = 1 whenever IsActive=false for that given memory unit  
   ```  
  
3. 接着定义 TestThreshold （TestThreshold、 MinThreshold、 maxthreshold 定义以秒为单位）：  
  
   ```  
   TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
   ```  
  
   > [!NOTE]
   >  MinThreshold 默认值 = 1。 MaxThreshold 默认值 = 1800年。 可以在 BTSNTSvc.exe.config 文件中更改这些值。 有关详细信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。  
  
4. 然后定义 TimeBlocked 和 EstimatedTime:  
  
   -   TimeBlocked = 我们等待满足此订阅的实际时间  
  
   -   EstimatedTime = 此业务流程将保持空闲状态 （例如剩余超时，侦听） 的估计的时间  
  
   决定是否冻结取决于是以下布尔条件的结果 (true = 冻结):  
  
-   冻结 = (EstimatedTime > TestThreshold OR TimeBlocked > (2 * TestThreshold))  
  
> [!NOTE]
>  估计时间是延迟结束前所剩余的时间 (如果延迟 5 分钟到 2 分钟过后，TimeBlocked = 120 秒，EstimatedTime = 180 秒)。  
  
## <a name="see-also"></a>请参阅  
 [冻结默认属性](../core/dehydration-default-properties.md)   
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)