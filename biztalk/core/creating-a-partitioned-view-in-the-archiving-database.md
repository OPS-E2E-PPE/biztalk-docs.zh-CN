---
title: 在存档数据库中创建分区的视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4a1b688356ca665f98903099c1acef293a21e64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354092"
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a>在存档数据库中创建分区的视图
当您运行 BAM 数据维护程序包 (BAM_DM_`<activity name>`) BAM 将每个分区中的 BAM 主导入数据库复制到 BAM 存档数据库中的单独表。 如果分离存档数据库，并重新附加它进行查询，它将很难找到您的查询的数据。  
  
 您可以在 BAM 存档数据库以简化数据查找过程中创建分区的视图。 BAM 支持最多 253 个分区。 对于每个活动，BAM 将生成一个 BAM 数据维护 DTS 包，其中将活动数据复制到 BAM 存档数据库，并将其删除从 BAM 主导入数据库。 如果存档数据库失败后将数据复制，但在下一次备份之前，数据都会丢失。  
  
 要防止数据丢失的解决方案是具有单个的存档程序包，它先将旧数据复制所有活动，然后备份 BAM 存档数据库，并最后删除从 BAM 主导入数据库复制的分区。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的 BizTalk Server Administrators 组的成员身份登录。  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a>若要在 SQL Server 2008 SP1 或 SQL Server 2008 R2 中的 BAM 存档数据库中创建分区的视图  
  
1.  打开 SQL Server Management Studio。  
  
2.  选择 BAM 存档数据库，然后单击**新查询**。  
  
3.  上**查询**菜单，依次指向**结果显示为**，然后单击**结果显示为文本**。  
  
4.  将以下 SQL 脚本复制到查询窗格。 替换\<活动名称\>与活动名称和替换`<view type>`与**实例**对于实例视图或**关系**对于关系视图。  
  
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
  
## <a name="see-also"></a>请参阅  
 [BAM DTS 包](../core/bam-dts-packages.md)   
 [如何备份 BAM 分析和跟踪分析服务器数据库](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)