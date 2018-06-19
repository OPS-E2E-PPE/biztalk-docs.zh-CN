---
title: BAM 动态基础结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3660eeb6f85fb21ff78b7b833b21adbb3af87385
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230445"
---
# <a name="bam-dynamic-infrastructure"></a><span data-ttu-id="6bda6-102">BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="6bda6-102">BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="6bda6-103">BAM 基础结构包含的 SQL Server 表、 BAM 视图、 存储的过程和作为配置和通过增量托管的 BAM 数据库 （主导入、 存档、 星型架构和分析） 中的数据转换服务 (DTS) 包部署的 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="6bda6-103">The BAM infrastructure consists of SQL Server tables, BAM views, stored procedures, and Data Transformation Services (DTS) packages in the BAM databases (Primary Import, Archive, Star Schema, and Analysis) as configured and managed through incremental deployments of BAM definitions.</span></span> <span data-ttu-id="6bda6-104">基础结构是其中，在运行时，事件是关联、 聚合，并且之后可用于查询的用户。</span><span class="sxs-lookup"><span data-stu-id="6bda6-104">The infrastructure is where, at run time, events are correlated, aggregated, and then made available for querying by users.</span></span>  
  
 <span data-ttu-id="6bda6-105">本部分介绍一些基础结构流程。</span><span class="sxs-lookup"><span data-stu-id="6bda6-105">This section describes some of these infrastructure processes.</span></span> <span data-ttu-id="6bda6-106">例如，从应用程序（BAM 定义）提取目标数据后，可以将其存储以便进行查询。</span><span class="sxs-lookup"><span data-stu-id="6bda6-106">For example, once you extract the data of interest from your applications (the BAM definition), you can store it so that it is available for queries.</span></span> <span data-ttu-id="6bda6-107">此外，可以维护预先创建的特定数据聚合，以使聚合查询更加迅速。</span><span class="sxs-lookup"><span data-stu-id="6bda6-107">Additionally, you can maintain certain pre-created aggregations of the data for faster aggregated queries.</span></span>  
  
 <span data-ttu-id="6bda6-108">通常，需要在实现数据仓库方面进行广泛的开发工作才能实现此功能。</span><span class="sxs-lookup"><span data-stu-id="6bda6-108">Typically, you achieve such functionality by an extensive development effort to implement a data warehouse.</span></span> <span data-ttu-id="6bda6-109">但是，Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 BAM 大大简化了此过程，因为其基于活动和视图定义自动生成 SQL 和 OLAP 基础结构。</span><span class="sxs-lookup"><span data-stu-id="6bda6-109">BAM in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] greatly simplifies this process, however, by automatically generating the SQL and OLAP infrastructure based on your activity and view definitions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6bda6-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="6bda6-110">In This Section</span></span>  
  
-   [<span data-ttu-id="6bda6-111">BAM 定义是什么？</span><span class="sxs-lookup"><span data-stu-id="6bda6-111">What Is a BAM Definition?</span></span>](../core/what-is-a-bam-definition.md)  
  
-   [<span data-ttu-id="6bda6-112">什么是 BAM 定义架构？</span><span class="sxs-lookup"><span data-stu-id="6bda6-112">What Is a BAM Definition Schema?</span></span>](../core/what-is-a-bam-definition-schema.md)  
  
-   [<span data-ttu-id="6bda6-113">活动数据存储</span><span class="sxs-lookup"><span data-stu-id="6bda6-113">Activity Data Storage</span></span>](../core/activity-data-storage.md)  
  
-   [<span data-ttu-id="6bda6-114">聚合是什么？</span><span class="sxs-lookup"><span data-stu-id="6bda6-114">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)  
  
-   [<span data-ttu-id="6bda6-115">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="6bda6-115">Querying BAM Data</span></span>](../core/querying-bam-data.md)  
  
-   [<span data-ttu-id="6bda6-116">BAM 基础结构限制</span><span class="sxs-lookup"><span data-stu-id="6bda6-116">BAM Infrastructure Limitations</span></span>](../core/bam-infrastructure-limitations.md)  
  
-   [<span data-ttu-id="6bda6-117">如何在非英语安装中定义的范围外数值维度警报</span><span class="sxs-lookup"><span data-stu-id="6bda6-117">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)