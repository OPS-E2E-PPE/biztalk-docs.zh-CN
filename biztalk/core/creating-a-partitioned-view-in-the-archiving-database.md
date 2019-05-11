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
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a><span data-ttu-id="15588-102">在存档数据库中创建分区的视图</span><span class="sxs-lookup"><span data-stu-id="15588-102">Creating a Partitioned View in the Archiving Database</span></span>
<span data-ttu-id="15588-103">当您运行 BAM 数据维护程序包 (BAM_DM_`<activity name>`) BAM 将每个分区中的 BAM 主导入数据库复制到 BAM 存档数据库中的单独表。</span><span class="sxs-lookup"><span data-stu-id="15588-103">When you run the BAM data maintenance package (BAM_DM_`<activity name>`) BAM copies each partition in the BAM Primary Import database to a separate table in the BAM Archive database.</span></span> <span data-ttu-id="15588-104">如果分离存档数据库，并重新附加它进行查询，它将很难找到您的查询的数据。</span><span class="sxs-lookup"><span data-stu-id="15588-104">If you detach the archive database and reattach it for querying, it will be difficult to locate the data for your query.</span></span>  
  
 <span data-ttu-id="15588-105">您可以在 BAM 存档数据库以简化数据查找过程中创建分区的视图。</span><span class="sxs-lookup"><span data-stu-id="15588-105">You can create partitioned views in the BAM Archive database to facilitate locating the data.</span></span> <span data-ttu-id="15588-106">BAM 支持最多 253 个分区。</span><span class="sxs-lookup"><span data-stu-id="15588-106">BAM supports up to 253 partitions.</span></span> <span data-ttu-id="15588-107">对于每个活动，BAM 将生成一个 BAM 数据维护 DTS 包，其中将活动数据复制到 BAM 存档数据库，并将其删除从 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="15588-107">For each activity, BAM generates one BAM data maintenance DTS package, which copies the activity data to the BAM Archive database and then removes it from the BAM Primary Import database.</span></span> <span data-ttu-id="15588-108">如果存档数据库失败后将数据复制，但在下一次备份之前，数据都会丢失。</span><span class="sxs-lookup"><span data-stu-id="15588-108">If the archive database fails after the data is copied but before the next backup, data is lost.</span></span>  
  
 <span data-ttu-id="15588-109">要防止数据丢失的解决方案是具有单个的存档程序包，它先将旧数据复制所有活动，然后备份 BAM 存档数据库，并最后删除从 BAM 主导入数据库复制的分区。</span><span class="sxs-lookup"><span data-stu-id="15588-109">The solution to prevent lost data is to have a single archiving package, which first copies the old data from all activities, then backs up the BAM Archive database, and finally drops the partitions that were copied from the BAM Primary Import database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15588-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="15588-110">Prerequisites</span></span>  
 <span data-ttu-id="15588-111">您必须为要执行此过程的 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="15588-111">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a><span data-ttu-id="15588-112">若要在 SQL Server 2008 SP1 或 SQL Server 2008 R2 中的 BAM 存档数据库中创建分区的视图</span><span class="sxs-lookup"><span data-stu-id="15588-112">To create a partitioned view in the BAM Archive database in SQL Server 2008 SP1 or SQL Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="15588-113">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="15588-113">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="15588-114">选择 BAM 存档数据库，然后单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="15588-114">Select the BAM Archive database, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="15588-115">上**查询**菜单，依次指向**结果显示为**，然后单击**结果显示为文本**。</span><span class="sxs-lookup"><span data-stu-id="15588-115">On the **Query** menu, point to **Results To** and then click **Results to Text**.</span></span>  
  
4.  <span data-ttu-id="15588-116">将以下 SQL 脚本复制到查询窗格。</span><span class="sxs-lookup"><span data-stu-id="15588-116">Copy the following SQL script into the query pane.</span></span> <span data-ttu-id="15588-117">替换\<活动名称\>与活动名称和替换`<view type>`与**实例**对于实例视图或**关系**对于关系视图。</span><span class="sxs-lookup"><span data-stu-id="15588-117">Replace \<activity name\> with your activity name, and replace `<view type>` with either **Instances** for instance view or **Relationships** for relationship view.</span></span>  
  
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
  
5.  <span data-ttu-id="15588-118">执行查询。</span><span class="sxs-lookup"><span data-stu-id="15588-118">Execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15588-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="15588-119">See Also</span></span>  
 <span data-ttu-id="15588-120">[BAM DTS 包](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="15588-120">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 [<span data-ttu-id="15588-121">如何备份 BAM 分析和跟踪分析服务器数据库</span><span class="sxs-lookup"><span data-stu-id="15588-121">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)