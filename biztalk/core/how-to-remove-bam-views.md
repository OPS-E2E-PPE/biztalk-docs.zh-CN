---
title: 如何删除 BAM 视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bab2394ab3e2d93f9e333c9f4c58940996dd431
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334989"
---
# <a name="how-to-remove-bam-views"></a>如何删除 BAM 视图
管理员使用**删除视图**命令以从 BAM 主导入数据库中删除视图。  
  
> [!NOTE]
>  删除视图时，您还会自动删除该视图的定义的所有警报。  
  
### <a name="to-remove-bam-views"></a>若要删除 BAM 视图  
  
1.  打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  通过键入导航到跟踪文件夹**C:\Program Files\Microsoft BizTalk Server 2009\Tracking**在命令提示符处。 按 **Enter**。  
  
3.  类型**bm 删除视图的名称：\<视图名称\>**。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何删除 BAM 警报](../core/how-to-remove-bam-alerts.md)