---
title: BAM WF 侦听器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e459084-cb72-4a75-9f5f-f1fd5fd80d17
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 898d3ebae85e3eadd44e27d7d5cb7f1ff32453b1
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530530"
---
# <a name="bam-wf-interceptor"></a><span data-ttu-id="ae878-102">BAM WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="ae878-102">BAM WF Interceptor</span></span>
<span data-ttu-id="ae878-103">BAM WF 侦听器向 WF 应用程序内的跟踪数据提供全面支持。</span><span class="sxs-lookup"><span data-stu-id="ae878-103">The BAM WF interceptor provides comprehensive support for tracking data within your WF application.</span></span>  
  
 <span data-ttu-id="ae878-104">可将 BAM WF 侦听器用于以下用途：</span><span class="sxs-lookup"><span data-stu-id="ae878-104">You can use the BAM WF interceptor to:</span></span>  
  
-   <span data-ttu-id="ae878-105">透明地将工作流应用程序数据传送给 BAM 而无需重新编译您的 WF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae878-105">Transparently deliver workflow application data to BAM without having to recompile your WF application.</span></span>  
  
-   <span data-ttu-id="ae878-106">针对工作流内的特定活动选择性地将工作流应用程序数据传送给 BAM。</span><span class="sxs-lookup"><span data-stu-id="ae878-106">Target specific activities within a workflow to selectively deliver workflow application data to BAM.</span></span>  
  
-   <span data-ttu-id="ae878-107">采用工作流的事务性语义。</span><span class="sxs-lookup"><span data-stu-id="ae878-107">Honor the transactional semantics of the workflow.</span></span> <span data-ttu-id="ae878-108">仅当拥有事务提交数据时，才会将该数据传送给 BAM。</span><span class="sxs-lookup"><span data-stu-id="ae878-108">Data will be delivered to BAM only if the owning transaction commits.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae878-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="ae878-109">In This Section</span></span>  
  
-   [<span data-ttu-id="ae878-110">如何配置 Workflow Foundation 应用程序用于侦听</span><span class="sxs-lookup"><span data-stu-id="ae878-110">How to Configure a Workflow Foundation Application for Interception</span></span>](../core/how-to-configure-a-workflow-foundation-application-for-interception.md)  
  
-   [<span data-ttu-id="ae878-111">Windows Workflow Foundation 架构</span><span class="sxs-lookup"><span data-stu-id="ae878-111">Windows Workflow Foundation Schema</span></span>](../core/windows-workflow-foundation-schema.md)  
  
-   [<span data-ttu-id="ae878-112">常用事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="ae878-112">Common Event Filter Patterns</span></span>](../core/common-event-filter-patterns.md)  
  
-   [<span data-ttu-id="ae878-113">Windows Workflow Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="ae878-113">Operations in Windows Workflow Foundation</span></span>](../core/operations-in-windows-workflow-foundation.md)