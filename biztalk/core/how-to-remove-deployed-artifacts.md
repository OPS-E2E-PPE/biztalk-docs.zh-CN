---
title: 如何删除已部署的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7008b327564de3af2462f0fa077ca456f817584
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968230"
---
# <a name="how-to-remove-deployed-artifacts"></a>如何删除已部署的项目
管理员使用**删除全部**命令以删除 BAM 主导入数据库中部署的项目。 所提供的 BAM 定义为 XML 文件或 Excel 工作簿，其中包含有关要删除的项目的信息。  
  
### <a name="to-remove-deployed-artifacts"></a>删除已部署的项目  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3. 类型**bm 全部删除-DefinitionFile:\<def 文件\>**。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [如何向应用程序添加 BAM 项目](../core/how-to-add-a-bam-artifact-to-an-application.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)