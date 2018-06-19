---
title: 实现自动测试 |Microsoft 文档
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
ms.openlocfilehash: aee97d5c44ebd32ca5b325af386fb1a8754f5b20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298045"
---
# <a name="implementing-automated-testing"></a><span data-ttu-id="8c23c-102">实现自动测试</span><span class="sxs-lookup"><span data-stu-id="8c23c-102">Implementing Automated Testing</span></span>
<span data-ttu-id="8c23c-103">BizTalk Server 解决方案通常部署在"任务关键型"的情况下，BizTalk 解决方案凭此是业务的核心组件。</span><span class="sxs-lookup"><span data-stu-id="8c23c-103">BizTalk Server solutions are often deployed in “mission-critical” scenarios, whereby the BizTalk solution is a core component of the business.</span></span> <span data-ttu-id="8c23c-104">在这些情况下，持续的性能和稳定性 BizTalk 解决方案会关键业务要求;如果 BizTalk 解决方案失败，则关联的停机时间成本是有意义。</span><span class="sxs-lookup"><span data-stu-id="8c23c-104">In these scenarios, the continual performance and stability of the BizTalk solution is a key business requirement; if the BizTalk solution fails, the associated downtime costs are significant.</span></span> <span data-ttu-id="8c23c-105">在这种情况下，它是一项极其重要解决方案放入到生产环境之前进行全面测试 BizTalk 解决方案问题。</span><span class="sxs-lookup"><span data-stu-id="8c23c-105">In such scenarios, it is of paramount importance that the BizTalk solution be thoroughly tested before the solution is placed into production.</span></span> <span data-ttu-id="8c23c-106">不测试或缺乏测试解决方案导致的停机时间成本相比，与正确的测试解决方案相关联的成本要小。</span><span class="sxs-lookup"><span data-stu-id="8c23c-106">The costs associated with properly testing the solution are small compared to the downtime costs resulting from not testing or insufficiently testing the solution.</span></span> <span data-ttu-id="8c23c-107">因此，测试 BizTalk Server 解决方案无疑是任何 BizTalk Server 解决方案部署的最重要阶段。</span><span class="sxs-lookup"><span data-stu-id="8c23c-107">Therefore, the testing of a BizTalk Server solution is arguably the most important phase of any BizTalk Server solution deployment.</span></span>  
  
 <span data-ttu-id="8c23c-108">本部分介绍用于在生产环境中运行该解决方案之前测试 BizTalk 解决方案的正确方法。</span><span class="sxs-lookup"><span data-stu-id="8c23c-108">This section describes the proper methodology for testing a BizTalk solution before running the solution in a production environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c23c-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8c23c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="8c23c-110">为什么很重要向测试</span><span class="sxs-lookup"><span data-stu-id="8c23c-110">Why It Is Important to Test</span></span>](../technical-guides/why-it-is-important-to-test.md)  
  
-   [<span data-ttu-id="8c23c-111">自动执行生成过程</span><span class="sxs-lookup"><span data-stu-id="8c23c-111">Automating the Build Process</span></span>](../technical-guides/automating-the-build-process.md)  
  
-   [<span data-ttu-id="8c23c-112">使用 BizUnit 以便于自动测试</span><span class="sxs-lookup"><span data-stu-id="8c23c-112">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)  
  
-   [<span data-ttu-id="8c23c-113">使用 Visual Studio 以便于自动测试</span><span class="sxs-lookup"><span data-stu-id="8c23c-113">Using Visual Studio to Facilitate Automated Testing</span></span>](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)