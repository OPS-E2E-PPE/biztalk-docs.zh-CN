---
title: 删除不完整的活动实例 |Microsoft Docs
description: 执行自定义的 RemoveDanglingInstances SQL 脚本，以便从 BizTalk Server 中的 BAM 主导入数据库删除不完整实例
ms.custom: ''
ms.date: 01/18/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7060578c-6267-487b-8530-efa18f9431ce
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bebb8d3899c34dcde7a5d5c3059434d23202929a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334978"
---
# <a name="remove-incomplete-activity-instances"></a>删除不完整的活动实例
部署 BAM 定义文件时，定义文件中定义的每个活动的 BAM 主导入数据库中创建五个表。 这些表是：  
  
- bam_`ActivityName`_Active  
  
- bam_`ActivityName`_Completed  
  
- bam_`ActivityName`_ActiveRelationships  
  
- bam_`ActivityName`_CompletedRelationships  
  
- bam_`ActivityName`_Continuations  
  
  其中`ActivityName`是用户定义的活动的名称。  
  
  常规执行期间，不完整的数据保留在 bam_`ActivityName`*活动表。如果数据包含关系和引用，则不会在 bam 中有数据\\*`ActivityName`_ActiveRelationships 表。  
  
  在使用继续符的活动跟踪，都可能有未完成状态在 BAM 数据库中保留一个活动的实例。 可以使用本主题末尾的存储的过程创建脚本以创建将清除不完整记录的存储的过程。  
  
  若要创建存储的过程，将脚本复制并执行它对 BAM 主导入数据库使用 SQL Server 管理。 此脚本将生成一个名为的存储的过程**RemoveDanglingInstances**数据库中。  
  
## <a name="create-the-removedanglinginstances-stored-procedure"></a>创建 RemoveDanglingInstances 存储过程  
  
1.  打开**SQL Server Management Studio**，并连接到 SQL server。
  
2.  展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。  
  
3.  单击 **“新建查询”**。  
  
4.  复制存储的过程创建脚本，并将其粘贴到查询窗格。  
  
5.  **执行**脚本。 生成的存储的过程可以查看存储过程的列表中，为 dbo。RemoveDanglingInstances。  
  
## <a name="remove-incomplete-activity-instances"></a>删除不完整的活动实例  
  
1.  打开**SQL Server Management Studio**，并连接到 SQL server。
  
2.  展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。  
  
3.  单击 **“新建查询”**。  
  
4.  在查询窗格中，键入`exec RemoveDanglingInstances`和要执行的删除操作的相应参数。 例如，若要删除所有未完成活动实例的采购订单，键入`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`。  
  
5.  **执行**脚本。  
  
## <a name="removedanglinginstances-usage-examples"></a>RemoveDanglingInstances 用法示例  
 存储的过程可以收到四个参数：  
  
|参数|Description|  
|---------------|-----------------|  
|@ActivityName nvarchar(128)|指定要删除的不完整的活动实例的名称。|  
|@ActivityId nvarchar(128)|（可选）指定存储的过程删除仅与指定的实例标识符的虚实例。|  
|@DateThreshold 日期时间|（可选）指定所有活动都实例中活动较旧的表 （不等于和早，只是早于） 给定日期会删除。|  
|@NewTableExtension nvarchar(30)|（可选）指定该存储的过程通过连接到现有活动表提供的扩展来创建三个新表。<br /><br /> 将生成的表：<br /><br /> bam_ActivityName_Active_\<Extension\><br /><br /> bam_ActivityName_ActiveRelationships_\<Extension\><br /><br /> bam_ActivityName_Continuations_\<Extension\><br /><br /> 未完成的实例会移到新表，而不是从数据库中清除。<br /><br /> 如果已存在的表，存储的过程重新使用它们;否则，将创建。 **重要提示：** 如果已存在的表，存储的过程假定其架构匹配的那些可在创建它们。 如果架构不匹配，存储的过程将无法将记录插入和删除操作将失败。|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 删除 PurchaseOrder 活动的所有活动实例处于活动状态，活动关系表和继续符表。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 已从活动，活动 ID 为 PO220567 的活动实例中删除活动关系表和 PurchaseOrder 活动的继续符表。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 删除 LastModified 时间早于 2005 年 2 月 2 日的所有活动实例从活动，7:27:03.533 PM 活动关系表和 PurchaseOrder 活动的继续符表。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 删除其活动 ID 为 po220567 且其 LastModified 列是早于 2005 年 2 月 2 日的活动实例 7:27:03.533 PM。  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 在数据库中创建以下表：  
  
 bam_PurchaseOrder_Active_Dangling  
  
 bam_PurchaseOrder_ActiveRelationships_Dangling  
  
 bam_PurchaseOrder_Continuations_Dangling  
  
 存储的过程将复制所有早于 2005 年 2 月 2 日的不完整的活动实例从活动、 活动关系 7:27:03.533 PM 和继续符表为 PurchaseOrder 活动，并将其插入到新创建的表。 从活动状态，然后删除复制的活动实例活动关系表和继续符表。  
  
## <a name="stored-procedure-creation-script"></a>存储的过程创建脚本  
  
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

## <a name="another-method-of-resolving-incomplete-instances"></a>解决未完成的实例的另一种方法
此外可以通过使用 SQL 查询来解析不完整的活动实例从 BAMPrimaryImport 数据库。 请参阅[解析不完整的活动实例](how-to-resolve-incomplete-activity-instances.md)。

## <a name="see-also"></a>请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)
