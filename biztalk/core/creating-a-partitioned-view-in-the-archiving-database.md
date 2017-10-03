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
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a><span data-ttu-id="046f2-102">在存档数据库中创建分区的视图</span><span class="sxs-lookup"><span data-stu-id="046f2-102">Creating a Partitioned View in the Archiving Database</span></span>
<span data-ttu-id="046f2-103">在运行 BAM 数据维护程序包 (BAM_DM_`<activity name>`) 时，BAM 会将 BAM 主导入数据库的每个分区分别复制到 BAM 存档数据库的一个单独的表中。</span><span class="sxs-lookup"><span data-stu-id="046f2-103">When you run the BAM data maintenance package (BAM_DM_`<activity name>`) BAM copies each partition in the BAM Primary Import database to a separate table in the BAM Archive database.</span></span> <span data-ttu-id="046f2-104">如果分离存档数据库，然后又重新附加它进行查询，那么很难找到您要查询的数据。</span><span class="sxs-lookup"><span data-stu-id="046f2-104">If you detach the archive database and reattach it for querying, it will be difficult to locate the data for your query.</span></span>  
  
 <span data-ttu-id="046f2-105">您可以在 BAM 存档数据库中创建分区视图，以简化数据查找过程。</span><span class="sxs-lookup"><span data-stu-id="046f2-105">You can create partitioned views in the BAM Archive database to facilitate locating the data.</span></span> <span data-ttu-id="046f2-106">BAM 最多支持 253 个分区。</span><span class="sxs-lookup"><span data-stu-id="046f2-106">BAM supports up to 253 partitions.</span></span> <span data-ttu-id="046f2-107">BAM 为每个活动生成一个 BAM 数据维护 DTS 程序包，该程序包将活动数据复制到 BAM 存档数据库，然后从 BAM 主导入数据库删除这些数据。</span><span class="sxs-lookup"><span data-stu-id="046f2-107">For each activity, BAM generates one BAM data maintenance DTS package, which copies the activity data to the BAM Archive database and then removes it from the BAM Primary Import database.</span></span> <span data-ttu-id="046f2-108">如果存档数据库在复制数据之后下一次备份之前失败，则数据将会丢失。</span><span class="sxs-lookup"><span data-stu-id="046f2-108">If the archive database fails after the data is copied but before the next backup, data is lost.</span></span>  
  
 <span data-ttu-id="046f2-109">防止丢失数据的办法是，创建一个单独的存档程序包，该程序包首先复制所有活动的旧数据，然后备份 BAM 存档数据库，最后删除从 BAM 主导入数据库复制的那些分区。</span><span class="sxs-lookup"><span data-stu-id="046f2-109">The solution to prevent lost data is to have a single archiving package, which first copies the old data from all activities, then backs up the BAM Archive database, and finally drops the partitions that were copied from the BAM Primary Import database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="046f2-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="046f2-110">Prerequisites</span></span>  
 <span data-ttu-id="046f2-111">必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="046f2-111">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a><span data-ttu-id="046f2-112">在 SQL Server 2008 SP1 或 SQL Server 2008 R2 的 BAM 存档数据库中创建分区视图</span><span class="sxs-lookup"><span data-stu-id="046f2-112">To create a partitioned view in the BAM Archive database in SQL Server 2008 SP1 or SQL Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="046f2-113">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="046f2-113">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="046f2-114">选择 BAM 存档数据库，然后单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="046f2-114">Select the BAM Archive database, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="046f2-115">上**查询**菜单上，指向**结果到**，然后单击**结果显示为文本**。</span><span class="sxs-lookup"><span data-stu-id="046f2-115">On the **Query** menu, point to **Results To** and then click **Results to Text**.</span></span>  
  
4.  <span data-ttu-id="046f2-116">将下面的 SQL 脚本复制到查询窗格中。</span><span class="sxs-lookup"><span data-stu-id="046f2-116">Copy the following SQL script into the query pane.</span></span> <span data-ttu-id="046f2-117">替换\<活动名称 > 替换为你的活动名称，并将`<view type>`使用**实例**实例查看或**关系**关系视图。</span><span class="sxs-lookup"><span data-stu-id="046f2-117">Replace \<activity name> with your activity name, and replace `<view type>` with either **Instances** for instance view or **Relationships** for relationship view.</span></span>  
  
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
  
5.  <span data-ttu-id="046f2-118">执行查询。</span><span class="sxs-lookup"><span data-stu-id="046f2-118">Execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046f2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="046f2-119">See Also</span></span>  
 <span data-ttu-id="046f2-120">[BAM DTS 包](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="046f2-120">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 [<span data-ttu-id="046f2-121">如何备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="046f2-121">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)