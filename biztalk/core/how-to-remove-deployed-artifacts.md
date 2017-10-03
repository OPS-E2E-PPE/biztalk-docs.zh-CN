---
title: "如何删除已部署的项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2a134e41c8f94c875498db03866d16a45bb9bc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-deployed-artifacts"></a>如何删除已部署的项目
管理员使用**删除所有**命令，以删除部署 BAM 主导入数据库中的项目。 所提供的 BAM 定义为 XML 文件或 Excel 工作簿，其中包含有关要删除的项目的信息。  
  
### <a name="to-remove-deployed-artifacts"></a>删除已部署的项目  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  类型**bm 删除全部-DefinitionFile:\<def 文件 >**。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [如何将一个 BAM 项目添加到应用程序](../core/how-to-add-a-bam-artifact-to-an-application.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)