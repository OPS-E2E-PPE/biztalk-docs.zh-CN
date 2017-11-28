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
ms.openlocfilehash: 99c2f77b6883b7ffba997551c4121013a4379267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-incomplete-activity-instances"></a><span data-ttu-id="a868a-102">如何删除不完整的活动实例</span><span class="sxs-lookup"><span data-stu-id="a868a-102">How to Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="a868a-103">在部署 BAM 定义文件时，系统会在 BAM 主导入数据库中为在该定义文件中定义的每个活动创建五个表。</span><span class="sxs-lookup"><span data-stu-id="a868a-103">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="a868a-104">这些表分别为：</span><span class="sxs-lookup"><span data-stu-id="a868a-104">These tables are:</span></span>  
  
-   <span data-ttu-id="a868a-105">bam_`ActivityName`_Active</span><span class="sxs-lookup"><span data-stu-id="a868a-105">bam_`ActivityName`_Active</span></span>  
  
-   <span data-ttu-id="a868a-106">bam_`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="a868a-106">bam_`ActivityName`_Completed</span></span>  
  
-   <span data-ttu-id="a868a-107">bam_`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="a868a-107">bam_`ActivityName`_ActiveRelationships</span></span>  
  
-   <span data-ttu-id="a868a-108">bam_`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="a868a-108">bam_`ActivityName`_CompletedRelationships</span></span>  
  
-   <span data-ttu-id="a868a-109">bam_`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="a868a-109">bam_`ActivityName`_Continuations</span></span>  
  
 <span data-ttu-id="a868a-110">其中，`ActivityName` 是用户已定义的活动名称。</span><span class="sxs-lookup"><span data-stu-id="a868a-110">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
 <span data-ttu-id="a868a-111">在正常的执行操作中，不完整的数据保留在 bam_`ActivityName`_Active 表中。</span><span class="sxs-lookup"><span data-stu-id="a868a-111">During normal execution, incomplete data remains in the bam_`ActivityName`_Active table.</span></span> <span data-ttu-id="a868a-112">如果数据具有关系和引用，则在 bam 将数据\_`ActivityName`_ActiveRelationships 表。</span><span class="sxs-lookup"><span data-stu-id="a868a-112">If the data has relations and references, then there will be data in the bam\_`ActivityName`_ActiveRelationships table.</span></span>  
  
 <span data-ttu-id="a868a-113">在跟踪使用继续符的活动期间，可能存在其活动在 BAM 数据库中尚保持未完成状态的实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-113">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="a868a-114">您可以使用本主题结尾处的存储过程创建脚本创建将清除不完整记录的存储过程。</span><span class="sxs-lookup"><span data-stu-id="a868a-114">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
 <span data-ttu-id="a868a-115">若要创建该存储过程，请通过使用 SQL Server Management 复制该脚本并对 BAM 主导入数据库执行它。</span><span class="sxs-lookup"><span data-stu-id="a868a-115">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="a868a-116">该脚本将生成名为的存储的过程**RemoveDanglingInstances**数据库中。</span><span class="sxs-lookup"><span data-stu-id="a868a-116">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
### <a name="to-create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="a868a-117">创建 RemoveDanglingInstances 存储过程</span><span class="sxs-lookup"><span data-stu-id="a868a-117">To create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="a868a-118">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="a868a-118">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="a868a-119">在**连接到服务器**对话框中，选择 SQL server 和适当的身份验证方法，，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="a868a-119">In the **Connect to Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="a868a-120">展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="a868a-120">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="a868a-121">单击 **“新建查询”**。</span><span class="sxs-lookup"><span data-stu-id="a868a-121">Click **New Query**.</span></span>  
  
5.  <span data-ttu-id="a868a-122">复制存储过程创建脚本并将其粘贴到适当的窗格中。</span><span class="sxs-lookup"><span data-stu-id="a868a-122">Copy the stored procedure creation script and paste it into the right pane.</span></span>  
  
6.  <span data-ttu-id="a868a-123">单击**执行**以运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="a868a-123">Click **Execute** to run the script.</span></span> <span data-ttu-id="a868a-124">生成的存储的过程可以查看存储过程的列表中，为 dbo。RemoveDanglingInstances。</span><span class="sxs-lookup"><span data-stu-id="a868a-124">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
### <a name="to-remove-incomplete-activity-instances"></a><span data-ttu-id="a868a-125">删除不完整的活动实例</span><span class="sxs-lookup"><span data-stu-id="a868a-125">To remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="a868a-126">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="a868a-126">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="a868a-127">在**连接到服务器**对话框中，选择 SQL server 和适当的身份验证方法，，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="a868a-127">In the **Connect to Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="a868a-128">展开服务器名称，展开**数据库**，然后选择 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="a868a-128">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="a868a-129">单击 **“新建查询”**。</span><span class="sxs-lookup"><span data-stu-id="a868a-129">Click **New Query**.</span></span>  
  
5.  <span data-ttu-id="a868a-130">在右窗格中，键入`exec RemoveDanglingInstances`和正在执行的删除操作的相应参数。</span><span class="sxs-lookup"><span data-stu-id="a868a-130">In the right pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="a868a-131">例如，若要删除所有未完成活动实例的采购订单，键入`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`。</span><span class="sxs-lookup"><span data-stu-id="a868a-131">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
6.  <span data-ttu-id="a868a-132">单击**执行**以运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="a868a-132">Click **Execute** to run the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="a868a-133">RemoveDanglingInstances 用法示例</span><span class="sxs-lookup"><span data-stu-id="a868a-133">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="a868a-134">存储的过程可以收到四个参数：</span><span class="sxs-lookup"><span data-stu-id="a868a-134">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="a868a-135">参数</span><span class="sxs-lookup"><span data-stu-id="a868a-135">Parameter</span></span>|<span data-ttu-id="a868a-136">Description</span><span class="sxs-lookup"><span data-stu-id="a868a-136">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a868a-137">@ActivityName nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="a868a-137">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="a868a-138">指定要删除的不完整活动实例的名称。</span><span class="sxs-lookup"><span data-stu-id="a868a-138">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="a868a-139">@ActivityId nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="a868a-139">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="a868a-140">（可选）指定存储过程只删除具有指定实例标识符的虚实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-140">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="a868a-141">@DateThreshold日期时间</span><span class="sxs-lookup"><span data-stu-id="a868a-141">@DateThreshold datetime</span></span>|<span data-ttu-id="a868a-142">（可选）指定删除活动表中早于（不是等于和早于，只是早于）给定日期的所有活动实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-142">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="a868a-143">@NewTableExtensionnvarchar (30)</span><span class="sxs-lookup"><span data-stu-id="a868a-143">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="a868a-144">（可选）指定存储过程通过将提供的扩展连接到现有活动表，创建三个新表。</span><span class="sxs-lookup"><span data-stu-id="a868a-144">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="a868a-145">生成的表将是：</span><span class="sxs-lookup"><span data-stu-id="a868a-145">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="a868a-146">bam_ActivityName_Active_\<扩展 ></span><span class="sxs-lookup"><span data-stu-id="a868a-146">bam_ActivityName_Active_\<Extension></span></span><br /><br /> <span data-ttu-id="a868a-147">bam_ActivityName_ActiveRelationships_\<扩展 ></span><span class="sxs-lookup"><span data-stu-id="a868a-147">bam_ActivityName_ActiveRelationships_\<Extension></span></span><br /><br /> <span data-ttu-id="a868a-148">bam_ActivityName_Continuations_\<扩展 ></span><span class="sxs-lookup"><span data-stu-id="a868a-148">bam_ActivityName_Continuations_\<Extension></span></span><br /><br /> <span data-ttu-id="a868a-149">不完整实例将会移到新的表中，而不是从数据库中清除。</span><span class="sxs-lookup"><span data-stu-id="a868a-149">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="a868a-150">如果这些表已存在，则该存储过程将重复使用它们；否则，将创建这些表。</span><span class="sxs-lookup"><span data-stu-id="a868a-150">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="a868a-151">**重要说明：**如果表已存在，存储的过程假定其架构匹配，就好像是将使用。</span><span class="sxs-lookup"><span data-stu-id="a868a-151">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="a868a-152">如果架构不匹配，则该存储过程将无法插入记录，并且取消操作也会失败。</span><span class="sxs-lookup"><span data-stu-id="a868a-152">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="a868a-153">删除活动表、活动关系表和继续符表中“PurchaseOrder”活动的所有活动实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-153">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="a868a-154">从“PurchaseOrder”活动的活动表、活动关系表和继续符表中只删除 ID 为“PO220567”的活动实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-154">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="a868a-155">从“PurchaseOrder”活动的活动表、活动关系表和继续符表中删除 LastModified 时间早于 2005 年 2 月 2 日的 7:27:03.533 PM 的所有活动实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-155">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="a868a-156">删除其活动 ID 为 PO220567 且其 LastModified 列早于 2005 年 2 月 2 日 7:27:03.533 PM 的实例。</span><span class="sxs-lookup"><span data-stu-id="a868a-156">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="a868a-157">在数据库中创建以下表：</span><span class="sxs-lookup"><span data-stu-id="a868a-157">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="a868a-158">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="a868a-158">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="a868a-159">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="a868a-159">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="a868a-160">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="a868a-160">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="a868a-161">存储过程将从“PurchaseOrder”活动的活动表、活动关系表和继续符表中复制早于 2005 年 2 月 2 日的 7:27:03.533 PM 的所有未完成实例，然后将它们插入新创建的表中。</span><span class="sxs-lookup"><span data-stu-id="a868a-161">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="a868a-162">然后，将已复制的活动实例从活动表、活动关系表和继续符表中删除。</span><span class="sxs-lookup"><span data-stu-id="a868a-162">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="a868a-163">存储过程创建脚本</span><span class="sxs-lookup"><span data-stu-id="a868a-163">Stored Procedure Creation Script</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a868a-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a868a-164">See Also</span></span>  
 [<span data-ttu-id="a868a-165">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="a868a-165">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)