---
title: "管理 BAM 定义 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions]
- definitions [BAM], managing
- definition files [BAM], managing
- managing [BAM], definitions
- managing [BAM definitions], about managing BAM definitions
ms.assetid: 7aba0e40-b8d3-4afc-9e4c-92392f1f6269
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93cf3d280d0e615442a4141b7fa41f6ee3566490
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-definitions"></a><span data-ttu-id="3b9d7-102">管理 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="3b9d7-102">Managing BAM Definitions</span></span>
<span data-ttu-id="3b9d7-103">BAM 定义是 BAM 基础结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="3b9d7-103">A BAM definition is part of the BAM infrastructure.</span></span> <span data-ttu-id="3b9d7-104">它定义要跟踪和聚合的数据，以及所跟踪数据的业务最终用户视图。</span><span class="sxs-lookup"><span data-stu-id="3b9d7-104">It defines the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="3b9d7-105">本部分的主题介绍管理 BAM 定义的各个元素（包括活动、视图、项目和警报）的过程。</span><span class="sxs-lookup"><span data-stu-id="3b9d7-105">The topics in this section give procedures for managing the elements of BAM definitions, which include activities, views, artifacts, and alerts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b9d7-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="3b9d7-106">In This Section</span></span>  
  
-   [<span data-ttu-id="3b9d7-107">管理 BAM 定义文件所需的用户权限</span><span class="sxs-lookup"><span data-stu-id="3b9d7-107">Required User Rights for Managing BAM Definition Files</span></span>](../core/required-user-rights-for-managing-bam-definition-files.md)  
  
-   [<span data-ttu-id="3b9d7-108">如何部署 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="3b9d7-108">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)  
  
-   [<span data-ttu-id="3b9d7-109">如何删除 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="3b9d7-109">How to Remove BAM Definitions</span></span>](../core/how-to-remove-bam-activities.md)  
  
-   [<span data-ttu-id="3b9d7-110">如何列出对 BAM 基础结构的更改</span><span class="sxs-lookup"><span data-stu-id="3b9d7-110">How to List Changes to the BAM Infrastructure</span></span>](../core/how-to-list-changes-to-the-bam-infrastructure.md)  
  
-   [<span data-ttu-id="3b9d7-111">如何列出 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="3b9d7-111">How to List BAM Activities</span></span>](../core/how-to-list-bam-activities.md)  
  
-   [<span data-ttu-id="3b9d7-112">如何删除 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="3b9d7-112">How to Remove BAM Activities</span></span>](../core/how-to-remove-bam-activities.md)  
  
-   [<span data-ttu-id="3b9d7-113">如何列出 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="3b9d7-113">How to List BAM Views</span></span>](../core/how-to-list-bam-views.md)  
  
-   [<span data-ttu-id="3b9d7-114">如何删除 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="3b9d7-114">How to Remove BAM Views</span></span>](../core/how-to-remove-bam-views.md)  
  
-   [<span data-ttu-id="3b9d7-115">如何启用警报</span><span class="sxs-lookup"><span data-stu-id="3b9d7-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)  
  
-   [<span data-ttu-id="3b9d7-116">如何禁用警报</span><span class="sxs-lookup"><span data-stu-id="3b9d7-116">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="3b9d7-117">如何删除 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="3b9d7-117">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
-   [<span data-ttu-id="3b9d7-118">如何更新 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="3b9d7-118">How to Update BAM Artifacts</span></span>](../core/how-to-update-bam-artifacts.md)  
  
-   [<span data-ttu-id="3b9d7-119">如何删除已部署的项目</span><span class="sxs-lookup"><span data-stu-id="3b9d7-119">How to Remove Deployed Artifacts</span></span>](../core/how-to-remove-deployed-artifacts.md)  
  
-   [<span data-ttu-id="3b9d7-120">配置 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="3b9d7-120">Configuring BAM Alerts</span></span>](../core/configuring-bam-alerts.md)  
  
-   [<span data-ttu-id="3b9d7-121">管理 BAM 警报执行</span><span class="sxs-lookup"><span data-stu-id="3b9d7-121">Managing BAM Alert Execution</span></span>](../core/managing-bam-alert-execution.md)  
  
-   [<span data-ttu-id="3b9d7-122">如何更改计算的警报的频率</span><span class="sxs-lookup"><span data-stu-id="3b9d7-122">How to Change the Frequency With Which Alerts Are Evaluated</span></span>](../core/how-to-change-the-frequency-with-which-alerts-are-evaluated.md)