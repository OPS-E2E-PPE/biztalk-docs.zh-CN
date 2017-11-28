---
title: "步骤 2： 配置负载测试控制器和代理计算机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f931a05796856816e19b53ff5cba9f53b48c3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a><span data-ttu-id="df601-102">步骤 2： 配置负载测试控制器和代理的计算机</span><span class="sxs-lookup"><span data-stu-id="df601-102">Step 2: Configure Load Test Controller and Agent Computers</span></span>
<span data-ttu-id="df601-103">Visual Studio 2010 旗舰版版可生成模拟最多 250 个虚拟用户在本地的负载测试运行的负载。</span><span class="sxs-lookup"><span data-stu-id="df601-103">Visual Studio 2010 Ultimate edition can generate load simulating up to 250 virtual users on a local load test run.</span></span> <span data-ttu-id="df601-104">模拟虚拟用户数超过 250 名和/或启动测试从远程计算机需要 Visual Studio 负载测试虚拟用户包 2010年。</span><span class="sxs-lookup"><span data-stu-id="df601-104">To simulate more than 250 virtual users and/or to initiate testing from a remote computer requires Visual Studio Load Test Virtual User Pack 2010.</span></span>  
  
 <span data-ttu-id="df601-105">从两台计算机的所有负载测试执行本指南中已都启动：</span><span class="sxs-lookup"><span data-stu-id="df601-105">All load testing performed for this guide was initiated from two computers:</span></span>  
  
-   <span data-ttu-id="df601-106">为负载测试控制器和负载测试代理运行的一台计算机。</span><span class="sxs-lookup"><span data-stu-id="df601-106">One computer running as both a Load Test Controller and a Load Test Agent.</span></span>  
  
-   <span data-ttu-id="df601-107">为负载测试代理只运行的另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="df601-107">Another computer running as a Load Test Agent only.</span></span>  
  
 <span data-ttu-id="df601-108">测试结果存储在远程负载测试结果储存库中的 SQL Server 2008 R2 数据库。</span><span class="sxs-lookup"><span data-stu-id="df601-108">Test results were stored in a remote load test results repository in a SQL Server 2008 R2 database.</span></span>  
  
 <span data-ttu-id="df601-109">有关使用测试控制器和测试代理在多台测试计算机之间分发负载测试的详细信息，请参阅[分发负载测试跨多个测试使用测试控制器和测试代理计算机](http://go.microsoft.com/fwlink/?LinkId=208406)(http://go.microsoft.com/fwlink/？LinkId = 208406)。</span><span class="sxs-lookup"><span data-stu-id="df601-109">For more information about using test controllers and test agents to distribute load tests across multiple test machines, see [Distributing Load Tests Across Multiple Test Machines Using Test Controllers and Test Agents](http://go.microsoft.com/fwlink/?LinkId=208406) (http://go.microsoft.com/fwlink/?LinkId=208406).</span></span>  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a><span data-ttu-id="df601-110">安装和配置的负载测试控制器和负载测试代理</span><span class="sxs-lookup"><span data-stu-id="df601-110">Install and Configure the Load Test Controller and Load Test Agents</span></span>  
 <span data-ttu-id="df601-111">若要安装并配置负载测试控制器和负载测试代理，请参阅主题中的以下部分[安装和配置 Visual Studio Agents 和测试和生成控制器](http://go.microsoft.com/fwlink/?LinkId=208455)(http://go.microsoft.com/fwlink/?LinkId=208455):</span><span class="sxs-lookup"><span data-stu-id="df601-111">To install and configure the load test controller and load test agents, see the following sections in the topic [Installing and Configuring Visual Studio Agents and Test and Build Controllers](http://go.microsoft.com/fwlink/?LinkId=208455) (http://go.microsoft.com/fwlink/?LinkId=208455):</span></span>  
  
-   <span data-ttu-id="df601-112">要设置测试控制器，请按照中的过程[安装测试控制器](http://go.microsoft.com/fwlink/?LinkId=208454)(http://go.microsoft.com/fwlink/?LinkId=208454) 部分。</span><span class="sxs-lookup"><span data-stu-id="df601-112">To setup a test controller, follow the procedures in the [Install a Test Controller](http://go.microsoft.com/fwlink/?LinkId=208454) (http://go.microsoft.com/fwlink/?LinkId=208454) section.</span></span>  
  
-   <span data-ttu-id="df601-113">要设置测试代理，请按照中的过程[安装测试代理](http://go.microsoft.com/fwlink/?LinkId=208456)(http://go.microsoft.com/fwlink/?LinkId=208456) 部分。</span><span class="sxs-lookup"><span data-stu-id="df601-113">To setup test agents, follow the procedures in the [Install a Test Agent](http://go.microsoft.com/fwlink/?LinkId=208456) (http://go.microsoft.com/fwlink/?LinkId=208456) section.</span></span>