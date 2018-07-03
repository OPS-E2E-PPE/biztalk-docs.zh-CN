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
ms.openlocfilehash: 237f951a4795ef6571a72989be22893d57572df9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011790"
---
# <a name="how-to-move-the-bam-analysis-database"></a>如何移动 BAM 分析数据库
可以使用此过程将 BAM 分析数据库移到另一台服务器。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-move-the-bam-analysis-database"></a>移动 BAM 分析数据库  
  
1. 获取用于还原 BAM 的 .xml 文件的副本：  
  
   1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2. 在命令提示符下，导航到以下目录：  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
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
  
8. 在命令提示符下，导航到以下目录：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
9. 在命令提示符下，键入：  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [移动 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)