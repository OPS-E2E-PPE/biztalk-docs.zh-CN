---
title: "BizUnit 测试用例的阶段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff435fd1c69118112b0121bf68b38ae3151885f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="stages-of-a-bizunit-test-case"></a><span data-ttu-id="0fd75-102">BizUnit 测试用例的阶段</span><span class="sxs-lookup"><span data-stu-id="0fd75-102">Stages of a BizUnit Test Case</span></span>
<span data-ttu-id="0fd75-103">每个 BizUnit 测试用例包括三个阶段： **TestSetup**， **TestExecution**，和**TestCleanup**。</span><span class="sxs-lookup"><span data-stu-id="0fd75-103">Each BizUnit test case consists of three stages: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="0fd75-104">每个阶段包含负责执行的工作; 单个离散单元的一个或多个测试步骤例如， **FileCreateStep**负责在给定文件名指定的位置中创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="0fd75-104">Each stage contains one or more test steps that are responsible for performing a single discrete unit of work; for example, the **FileCreateStep** is responsible for creating a file in a location you specify with a given filename.</span></span>  <span data-ttu-id="0fd75-105">BizUnit 包括超过 70 测试步骤，并提供扩展功能，使新的测试步骤，以可轻松添加到框架。</span><span class="sxs-lookup"><span data-stu-id="0fd75-105">BizUnit includes over 70 test steps and also provides extension capabilities which allow new test steps to be easily added to the framework.</span></span> <span data-ttu-id="0fd75-106">能够将新的步骤添加到框架允许 BizUnit 方案的广泛使用。</span><span class="sxs-lookup"><span data-stu-id="0fd75-106">The ability to add new steps to the framework allows BizUnit to be used across a broad range of scenarios.</span></span> <span data-ttu-id="0fd75-107">本主题介绍 BizUnit 测试阶段中详细说明。</span><span class="sxs-lookup"><span data-stu-id="0fd75-107">This topic describes the BizUnit test stages in further detail.</span></span>  
  
## <a name="setup-stage"></a><span data-ttu-id="0fd75-108">安装程序阶段</span><span class="sxs-lookup"><span data-stu-id="0fd75-108">Setup Stage</span></span>  
 <span data-ttu-id="0fd75-109">此安装程序阶段准备以便进行测试的平台。</span><span class="sxs-lookup"><span data-stu-id="0fd75-109">This setup stage prepares the platform for the testing.</span></span> <span data-ttu-id="0fd75-110">例如，可以运行特定测试之前，文件可能需要复制为文件放置在实际执行测试准备。</span><span class="sxs-lookup"><span data-stu-id="0fd75-110">For example, before a particular test can be run, a file may need to be copied to a file drop in preparation for the actual execution of the test.</span></span> <span data-ttu-id="0fd75-111">你也可以使用此阶段清理任何文件位置或将测试中使用的数据库表。</span><span class="sxs-lookup"><span data-stu-id="0fd75-111">You could also use this stage to cleanup any file locations or database tables that will be used in the test.</span></span> <span data-ttu-id="0fd75-112">与一样 BizUnit 中的每个阶段，可以添加的测试步骤的数量没有限制，它提供了处理复杂的方案所需的灵活性。</span><span class="sxs-lookup"><span data-stu-id="0fd75-112">As with every stage in BizUnit, there is no limit to the number of test steps that can be added, which provides the flexibility required to handle complex scenarios.</span></span>  
  
## <a name="execution-stage"></a><span data-ttu-id="0fd75-113">执行阶段</span><span class="sxs-lookup"><span data-stu-id="0fd75-113">Execution Stage</span></span>  
 <span data-ttu-id="0fd75-114">执行阶段是实际运行该测试时。</span><span class="sxs-lookup"><span data-stu-id="0fd75-114">The execution stage is where the test is actually run.</span></span> <span data-ttu-id="0fd75-115">这是系统的进行实际测试的验证函数。</span><span class="sxs-lookup"><span data-stu-id="0fd75-115">This is where the function of the system you are validating is actually tested.</span></span>  
  
## <a name="cleanup-stage"></a><span data-ttu-id="0fd75-116">清理阶段</span><span class="sxs-lookup"><span data-stu-id="0fd75-116">Cleanup Stage</span></span>  
 <span data-ttu-id="0fd75-117">清理阶段是测试步骤返回到之前运行测试的一致状态的平台的容器。</span><span class="sxs-lookup"><span data-stu-id="0fd75-117">The cleanup stage is the container for test steps that returns the platform to the consistent state that it was in before you ran the test.</span></span> <span data-ttu-id="0fd75-118">始终执行这一阶段，即使在执行阶段发生错误。</span><span class="sxs-lookup"><span data-stu-id="0fd75-118">This stage is always executed, even if an error occurs in the execution stage.</span></span> <span data-ttu-id="0fd75-119">平台应返回到起始点的原因是为了防止一个测试用例干扰另一，以便每个测试用例自主运行作为测试套件的一部分。</span><span class="sxs-lookup"><span data-stu-id="0fd75-119">The reason the platform should be returned to its starting point is to prevent one test case from interfering with another so that each test case is run autonomously as part of the test suite.</span></span> <span data-ttu-id="0fd75-120">在此阶段确保系统完全清除是用于与 BizUnit 有效测试的指导原则之一。</span><span class="sxs-lookup"><span data-stu-id="0fd75-120">Ensuring a complete cleanup of the system at this stage is one of the guiding principles for effective testing with BizUnit.</span></span>  
  
 <span data-ttu-id="0fd75-121">下图演示了包含三个阶段中的测试步骤将示例测试用例的格式： 安装程序、 执行和清理。</span><span class="sxs-lookup"><span data-stu-id="0fd75-121">The following diagram illustrates the format of a sample test case, which contains test steps in the three stages: setup, execution, and cleanup.</span></span> <span data-ttu-id="0fd75-122">请务必始终遵循以下结构定义测试用例和 BizUnit 时。</span><span class="sxs-lookup"><span data-stu-id="0fd75-122">It is important to always follow this structure when defining test cases with BizUnit.</span></span>  
  
 <span data-ttu-id="0fd75-123">![BizUnit 测试阶段](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")</span><span class="sxs-lookup"><span data-stu-id="0fd75-123">![Stages of a BizUnit Test](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")</span></span>  
<span data-ttu-id="0fd75-124">BizUnit 测试的阶段</span><span class="sxs-lookup"><span data-stu-id="0fd75-124">Stages of a BizUnit test</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd75-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fd75-125">See Also</span></span>  
 [<span data-ttu-id="0fd75-126">使用 BizUnit 以便于自动测试</span><span class="sxs-lookup"><span data-stu-id="0fd75-126">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)