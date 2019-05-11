---
title: 执行瓶颈测试并优化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57d5d46bfa71fe6502b1831a8851e2ff448821d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291314"
---
# <a name="performing-bottleneck-testing-and-tuning"></a><span data-ttu-id="bcae7-102">执行瓶颈测试并优化</span><span class="sxs-lookup"><span data-stu-id="bcae7-102">Performing Bottleneck Testing and Tuning</span></span>
<span data-ttu-id="bcae7-103">您应该完成性能测试来确定系统中的瓶颈和相应地调整系统。</span><span class="sxs-lookup"><span data-stu-id="bcae7-103">You should complete performance testing to determine bottlenecks in the system and to tune the system accordingly.</span></span>  
  
## <a name="testing-a-subsystem"></a><span data-ttu-id="bcae7-104">测试一个子系统</span><span class="sxs-lookup"><span data-stu-id="bcae7-104">Testing a Subsystem</span></span>  
 <span data-ttu-id="bcae7-105">确定系统瓶颈的最佳做法是在整个系统的子集上运行性能测试例如：</span><span class="sxs-lookup"><span data-stu-id="bcae7-105">A best practice for identifying system bottlenecks is to run performance tests on subsets of the entire system, for example:</span></span>  
  
- <span data-ttu-id="bcae7-106">建立相互发送或接收来自消息的外部系统的基线性能参数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bcae7-106">Establish baseline performance parameters for external systems that send messages to or receive message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="bcae7-107">登记业务流程，但没有启动它们。</span><span class="sxs-lookup"><span data-stu-id="bcae7-107">Enlist orchestrations, but do not start them.</span></span> <span data-ttu-id="bcae7-108">放入站的队列/文件位置的消息，并允许入站接收适配器清空队列/文件位置和将消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="bcae7-108">Drop messages into the inbound queues/file locations and let the inbound receive adapters drain the queue/file locations and publish messages into the MessageBox database.</span></span> <span data-ttu-id="bcae7-109">这样，您能够隔离在接收端口，以确定其最大持续输入的速率。</span><span class="sxs-lookup"><span data-stu-id="bcae7-109">This allows you to isolate your receive ports to determine their maximum sustained input rate.</span></span>  
  
- <span data-ttu-id="bcae7-110">消息拉取后到 MessageBox 数据库，停止接收适配器、 启用业务流程和/或发送适配器，然后测量在哪个业务流程的速率和/或发送适配器所处理的消息。</span><span class="sxs-lookup"><span data-stu-id="bcae7-110">Once the messages are pulled into the MessageBox database, stop the receive adapters, enable the orchestration processes and/or send adapters, and then measure the rate at which orchestrations and/or send adapters are processing messages.</span></span>  
  
## <a name="testing-the-end-to-end-system"></a><span data-ttu-id="bcae7-111">测试端到端系统</span><span class="sxs-lookup"><span data-stu-id="bcae7-111">Testing the End-to-End System</span></span>  
 <span data-ttu-id="bcae7-112">前面部分中所述测试的输入和输出费率是隔离应用程序子系统的性能的有效方法，尽管它没有描述的端到端性能。</span><span class="sxs-lookup"><span data-stu-id="bcae7-112">Testing of input and output rates as described in preceding section is an effective way to isolate performance of the application subsystem, although it does not describe end-to-end performance.</span></span> <span data-ttu-id="bcae7-113">此外应测试端到端性能，因为无法识别一些瓶颈，直到争用同一共享资源 （例如，MessageBox 数据库） 的多个资源开始。</span><span class="sxs-lookup"><span data-stu-id="bcae7-113">You should also test end-to-end performance because some bottlenecks cannot be identified until multiple resources begin to contend for the same shared resource (for example, the MessageBox database).</span></span>  
  
 <span data-ttu-id="bcae7-114">若要生成针对负载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，请考虑使用 Microsoft BizTalk LoadGen 2007 工具。</span><span class="sxs-lookup"><span data-stu-id="bcae7-114">To generate load against a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, consider using the Microsoft BizTalk LoadGen 2007 tool.</span></span> <span data-ttu-id="bcae7-115">下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。</span><span class="sxs-lookup"><span data-stu-id="bcae7-115">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span>  
  
 <span data-ttu-id="bcae7-116">若要生成和分析的性能报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，请考虑使用性能分析日志 (PAL) 的工具。</span><span class="sxs-lookup"><span data-stu-id="bcae7-116">To generate and analyze a performance report for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, consider using the Performance Analysis of Logs (PAL) tool.</span></span> <span data-ttu-id="bcae7-117">有关 PAL 工具的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="bcae7-117">For more information about the PAL tool, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
## <a name="what-developers-operators-and-administrators-should-know"></a><span data-ttu-id="bcae7-118">哪些开发人员、 运算符和管理员应了解</span><span class="sxs-lookup"><span data-stu-id="bcae7-118">What Developers, Operators, and Administrators Should Know</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bcae7-119">开发人员应上也理解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能特征和优化。</span><span class="sxs-lookup"><span data-stu-id="bcae7-119">developers should be well versed on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance characteristics and tuning.</span></span> <span data-ttu-id="bcae7-120">操作员和管理员应了解 MessageBox 数据库向外缩放方面，SAN 优化、 网络优化和 SQL Server 数据库优化 (有关示例，请参阅[SQL Server 设置，不应更改](../technical-guides/sql-server-settings-that-should-not-be-changed.md))。</span><span class="sxs-lookup"><span data-stu-id="bcae7-120">Operators and administrators should be knowledgeable about MessageBox database scale-out aspects, SAN tuning, network tuning, and SQL Server database tuning (for example, see [SQL Server Settings That Should Not Be Changed](../technical-guides/sql-server-settings-that-should-not-be-changed.md)).</span></span> <span data-ttu-id="bcae7-121">开发人员、 运算符和管理员应了解如何优化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高吞吐量和低延迟。</span><span class="sxs-lookup"><span data-stu-id="bcae7-121">Developers, operators, and administrators should be aware of how to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for high-throughput and low-latency.</span></span>