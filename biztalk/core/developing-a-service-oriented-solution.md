---
title: 开发面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, developing
- service solution tutorial, background information
- service solution tutorial, developing
- developing, tutorials
- developing, service solution tutorial
ms.assetid: 7979a05c-7fd3-4476-a623-55de8abdc493
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62bac2f534b5f542f65b316faef7ecbad976dfee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351464"
---
# <a name="developing-a-service-oriented-solution"></a><span data-ttu-id="b1f57-102">开发面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="b1f57-102">Developing a Service Oriented Solution</span></span>
<span data-ttu-id="b1f57-103">面向服务的解决方案演示了 Woodgrove bank 的信用帐户余额系统。</span><span class="sxs-lookup"><span data-stu-id="b1f57-103">The service oriented solution demonstrates a credit account balance system for Woodgrove Bank.</span></span> <span data-ttu-id="b1f57-104">有关帐户的信息来自三个旧系统： 提供信用限额的 SAP 系统、 在大型机上运行的挂起事务系统和使用 MQSeries 的付款跟踪系统。</span><span class="sxs-lookup"><span data-stu-id="b1f57-104">Information about an account comes from three legacy systems: an SAP system that provides the credit limit, a pending transactions system running on a mainframe, and a payment tracking system using MQSeries.</span></span> <span data-ttu-id="b1f57-105">余额检查请求来自 Web 服务或交互式语音应答 (IVR) 系统。</span><span class="sxs-lookup"><span data-stu-id="b1f57-105">Balance check requests come through a Web service or an Interactive Voice Response (IVR) system.</span></span> <span data-ttu-id="b1f57-106">有关方案的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="b1f57-106">For more information about the scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="b1f57-107">此开发人员指南提供了构建面向服务的体系结构解决方案的 Woodgrove Bank 方案的一种方法。</span><span class="sxs-lookup"><span data-stu-id="b1f57-107">This Developer's Guide presents one approach to building a service oriented architecture solution for the Woodgrove Bank scenario.</span></span> <span data-ttu-id="b1f57-108">该指南首先考虑行业标准的模式方面可能的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b1f57-108">The Guide begins by considering a possible solution in terms of industry-standard patterns.</span></span> <span data-ttu-id="b1f57-109">"面向服务的解决方案中的模式"开始该模式的翻译为 BizTalk 应用程序的相应的项目。</span><span class="sxs-lookup"><span data-stu-id="b1f57-109">"Patterns in the Service Oriented Solution" begins the translation of that pattern into the appropriate artifacts of a BizTalk application.</span></span> <span data-ttu-id="b1f57-110">下一步的部分中，"组件的面向服务的解决方案，"汇总了应用程序和它们之间的关系的各个组成部分。</span><span class="sxs-lookup"><span data-stu-id="b1f57-110">The next section, "Components of the Service Oriented Solution," summarizes the various parts of the application and their relationships.</span></span> <span data-ttu-id="b1f57-111">实现重点部分讨论了区域-例如，使用企业单一登录，这是必需的特定工作以满足方案的条件。</span><span class="sxs-lookup"><span data-stu-id="b1f57-111">The Implementation Highlights section discusses areas—such as using Enterprise Single Sign-On—that required special work to meet the criteria of the scenario.</span></span> <span data-ttu-id="b1f57-112">"监视面向服务的解决方案使用 BAM"介绍了该解决方案如何使用 BAM API 来跟踪请求的进度和结果。</span><span class="sxs-lookup"><span data-stu-id="b1f57-112">"Monitoring the Service Oriented Solution with BAM" describes how the solution uses the BAM API to track progress of requests and results.</span></span> <span data-ttu-id="b1f57-113">在"版本控制面向服务的解决方案"和"扩展面向服务的解决方案"部分建议的扩展或修改该解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="b1f57-113">The "Versioning the Service Oriented Solution" and "Scaling the Service Oriented Solution" sections suggest ways of extending or modifying the solution.</span></span> <span data-ttu-id="b1f57-114">参考部分列出了解决方案中的文件，并提供对消息的引用。</span><span class="sxs-lookup"><span data-stu-id="b1f57-114">The reference section lists the files in the solution and provides a reference to the messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1f57-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="b1f57-115">In This Section</span></span>  
  
-   [<span data-ttu-id="b1f57-116">面向服务的解决方案中的模式</span><span class="sxs-lookup"><span data-stu-id="b1f57-116">Patterns in the Service Oriented Solution</span></span>](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b1f57-117">面向服务的解决方案的组件</span><span class="sxs-lookup"><span data-stu-id="b1f57-117">Components of the Service Oriented Solution</span></span>](../core/components-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b1f57-118">面向服务的解决方案的实施要点</span><span class="sxs-lookup"><span data-stu-id="b1f57-118">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b1f57-119">监视面向服务的解决方案使用 BAM</span><span class="sxs-lookup"><span data-stu-id="b1f57-119">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [<span data-ttu-id="b1f57-120">版本控制服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b1f57-120">Versioning the Service Oriented Solution</span></span>](../core/versioning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b1f57-121">扩展面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="b1f57-121">Scaling the Service Oriented Solution</span></span>](../core/scaling-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b1f57-122">面向服务的解决方案参考</span><span class="sxs-lookup"><span data-stu-id="b1f57-122">Service Oriented Solution Reference</span></span>](../core/service-oriented-solution-reference.md)