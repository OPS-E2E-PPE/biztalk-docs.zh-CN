---
title: 如何获取 RTA 时段的持续时间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4b69ccb37e1104f78515e2974fc9ff791b45c39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385021"
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a>如何获取 RTA 时段的持续时间
管理员使用**get rtawindow**命令来获取指定实时聚合 (RTA) 的持续时间。 该命令返回持续时间和持续时间单位所依据的单位的长度。  
  
### <a name="to-get-the-duration-on-an-aggregation"></a>若要获取聚合的持续时间  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到的文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 类型**bm get rtawindow 的视图：\<视图名称\>的活动：\<活动名称\>-Rta:\<RTA 名称\>**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何设置 RTA 时段的持续时间](../core/how-to-set-the-duration-on-an-rta-window.md)