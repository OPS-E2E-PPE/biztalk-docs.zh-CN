---
title: 如何设置 RTA 时段的持续时间 |Microsoft Docs
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
- Set-RTAWindow command [BAM]
- managing [BAM], time intervals
ms.assetid: 3042c3f5-be0f-48fb-9831-daa4868b90fe
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b090f8b21c58b6e73435c880effd6fb6597b8371
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383885"
---
# <a name="how-to-set-the-duration-on-an-rta-window"></a>如何设置 RTA 时段的持续时间
管理员使用**集 rtawindow**命令以设置指定实时聚合 (RTA) 的持续时间。  
  
### <a name="to-set-the-duration-on-an-aggregation"></a>若要设置聚合的持续时间  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。 按 **Enter**。  
  
3. 类型**bm 集 rtawindow 的视图：\<视图名称\>的活动：\<活动名称\>-名称：\<RTA 名称\>-TimeLength:\<整数\>-时间单位： 天&#124;小时&#124;分钟**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何获取 RTA 时段的持续时间](../core/how-to-get-the-duration-on-an-rta-window.md)