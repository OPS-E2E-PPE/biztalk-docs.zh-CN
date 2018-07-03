---
title: BAM 侦听器的常见问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32145e2-1367-4576-9103-86c9182c11a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e6217a96bfbbe0a9dfddef6e8cec5a82cb93254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004070"
---
# <a name="common-issues-with-the-bam-interceptors"></a><span data-ttu-id="99daf-102">BAM 侦听器中的常见问题</span><span class="sxs-lookup"><span data-stu-id="99daf-102">Common Issues with the BAM Interceptors</span></span>
<span data-ttu-id="99daf-103">本主题讨论使用 BAM 侦听器时，可能会出现的以下常见问题：</span><span class="sxs-lookup"><span data-stu-id="99daf-103">This topic discusses the following common problems that can arise when using BAM interceptors:</span></span>  
  
-   <span data-ttu-id="99daf-104">为分布式事务相关的 SQL 异常</span><span class="sxs-lookup"><span data-stu-id="99daf-104">SQL Exception relating to a distributed transaction</span></span>  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a><span data-ttu-id="99daf-105">收到 SQL 异常，就已完成的分布式的事务或事务描述符</span><span class="sxs-lookup"><span data-stu-id="99daf-105">You Receive a SQL Exception Concerning a Completed Distributed Transaction or a Transaction Descriptor</span></span>  
 <span data-ttu-id="99daf-106">运行 BAM Windows Communication Framework (WCF) 侦听器时，可能会看到以下异常之一：</span><span class="sxs-lookup"><span data-stu-id="99daf-106">You may see one of the following exceptions when running the BAM Windows Communication Framework (WCF) interceptor:</span></span>  
  
- <span data-ttu-id="99daf-107">分布式事务已完成。</span><span class="sxs-lookup"><span data-stu-id="99daf-107">Distributed transaction completed.</span></span> <span data-ttu-id="99daf-108">请将此会话登记到新事务或 NULL 事务中。</span><span class="sxs-lookup"><span data-stu-id="99daf-108">Either enlist this session in a new transaction or the NULL transaction.</span></span>  
  
- <span data-ttu-id="99daf-109">新的请求不能启动，因为它应具有有效的事务描述符。</span><span class="sxs-lookup"><span data-stu-id="99daf-109">New request is not allowed to start because it should come with a valid transaction descriptor.</span></span>  
  
  <span data-ttu-id="99daf-110">有关解决此问题的一些建议是：</span><span class="sxs-lookup"><span data-stu-id="99daf-110">Some suggestions for troubleshooting this problem are:</span></span>  
  
- <span data-ttu-id="99daf-111">启用 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="99daf-111">Enable BAM tracing.</span></span> <span data-ttu-id="99daf-112">此跟踪将包括所有相关的消息包括错误的根本原因。</span><span class="sxs-lookup"><span data-stu-id="99daf-112">This trace will include all relevant messages including the root cause of the error.</span></span> <span data-ttu-id="99daf-113">有关 BAM 跟踪的详细信息，请参阅[如何在 BAM 中启用跟踪](../core/how-to-enable-tracing-in-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="99daf-113">For more information about BAM tracing, see [How to Enable Tracing in BAM](../core/how-to-enable-tracing-in-bam.md).</span></span>  
  
- <span data-ttu-id="99daf-114">当你看到此分布式的事务处理协调器 (DTC) 异常时，尝试重新运行不具有事务相同的方案。</span><span class="sxs-lookup"><span data-stu-id="99daf-114">When you see this distributed transaction coordinator (DTC) exception, try to rerun exactly the same scenario without transactions.</span></span>  
  
- <span data-ttu-id="99daf-115">使用 SQL Server Profiler 并检查存在错误将导致事务中止的跟踪中。</span><span class="sxs-lookup"><span data-stu-id="99daf-115">Use SQL Server Profiler and look for errors in the trace that will cause the transaction to be aborted.</span></span>  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a><span data-ttu-id="99daf-116">使用 WCF 侦听器时收到“侦听器配置轮询间隔‘0’必须至少为‘5’秒”的错误</span><span class="sxs-lookup"><span data-stu-id="99daf-116">You receive an error similar to "interceptor configuration polling interval '0' must be at least '5' seconds" when using the WCF Interceptor</span></span>  
 <span data-ttu-id="99daf-117">未显式提供侦听器配置轮询间隔值在应用程序配置文件中，或提供一个值，但它是 5 秒内，需最小值时，可能会遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="99daf-117">You may encounter this error when you do not explicitly provide an interceptor configuration polling interval value in the application configuration file, or when you provide a value but it is less than 5 seconds, the required minimum.</span></span>  
  
 <span data-ttu-id="99daf-118">若要解决此问题，请为 PollingIntervalSec 提供有效的值所示：</span><span class="sxs-lookup"><span data-stu-id="99daf-118">To fix the problem, provide a valid value for PollingIntervalSec as shown:</span></span>  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="99daf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="99daf-119">See Also</span></span>  
 [<span data-ttu-id="99daf-120">BAM 侦听器疑难解答</span><span class="sxs-lookup"><span data-stu-id="99daf-120">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)