---
title: 如何定义 BAM 聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- aggregations [BAM], creating
- Excel add-in [BAM], security
- Excel add-in [BAM], creating aggregations
- managing [BAM], creating aggregations
ms.assetid: a5ef3a15-b1de-4099-8e94-64af4b5ec746
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f330e6a4d3dd2525e79ad70b2fcad73217c70c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338931"
---
# <a name="how-to-define-bam-aggregations"></a><span data-ttu-id="929b2-102">如何定义 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="929b2-102">How to Define BAM Aggregations</span></span>
<span data-ttu-id="929b2-103">BAM 支持两种类型的数据聚合：</span><span class="sxs-lookup"><span data-stu-id="929b2-103">BAM supports two types of data aggregation:</span></span>  
  
- <span data-ttu-id="929b2-104">联机分析处理 (OLAP) 聚合</span><span class="sxs-lookup"><span data-stu-id="929b2-104">Online analytical processing (OLAP) aggregations</span></span>  
  
- <span data-ttu-id="929b2-105">实时聚合 (RTA)</span><span class="sxs-lookup"><span data-stu-id="929b2-105">Real-time aggregations (RTA)</span></span>  
  
  <span data-ttu-id="929b2-106">BAM 使用 Microsoft SQL Server Analysis Services 实现 OLAP 聚合。</span><span class="sxs-lookup"><span data-stu-id="929b2-106">BAM uses Microsoft SQL Server Analysis Services to implement OLAP aggregations.</span></span>  
  
  <span data-ttu-id="929b2-107">必须在定义 RTA 的 BAM 主导入数据库上配置触发器。</span><span class="sxs-lookup"><span data-stu-id="929b2-107">You must configure the triggers on the BAM Primary Import database that define RTA.</span></span>  
  
### <a name="to-define-olap-aggregations"></a><span data-ttu-id="929b2-108">若要定义 OLAP 聚合</span><span class="sxs-lookup"><span data-stu-id="929b2-108">To define OLAP aggregations</span></span>  
  
1.  <span data-ttu-id="929b2-109">BAM Excel 工作簿中创建视图、 将至少一个维度和一个度量值添加到数据透视表报表、 清除 RTA 工具栏按钮，然后保存该工作簿。</span><span class="sxs-lookup"><span data-stu-id="929b2-109">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, clear the RTA toolbar button, and then save the workbook.</span></span>  
  
    -   <span data-ttu-id="929b2-110">有关打开 BAM 工作簿的信息，创建视图、 添加维度和度量值，请参阅[定义 BAM 视图](../core/defining-a-bam-view.md)。</span><span class="sxs-lookup"><span data-stu-id="929b2-110">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
2.  <span data-ttu-id="929b2-111">部署工作簿。</span><span class="sxs-lookup"><span data-stu-id="929b2-111">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="929b2-112">若要部署该工作簿，请按照中的说明[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="929b2-112">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="929b2-113">解决方案开发人员可以使用**DirectEventStream**类将事件导入 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="929b2-113">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  
  
    -   <span data-ttu-id="929b2-114">璝惠**DirectEventStream**类，请参阅[DirectEventStream 类](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)。</span><span class="sxs-lookup"><span data-stu-id="929b2-114">For information about the **DirectEventStream** class, see [DirectEventStream Class](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span>  
  
4.  <span data-ttu-id="929b2-115">运行更新多维数据集数据转换服务 (DTS) 包。</span><span class="sxs-lookup"><span data-stu-id="929b2-115">Run the update cube Data Transformation Services (DTS) package.</span></span>  
  
    -   <span data-ttu-id="929b2-116">有关运行更新多维数据集 DTS 包的信息，请参阅[BAM DTS 包](../core/bam-dts-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="929b2-116">For information about running the update cube DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
5.  <span data-ttu-id="929b2-117">打开要查看 OLAP 聚合的工作簿的最新实时数据副本。</span><span class="sxs-lookup"><span data-stu-id="929b2-117">Open the most recent live data copy of the workbook to see the OLAP aggregations.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="929b2-118">出于安全原因，BAM 不删除现有的工作簿的实时数据副本。</span><span class="sxs-lookup"><span data-stu-id="929b2-118">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="929b2-119">相反，BAM 递增实时数据副本的文件名。</span><span class="sxs-lookup"><span data-stu-id="929b2-119">Instead, BAM increments the file name of the live data copy.</span></span>  
  
### <a name="to-define-the-rta"></a><span data-ttu-id="929b2-120">若要定义 RTA</span><span class="sxs-lookup"><span data-stu-id="929b2-120">To define the RTA</span></span>  
  
1.  <span data-ttu-id="929b2-121">BAM Excel 工作簿中创建视图、 将至少一个维度和一个度量值添加到数据透视表报表中，选择 RTA 工具栏按钮，然后保存该工作簿。</span><span class="sxs-lookup"><span data-stu-id="929b2-121">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, select the RTA toolbar button, and then save the workbook.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="929b2-122">未定义使用同一个 BAM 活动的多个 Rta。</span><span class="sxs-lookup"><span data-stu-id="929b2-122">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="929b2-123">如果这样做，RTA 数据将不正确，当您存档 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="929b2-123">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
    -   <span data-ttu-id="929b2-124">有关打开 BAM 工作簿的信息，创建视图、 添加维度和度量值，请参阅"定义业务活动视图"和"定义聚合"中*信息工作者用户指南*。</span><span class="sxs-lookup"><span data-stu-id="929b2-124">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see "Defining a Business Activity View" and "Defining Aggregations" in the *Information Workers User Guide*.</span></span>  
  
2.  <span data-ttu-id="929b2-125">部署工作簿。</span><span class="sxs-lookup"><span data-stu-id="929b2-125">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="929b2-126">若要部署该工作簿，请按照中的说明[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="929b2-126">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="929b2-127">解决方案开发人员可以使用**DirectEventStream**类将事件导入 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="929b2-127">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  

  
4.  <span data-ttu-id="929b2-128">打开工作簿以查看 Rta 的最新的实时数据副本。</span><span class="sxs-lookup"><span data-stu-id="929b2-128">Open the most recent live data copy of the workbook to see the RTAs.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="929b2-129">出于安全原因，BAM 不删除现有的工作簿的实时数据副本。</span><span class="sxs-lookup"><span data-stu-id="929b2-129">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="929b2-130">相反，BAM 递增实时数据副本的文件名。</span><span class="sxs-lookup"><span data-stu-id="929b2-130">Instead, BAM increments the file name of the live data copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929b2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="929b2-131">See Also</span></span>  
 <span data-ttu-id="929b2-132">[BAM DTS 包](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="929b2-132">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 <span data-ttu-id="929b2-133">[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="929b2-133">[How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md) </span></span>  
 <span data-ttu-id="929b2-134">[更新 OLAP 和 RTA 连接字符串属性](../core/updating-olap-and-rta-connection-string-properties.md) </span><span class="sxs-lookup"><span data-stu-id="929b2-134">[Updating OLAP and RTA Connection String Properties](../core/updating-olap-and-rta-connection-string-properties.md) </span></span>  
 [<span data-ttu-id="929b2-135">管理 BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="929b2-135">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)