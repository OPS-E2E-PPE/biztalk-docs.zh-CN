---
title: 如何获取活动时段的持续时间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], time intervals
- managing [BAM], time intervals
- Get-ActivityWindow command [BAM]
ms.assetid: d70f6767-f6f7-4ecf-ad9d-4a9d8c76edea
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cd175c4bc4f96a9717371ad3fe72433231cbc44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337641"
---
# <a name="how-to-get-the-duration-on-an-activity-window"></a>如何获取活动时段的持续时间
管理员使用**get activitywindow**命令来获取指定活动的持续时间。 该命令返回持续时间和持续时间单位所依据的单位的长度。  
  
### <a name="to-get-the-duration-on-an-activity"></a>若要获取活动的持续时间  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 键入 bm get activitywindow-活动：\<活动名称\>。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何设置活动时段的持续时间](../core/how-to-set-the-duration-on-an-activity-window.md)