---
title: BAM 动态基础结构 |Microsoft Docs
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
ms.openlocfilehash: 2ed2c99ad52068d26a1144bb47cf3d247c6456d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358554"
---
# <a name="bam-dynamic-infrastructure"></a><span data-ttu-id="43995-102">BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="43995-102">BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="43995-103">BAM 基础结构包括 SQL Server 表、 BAM 视图、 存储的过程和 BAM 数据库 （主导入、 存档、 星型架构和分析） 配置和管理通过增量中的数据转换服务 (DTS) 包部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="43995-103">The BAM infrastructure consists of SQL Server tables, BAM views, stored procedures, and Data Transformation Services (DTS) packages in the BAM databases (Primary Import, Archive, Star Schema, and Analysis) as configured and managed through incremental deployments of BAM definitions.</span></span> <span data-ttu-id="43995-104">基础结构是位置，在运行时，事件是相关、 聚合，之后可用于查询的用户。</span><span class="sxs-lookup"><span data-stu-id="43995-104">The infrastructure is where, at run time, events are correlated, aggregated, and then made available for querying by users.</span></span>  
  
 <span data-ttu-id="43995-105">本部分介绍一些基础结构流程。</span><span class="sxs-lookup"><span data-stu-id="43995-105">This section describes some of these infrastructure processes.</span></span> <span data-ttu-id="43995-106">例如后从您的应用程序 （BAM 定义） 中提取所需的数据，, 您可以将其存储，这样就可用于查询。</span><span class="sxs-lookup"><span data-stu-id="43995-106">For example, once you extract the data of interest from your applications (the BAM definition), you can store it so that it is available for queries.</span></span> <span data-ttu-id="43995-107">此外，可以维护更快地聚合查询的数据的某些预创建的聚合。</span><span class="sxs-lookup"><span data-stu-id="43995-107">Additionally, you can maintain certain pre-created aggregations of the data for faster aggregated queries.</span></span>  
  
 <span data-ttu-id="43995-108">通常情况下，通过广泛的开发工作来实现数据仓库实现此类功能。</span><span class="sxs-lookup"><span data-stu-id="43995-108">Typically, you achieve such functionality by an extensive development effort to implement a data warehouse.</span></span> <span data-ttu-id="43995-109">Microsoft 中的 BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]极大地简化了此过程中，但是，自动生成基于活动和视图定义的 SQL 和 OLAP 基础结构。</span><span class="sxs-lookup"><span data-stu-id="43995-109">BAM in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] greatly simplifies this process, however, by automatically generating the SQL and OLAP infrastructure based on your activity and view definitions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43995-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="43995-110">In This Section</span></span>  
  
-   [<span data-ttu-id="43995-111">BAM 定义概述</span><span class="sxs-lookup"><span data-stu-id="43995-111">What Is a BAM Definition?</span></span>](../core/what-is-a-bam-definition.md)  
  
-   [<span data-ttu-id="43995-112">BAM 定义架构概述</span><span class="sxs-lookup"><span data-stu-id="43995-112">What Is a BAM Definition Schema?</span></span>](../core/what-is-a-bam-definition-schema.md)  
  
-   [<span data-ttu-id="43995-113">活动数据存储</span><span class="sxs-lookup"><span data-stu-id="43995-113">Activity Data Storage</span></span>](../core/activity-data-storage.md)  
  
-   [<span data-ttu-id="43995-114">聚合概述</span><span class="sxs-lookup"><span data-stu-id="43995-114">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)  
  
-   [<span data-ttu-id="43995-115">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="43995-115">Querying BAM Data</span></span>](../core/querying-bam-data.md)  
  
-   [<span data-ttu-id="43995-116">BAM 基础结构限制</span><span class="sxs-lookup"><span data-stu-id="43995-116">BAM Infrastructure Limitations</span></span>](../core/bam-infrastructure-limitations.md)  
  
-   [<span data-ttu-id="43995-117">如何在非英语系统中定义的范围的数值维度警报</span><span class="sxs-lookup"><span data-stu-id="43995-117">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)