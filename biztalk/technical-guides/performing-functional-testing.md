---
title: "执行功能测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b9c8c95-5a25-4255-a4c2-e26c67b7a620
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f17c2701d6aa90393b8839bafc933bea2fba5746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="performing-functional-testing"></a><span data-ttu-id="f57c9-102">执行功能测试</span><span class="sxs-lookup"><span data-stu-id="f57c9-102">Performing Functional Testing</span></span>
<span data-ttu-id="f57c9-103">使用功能的测试来测试特定的 BizTalk 应用程序的上下文中的特定的端到端方案或给定的用例。</span><span class="sxs-lookup"><span data-stu-id="f57c9-103">You use functional testing to test a specific end-to-end scenario or a given use case in the context of a particular BizTalk application.</span></span> <span data-ttu-id="f57c9-104">功能测试应涵盖通过给定的方案，包括故障路径的所有可能路径。</span><span class="sxs-lookup"><span data-stu-id="f57c9-104">A functional test should cover all the possible paths through a given scenario, including the failure paths.</span></span> <span data-ttu-id="f57c9-105">故障路径应进行评估，以确保应用程序适当地处理故障条件。</span><span class="sxs-lookup"><span data-stu-id="f57c9-105">Failure paths should be evaluated to ensure that the application deals with failure conditions appropriately.</span></span>  
  
 <span data-ttu-id="f57c9-106">应调用 （如业务流程、 自定义管道组件和自定义程序集） 的所有项目，并且应该以及测试通过这些对象的所有代码分支。</span><span class="sxs-lookup"><span data-stu-id="f57c9-106">All the artifacts (such as orchestrations, custom pipeline components, and custom assemblies) should be invoked, and all the code branches through these objects should be tested as well.</span></span> <span data-ttu-id="f57c9-107">必须小心的消息的所有可能组合，以确保消息正确流过系统。</span><span class="sxs-lookup"><span data-stu-id="f57c9-107">All the possible combinations of messages should be exercised to ensure that messages flow through the system correctly.</span></span> <span data-ttu-id="f57c9-108">若要确保应用程序做出反应，在发生错误预期的方式，若要测试的业务流程和自定义组件的所有异常块中包含的代码，应以及测试的无效消息。</span><span class="sxs-lookup"><span data-stu-id="f57c9-108">Invalid messages should be tested as well to make sure that the application reacts in the expected way in case of error and to test the code contained in all the exception blocks of orchestrations and custom components.</span></span>  
  
## <a name="automating-functional-testing"></a><span data-ttu-id="f57c9-109">自动执行功能测试</span><span class="sxs-lookup"><span data-stu-id="f57c9-109">Automating Functional Testing</span></span>  
 <span data-ttu-id="f57c9-110">你应自动执行功能测试，以便它快，以便可以重复，且，以便它将避免人为失误。</span><span class="sxs-lookup"><span data-stu-id="f57c9-110">You should automate functional testing so that it is fast, so that it can be repeated, and so that it will avoid human errors.</span></span> <span data-ttu-id="f57c9-111">**BizUnit**是一个声明性测试框架，旨在使开发人员能够快速设计测试用例。</span><span class="sxs-lookup"><span data-stu-id="f57c9-111">**BizUnit** is a declarative test framework designed to enable developers to rapidly design test cases.</span></span> <span data-ttu-id="f57c9-112">事实上，XML 配置文件调用 BizUnit XML 测试用例是不足以定义应如何执行测试。</span><span class="sxs-lookup"><span data-stu-id="f57c9-112">In fact, an XML configuration file called BizUnit XML test case is enough to define how a test should be performed.</span></span> <span data-ttu-id="f57c9-113">若要运行测试你可以创建你自己的自定义驱动程序或更多方便地利用**Visual Studio 单元测试**或**NUnit**承载和运行测试。</span><span class="sxs-lookup"><span data-stu-id="f57c9-113">To run tests you can create your own custom driver or more easily leverage **Visual Studio Unit Testing** or **NUnit** to host and run your tests.</span></span>  
  
 <span data-ttu-id="f57c9-114">每个 BizUnit XML 测试用例包含三个阶段： **TestSetup**， **TestExecution**，和**TestCleanup**。</span><span class="sxs-lookup"><span data-stu-id="f57c9-114">Every BizUnit XML test case contains three phases: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="f57c9-115">每个阶段可以包含零个或多个测试步骤。</span><span class="sxs-lookup"><span data-stu-id="f57c9-115">Each of these phases can contain zero or more test steps.</span></span> <span data-ttu-id="f57c9-116">每个步骤表示的工作单元，并实现为旨在执行某项任务的.NET 类。</span><span class="sxs-lookup"><span data-stu-id="f57c9-116">Each step represents a unit of work and is implemented as a .NET class designed to perform a certain task.</span></span> <span data-ttu-id="f57c9-117">此框架提供了一套丰富的组件。</span><span class="sxs-lookup"><span data-stu-id="f57c9-117">This framework provides a rich set of components.</span></span> <span data-ttu-id="f57c9-118">如果你需要实现专用的组件以满足特定要求，但是，你可以编写自己的自定义测试步骤的组件。</span><span class="sxs-lookup"><span data-stu-id="f57c9-118">If you need to realize specialized components to meet specific requirements, however, you can write your own custom test step components.</span></span> <span data-ttu-id="f57c9-119">有关这些工具的详细信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="f57c9-119">For more information about these tools, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f57c9-120">使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。</span><span class="sxs-lookup"><span data-stu-id="f57c9-120">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="f57c9-121">使用此程序风险自负。</span><span class="sxs-lookup"><span data-stu-id="f57c9-121">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57c9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f57c9-122">See Also</span></span>  
 [<span data-ttu-id="f57c9-123">清单： 测试操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="f57c9-123">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)