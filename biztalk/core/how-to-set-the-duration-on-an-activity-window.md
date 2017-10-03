---
title: "如何在非活动窗口上设置的持续时间 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Set-ActivityWindow command [BAM]
- activities [BAM], time intervals
- managing [BAM], time intervals
ms.assetid: e39c315e-f215-4f81-9774-cf7aedf6ba33
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50b4aaa0187c10038dde907fa8b5fa8c595d2847
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-duration-on-an-activity-window"></a>如何设置活动时段的持续时间
管理员使用**集 activitywindow**命令以设置指定的活动的持续时间。  
  
### <a name="to-set-the-duration-on-an-activity"></a>设置活动的持续时间  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。 按 **Enter**。  
  
3.  类型**bm 集 activitywindow 的活动：\<活动名称 >-TimeLength:\<整数 >-时间单位： 月 &#124; 天 &#124;小时 &#124;分钟**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)   
 [如何在非活动窗口上获取持续时间](../core/how-to-get-the-duration-on-an-activity-window.md)