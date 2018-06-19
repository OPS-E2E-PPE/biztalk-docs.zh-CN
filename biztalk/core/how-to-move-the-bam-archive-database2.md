---
title: 如何移动 BAM 存档 Database2 |Microsoft 文档
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
ms.openlocfilehash: 4398e155168a903d39f3fbd1c9fd8f1421862cc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253989"
---
# <a name="how-to-move-the-bam-archive-database"></a>如何移动 BAM 存档数据库
您可以使用此过程将 BAM 存档数据库移到其他服务器。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-move-the-bam-archive-database"></a>移动 BAM 存档数据库  
  
1.  获取用于还原 BAM 的 .xml 文件的副本：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，导航到以下目录：  
  
         [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
    3.  在命令提示符下，键入：  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
2.  按照 SQL Server 联机丛书中的说明，以将旧的服务器上备份数据库。  
  
3.  将 BAM 存档数据库复制到新的 SQL Server 中。  
  
4.  按照 SQL Server 联机丛书中的说明还原新服务器上的数据库。  
  
5.  编辑 BAMConfiguration.xml 文件，将 ArchivingDatabase DeploymentUnit 部分中的 ServerName 更改为新服务器名称。  
  
6.  保存并关闭 BAMConfiguration.xml 文件。  
  
7.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
8.  在命令提示符下，导航到以下目录：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
9. 在命令提示符下，键入：  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [将 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)