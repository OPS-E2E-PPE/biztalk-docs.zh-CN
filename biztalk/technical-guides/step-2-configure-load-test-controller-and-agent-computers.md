---
title: 步骤 2： 配置负载测试控制器和代理计算机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b03a191269936311d04f7b773ed3159db66e34f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972446"
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a><span data-ttu-id="01b82-102">步骤 2： 配置负载测试控制器和代理的计算机</span><span class="sxs-lookup"><span data-stu-id="01b82-102">Step 2: Configure Load Test Controller and Agent Computers</span></span>

## <a name="overview"></a><span data-ttu-id="01b82-103">概述</span><span class="sxs-lookup"><span data-stu-id="01b82-103">Overview</span></span>
<span data-ttu-id="01b82-104">Visual Studio 可以生成模拟最多 250 个虚拟用户的本地负载测试运行的负载。</span><span class="sxs-lookup"><span data-stu-id="01b82-104">Visual Studio can generate load simulating up to 250 virtual users on a local load test run.</span></span> <span data-ttu-id="01b82-105">若要模拟 250 多个虚拟用户和/或启动测试从远程计算机需要安装 Visual Studio 负载测试虚拟用户。</span><span class="sxs-lookup"><span data-stu-id="01b82-105">To simulate more than 250 virtual users and/or to initiate testing from a remote computer requires Visual Studio Load Test Virtual User.</span></span>  
  
 <span data-ttu-id="01b82-106">所有负载测试执行本指南中的都启动两台计算机：</span><span class="sxs-lookup"><span data-stu-id="01b82-106">All load testing performed for this guide was initiated from two computers:</span></span>  
  
- <span data-ttu-id="01b82-107">一台计算机运行负载测试控制器和负载测试代理。</span><span class="sxs-lookup"><span data-stu-id="01b82-107">One computer running as both a Load Test Controller and a Load Test Agent.</span></span>  
  
- <span data-ttu-id="01b82-108">运行负载测试代理仅作为另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="01b82-108">Another computer running as a Load Test Agent only.</span></span>  
  
  <span data-ttu-id="01b82-109">测试结果存储在 SQL Server 数据库中的远程负载测试结果存储库中。</span><span class="sxs-lookup"><span data-stu-id="01b82-109">Test results were stored in a remote load test results repository in a SQL Server database.</span></span>  
  
  <span data-ttu-id="01b82-110">有关使用测试控制器和测试代理在多台测试计算机间分发负载测试的详细信息，请参阅[分发负载测试跨多个测试使用测试控制器和测试代理计算机](https://msdn.microsoft.com/library/dd728093.aspx)。</span><span class="sxs-lookup"><span data-stu-id="01b82-110">For more information about using test controllers and test agents to distribute load tests across multiple test machines, see [Distributing Load Tests Across Multiple Test Machines Using Test Controllers and Test Agents](https://msdn.microsoft.com/library/dd728093.aspx).</span></span>  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a><span data-ttu-id="01b82-111">安装和配置负载测试控制器和负载测试代理</span><span class="sxs-lookup"><span data-stu-id="01b82-111">Install and Configure the Load Test Controller and Load Test Agents</span></span>  
 <span data-ttu-id="01b82-112">若要安装和配置负载测试控制器和负载测试代理，请参阅[安装和配置测试代理](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents)。</span><span class="sxs-lookup"><span data-stu-id="01b82-112">To install and configure the load test controller and load test agents, see [Install and configure test agents](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents).</span></span>
