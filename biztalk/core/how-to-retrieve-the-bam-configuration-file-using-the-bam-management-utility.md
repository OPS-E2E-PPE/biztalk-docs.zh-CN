---
title: 如何检索 BAM 配置文件使用 BAM 管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80974231b839225652721e8c64aaf35a0f1369f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384080"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>如何检索 BAM 配置文件使用 BAM 管理实用程序
管理员和开发人员可以使用 BAM 管理实用程序来检索 BAM 基础结构的当前配置。 可以使用检索到的配置将 BAM 安装迁移到新服务器或可以修改并用于更新现有 BAM 安装。  
  
## <a name="prerequisites"></a>先决条件  
 在本主题中执行该过程的先决条件如下：  
  
-   配置的 BAM 数据库  
  
-   读取 BAM 主导入数据库的权限  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>若要检索 BAM 配置文件使用 BAM 管理实用程序  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 在命令行提示符下键入以下内容： **bm 获取配置-FileName:\<输出文件\>**，其中\<*输出文件*\>将替换为BAM 配置文件的名称。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)