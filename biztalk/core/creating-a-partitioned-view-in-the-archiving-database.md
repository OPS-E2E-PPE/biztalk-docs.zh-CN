---
title: "在存档数据库中创建分区的视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f6000c95b94570b5f058073537fa926fd1651c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a>在存档数据库中创建分区的视图
在运行 BAM 数据维护程序包 (BAM_DM_`<activity name>`) 时，BAM 会将 BAM 主导入数据库的每个分区分别复制到 BAM 存档数据库的一个单独的表中。 如果分离存档数据库，然后又重新附加它进行查询，那么很难找到您要查询的数据。  
  
 您可以在 BAM 存档数据库中创建分区视图，以简化数据查找过程。 BAM 最多支持 253 个分区。 BAM 为每个活动生成一个 BAM 数据维护 DTS 程序包，该程序包将活动数据复制到 BAM 存档数据库，然后从 BAM 主导入数据库删除这些数据。 如果存档数据库在复制数据之后下一次备份之前失败，则数据将会丢失。  
  
 防止丢失数据的办法是，创建一个单独的存档程序包，该程序包首先复制所有活动的旧数据，然后备份 BAM 存档数据库，最后删除从 BAM 主导入数据库复制的那些分区。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a>在 SQL Server 2008 SP1 或 SQL Server 2008 R2 的 BAM 存档数据库中创建分区视图  
  
1.  打开 SQL Server Management Studio。  
  
2.  选择 BAM 存档数据库，然后单击**新查询**。  
  
3.  上**查询**菜单上，指向**结果到**，然后单击**结果显示为文本**。  
  
4.  将下面的 SQL 脚本复制到查询窗格中。 替换\<活动名称 > 替换为你的活动名称，并将`<view type>`使用**实例**实例查看或**关系**关系视图。  
  
    ```  
    set nocount on  
  
    declare @activityName as nvarchar(128)  
    declare @viewType as nvarchar(50)  
    set @activityName = N'<activity name>'-- Substitute your activity name here  
    set @viewType = N'<view type>'-- Substitute the view type here, either "Instances" or "Relationships"  
  
    declare @tableName nvarchar(128)  
    declare @viewName nvarchar(128)  
    declare @isFirstTable bit  
    declare @scriptLine nvarchar(300)  
  
    set @viewName = N'bam_' + @activityName + '_' + @viewType + 'View'  
    select N'SELECT Name FROM sysobjects where name = N''' + @viewName + ''' and type = ''V'''   
     + char(13) + char(10) + 'IF @@ROWCOUNT > 0 DROP VIEW ' + @viewName   
     + char(13) + char(10) + 'GO'  
  
    select 'CREATE VIEW ' +  @viewName + ' AS ' + char(13) + char(10)  
  
    declare instance_cursor cursor local for  
    select name from sysobjects   
    where name like N'bam_' + @activityName + '_' + @viewType + '_%' and type = 'U'  
  
    SET @isFirstTable = 1  
    OPEN instance_cursor  
    FETCH NEXT FROM instance_cursor INTO @tableName  
  
    WHILE @@fetch_status = 0   
    BEGIN  
  
    if @isFirstTable = 1  
    BEGIN  
    SET @scriptLine = N'SELECT * FROM [' + @tableName + ']'  
    SET @isFirstTable = 0  
    END  
    ELSE  
    SET @scriptLine = N'UNION ALL SELECT * FROM [' + @tableName + ']'  
  
    SELECT @scriptLine  
  
    FETCH NEXT FROM instance_cursor INTO @tableName  
    END  
    CLOSE instance_cursor  
    DEALLOCATE instance_cursor  
  
    select 'GO'  
    set nocount off  
    ```  
  
5.  执行查询。  
  
## <a name="see-also"></a>另请参阅  
 [BAM DTS 包](../core/bam-dts-packages.md)   
 [如何备份 BAM 分析和跟踪 Analysis Server 数据库](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)