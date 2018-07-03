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
ms.openlocfilehash: 4c925e1b77b53bc2ec30a7f42b2446ee410ffef7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989934"
---
# <a name="bam-workflow"></a><span data-ttu-id="30af0-102">BAM 工作流</span><span class="sxs-lookup"><span data-stu-id="30af0-102">BAM Workflow</span></span>
<span data-ttu-id="30af0-103">下图显示了使用业务活动监视的 4 个用户角色，以及他们使用的工具。</span><span class="sxs-lookup"><span data-stu-id="30af0-103">The following figure shows the four user roles who work with Business Activity Monitoring, and the tools that they use.</span></span>  
  
 <span data-ttu-id="30af0-104">![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")</span><span class="sxs-lookup"><span data-stu-id="30af0-104">![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")</span></span>  
<span data-ttu-id="30af0-105">BAM 角色</span><span class="sxs-lookup"><span data-stu-id="30af0-105">BAM Roles</span></span>  
  
 <span data-ttu-id="30af0-106">以下步骤对用于使用业务活动监视的工作流进行了高级概述。</span><span class="sxs-lookup"><span data-stu-id="30af0-106">The following steps provide a high-level overview of the workflow for using Business Activity Monitoring.</span></span>  
  
## <a name="specifying-the-business-data-to-collect"></a><span data-ttu-id="30af0-107">指定要收集的业务数据</span><span class="sxs-lookup"><span data-stu-id="30af0-107">Specifying the business data to collect</span></span>  
 <span data-ttu-id="30af0-108">按以下方式收集业务数据：</span><span class="sxs-lookup"><span data-stu-id="30af0-108">Business data is collected in the following manner:</span></span>  
  
-   <span data-ttu-id="30af0-109">业务分析员使用“BAM 活动向导”来指定要收集所有业务用户的哪些数据。</span><span class="sxs-lookup"><span data-stu-id="30af0-109">The business analyst uses the BAM Activity Wizard to specify what data to collect for all business users.</span></span>  
  
-   <span data-ttu-id="30af0-110">业务分析员使用“BAM 视图向导”来定义业务用户的每个类别的视图。</span><span class="sxs-lookup"><span data-stu-id="30af0-110">The business analyst uses the BAM View Wizard to define the view for each category of business user.</span></span>  
  
-   <span data-ttu-id="30af0-111">完成后，他将这些活动和视图保存在一个名为“BAM 定义工作簿”的 Microsoft® Excel 工作簿中。</span><span class="sxs-lookup"><span data-stu-id="30af0-111">When finished, he saves the activities and views in a Microsoft® Excel Workbook called the BAM Definition Workbook.</span></span>  
  
-   <span data-ttu-id="30af0-112">业务分析员将 BAM 定义工作簿导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="30af0-112">The business analyst exports the BAM Definition Workbook to XML.</span></span>  
  
-   <span data-ttu-id="30af0-113">系统管理员和开发人员使用该 XML 文件来执行他们的角色。</span><span class="sxs-lookup"><span data-stu-id="30af0-113">The system administrator and developer use the XML to perform their roles.</span></span>  
  
-   <span data-ttu-id="30af0-114">有关使用 BAM 定义工作簿的说明位于[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="30af0-114">Instructions for using the BAM Definition Workbook are located in [Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
## <a name="managing-the-bam-infrastructure"></a><span data-ttu-id="30af0-115">管理 BAM 基础结构</span><span class="sxs-lookup"><span data-stu-id="30af0-115">Managing the BAM Infrastructure</span></span>  
 <span data-ttu-id="30af0-116">业务分析员定义了其所需的 BAM 视图后，系统管理员使用 BAM 管理实用程序（即 BM.EXE，它是一个命令行工具）根据 BAM 定义工作簿或从该工作簿导出的 XML 文件来部署 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="30af0-116">After the business analyst has defined the BAM view he wants, the system administrator uses the BAM management utility (BM.EXE), a command-line tool, to deploy the BAM infrastructure from the BAM Definition Workbook or the XML exported from the workbook.</span></span>  
  
 <span data-ttu-id="30af0-117">BAM 管理实用程序动态创建支持 BAM 视图所需的表、触发器、DTS 包，以及 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="30af0-117">The BAM management utility dynamically creates the tables, triggers, DTS packages, and OLAP cubes necessary to support the BAM view.</span></span>  
  
 <span data-ttu-id="30af0-118">每当业务分析员定义其他 BAM 视图或更改现有 BAM 视图时，系统管理员都必须重新部署 BAM 定义工作簿。</span><span class="sxs-lookup"><span data-stu-id="30af0-118">Each time the business analyst defines a different BAM view, or changes an existing BAM view, the system administrator must redeploy the BAM Definition Workbook.</span></span>  
  
## <a name="mapping-the-xml-to-an-orchestration"></a><span data-ttu-id="30af0-119">将 XML 文件映射到业务流程</span><span class="sxs-lookup"><span data-stu-id="30af0-119">Mapping the XML to an orchestration</span></span>  
 <span data-ttu-id="30af0-120">业务分析员将 BAM 定义工作簿导出到 XML 文件后，开发人员将该 XML 文件导入到跟踪配置文件编辑器中。</span><span class="sxs-lookup"><span data-stu-id="30af0-120">After the business analyst exports the BAM Definition Workbook to XML, the developer imports the XML file into the Tracking Profile Editor.</span></span> <span data-ttu-id="30af0-121">然后，开发人员实现业务分析员的信息要求，并将 XML 文件映射到业务流程。</span><span class="sxs-lookup"><span data-stu-id="30af0-121">The developer implements the business analyst's information requirements, mapping the XML to an orchestration.</span></span>  
  
 <span data-ttu-id="30af0-122">使用跟踪配置文件编辑器，开发人员可以执行以下步骤将 XML 文件映射到业务流程：</span><span class="sxs-lookup"><span data-stu-id="30af0-122">Using the Tracking Profile Editor, the developer performs the following steps to map the XML to an orchestration:</span></span>  
  
- <span data-ttu-id="30af0-123">加载存储在 BizTalk 管理数据库（又称为配置数据库）中的已部署程序集。</span><span class="sxs-lookup"><span data-stu-id="30af0-123">Loads the deployed assembly that is stored in the BizTalk Management database (also known as the Configuration database).</span></span> <span data-ttu-id="30af0-124">该已部署程序集包含与业务分析员在上面的第 1 步中指定的要求相对应的一个或多个业务流程。</span><span class="sxs-lookup"><span data-stu-id="30af0-124">The deployed assembly contains one or more orchestrations corresponding to the requirements that the business analyst specified in Step 1 above.</span></span>  
  
- <span data-ttu-id="30af0-125">定义要从业务流程中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="30af0-125">Defines the data to be extracted from an orchestration.</span></span> <span data-ttu-id="30af0-126">为此，您可以将消息架构和业务流程形状中的项放到相应的业务里程碑（事件）和数据项文件夹中。</span><span class="sxs-lookup"><span data-stu-id="30af0-126">You do this by dropping items from the message schemas and orchestration shapes into the appropriate business milestone (event) and data item folders.</span></span>  
  
- <span data-ttu-id="30af0-127">完成后，开发人员将配置文件另存为 BizTalk® Server 跟踪文件 (.btt)，存放到某个存储数据库中，例如 Visual SourceSafe。</span><span class="sxs-lookup"><span data-stu-id="30af0-127">When he is finished, he saves the profile as a BizTalk® Server tracking (.btt) file, to a storage database such as Visual SourceSafe.</span></span>  
  
  <span data-ttu-id="30af0-128">开发人员将该 .btt 文件部署到测试数据库，然后通过集成测试来验证结果。</span><span class="sxs-lookup"><span data-stu-id="30af0-128">The developer deploys the .btt file to a testing database, and verifies the result through integration testing.</span></span>  
  
## <a name="deploying-the-tracking-profile"></a><span data-ttu-id="30af0-129">部署跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="30af0-129">Deploying the Tracking Profile</span></span>  
 <span data-ttu-id="30af0-130">使用跟踪配置文件编辑器，系统管理员可以将配置文件部署到一个或多个 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="30af0-130">Using the Tracking Profile Editor, the system administrator deploys the profile to one or more BizTalk Management databases.</span></span>  
  
 <span data-ttu-id="30af0-131">每当开发人员更改业务流程时，或业务用户的要求发生变化并且他们要跟踪更多数据时，系统管理员都需要使用 bttdeploy.exe 命令行实用工具重新部署跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="30af0-131">Each time the developer changes the orchestration, or the requirements of the business users change and they want to track more data, the system administrator needs to redeploy the tracking profile using the bttdeploy.exe command line utility.</span></span>  
  
## <a name="viewing-the-business-data"></a><span data-ttu-id="30af0-132">查看业务数据</span><span class="sxs-lookup"><span data-stu-id="30af0-132">Viewing the business data</span></span>  
 <span data-ttu-id="30af0-133">业务用户使用 _LiveData 工作簿，该工作簿是由 BM.exe 实用工具生成的。</span><span class="sxs-lookup"><span data-stu-id="30af0-133">The business user uses the _LiveData workbook, which is produced by the BM.exe utility.</span></span> <span data-ttu-id="30af0-134">每当业务用户打开 _LiveData 工作簿时，他都会收到为监视业务流程的特定方面而收集的数据的实时版本。</span><span class="sxs-lookup"><span data-stu-id="30af0-134">Each time the business user opens the _LiveData workbook, he receives a new live version of the data that is collected to monitor a specific aspect of the business process.</span></span>  
  
-   <span data-ttu-id="30af0-135">若要查看被定义为实时聚合的数据，业务用户只需单击**刷新**要查看的数据的工作簿中。</span><span class="sxs-lookup"><span data-stu-id="30af0-135">To view data that is defined as real-time aggregation, the business user just needs to click **Refresh** in the workbook to view the data.</span></span>  
  
-   <span data-ttu-id="30af0-136">如果聚合数据不是实时的，则业务用户看到的是在计划的 DTS 包运行时拍摄的业务数据快照。</span><span class="sxs-lookup"><span data-stu-id="30af0-136">If the aggregation data is not real-time, the business user views a snapshot of the business data that is taken at the time that the scheduled DTS package runs.</span></span>  
  
-   <span data-ttu-id="30af0-137">如果您的组织有协作要求，业务用户可以从 BAS Web 站点访问实时数据。</span><span class="sxs-lookup"><span data-stu-id="30af0-137">If your organization has collaboration requirements, the business user can access the live data from the BAS Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30af0-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="30af0-138">See Also</span></span>  
 <span data-ttu-id="30af0-139">[在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="30af0-139">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="30af0-140">使用 BAM 监视业务活动</span><span class="sxs-lookup"><span data-stu-id="30af0-140">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)