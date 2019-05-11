---
title: 如何移动 BAM 存档数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], migrating
- migrating, Archive database [BAM]
ms.assetid: 88b96dc2-8c9c-43f5-afb9-a937e05de36b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb306cd7b7115d5ed9e28577d34f84332a161eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335872"
---
# <a name="how-to-move-the-bam-archive-database"></a>如何移动 BAM 存档数据库
可以使用此过程将 BAM 存档数据库移到另一台服务器。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
### <a name="to-move-the-bam-archive-database"></a>移动 BAM 存档数据库  
  
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
  
2. 按照 SQL Server 联机丛书中的说明在旧服务器上备份数据库。  
  
3. 将 BAM 存档数据库复制到新的 SQL server。  
  
4. 按照 SQL Server 联机丛书中的说明来还原新服务器上的数据库。  
  
5. 编辑 BAMConfiguration.xml 文件，将 ArchivingDatabase DeploymentUnit 部分中的 ServerName 更改为新的服务器名称。  
  
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