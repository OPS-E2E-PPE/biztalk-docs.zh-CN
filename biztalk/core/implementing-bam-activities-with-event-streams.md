---
title: 实现通过事件流的 BAM 活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f64b52fe6985da2f5f83cabe77fc3841c1a4db8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382621"
---
# <a name="implementing-bam-activities-with-event-streams"></a><span data-ttu-id="49d1d-102">与事件流实现 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="49d1d-102">Implementing BAM Activities with Event Streams</span></span>
<span data-ttu-id="49d1d-103">BAM 活动代表在企业中，如采购订单或贷款申请的工作单元。</span><span class="sxs-lookup"><span data-stu-id="49d1d-103">A BAM activity represents a unit of work in the business, such as purchase order or loan application.</span></span> <span data-ttu-id="49d1d-104">活动向业务最终用户或信息工作者显示历史记录 （里程碑） 和有关此工作单位的数据。</span><span class="sxs-lookup"><span data-stu-id="49d1d-104">The activity shows the history (milestones) and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="49d1d-105">例如，贷款申请活动可能包含如"贷款已批准"的里程碑和数据，如"申请人姓名"和"贷款金额"。</span><span class="sxs-lookup"><span data-stu-id="49d1d-105">For example, a loan application activity might contain milestones such as “Loan approved” and data such as “Applicant name” and “Loan amount.”</span></span> <span data-ttu-id="49d1d-106">BAM 活动常常直接映射到业务流程，尽管作为高级抽象活动是独立于你的 IT 基础结构的实际实现。</span><span class="sxs-lookup"><span data-stu-id="49d1d-106">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="49d1d-107">您作为开发人员的工作是通过公开的相关里程碑和上下文中的特定活动的实现中的数据来保持这种抽象。</span><span class="sxs-lookup"><span data-stu-id="49d1d-107">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span> <span data-ttu-id="49d1d-108">有关演示如何将活动的代码示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="49d1d-108">For a code sample that demonstrates the use of an activity, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49d1d-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="49d1d-109">In This Section</span></span>  
  
-   [<span data-ttu-id="49d1d-110">为什么为 BAM 编写代码？</span><span class="sxs-lookup"><span data-stu-id="49d1d-110">Why Write Code For BAM?</span></span>](../core/why-write-code-for-bam.md)  
  
-   [<span data-ttu-id="49d1d-111">适用于开发人员的 BAM 概念</span><span class="sxs-lookup"><span data-stu-id="49d1d-111">BAM Concepts for the Developer</span></span>](../core/bam-concepts-for-the-developer.md)  
  
-   [<span data-ttu-id="49d1d-112">BAM 开发过程概述</span><span class="sxs-lookup"><span data-stu-id="49d1d-112">Overview of the BAM Development Process</span></span>](../core/overview-of-the-bam-development-process.md)  
  
-   [<span data-ttu-id="49d1d-113">EventStream 类</span><span class="sxs-lookup"><span data-stu-id="49d1d-113">EventStream Classes</span></span>](../core/eventstream-classes.md)  
  
-   [<span data-ttu-id="49d1d-114">通过使用活动</span><span class="sxs-lookup"><span data-stu-id="49d1d-114">Using an Activity</span></span>](../core/using-an-activity.md)  
  
-   [<span data-ttu-id="49d1d-115">活动关系</span><span class="sxs-lookup"><span data-stu-id="49d1d-115">Activity Relationships</span></span>](../core/activity-relationships.md)  
  
-   [<span data-ttu-id="49d1d-116">活动延续</span><span class="sxs-lookup"><span data-stu-id="49d1d-116">Activity Continuation</span></span>](../core/activity-continuation.md)  
  
-   [<span data-ttu-id="49d1d-117">循环活动</span><span class="sxs-lookup"><span data-stu-id="49d1d-117">Looping Activities</span></span>](../core/looping-activities.md)  
  
-   [<span data-ttu-id="49d1d-118">检测解决方案：分步 API 使用情况</span><span class="sxs-lookup"><span data-stu-id="49d1d-118">Instrumenting a Solution: Step-by-Step API Usage</span></span>](../core/instrumenting-a-solution-step-by-step-api-usage.md)