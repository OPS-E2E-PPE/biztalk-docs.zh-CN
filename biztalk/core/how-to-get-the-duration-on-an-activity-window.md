---
title: "如何在非活动窗口上获取持续时间 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], time intervals
- managing [BAM], time intervals
- Get-ActivityWindow command [BAM]
ms.assetid: d70f6767-f6f7-4ecf-ad9d-4a9d8c76edea
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbef138603421a46edd4b2d17a5123116cece6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-get-the-duration-on-an-activity-window"></a>如何获取活动时段的持续时间
管理员使用**get activitywindow**命令来获取指定的活动的持续时间。 该命令返回持续时间的长度和度量单位。  
  
### <a name="to-get-the-duration-on-an-activity"></a>获取活动的持续时间  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  键入 bm get activitywindow 的活动：\<活动名称 >。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)   
 [如何在非活动窗口上设置的持续时间](../core/how-to-set-the-duration-on-an-activity-window.md)