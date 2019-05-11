---
title: 如何从警报删除订户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- managing [BAM], deleting alert subscibers
- alerts, subscribers
ms.assetid: d5571863-26e3-4c1b-991f-538cd1fef347
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc00662ce082721ee8c6d385a5c83cd105d0b83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335003"
---
# <a name="how-to-remove-subscribers-from-an-alert"></a>如何从警报删除订户
管理员使用**删除订阅**命令从警报作为订阅服务器中删除指定的用户。  
  
### <a name="to-remove-subscribers-from-an-alert"></a>若要从警报删除订户  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 类型**bm 删除订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何向警报添加订户](../core/how-to-add-subscribers-to-an-alert.md)