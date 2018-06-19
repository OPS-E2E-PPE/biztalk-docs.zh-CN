---
title: 实现事件流 BAM 活动 |Microsoft 文档
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
ms.openlocfilehash: 63594b956affc0f5b94f26ccdcb10d904ef171cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257341"
---
# <a name="implementing-bam-activities-with-event-streams"></a><span data-ttu-id="a6586-102">实现事件流 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="a6586-102">Implementing BAM Activities with Event Streams</span></span>
<span data-ttu-id="a6586-103">BAM 活动表示业务，例如采购订单或贷款应用程序中的工作单元。</span><span class="sxs-lookup"><span data-stu-id="a6586-103">A BAM activity represents a unit of work in the business, such as purchase order or loan application.</span></span> <span data-ttu-id="a6586-104">活动向业务最终用户或信息工作者显示有关此工作单位的历史记录（里程碑）和数据。</span><span class="sxs-lookup"><span data-stu-id="a6586-104">The activity shows the history (milestones) and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="a6586-105">例如，贷款申请活动可能包含里程碑（如“贷款已批准”）和数据（如“申请人姓名”和“贷款金额”）。</span><span class="sxs-lookup"><span data-stu-id="a6586-105">For example, a loan application activity might contain milestones such as “Loan approved” and data such as “Applicant name” and “Loan amount.”</span></span> <span data-ttu-id="a6586-106">BAM 活动常常直接映射到业务流程，尽管作为高级抽象概念，活动独立于 IT 基础结构的实际实现。</span><span class="sxs-lookup"><span data-stu-id="a6586-106">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="a6586-107">开发人员可以只在特定活动的上下文公开实现的相关里程碑和数据，以此来维护这种抽象概念。</span><span class="sxs-lookup"><span data-stu-id="a6586-107">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span> <span data-ttu-id="a6586-108">有关演示如何使用活动的代码示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a6586-108">For a code sample that demonstrates the use of an activity, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6586-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="a6586-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a6586-110">为什么为 BAM 编写代码？</span><span class="sxs-lookup"><span data-stu-id="a6586-110">Why Write Code For BAM?</span></span>](../core/why-write-code-for-bam.md)  
  
-   [<span data-ttu-id="a6586-111">开发人员的 BAM 概念</span><span class="sxs-lookup"><span data-stu-id="a6586-111">BAM Concepts for the Developer</span></span>](../core/bam-concepts-for-the-developer.md)  
  
-   [<span data-ttu-id="a6586-112">BAM 开发过程概述</span><span class="sxs-lookup"><span data-stu-id="a6586-112">Overview of the BAM Development Process</span></span>](../core/overview-of-the-bam-development-process.md)  
  
-   [<span data-ttu-id="a6586-113">EventStream 类</span><span class="sxs-lookup"><span data-stu-id="a6586-113">EventStream Classes</span></span>](../core/eventstream-classes.md)  
  
-   [<span data-ttu-id="a6586-114">使用活动</span><span class="sxs-lookup"><span data-stu-id="a6586-114">Using an Activity</span></span>](../core/using-an-activity.md)  
  
-   [<span data-ttu-id="a6586-115">活动关系</span><span class="sxs-lookup"><span data-stu-id="a6586-115">Activity Relationships</span></span>](../core/activity-relationships.md)  
  
-   [<span data-ttu-id="a6586-116">活动延续</span><span class="sxs-lookup"><span data-stu-id="a6586-116">Activity Continuation</span></span>](../core/activity-continuation.md)  
  
-   [<span data-ttu-id="a6586-117">循环的活动</span><span class="sxs-lookup"><span data-stu-id="a6586-117">Looping Activities</span></span>](../core/looping-activities.md)  
  
-   [<span data-ttu-id="a6586-118">在插入检测点解决方案： 分步 API 使用情况</span><span class="sxs-lookup"><span data-stu-id="a6586-118">Instrumenting a Solution: Step-by-Step API Usage</span></span>](../core/instrumenting-a-solution-step-by-step-api-usage.md)