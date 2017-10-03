---
title: "如何删除 BAM 视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d8930fb4e3f2014945b743b15da4dbdfff3451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-bam-views"></a>如何删除 BAM 视图
管理员使用**删除视图**命令从 BAM 主导入数据库中删除视图。  
  
> [!NOTE]
>  在删除视图时，还会自动删除为该视图定义的所有警报。  
  
### <a name="to-remove-bam-views"></a>若要删除 BAM 视图  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到的跟踪文件夹中，通过键入**C:\Program Files\Microsoft BizTalk Server 2009\Tracking**在命令提示符。 按 **Enter**。  
  
3.  类型**bm 删除视图的名称：\<视图名称 >**。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)   
 [如何删除 BAM 警报](../core/how-to-remove-bam-alerts.md)