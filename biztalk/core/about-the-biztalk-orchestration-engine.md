---
title: 关于 BizTalk 业务流程引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5ba658a0df6675992601ecb55796e606791b6af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362305"
---
# <a name="about-the-biztalk-orchestration-engine"></a><span data-ttu-id="8999d-102">关于 BizTalk 业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="8999d-102">About the BizTalk Orchestration Engine</span></span>
<span data-ttu-id="8999d-103">在运行时，BizTalk 业务流程引擎执行 BizTalk 业务流程设计器生成的 XLANG/s 文件。</span><span class="sxs-lookup"><span data-stu-id="8999d-103">At run time, the BizTalk Orchestration Engine executes XLANG/s files that are produced by BizTalk Orchestration Designer.</span></span> <span data-ttu-id="8999d-104">业务流程设计器是用于以可视方式设计业务流程的丰富图形工具。</span><span class="sxs-lookup"><span data-stu-id="8999d-104">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="8999d-105">它将生成 XLANG/s 文件具有.odx 扩展名，并包含其标头中的其他可视化效果信息和在其主体的自定义特性信息。</span><span class="sxs-lookup"><span data-stu-id="8999d-105">It generates XLANG/s files that have an .odx extension and contain additional visualization information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8999d-106">XLANG/s 可被视为的表达式功能的某些消息传递语言C#。</span><span class="sxs-lookup"><span data-stu-id="8999d-106">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span>  
  
 <span data-ttu-id="8999d-107">业务流程引擎的主要功能是：</span><span class="sxs-lookup"><span data-stu-id="8999d-107">The primary functions of the orchestration engine are:</span></span>  
  
-   <span data-ttu-id="8999d-108">暂留</span><span class="sxs-lookup"><span data-stu-id="8999d-108">Persistence</span></span>  
  
-   <span data-ttu-id="8999d-109">托管.NET 组件</span><span class="sxs-lookup"><span data-stu-id="8999d-109">Hosting the .NET components</span></span>  
  
-   <span data-ttu-id="8999d-110">事务</span><span class="sxs-lookup"><span data-stu-id="8999d-110">Transactions</span></span>  
  
-   <span data-ttu-id="8999d-111">支持大消息</span><span class="sxs-lookup"><span data-stu-id="8999d-111">Large message support</span></span>  
  
-   <span data-ttu-id="8999d-112">运行时验证</span><span class="sxs-lookup"><span data-stu-id="8999d-112">Runtime validation</span></span>  
  
-   <span data-ttu-id="8999d-113">加载阻止</span><span class="sxs-lookup"><span data-stu-id="8999d-113">Load throttling</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8999d-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="8999d-114">In This Section</span></span>  
  
-   [<span data-ttu-id="8999d-115">持久化和业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="8999d-115">Persistence and the Orchestration Engine</span></span>](../core/persistence-and-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="8999d-116">业务流程冻结和解除冻结</span><span class="sxs-lookup"><span data-stu-id="8999d-116">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [<span data-ttu-id="8999d-117">业务流程引擎的运行时验证</span><span class="sxs-lookup"><span data-stu-id="8999d-117">Runtime Validation for the Orchestration Engine</span></span>](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="8999d-118">业务流程引擎配置</span><span class="sxs-lookup"><span data-stu-id="8999d-118">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="8999d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8999d-119">See Also</span></span>  
 <span data-ttu-id="8999d-120">[BizTalk Server 体系结构](../core/biztalk-server-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="8999d-120">[BizTalk Server Architecture](../core/biztalk-server-architecture.md) </span></span>  
 <span data-ttu-id="8999d-121">[XLANG-s 语言](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="8999d-121">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="8999d-122">[通过主机阻止优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md) </span><span class="sxs-lookup"><span data-stu-id="8999d-122">[Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) </span></span>  
 [<span data-ttu-id="8999d-123">BizTalk Server 如何处理大消息</span><span class="sxs-lookup"><span data-stu-id="8999d-123">How BizTalk Server Processes Large Messages</span></span>](../core/how-biztalk-server-processes-large-messages.md)