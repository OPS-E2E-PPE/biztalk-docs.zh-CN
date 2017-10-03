---
title: "如何检索使用 BAM 管理实用工具对 BAM 配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb7dee70d3a5b8dc7226203df9f48aefe1d5fc0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>如何检索 BAM 配置文件使用 BAM 管理实用工具
管理员和开发人员可以使用 BAM 管理实用程序来检索 BAM 基础结构的当前配置。 检索的配置可以用来将 BAM 安装迁移到新的服务器，也可以对该配置进行修改并用于更新现有的 BAM 安装。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中的过程的前提条件：  
  
-   已配置的 BAM 数据库  
  
-   读取 BAM 主导入数据库的权限  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>使用 BAM 管理实用程序检索 BAM 配置文件  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  在命令行提示符下键入以下内容： **bm get-config FileName:\<输出文件 >**，其中\<*输出文件*> 替换为你 BAM 配置的名称文件。 按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)