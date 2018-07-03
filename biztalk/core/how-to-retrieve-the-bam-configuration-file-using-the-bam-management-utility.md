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
ms.openlocfilehash: 4277e6b088ed136021b898e26204a63dc782a895
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008510"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>如何检索 BAM 配置文件使用 BAM 管理实用程序
管理员和开发人员可以使用 BAM 管理实用程序来检索 BAM 基础结构的当前配置。 检索的配置可以用来将 BAM 安装迁移到新的服务器，也可以对该配置进行修改并用于更新现有的 BAM 安装。  
  
## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中的过程的前提条件：  
  
-   已配置的 BAM 数据库  
  
-   读取 BAM 主导入数据库的权限  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>使用 BAM 管理实用程序检索 BAM 配置文件  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3. 在命令行提示符下键入以下内容： **bm 获取配置-FileName:\<输出文件\>**，其中\<*输出文件*\>将替换为BAM 配置文件的名称。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)