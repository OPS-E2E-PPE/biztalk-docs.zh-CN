---
title: 如何集成 BAM 与 SQL Server Reporting Services |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cba4a9fe610167105f9bf2b89c78f3a4b0ced0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336942"
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a><span data-ttu-id="d9893-102">如何集成 BAM 与 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d9893-102">How to Integrate BAM with SQL Server Reporting Services</span></span>
<span data-ttu-id="d9893-103">报表基于数据创建 BAM 基础结构使用与创建任何其他 SQL Server 数据源的报表相关联的典型任务。</span><span class="sxs-lookup"><span data-stu-id="d9893-103">Creating a report based on data in the BAM infrastructure use the typical tasks associated with creating a report for any other SQL Server data source.</span></span> <span data-ttu-id="d9893-104">有关使用报表设计器创建报表的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=82437 ](http://go.microsoft.com/fwlink/?LinkId=82437)。</span><span class="sxs-lookup"><span data-stu-id="d9893-104">For more information about creating a report with Report Designer, see [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d9893-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="d9893-105">Prerequisites</span></span>  
 <span data-ttu-id="d9893-106">必须有权访问创建报表所需的数据。</span><span class="sxs-lookup"><span data-stu-id="d9893-106">You must have permissions to access the data necessary to create the report.</span></span>  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a><span data-ttu-id="d9893-107">如何使用 SQL Server Reporting Service 在 BAM 中创建报表</span><span class="sxs-lookup"><span data-stu-id="d9893-107">How to Create a Report in BAM by Using SQL Server Reporting Service</span></span>  
  
1.  <span data-ttu-id="d9893-108">选择要创建报表的数据源。</span><span class="sxs-lookup"><span data-stu-id="d9893-108">Select the data source from which to create the report.</span></span>  
  
     <span data-ttu-id="d9893-109">BAM 提供 Reporting Services 可以指向两个数据源。</span><span class="sxs-lookup"><span data-stu-id="d9893-109">BAM provides two data sources to which Reporting Services can point.</span></span>  
  
    |<span data-ttu-id="d9893-110">数据源</span><span class="sxs-lookup"><span data-stu-id="d9893-110">Data Source</span></span>|<span data-ttu-id="d9893-111">Description</span><span class="sxs-lookup"><span data-stu-id="d9893-111">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="d9893-112">BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="d9893-112">BAM Primary Import database</span></span>|<span data-ttu-id="d9893-113">包含关于活动实例和实时聚合的视图。</span><span class="sxs-lookup"><span data-stu-id="d9893-113">Contains views on activity instances and real-time aggregations.</span></span> <span data-ttu-id="d9893-114">选择类型 ="Microsoft SQL Server"，Connection String ="数据源 =\<*服务器名称*\>;初始目录 =\<*数据库名称*\>"，其中\<*服务器名称*\>并\<*数据库名称*\>是 Bam 主导入数据库的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d9893-114">Select Type=”Microsoft SQL Server” and Connection String=”Data Source=\<*server name*\>; Initial Catalog=\<*database name*\>”, where \<*server name*\> and \<*database name*\> are the server and database names of your Bam Primary Import database.</span></span>|  
    |<span data-ttu-id="d9893-115">BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="d9893-115">BAM Analysis database</span></span>|<span data-ttu-id="d9893-116">包含用于查询分析多维数据集的数据。</span><span class="sxs-lookup"><span data-stu-id="d9893-116">Contains data that is used to query the analysis cube.</span></span> <span data-ttu-id="d9893-117">选择类型 ="Microsoft SQL Server Analysis Server"，Connection String ="数据源 =\<*服务器名称*\>;初始目录 =\<*数据库名称*\>"，其中\<*服务器名称*\>并\<*数据库名称*\>是 BAM 分析数据库的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d9893-117">Select Type=”Microsoft SQL Server Analysis Server” and Connection String=”Data Source=\<*server name*\>; Initial Catalog=\<*database name*\>”, where \<*server name*\> and \<*database name*\> are the server and database names of your BAM Analysis database.</span></span>|  
  
2.  <span data-ttu-id="d9893-118">设计查询。</span><span class="sxs-lookup"><span data-stu-id="d9893-118">Design the query.</span></span> <span data-ttu-id="d9893-119">对于 BAM 主导入数据库中，有两种类型的视图：</span><span class="sxs-lookup"><span data-stu-id="d9893-119">For the BAM Primary Import database, there are two types of views:</span></span>  
  
    |<span data-ttu-id="d9893-120">视图名称</span><span class="sxs-lookup"><span data-stu-id="d9893-120">View Name</span></span>|<span data-ttu-id="d9893-121">Description</span><span class="sxs-lookup"><span data-stu-id="d9893-121">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d9893-122">dbo.bam_\<*视图名称*\>_\<*活动名称*\>View_View。</span><span class="sxs-lookup"><span data-stu-id="d9893-122">dbo.bam_\<*view name*\>_\<*activity name*\>View_View.</span></span>|<span data-ttu-id="d9893-123">此视图包含实例数据。</span><span class="sxs-lookup"><span data-stu-id="d9893-123">This view contains instance data.</span></span>|  
    |<span data-ttu-id="d9893-124">dbo.bam_\<*视图名称*\>_\<*实时聚合透视表名称*\>_RTAView</span><span class="sxs-lookup"><span data-stu-id="d9893-124">dbo.bam_\<*view name*\>_\<*real time aggregation pivot table name*\>_RTAView</span></span>|<span data-ttu-id="d9893-125">此视图包含在实时聚合中使用的数据。</span><span class="sxs-lookup"><span data-stu-id="d9893-125">This view contains data used in real-time aggregations.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d9893-126">您可以键入**选择\*从视图**返回返回所需的结果集。</span><span class="sxs-lookup"><span data-stu-id="d9893-126">You can type **select \* from view** to return the desired result set.</span></span> <span data-ttu-id="d9893-127">对于 BAM 分析数据库中，单击查询生成器，将维度和度量值的名为多维数据集拖\<*视图名称*\>返回返回所需的结果集。</span><span class="sxs-lookup"><span data-stu-id="d9893-127">For the BAM Analysis database, click the query builder and drag the dimensions and measures of the cube named \<*view name*\> to return the desired result set.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d9893-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d9893-128">Next Steps</span></span>  
 <span data-ttu-id="d9893-129">完成报表向导来指定为将存在且数据的方式呈现的数据中的步骤。</span><span class="sxs-lookup"><span data-stu-id="d9893-129">Complete the steps in the Report Wizard to specify which data you are going to present and how the data is to be presented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9893-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9893-130">See Also</span></span>  
 [<span data-ttu-id="d9893-131">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="d9893-131">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)