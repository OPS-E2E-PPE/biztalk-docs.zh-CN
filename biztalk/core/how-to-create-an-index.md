---
title: "如何创建索引 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Create-Index command [BAM]
- indexes [BAM], creating
- indexes [BAM], aggregations
- creating, indexes [BAM]
- aggregations [BAM], indexes
ms.assetid: 456d94e6-2e84-4d12-ad38-49f9eeb103f3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1427e8ee22e2012f759817350b0e3fa8ae49cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-index"></a>如何创建索引
管理员使用**创建索引**命令以在指定的检查点的指定活动上创建索引。  
  
### <a name="to-create-an-index-on-an-activity"></a>对活动创建索引  
  
1.  从命令提示符处，浏览到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
2.  类型**bm 创建索引 IndexName:\<索引名称 >-活动：\<活动名称 >-检查点：\<checkpoint1 >**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
3.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)   
 [如何删除索引](../core/how-to-delete-an-index.md)   
 [如何获取有关聚合的索引的列表](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)