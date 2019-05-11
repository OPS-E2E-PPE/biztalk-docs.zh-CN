---
title: 如何移动 BAM 分析数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Analysis database [BAM]
- Analysis database [BAM], migrating
ms.assetid: b0320273-4840-4573-bb82-bba95021535e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9f0afd5c8bbd06786c07b84dd465f97cbb1559d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384515"
---
# <a name="how-to-move-the-bam-analysis-database"></a>如何移动 BAM 分析数据库
可以使用此过程将 BAM 分析数据库移到另一台服务器。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
### <a name="to-move-the-bam-analysis-database"></a>移动 BAM 分析数据库  
  
1. 获取用于还原 BAM 的.xml 文件的副本：  
  
   1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2. 在命令提示符处，导航到以下目录：  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪  
  
   3. 在命令提示符下，键入：  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
2. 有关如何在旧服务器上备份数据库按照 SQL Server 联机丛书中的说明。  
  
3. 将 BAM 分析数据库复制到新的 SQL Server。  
  
4. 有关如何还原新服务器上的数据库，请按照 SQL Server 联机丛书中的说明进行操作。  
  
5. 编辑 BAMConfiguration.xml 文件，并将 AnalysisDatabase DeploymentUnit 部分中的 ServerName 更改为新的服务器名称。  
  
6. 保存并关闭 BAMConfiguration.xml 文件。  
  
7. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
8. 在命令提示符处，导航到以下目录：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪  
  
9. 在命令提示符下，键入：  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [移动 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)