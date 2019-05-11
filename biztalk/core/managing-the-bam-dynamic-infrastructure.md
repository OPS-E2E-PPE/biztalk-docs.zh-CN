---
title: 管理 BAM 动态基础结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40b0ef23d013149f7f01efe6f0157ce98b856f2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380184"
---
# <a name="managing-the-bam-dynamic-infrastructure"></a><span data-ttu-id="98c03-102">管理 BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="98c03-102">Managing the BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="98c03-103">业务活动监视 (BAM) 功能使用动态生成的 SQL 和联机分析处理 (OLAP) 基础结构。</span><span class="sxs-lookup"><span data-stu-id="98c03-103">Business Activity Monitoring (BAM) features use a dynamically generated SQL and online analytical processing (OLAP) infrastructure.</span></span> <span data-ttu-id="98c03-104">管理员使用 BAM 管理实用程序来部署 BAM 定义工作簿或 XML 文件，业务分析人员开发。</span><span class="sxs-lookup"><span data-stu-id="98c03-104">Administrators use the BAM Management utility to deploy the BAM definition workbook or XML file, which the business analyst develops.</span></span>  
  
 <span data-ttu-id="98c03-105">BAM 动态基础结构组成的 BAM 工作簿视图、 BAM 部署、 BAM 数据转换服务 (DTS) 包和 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="98c03-105">The BAM dynamic infrastructure consists of the BAM workbook views, BAM deployments, the BAM Data Transformation Services (DTS) packages, and the BAM databases.</span></span> <span data-ttu-id="98c03-106">有关 BAM 动态基础结构的详细信息，请参阅[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="98c03-106">For more information about the BAM dynamic infrastructure, see [BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md).</span></span>  
  
 <span data-ttu-id="98c03-107">配置 BizTalk Server 时，BizTalk Server 将创建以下 BAM 数据库：</span><span class="sxs-lookup"><span data-stu-id="98c03-107">BizTalk Server creates the following BAM databases when you configure BizTalk Server:</span></span>  
  
- <span data-ttu-id="98c03-108">BAM 主导入 (BAMPrimaryImport) 数据库</span><span class="sxs-lookup"><span data-stu-id="98c03-108">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
- <span data-ttu-id="98c03-109">BAM 星型架构 (BAMStarSchema) 数据库 （可选）</span><span class="sxs-lookup"><span data-stu-id="98c03-109">BAM Star Schema (BAMStarSchema) database (optional)</span></span>  
  
- <span data-ttu-id="98c03-110">BAM 分析 (BAMAnalysis) 数据库 （可选）</span><span class="sxs-lookup"><span data-stu-id="98c03-110">BAM Analysis (BAMAnalysis) database (optional)</span></span>  
  
- <span data-ttu-id="98c03-111">BAM 存档 (BAMArchive) 数据库</span><span class="sxs-lookup"><span data-stu-id="98c03-111">BAM Archive (BAMArchive) database</span></span>  
  
  <span data-ttu-id="98c03-112">有关 BAM 数据库的信息，请参阅[管理 BAM 数据库](../core/managing-bam-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="98c03-112">For information about the BAM databases, see [Managing BAM Databases](../core/managing-bam-databases.md).</span></span>  
  
  <span data-ttu-id="98c03-113">管理员执行以下管理任务的 BAM 基础结构，在本部分中所述：</span><span class="sxs-lookup"><span data-stu-id="98c03-113">Administrators perform the following management tasks for the BAM infrastructure, which are described in this section:</span></span>  
  
- <span data-ttu-id="98c03-114">部署和取消部署 BAM 定义和视图</span><span class="sxs-lookup"><span data-stu-id="98c03-114">Deploy and undeploy BAM definitions and views</span></span>  
  
- <span data-ttu-id="98c03-115">管理用户访问权限的 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="98c03-115">Manage user access to BAM views</span></span>  
  
- <span data-ttu-id="98c03-116">运行 BAM DTS 包</span><span class="sxs-lookup"><span data-stu-id="98c03-116">Run the BAM DTS packages</span></span>  
  
- <span data-ttu-id="98c03-117">备份 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="98c03-117">Back up the BAM databases</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98c03-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="98c03-118">In This Section</span></span>  
  
-   [<span data-ttu-id="98c03-119">管理 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="98c03-119">Managing BAM Definitions</span></span>](../core/managing-bam-definitions.md)
  
-   [<span data-ttu-id="98c03-120">管理 BAM 安全性</span><span class="sxs-lookup"><span data-stu-id="98c03-120">Managing BAM Security</span></span>](../core/managing-bam-security.md)  
  
-   [<span data-ttu-id="98c03-121">管理聚合</span><span class="sxs-lookup"><span data-stu-id="98c03-121">Managing Aggregations</span></span>](../core/managing-aggregations.md) 
  
-   [<span data-ttu-id="98c03-122">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="98c03-122">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
  
## <a name="see-also"></a><span data-ttu-id="98c03-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="98c03-123">See Also</span></span>  
 [<span data-ttu-id="98c03-124">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="98c03-124">Managing BAM</span></span>](../core/managing-bam.md)