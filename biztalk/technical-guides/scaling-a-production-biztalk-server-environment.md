---
title: 缩放生产 BizTalk Server 环境 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a972b983-5ec5-4a2a-934f-b2788ccd424e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6dfd90864f6698c54558c65aa3a87b96c0459c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302949"
---
# <a name="scaling-a-production-biztalk-server-environment"></a><span data-ttu-id="dc3d1-102">缩放生产 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="dc3d1-102">Scaling a Production BizTalk Server Environment</span></span>
<span data-ttu-id="dc3d1-103">本部分提供用于执行负载测试的 BizTalk Server 解决方案，负载测试结果和常规观测结果和建议基于在实验室中发现的摘要的实验室环境的概述。</span><span class="sxs-lookup"><span data-stu-id="dc3d1-103">This section provides an overview of the lab environment that was used to perform load testing of a BizTalk Server solution, a summary of the load test results, and general observations and recommendations based upon the findings in the lab.</span></span>  
  
 <span data-ttu-id="dc3d1-104">这些主题中提供的信息可以和应作为指南使用缩放你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="dc3d1-104">The information provided in these topics can and should be used as a guide for scaling your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="dc3d1-105">除了本指南，我们建议你先完成定期负载测试时在整个开发周期的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc3d1-105">In addition to this guidance we recommend that you complete periodic load testing throughout the development cycle of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc3d1-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="dc3d1-106">In This Section</span></span>  
  
-   [<span data-ttu-id="dc3d1-107">方案概述</span><span class="sxs-lookup"><span data-stu-id="dc3d1-107">Scenario Overview</span></span>](../technical-guides/scenario-overview.md)  
  
-   [<span data-ttu-id="dc3d1-108">关键绩效指标</span><span class="sxs-lookup"><span data-stu-id="dc3d1-108">Key Performance Indicators</span></span>](../technical-guides/key-performance-indicators.md)  
  
-   [<span data-ttu-id="dc3d1-109">观察值和建议</span><span class="sxs-lookup"><span data-stu-id="dc3d1-109">Observations and Recommendations</span></span>](../technical-guides/observations-and-recommendations.md)