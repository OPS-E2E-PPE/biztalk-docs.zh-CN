---
title: "有关 BizTalk 业务流程引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4e686f066c2fcde921e45d08b60d6386e86640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-biztalk-orchestration-engine"></a><span data-ttu-id="ef9a1-102">关于 BizTalk 业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="ef9a1-102">About the BizTalk Orchestration Engine</span></span>
<span data-ttu-id="ef9a1-103">在运行时，BizTalk 业务流程引擎执行 BizTalk 业务流程设计器生成的 XLANG/s 文件。</span><span class="sxs-lookup"><span data-stu-id="ef9a1-103">At run time, the BizTalk Orchestration Engine executes XLANG/s files that are produced by BizTalk Orchestration Designer.</span></span> <span data-ttu-id="ef9a1-104">业务流程设计器是用于以可视方式设计业务流程的丰富图形工具。</span><span class="sxs-lookup"><span data-stu-id="ef9a1-104">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="ef9a1-105">它可以生成 XLANG/s 文件，这些文件具有 .odx 扩展名，在其标头中包含其他直观信息，同时在其主体中包含自定义的属性信息。</span><span class="sxs-lookup"><span data-stu-id="ef9a1-105">It generates XLANG/s files that have an .odx extension and contain additional visualization information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef9a1-106">作为消息传递使用的某些表达式功能的 C# 语言，可以查看 XLANG/s。</span><span class="sxs-lookup"><span data-stu-id="ef9a1-106">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span>  
  
 <span data-ttu-id="ef9a1-107">业务流程引擎的主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="ef9a1-107">The primary functions of the orchestration engine are:</span></span>  
  
-   <span data-ttu-id="ef9a1-108">持久化</span><span class="sxs-lookup"><span data-stu-id="ef9a1-108">Persistence</span></span>  
  
-   <span data-ttu-id="ef9a1-109">作为 .NET 组件的宿主</span><span class="sxs-lookup"><span data-stu-id="ef9a1-109">Hosting the .NET components</span></span>  
  
-   <span data-ttu-id="ef9a1-110">中的</span><span class="sxs-lookup"><span data-stu-id="ef9a1-110">Transactions</span></span>  
  
-   <span data-ttu-id="ef9a1-111">大消息支持</span><span class="sxs-lookup"><span data-stu-id="ef9a1-111">Large message support</span></span>  
  
-   <span data-ttu-id="ef9a1-112">运行时验证</span><span class="sxs-lookup"><span data-stu-id="ef9a1-112">Runtime validation</span></span>  
  
-   <span data-ttu-id="ef9a1-113">加载阻止</span><span class="sxs-lookup"><span data-stu-id="ef9a1-113">Load throttling</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef9a1-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="ef9a1-114">In This Section</span></span>  
  
-   [<span data-ttu-id="ef9a1-115">持久性和业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="ef9a1-115">Persistence and the Orchestration Engine</span></span>](../core/persistence-and-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="ef9a1-116">业务流程冻结和 Rehydration</span><span class="sxs-lookup"><span data-stu-id="ef9a1-116">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [<span data-ttu-id="ef9a1-117">业务流程引擎的运行时验证</span><span class="sxs-lookup"><span data-stu-id="ef9a1-117">Runtime Validation for the Orchestration Engine</span></span>](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="ef9a1-118">业务流程引擎配置</span><span class="sxs-lookup"><span data-stu-id="ef9a1-118">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="ef9a1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef9a1-119">See Also</span></span>  
 <span data-ttu-id="ef9a1-120">[BizTalk Server 体系结构](../core/biztalk-server-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="ef9a1-120">[BizTalk Server Architecture](../core/biztalk-server-architecture.md) </span></span>  
 <span data-ttu-id="ef9a1-121">[XLANG-s 语言](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="ef9a1-121">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="ef9a1-122">[通过主机限制的优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md) </span><span class="sxs-lookup"><span data-stu-id="ef9a1-122">[Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) </span></span>  
 [<span data-ttu-id="ef9a1-123">BizTalk Server 如何处理大消息</span><span class="sxs-lookup"><span data-stu-id="ef9a1-123">How BizTalk Server Processes Large Messages</span></span>](../core/how-biztalk-server-processes-large-messages.md)