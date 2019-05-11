---
title: 如何列出对 BAM 基础结构的更改 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bb796c7572e00c0a66cf89eb61035a46ac361c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336880"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a>如何列出对 BAM 基础结构的更改
管理员使用**get 更改**列出有关已部署的 BAM 定义的当前信息，BAM 管理实用程序的命令。 您还可以使用 get-changes 命令列出当前 BAM 主导入数据库中的部署项目。  
  
 这些信息包括成功的部署和取消部署的服务、 BAM 定义文件的名称、 BAM 配置文件的名称、 所有活动和视图的定义文件，并应用了更改的用户帐户与关联的名称。 Get-changes 列表显示了部署和定义删除及其关联的标识号。  
  
### <a name="to-list-changes-to-the-bam-definition"></a>列出对 BAM 定义的更改  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 类型**bm 获取更改。**  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)