---
title: "如何禁用 BAM 主导入数据库引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc9afef7bdcfad84f105abda158c5ed5c6461619
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a>如何禁用 BAM 主导入数据库引用
管理员使用**禁用引用**命令以禁用对指定的 BAM 主导入数据库的引用。  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a>禁用对 BAM 主导入数据库的引用  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  在命令行提示符下键入以下内容： **bm 禁用引用 TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<服务器\> ][-数据库：\<数据库\>]**，其中 **\<** *目标服务器* **\>** 由在其上通过将指定的目标 BAM 主导入数据库的 SQL server 的名称替换\<*目标数据库*\>驻留。 按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)