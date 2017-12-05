---
title: "如何删除不完整的活动实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7060578c-6267-487b-8530-efa18f9431ce
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2809fd4fcc1d94a96b158ffa46c3e217084a905d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-remove-incomplete-activity-instances"></a>如何删除不完整的活动实例
在部署 BAM 定义文件时，系统会在 BAM 主导入数据库中为在该定义文件中定义的每个活动创建五个表。 这些表分别为：  
  
-   bam_`ActivityName`_Active  
  
-   bam_`ActivityName`_Completed  
  
-   bam_`ActivityName`_ActiveRelationships  
  
-   bam_`ActivityName`_CompletedRelationships  
  
-   bam_`ActivityName`_Continuations  
  
 其中，`ActivityName` 是用户已定义的活动名称。  
  
 在正常的执行操作中，不完整的数据保留在 bam_`ActivityName`_Active 表中。 如果数据具有关系和引用，则在 bam 将数据\_`ActivityName`_ActiveRelationships 表。  
  
 在跟踪使用继续符的活动期间，可能存在其活动在 BAM 数据库中尚保持未完成状态的实例。 您可以使用本主题结尾处的存储过程创建脚本创建将清除不完整记录的存储过程。  
  
 若要创建该存储过程，请通过使用 SQL Server Management 复制该脚本并对 BAM 主导入数据库执行它。 该脚本将生成名为的存储的过程**RemoveDanglingInstances**数据库中。  
  
### <a name="to-create-the-removedanglinginstances-stored-procedure"></a>创建 RemoveDanglingInstances 存储过程  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，选择 SQL server 和适当的身份验证方法，，然后单击**连接**。  
  
3.  展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。  
  
4.  单击 **“新建查询”**。  
  
5.  复制存储过程创建脚本并将其粘贴到适当的窗格中。  
  
6.  单击**执行**以运行该脚本。 生成的存储的过程可以查看存储过程的列表中，为 dbo。RemoveDanglingInstances。  
  
### <a name="to-remove-incomplete-activity-instances"></a>删除不完整的活动实例  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，选择 SQL server 和适当的身份验证方法，，然后单击**连接**。  
  
3.  展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。  
  
4.  单击 **“新建查询”**。  
  
5.  在右窗格中，键入`exec RemoveDanglingInstances`和正在执行的删除操作的相应参数。 例如，若要删除所有未完成活动实例的采购订单，键入`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`。  
  
6.  单击**执行**以运行该脚本。  
  
## <a name="removedanglinginstances-usage-examples"></a>RemoveDanglingInstances 用法示例  
 存储的过程可以收到四个参数：  
  
|参数|Description|  
|---------------|-----------------|  
|@ActivityName nvarchar(128)|指定要删除的不完整活动实例的名称。|  
|@ActivityId nvarchar(128)|（可选）指定存储过程只删除具有指定实例标识符的虚实例。|  
|@DateThreshold日期时间|（可选）指定删除活动表中早于（不是等于和早于，只是早于）给定日期的所有活动实例。|  
|@NewTableExtensionnvarchar (30)|（可选）指定存储过程通过将提供的扩展连接到现有活动表，创建三个新表。<br /><br /> 生成的表将是：<br /><br /> bam_ActivityName_Active_\<扩展\><br /><br /> bam_ActivityName_ActiveRelationships_\<扩展\><br /><br /> bam_ActivityName_Continuations_\<扩展\><br /><br /> 不完整实例将会移到新的表中，而不是从数据库中清除。<br /><br /> 如果这些表已存在，则该存储过程将重复使用它们；否则，将创建这些表。 **重要说明：**如果表已存在，存储的过程假定其架构匹配，就好像是将使用。 如果架构不匹配，则该存储过程将无法插入记录，并且取消操作也会失败。|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 删除活动表、活动关系表和继续符表中“PurchaseOrder”活动的所有活动实例。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 从“PurchaseOrder”活动的活动表、活动关系表和继续符表中只删除 ID 为“PO220567”的活动实例。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 从“PurchaseOrder”活动的活动表、活动关系表和继续符表中删除 LastModified 时间早于 2005 年 2 月 2 日的 7:27:03.533 PM 的所有活动实例。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 删除其活动 ID 为 PO220567 且其 LastModified 列早于 2005 年 2 月 2 日 7:27:03.533 PM 的实例。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 在数据库中创建以下表：  
  
 bam_PurchaseOrder_Active_Dangling  
  
 bam_PurchaseOrder_ActiveRelationships_Dangling  
  
 bam_PurchaseOrder_Continuations_Dangling  
  
 存储过程将从“PurchaseOrder”活动的活动表、活动关系表和继续符表中复制早于 2005 年 2 月 2 日的 7:27:03.533 PM 的所有未完成实例，然后将它们插入新创建的表中。 然后，将已复制的活动实例从活动表、活动关系表和继续符表中删除。  
  
## <a name="stored-procedure-creation-script"></a>存储过程创建脚本  
  
```  
EXEC sp_stored_procedures @sp_name = 'RemoveDanglingInstances'  
IF @@ROWCOUNT > 0 DROP PROCEDURE RemoveDanglingInstances  
GO  
  
CREATE PROCEDURE RemoveDanglingInstances  
    @ActivityName nvarchar(128),  
    @ActivityId nvarchar(128) = NULL,  
    @DateThreshold datetime = NULL,  
    @NewTableExtension nvarchar(30) = NULL  
AS  
    DECLARE @QueryString nvarchar(4000)  
    DECLARE @ActiveTableName sysname  
    DECLARE @ActiveRelationshipsTableName sysname  
    DECLARE @ContinuationsTableName sysname  
    DECLARE @DanglingActiveTableName sysname  
    DECLARE @DanglingActiveRelationshipsTableName sysname  
    DECLARE @DanglingContinuationsTableName sysname  
  
    SET @ActiveTableName = 'bam_' + @ActivityName + '_Active'  
    SET @ActiveRelationshipsTableName = 'bam_' + @ActivityName + '_ActiveRelationships'  
    SET @ContinuationsTableName = 'bam_' + @ActivityName + '_Continuations'  
  
    SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
    BEGIN TRAN  
  
    DECLARE @LockActivity nvarchar(128)  
    SELECT @LockActivity = ActivityName  
    FROM bam_Metadata_Activities WITH (XLOCK)  
    WHERE ActivityName = @ActivityName  
  
    EXEC sp_tables @table_name = #DanglingActivities  
    IF @@ROWCOUNT > 0 DROP TABLE #DanglingActivities  
  
    CREATE TABLE #DanglingActivities(ActivityID nvarchar(128) PRIMARY KEY)  
  
    SET @QueryString = N'INSERT INTO #DanglingActivities (ActivityID) SELECT ActivityID FROM [bam_' + @ActivityName + '_Active]'  
  
    IF (@DateThreshold is not NULL) OR (@ActivityId is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' WHERE'  
    END  
  
    IF (@DateThreshold is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' LastModified < N''' + CONVERT(nvarchar(50), @DateThreshold, 109) + ''''  
        IF (@ActivityId is not NULL)  
        BEGIN  
            SET @QueryString = @QueryString + ' AND'  
        END  
    END  
  
    IF (@ActivityId is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' ActivityID = N''' + @ActivityId + ''''  
    END  
  
    EXEC sp_executesql @QueryString  
    SELECT * FROM #DanglingActivities  
  
    SET @QueryString = N''  
  
    -- If the user gave a table extension, the dangling instances will be inserted  
    -- into that table.   
    IF (isnull(@NewTableExtension, '') <> '')  
    BEGIN  
        SET @DanglingActiveTableName = @ActiveTableName + '_' + @NewTableExtension  
        SET @DanglingActiveRelationshipsTableName = @ActiveRelationshipsTableName + '_' + @NewTableExtension  
        SET @DanglingContinuationsTableName = @ContinuationsTableName + '_' + @NewTableExtension  
  
        -- If the table for the dangling instances exists then insert into it  
        -- If the table does not exist, then create the dangling instances table  
        -- and then insert into it. SELECT INTO will do that.  
        EXEC sp_tables @table_name = @DanglingActiveTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingActiveTableName + '] SELECT active.* FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingActiveTableName + '] FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
  
        -- Now do what you did for the Active Instances table for the   
        -- ActiveRelationships table  
        EXEC sp_tables @table_name = @DanglingActiveRelationshipsTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingActiveRelationshipsTableName + '] SELECT active.* FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingActiveRelationshipsTableName + '] FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
  
        -- And finally for the continuations table  
        EXEC sp_tables @table_name = @DanglingContinuationsTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingContinuationsTableName + '] SELECT active.* FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingContinuationsTableName + '] FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
    END  
  
    -- Remove the dangling instances from the Active Instances Table  
    SET @QueryString = 'DELETE FROM [' + @ActiveTableName + '] FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    SET @QueryString = 'DELETE FROM [' + @ActiveRelationshipsTableName + '] FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    SET @QueryString = 'DELETE FROM [' + @ContinuationsTableName + '] FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    DROP TABLE #DanglingActivities  
  
    COMMIT TRAN      
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)