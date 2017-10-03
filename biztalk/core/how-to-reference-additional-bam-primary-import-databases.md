---
title: "如何引用其他 BAM 主导入数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be973777fda6fad83b4ed6c672b68969cdde5919
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a>如何引用其他 BAM 主导入数据库
管理员使用**启用引用**命令以引用其他 BAM 主导入数据库。 引用多个 BAM 主导入数据库可更有效地查看分布式 BAM 活动。  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a>启用对其他 BAM 主导入数据库的引用  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  在命令行提示符下键入以下内容： **bm 启用引用 TargetServer:\<目标服务器 >-TargetDatabase:\<目标数据库 >**，其中\<*目标服务器*> 替换为在其上通过将指定的目标 BAM 主导入数据库的 SQL server 名称\<目标数据库 > 驻留。 按 Enter。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)