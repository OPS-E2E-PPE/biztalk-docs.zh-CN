---
title: 如何引用其他 BAM 主导入数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54982491ca8ce2c7ca7acd9e176a7341b2642c78
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992310"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a>如何引用其他 BAM 主导入数据库
管理员使用**启用引用**命令引用其他 BAM 主导入数据库。 引用多个 BAM 主导入数据库可更有效地查看分布式 BAM 活动。  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a>启用对其他 BAM 主导入数据库的引用  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3. 在命令行提示符下键入以下内容： **bm 启用引用-TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>**，其中\<*目标服务器*\>替换为在其通过将指定的目标 BAM 主导入数据库的 SQL server 的名称\<目标数据库\>驻留。 按 Enter。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)