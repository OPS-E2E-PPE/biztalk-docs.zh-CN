---
title: 执行功能测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b9c8c95-5a25-4255-a4c2-e26c67b7a620
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0f1736ddc0956de470ebdc1f3f1a6adaa2f8f94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291333"
---
# <a name="performing-functional-testing"></a><span data-ttu-id="ffa3e-102">执行功能测试</span><span class="sxs-lookup"><span data-stu-id="ffa3e-102">Performing Functional Testing</span></span>
<span data-ttu-id="ffa3e-103">使用功能测试来测试特定的 BizTalk 应用程序的上下文中的一个特定的端到端方案或给定的用例。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-103">You use functional testing to test a specific end-to-end scenario or a given use case in the context of a particular BizTalk application.</span></span> <span data-ttu-id="ffa3e-104">功能测试应涵盖通过给定方案中，包括故障路径的所有可能路径。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-104">A functional test should cover all the possible paths through a given scenario, including the failure paths.</span></span> <span data-ttu-id="ffa3e-105">故障路径应进行评估，以确保应用程序适当地处理故障条件。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-105">Failure paths should be evaluated to ensure that the application deals with failure conditions appropriately.</span></span>  
  
 <span data-ttu-id="ffa3e-106">应调用 （如业务流程、 自定义管道组件和自定义程序集） 的所有项目，并且还应测试通过这些对象的所有代码分支。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-106">All the artifacts (such as orchestrations, custom pipeline components, and custom assemblies) should be invoked, and all the code branches through these objects should be tested as well.</span></span> <span data-ttu-id="ffa3e-107">必须小心的消息的所有可能组合，以确保消息正确流过系统。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-107">All the possible combinations of messages should be exercised to ensure that messages flow through the system correctly.</span></span> <span data-ttu-id="ffa3e-108">请确保在发生错误时预期的方式做出响应应用程序并进行测试的业务流程和自定义组件的所有异常块中包含的代码应以及测试无效消息。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-108">Invalid messages should be tested as well to make sure that the application reacts in the expected way in case of error and to test the code contained in all the exception blocks of orchestrations and custom components.</span></span>  
  
## <a name="automating-functional-testing"></a><span data-ttu-id="ffa3e-109">自动执行功能测试</span><span class="sxs-lookup"><span data-stu-id="ffa3e-109">Automating Functional Testing</span></span>  
 <span data-ttu-id="ffa3e-110">您应当自动完成功能测试，以便它速度快，以便可以重复，并它将避免人为错误。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-110">You should automate functional testing so that it is fast, so that it can be repeated, and so that it will avoid human errors.</span></span> <span data-ttu-id="ffa3e-111">**BizUnit**是一个声明性的测试框架，旨在让开发人员快速设计测试用例。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-111">**BizUnit** is a declarative test framework designed to enable developers to rapidly design test cases.</span></span> <span data-ttu-id="ffa3e-112">实际上，XML 配置文件调用 BizUnit XML 测试用例就足以定义应如何执行测试。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-112">In fact, an XML configuration file called BizUnit XML test case is enough to define how a test should be performed.</span></span> <span data-ttu-id="ffa3e-113">若要运行测试可以创建自定义驱动程序或更多方便地利用**Visual Studio 单元测试**或**NUnit**托管和运行测试。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-113">To run tests you can create your own custom driver or more easily leverage **Visual Studio Unit Testing** or **NUnit** to host and run your tests.</span></span>  
  
 <span data-ttu-id="ffa3e-114">每个 XML BizUnit 测试用例包含三个阶段：**TestSetup**， **TestExecution**，和**TestCleanup**。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-114">Every BizUnit XML test case contains three phases: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="ffa3e-115">每个阶段可以包含零个或多个测试步骤。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-115">Each of these phases can contain zero or more test steps.</span></span> <span data-ttu-id="ffa3e-116">每个步骤表示的工作单元，并作为设计为执行特定任务的.NET 类实现。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-116">Each step represents a unit of work and is implemented as a .NET class designed to perform a certain task.</span></span> <span data-ttu-id="ffa3e-117">此框架提供了一套丰富的组件。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-117">This framework provides a rich set of components.</span></span> <span data-ttu-id="ffa3e-118">如果您需要意识到专用的组件，以满足特定要求，但是，可以编写您自己的自定义测试步骤组件。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-118">If you need to realize specialized components to meet specific requirements, however, you can write your own custom test step components.</span></span> <span data-ttu-id="ffa3e-119">有关这些工具的详细信息，请参阅[用于测试工具](~/technical-guides/tools-for-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-119">For more information about these tools, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ffa3e-120">使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-120">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="ffa3e-121">使用此程序是完全由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="ffa3e-121">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa3e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffa3e-122">See Also</span></span>  
 [<span data-ttu-id="ffa3e-123">清单：测试操作准备情况</span><span class="sxs-lookup"><span data-stu-id="ffa3e-123">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)