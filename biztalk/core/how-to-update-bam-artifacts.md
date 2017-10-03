---
title: "如何更新 BAM 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Update-All command [BAM]
- managing [BAM definitions], updating artifacts
- updating, artifacts
- artifacts, updating
ms.assetid: bc28159e-df51-499b-bd51-7b682b849891
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e377a455089127c9dc219846ec3f66e3322924cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-bam-artifacts"></a>如何更新 BAM 项目
管理员使用**更新所有**命令以更新在 BAM 主导入数据库中部署的项目。 提供的 BAM 定义是包含有关要更新项目的信息的 XML 文件或 Excel 工作簿。  
  
### <a name="to-update-bam-artifacts"></a>更新 BAM 项目  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  类型**bm 更新所有-DefinitionFile:\<def 文件 >**。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)