---
title: 使用 Visual Studio 优化自动测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78f622af-08d5-480c-bd5e-f1db52e8d490
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bdcc6f996d48bef8249bffa66d732a9ba20eb01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400281"
---
# <a name="using-visual-studio-to-facilitate-automated-testing"></a><span data-ttu-id="9edc1-102">使用 Visual Studio 优化自动测试</span><span class="sxs-lookup"><span data-stu-id="9edc1-102">Using Visual Studio to Facilitate Automated Testing</span></span>
<span data-ttu-id="9edc1-103">Visual Studio 2010 提供了功能强大的负载测试功能，能模拟多达数百个用户同时访问服务器应用程序的负载配置文件。</span><span class="sxs-lookup"><span data-stu-id="9edc1-103">Visual Studio 2010 provides powerful load test functionality that can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="9edc1-104">此负载测试功能提供了所选的关键性能指标，以及能够以供未来分析数据库中存储这些指标的实时度量值。</span><span class="sxs-lookup"><span data-stu-id="9edc1-104">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="9edc1-105">本部分介绍如何使用 Visual Studio 负载测试来评估 BizTalk Server 应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="9edc1-105">This section describes the use of Visual Studio Load testing to evaluate the performance of a BizTalk Server application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9edc1-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="9edc1-106">In This Section</span></span>  
  
-   [<span data-ttu-id="9edc1-107">步骤 1：创建单元测试，以将文档提交给 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9edc1-107">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)  
  
-   [<span data-ttu-id="9edc1-108">步骤 2：配置负载测试控制器和代理的计算机</span><span class="sxs-lookup"><span data-stu-id="9edc1-108">Step 2: Configure Load Test Controller and Agent Computers</span></span>](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md)  
  
-   [<span data-ttu-id="9edc1-109">步骤 3：创建负载测试，以同时执行多个单元测试</span><span class="sxs-lookup"><span data-stu-id="9edc1-109">Step 3: Create a Load Test to Perform Multiple Unit Tests Simultaneously</span></span>](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)  
  
-   [<span data-ttu-id="9edc1-110">步骤 4：配置 BizTalk Server 环境以进行负载测试</span><span class="sxs-lookup"><span data-stu-id="9edc1-110">Step 4: Configure BizTalk Server Environment for Load Testing</span></span>](~/technical-guides/step-4-configure-biztalk-server-environment-for-load-testing.md)  
  
-   [<span data-ttu-id="9edc1-111">步骤 5：执行分级负载模式测试以确定最大可承受吞吐量</span><span class="sxs-lookup"><span data-stu-id="9edc1-111">Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput</span></span>](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)  
  
-   [<span data-ttu-id="9edc1-112">步骤 6：执行常量负载模式测试以确定最大可承受吞吐量</span><span class="sxs-lookup"><span data-stu-id="9edc1-112">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)