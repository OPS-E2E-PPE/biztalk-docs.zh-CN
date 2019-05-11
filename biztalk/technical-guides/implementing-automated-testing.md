---
title: 实现自动测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ba540e-789d-49bf-af4b-87e6f37ab96f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 800a7070c291048f592f21aefb609f0b15781d05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270457"
---
# <a name="implementing-automated-testing"></a><span data-ttu-id="4c614-102">实现自动测试</span><span class="sxs-lookup"><span data-stu-id="4c614-102">Implementing Automated Testing</span></span>
<span data-ttu-id="4c614-103">BizTalk Server 解决方案通常部署在"任务关键"的情况下，BizTalk 解决方案，是业务的核心组件。</span><span class="sxs-lookup"><span data-stu-id="4c614-103">BizTalk Server solutions are often deployed in “mission-critical” scenarios, whereby the BizTalk solution is a core component of the business.</span></span> <span data-ttu-id="4c614-104">在这些方案、 持续的性能和稳定性的 BizTalk 解决方案是一项关键的业务要求;如果 BizTalk 解决方案失败，关联的停机时间成本都重要。</span><span class="sxs-lookup"><span data-stu-id="4c614-104">In these scenarios, the continual performance and stability of the BizTalk solution is a key business requirement; if the BizTalk solution fails, the associated downtime costs are significant.</span></span> <span data-ttu-id="4c614-105">在这种情况下，是一项极其重要解决方案放入生产环境之前进行全面测试 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="4c614-105">In such scenarios, it is of paramount importance that the BizTalk solution be thoroughly tested before the solution is placed into production.</span></span> <span data-ttu-id="4c614-106">因不测试或无法测试该解决方案的停机时间成本相比，正确测试解决方案的成本要小。</span><span class="sxs-lookup"><span data-stu-id="4c614-106">The costs associated with properly testing the solution are small compared to the downtime costs resulting from not testing or insufficiently testing the solution.</span></span> <span data-ttu-id="4c614-107">因此，BizTalk Server 解决方案的测试可以说是任何 BizTalk Server 解决方案部署的最重要的阶段。</span><span class="sxs-lookup"><span data-stu-id="4c614-107">Therefore, the testing of a BizTalk Server solution is arguably the most important phase of any BizTalk Server solution deployment.</span></span>  
  
 <span data-ttu-id="4c614-108">本部分介绍用于在生产环境中运行该解决方案之前测试 BizTalk 解决方案的正确方法。</span><span class="sxs-lookup"><span data-stu-id="4c614-108">This section describes the proper methodology for testing a BizTalk solution before running the solution in a production environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c614-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="4c614-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4c614-110">测试的重要性</span><span class="sxs-lookup"><span data-stu-id="4c614-110">Why It Is Important to Test</span></span>](../technical-guides/why-it-is-important-to-test.md)  
  
-   [<span data-ttu-id="4c614-111">自动执行生成过程</span><span class="sxs-lookup"><span data-stu-id="4c614-111">Automating the Build Process</span></span>](../technical-guides/automating-the-build-process.md)  
  
-   [<span data-ttu-id="4c614-112">使用 BizUnit 优化自动测试</span><span class="sxs-lookup"><span data-stu-id="4c614-112">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)  
  
-   [<span data-ttu-id="4c614-113">使用 Visual Studio 优化自动测试</span><span class="sxs-lookup"><span data-stu-id="4c614-113">Using Visual Studio to Facilitate Automated Testing</span></span>](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)