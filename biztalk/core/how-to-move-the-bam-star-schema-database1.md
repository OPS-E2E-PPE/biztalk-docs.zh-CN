---
title: "如何移动 BAM 星型架构 Database1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Star Schema database [BAM], migrating
- migrating, Star Schema database [BAM]
ms.assetid: b4a5f8fc-0dc4-4987-b96f-ecd49bd4dba3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6661a9ae315988a5348198fa463e24ea508cf50f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-star-schema-database"></a>如何移动 BAM 星型架构数据库
您可以使用此过程将 BAM 星型架构数据库移到其他服务器。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-move-the-bam-star-schema-database"></a>移动 BAM 星型架构数据库  
  
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
  
2.  有关如何将旧的服务器上备份数据库按照 SQL Server 联机丛书中的说明。  
  
3.  将 BAM 星型架构数据库复制到新的 SQL Server 中。  
  
4.  按照如何还原新服务器上的数据库上的 SQL Server 联机丛书中的说明进行操作。  
  
5.  编辑 BAMConfiguration.xml 文件，将 StarSchemaDatabase DeploymentUnit 部分中的 ServerName 更改为新服务器名称。  
  
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
  
10. 按照以下步骤，更新 SQL Connection 2 以更改所有 BAM 分析 DTS 包（带有“BAM_AN_”前缀）中的服务器名称和数据库名称：  
  
    1.  使用 SQL Server Management Studio 打开 BAM 的宿主服务器。  
  
    2.  打开**Data Transformation Services**文件夹。  
  
    3.  打开**本地包**文件夹。  
  
    4.  打开 DTS 包，然后双击**连接 2**来打开连接。  
  
    5.  在下拉框中选择新的服务器名称和数据库名称。  
  
11. 按照以下步骤更新 BAM 分析数据库中的数据源：  
  
    1.  使用 SQL Server 分析管理器，打开 BAM 分析数据库的宿主服务器。  
  
    2.  打开**数据源**文件夹。  
  
    3.  右键单击该多维数据集，数据源，然后单击**编辑**。  
  
    4.  上**连接**选项卡上，键入新的服务器名称和 BAM 星型架构数据库，数据库名称，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [将 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)