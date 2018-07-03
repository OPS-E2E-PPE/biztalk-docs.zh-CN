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
ms.openlocfilehash: 8a4ed81978dd275be8eb0348ff15dc8748258239
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977166"
---
# <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="2ce73-103">删除不完整的活动实例</span><span class="sxs-lookup"><span data-stu-id="2ce73-103">Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="2ce73-104">在部署 BAM 定义文件时，系统会在 BAM 主导入数据库中为在该定义文件中定义的每个活动创建五个表。</span><span class="sxs-lookup"><span data-stu-id="2ce73-104">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="2ce73-105">这些表分别为：</span><span class="sxs-lookup"><span data-stu-id="2ce73-105">These tables are:</span></span>  
  
- <span data-ttu-id="2ce73-106">bam_`ActivityName`_Active</span><span class="sxs-lookup"><span data-stu-id="2ce73-106">bam_`ActivityName`_Active</span></span>  
  
- <span data-ttu-id="2ce73-107">bam_`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="2ce73-107">bam_`ActivityName`_Completed</span></span>  
  
- <span data-ttu-id="2ce73-108">bam_`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="2ce73-108">bam_`ActivityName`_ActiveRelationships</span></span>  
  
- <span data-ttu-id="2ce73-109">bam_`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="2ce73-109">bam_`ActivityName`_CompletedRelationships</span></span>  
  
- <span data-ttu-id="2ce73-110">bam_`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="2ce73-110">bam_`ActivityName`_Continuations</span></span>  
  
  <span data-ttu-id="2ce73-111">其中，`ActivityName` 是用户已定义的活动名称。</span><span class="sxs-lookup"><span data-stu-id="2ce73-111">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
  <span data-ttu-id="2ce73-112">常规执行期间，不完整的数据保留在 bam_`ActivityName`*活动表。如果数据包含关系和引用，则不会在 bam 中有数据\\*`ActivityName`_ActiveRelationships 表。</span><span class="sxs-lookup"><span data-stu-id="2ce73-112">During normal execution, incomplete data remains in the bam_`ActivityName`*Active table. If the data has relations and references, then there will be data in the bam\\*`ActivityName`_ActiveRelationships table.</span></span>  
  
  <span data-ttu-id="2ce73-113">在跟踪使用继续符的活动期间，可能存在其活动在 BAM 数据库中尚保持未完成状态的实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-113">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="2ce73-114">您可以使用本主题结尾处的存储过程创建脚本创建将清除不完整记录的存储过程。</span><span class="sxs-lookup"><span data-stu-id="2ce73-114">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
  <span data-ttu-id="2ce73-115">若要创建该存储过程，请通过使用 SQL Server Management 复制该脚本并对 BAM 主导入数据库执行它。</span><span class="sxs-lookup"><span data-stu-id="2ce73-115">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="2ce73-116">此脚本将生成一个名为的存储的过程**RemoveDanglingInstances**数据库中。</span><span class="sxs-lookup"><span data-stu-id="2ce73-116">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
## <a name="create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="2ce73-117">创建 RemoveDanglingInstances 存储过程</span><span class="sxs-lookup"><span data-stu-id="2ce73-117">Create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="2ce73-118">打开**SQL Server Management Studio**，并连接到 SQL server。</span><span class="sxs-lookup"><span data-stu-id="2ce73-118">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="2ce73-119">展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="2ce73-119">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="2ce73-120">单击 **“新建查询”**。</span><span class="sxs-lookup"><span data-stu-id="2ce73-120">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="2ce73-121">复制存储的过程创建脚本，并将其粘贴到查询窗格。</span><span class="sxs-lookup"><span data-stu-id="2ce73-121">Copy the stored procedure creation script, and paste it into the query pane.</span></span>  
  
5.  <span data-ttu-id="2ce73-122">**执行**脚本。</span><span class="sxs-lookup"><span data-stu-id="2ce73-122">**Execute** the script.</span></span> <span data-ttu-id="2ce73-123">生成的存储的过程可以查看存储过程的列表中，为 dbo。RemoveDanglingInstances。</span><span class="sxs-lookup"><span data-stu-id="2ce73-123">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
## <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="2ce73-124">删除不完整的活动实例</span><span class="sxs-lookup"><span data-stu-id="2ce73-124">Remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="2ce73-125">打开**SQL Server Management Studio**，并连接到 SQL server。</span><span class="sxs-lookup"><span data-stu-id="2ce73-125">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="2ce73-126">展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="2ce73-126">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="2ce73-127">单击 **“新建查询”**。</span><span class="sxs-lookup"><span data-stu-id="2ce73-127">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="2ce73-128">在查询窗格中，键入`exec RemoveDanglingInstances`和要执行的删除操作的相应参数。</span><span class="sxs-lookup"><span data-stu-id="2ce73-128">In the query pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="2ce73-129">例如，若要删除所有未完成活动实例的采购订单，键入`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`。</span><span class="sxs-lookup"><span data-stu-id="2ce73-129">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
5.  <span data-ttu-id="2ce73-130">**执行**脚本。</span><span class="sxs-lookup"><span data-stu-id="2ce73-130">**Execute** the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="2ce73-131">RemoveDanglingInstances 用法示例</span><span class="sxs-lookup"><span data-stu-id="2ce73-131">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="2ce73-132">存储的过程可以收到四个参数：</span><span class="sxs-lookup"><span data-stu-id="2ce73-132">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="2ce73-133">参数</span><span class="sxs-lookup"><span data-stu-id="2ce73-133">Parameter</span></span>|<span data-ttu-id="2ce73-134">Description</span><span class="sxs-lookup"><span data-stu-id="2ce73-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ce73-135">@ActivityName nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="2ce73-135">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="2ce73-136">指定要删除的不完整活动实例的名称。</span><span class="sxs-lookup"><span data-stu-id="2ce73-136">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="2ce73-137">@ActivityId nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="2ce73-137">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="2ce73-138">（可选）指定存储过程只删除具有指定实例标识符的虚实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-138">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="2ce73-139">@DateThreshold 日期时间</span><span class="sxs-lookup"><span data-stu-id="2ce73-139">@DateThreshold datetime</span></span>|<span data-ttu-id="2ce73-140">（可选）指定删除活动表中早于（不是等于和早于，只是早于）给定日期的所有活动实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-140">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="2ce73-141">@NewTableExtension nvarchar(30)</span><span class="sxs-lookup"><span data-stu-id="2ce73-141">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="2ce73-142">（可选）指定存储过程通过将提供的扩展连接到现有活动表，创建三个新表。</span><span class="sxs-lookup"><span data-stu-id="2ce73-142">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="2ce73-143">生成的表将是：</span><span class="sxs-lookup"><span data-stu-id="2ce73-143">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="2ce73-144">bam_ActivityName_Active_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="2ce73-144">bam_ActivityName_Active_\<Extension\></span></span><br /><br /> <span data-ttu-id="2ce73-145">bam_ActivityName_ActiveRelationships_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="2ce73-145">bam_ActivityName_ActiveRelationships_\<Extension\></span></span><br /><br /> <span data-ttu-id="2ce73-146">bam_ActivityName_Continuations_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="2ce73-146">bam_ActivityName_Continuations_\<Extension\></span></span><br /><br /> <span data-ttu-id="2ce73-147">不完整实例将会移到新的表中，而不是从数据库中清除。</span><span class="sxs-lookup"><span data-stu-id="2ce73-147">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="2ce73-148">如果这些表已存在，则该存储过程将重复使用它们；否则，将创建这些表。</span><span class="sxs-lookup"><span data-stu-id="2ce73-148">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="2ce73-149">**重要说明：** 的存储的过程已存在的表，如果假定其架构匹配的那些可在创建它们。</span><span class="sxs-lookup"><span data-stu-id="2ce73-149">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="2ce73-150">如果架构不匹配，则该存储过程将无法插入记录，并且取消操作也会失败。</span><span class="sxs-lookup"><span data-stu-id="2ce73-150">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="2ce73-151">删除活动表、活动关系表和继续符表中“PurchaseOrder”活动的所有活动实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-151">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="2ce73-152">从“PurchaseOrder”活动的活动表、活动关系表和继续符表中只删除 ID 为“PO220567”的活动实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-152">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="2ce73-153">从“PurchaseOrder”活动的活动表、活动关系表和继续符表中删除 LastModified 时间早于 2005 年 2 月 2 日的 7:27:03.533 PM 的所有活动实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-153">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="2ce73-154">删除其活动 ID 为 PO220567 且其 LastModified 列早于 2005 年 2 月 2 日 7:27:03.533 PM 的实例。</span><span class="sxs-lookup"><span data-stu-id="2ce73-154">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="2ce73-155">在数据库中创建以下表：</span><span class="sxs-lookup"><span data-stu-id="2ce73-155">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="2ce73-156">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="2ce73-156">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="2ce73-157">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="2ce73-157">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="2ce73-158">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="2ce73-158">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="2ce73-159">存储过程将从“PurchaseOrder”活动的活动表、活动关系表和继续符表中复制早于 2005 年 2 月 2 日的 7:27:03.533 PM 的所有未完成实例，然后将它们插入新创建的表中。</span><span class="sxs-lookup"><span data-stu-id="2ce73-159">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="2ce73-160">然后，将已复制的活动实例从活动表、活动关系表和继续符表中删除。</span><span class="sxs-lookup"><span data-stu-id="2ce73-160">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="2ce73-161">存储过程创建脚本</span><span class="sxs-lookup"><span data-stu-id="2ce73-161">Stored Procedure Creation Script</span></span>  
  
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

## <a name="another-method-of-resolving-incomplete-instances"></a><span data-ttu-id="2ce73-162">解决未完成的实例的另一种方法</span><span class="sxs-lookup"><span data-stu-id="2ce73-162">Another method of resolving incomplete instances</span></span>
<span data-ttu-id="2ce73-163">此外可以通过使用 SQL 查询来解析不完整的活动实例从 BAMPrimaryImport 数据库。</span><span class="sxs-lookup"><span data-stu-id="2ce73-163">You can also resolve incomplete activity instances from the BAMPrimaryImport database by using a SQL query.</span></span> <span data-ttu-id="2ce73-164">请参阅[解析不完整的活动实例](how-to-resolve-incomplete-activity-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce73-164">See [Resolve incomplete activity instances](how-to-resolve-incomplete-activity-instances.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ce73-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ce73-165">See Also</span></span>  
 [<span data-ttu-id="2ce73-166">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="2ce73-166">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
