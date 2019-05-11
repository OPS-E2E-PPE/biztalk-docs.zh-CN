---
title: BAM 工作流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring business activities [BAM], collecting business data
- XML files
- orchestrations, XML files
- business activities, business data
- infrastructure, managing [BAM]
- business activities, monitoring
- monitoring business activities [BAM], monitoring flow
- managing [BAM], infrastructure
- monitoring business activities [BAM], viewing business data
- managing [orchestrations], mapping XML to orchestrations
ms.assetid: 8b4ae145-3e16-4bb8-bfba-09b9f666218d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82cfe7fe5f29994c72b9f9026c03321ba44e3575
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529165"
---
# <a name="bam-workflow"></a><span data-ttu-id="56870-102">BAM 工作流</span><span class="sxs-lookup"><span data-stu-id="56870-102">BAM Workflow</span></span>
<span data-ttu-id="56870-103">下图显示了四个用户角色的用户使用业务活动监视，以及他们使用的工具。</span><span class="sxs-lookup"><span data-stu-id="56870-103">The following figure shows the four user roles who work with Business Activity Monitoring, and the tools that they use.</span></span>  
  
 <span data-ttu-id="56870-104">![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")</span><span class="sxs-lookup"><span data-stu-id="56870-104">![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")</span></span>  
<span data-ttu-id="56870-105">BAM 角色</span><span class="sxs-lookup"><span data-stu-id="56870-105">BAM Roles</span></span>  
  
 <span data-ttu-id="56870-106">以下步骤提供使用业务活动监视的工作流的高级概述。</span><span class="sxs-lookup"><span data-stu-id="56870-106">The following steps provide a high-level overview of the workflow for using Business Activity Monitoring.</span></span>  
  
## <a name="specifying-the-business-data-to-collect"></a><span data-ttu-id="56870-107">指定要收集的业务数据</span><span class="sxs-lookup"><span data-stu-id="56870-107">Specifying the business data to collect</span></span>  
 <span data-ttu-id="56870-108">按以下方式收集业务数据：</span><span class="sxs-lookup"><span data-stu-id="56870-108">Business data is collected in the following manner:</span></span>  
  
-   <span data-ttu-id="56870-109">业务分析员使用 BAM 活动向导来指定要收集所有业务用户的数据。</span><span class="sxs-lookup"><span data-stu-id="56870-109">The business analyst uses the BAM Activity Wizard to specify what data to collect for all business users.</span></span>  
  
-   <span data-ttu-id="56870-110">业务分析员使用 BAM 视图向导来为每个类别的业务用户定义视图。</span><span class="sxs-lookup"><span data-stu-id="56870-110">The business analyst uses the BAM View Wizard to define the view for each category of business user.</span></span>  
  
-   <span data-ttu-id="56870-111">完成后，他将保存活动和视图的 Microsoft® Excel 工作簿中名为 BAM 定义工作簿。</span><span class="sxs-lookup"><span data-stu-id="56870-111">When finished, he saves the activities and views in a Microsoft® Excel Workbook called the BAM Definition Workbook.</span></span>  
  
-   <span data-ttu-id="56870-112">业务分析员将 BAM 定义工作簿导出到 XML。</span><span class="sxs-lookup"><span data-stu-id="56870-112">The business analyst exports the BAM Definition Workbook to XML.</span></span>  
  
-   <span data-ttu-id="56870-113">系统管理员和开发人员使用 XML 来执行他们的角色。</span><span class="sxs-lookup"><span data-stu-id="56870-113">The system administrator and developer use the XML to perform their roles.</span></span>  
  
-   <span data-ttu-id="56870-114">有关使用 BAM 定义工作簿的说明位于[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="56870-114">Instructions for using the BAM Definition Workbook are located in [Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
## <a name="managing-the-bam-infrastructure"></a><span data-ttu-id="56870-115">管理 BAM 基础结构</span><span class="sxs-lookup"><span data-stu-id="56870-115">Managing the BAM Infrastructure</span></span>  
 <span data-ttu-id="56870-116">业务分析员定义的 BAM 视图后，系统管理员使用 BAM 管理实用工具 (BM。Exe 文件），从工作簿导出的命令行工具，以部署 BAM 基础结构从 BAM 定义工作簿或 XML。</span><span class="sxs-lookup"><span data-stu-id="56870-116">After the business analyst has defined the BAM view he wants, the system administrator uses the BAM management utility (BM.EXE), a command-line tool, to deploy the BAM infrastructure from the BAM Definition Workbook or the XML exported from the workbook.</span></span>  
  
 <span data-ttu-id="56870-117">BAM 管理实用程序动态创建表、 触发器、 DTS 包和 OLAP 多维数据集支持 BAM 视图所需。</span><span class="sxs-lookup"><span data-stu-id="56870-117">The BAM management utility dynamically creates the tables, triggers, DTS packages, and OLAP cubes necessary to support the BAM view.</span></span>  
  
 <span data-ttu-id="56870-118">每次业务分析员定义其他 BAM 视图，或更改现有 BAM 视图时，系统管理员必须重新部署 BAM 定义工作簿。</span><span class="sxs-lookup"><span data-stu-id="56870-118">Each time the business analyst defines a different BAM view, or changes an existing BAM view, the system administrator must redeploy the BAM Definition Workbook.</span></span>  
  
## <a name="mapping-the-xml-to-an-orchestration"></a><span data-ttu-id="56870-119">XML 文件映射到业务流程</span><span class="sxs-lookup"><span data-stu-id="56870-119">Mapping the XML to an orchestration</span></span>  
 <span data-ttu-id="56870-120">业务分析员将 BAM 定义工作簿导出到 XML 后，开发人员 XML 文件导入跟踪配置文件编辑器。</span><span class="sxs-lookup"><span data-stu-id="56870-120">After the business analyst exports the BAM Definition Workbook to XML, the developer imports the XML file into the Tracking Profile Editor.</span></span> <span data-ttu-id="56870-121">开发人员实现业务分析员的信息要求 XML 文件映射到业务流程。</span><span class="sxs-lookup"><span data-stu-id="56870-121">The developer implements the business analyst's information requirements, mapping the XML to an orchestration.</span></span>  
  
 <span data-ttu-id="56870-122">使用跟踪配置文件编辑器，开发人员可以执行以下步骤以将 XML 映射到业务流程：</span><span class="sxs-lookup"><span data-stu-id="56870-122">Using the Tracking Profile Editor, the developer performs the following steps to map the XML to an orchestration:</span></span>  
  
- <span data-ttu-id="56870-123">加载存储在 BizTalk 管理数据库 （也称为配置数据库） 中的已部署程序集。</span><span class="sxs-lookup"><span data-stu-id="56870-123">Loads the deployed assembly that is stored in the BizTalk Management database (also known as the Configuration database).</span></span> <span data-ttu-id="56870-124">已部署的程序集包含与业务分析员在上面的步骤 1 中指定的要求相对应的一个或多个业务流程。</span><span class="sxs-lookup"><span data-stu-id="56870-124">The deployed assembly contains one or more orchestrations corresponding to the requirements that the business analyst specified in Step 1 above.</span></span>  
  
- <span data-ttu-id="56870-125">定义要从业务流程中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="56870-125">Defines the data to be extracted from an orchestration.</span></span> <span data-ttu-id="56870-126">执行此操作的消息架构中的项放和业务流程形状的相应的业务里程碑 （事件） 和数据插入项的文件夹。</span><span class="sxs-lookup"><span data-stu-id="56870-126">You do this by dropping items from the message schemas and orchestration shapes into the appropriate business milestone (event) and data item folders.</span></span>  
  
- <span data-ttu-id="56870-127">完成后，他将保存该配置文件为 BizTalk® Server 跟踪 (.btt) 文件，例如 Visual SourceSafe 存储数据库。</span><span class="sxs-lookup"><span data-stu-id="56870-127">When he is finished, he saves the profile as a BizTalk® Server tracking (.btt) file, to a storage database such as Visual SourceSafe.</span></span>  
  
  <span data-ttu-id="56870-128">开发人员将该.btt 文件部署到测试数据库，并验证通过集成测试的结果。</span><span class="sxs-lookup"><span data-stu-id="56870-128">The developer deploys the .btt file to a testing database, and verifies the result through integration testing.</span></span>  
  
## <a name="deploying-the-tracking-profile"></a><span data-ttu-id="56870-129">部署跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="56870-129">Deploying the Tracking Profile</span></span>  
 <span data-ttu-id="56870-130">系统管理员使用跟踪配置文件编辑器，将该配置文件部署到一个或多个 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="56870-130">Using the Tracking Profile Editor, the system administrator deploys the profile to one or more BizTalk Management databases.</span></span>  
  
 <span data-ttu-id="56870-131">每次开发人员更改业务流程中或业务用户变化的要求和他们想要跟踪更多数据，系统管理员需要重新部署跟踪配置文件使用 bttdeploy.exe 命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="56870-131">Each time the developer changes the orchestration, or the requirements of the business users change and they want to track more data, the system administrator needs to redeploy the tracking profile using the bttdeploy.exe command line utility.</span></span>  
  
## <a name="viewing-the-business-data"></a><span data-ttu-id="56870-132">查看业务数据</span><span class="sxs-lookup"><span data-stu-id="56870-132">Viewing the business data</span></span>  
 <span data-ttu-id="56870-133">业务用户使用 _LiveData 工作簿，这由 BM.exe 实用工具生成。</span><span class="sxs-lookup"><span data-stu-id="56870-133">The business user uses the _LiveData workbook, which is produced by the BM.exe utility.</span></span> <span data-ttu-id="56870-134">业务用户打开 _LiveData 工作簿中，每次他接收新收集要监视的业务流程特定方面的数据的实时版本。</span><span class="sxs-lookup"><span data-stu-id="56870-134">Each time the business user opens the _LiveData workbook, he receives a new live version of the data that is collected to monitor a specific aspect of the business process.</span></span>  
  
-   <span data-ttu-id="56870-135">若要查看被定义为实时聚合的数据，业务用户只需单击**刷新**要查看的数据的工作簿中。</span><span class="sxs-lookup"><span data-stu-id="56870-135">To view data that is defined as real-time aggregation, the business user just needs to click **Refresh** in the workbook to view the data.</span></span>  
  
-   <span data-ttu-id="56870-136">如果不是实时聚合数据，则业务用户将看到在计划的 DTS 包运行时执行的业务数据的快照。</span><span class="sxs-lookup"><span data-stu-id="56870-136">If the aggregation data is not real-time, the business user views a snapshot of the business data that is taken at the time that the scheduled DTS package runs.</span></span>  
  
-   <span data-ttu-id="56870-137">如果你的组织有协作要求，业务用户可以从 BAS 网站访问实时数据。</span><span class="sxs-lookup"><span data-stu-id="56870-137">If your organization has collaboration requirements, the business user can access the live data from the BAS Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56870-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="56870-138">See Also</span></span>  
 <span data-ttu-id="56870-139">[在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="56870-139">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="56870-140">使用 BAM 监视业务活动</span><span class="sxs-lookup"><span data-stu-id="56870-140">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)