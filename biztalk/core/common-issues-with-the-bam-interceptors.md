---
title: BAM 拦截器的常见问题 |Microsoft 文档
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
ms.openlocfilehash: 312bcd2ea1eaedcf44f02e2d3b702989095969d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231493"
---
# <a name="common-issues-with-the-bam-interceptors"></a><span data-ttu-id="54378-102">BAM 侦听器中的常见问题</span><span class="sxs-lookup"><span data-stu-id="54378-102">Common Issues with the BAM Interceptors</span></span>
<span data-ttu-id="54378-103">本主题讨论使用 BAM 拦截器时可能会出现以下常见的问题：</span><span class="sxs-lookup"><span data-stu-id="54378-103">This topic discusses the following common problems that can arise when using BAM interceptors:</span></span>  
  
-   <span data-ttu-id="54378-104">为分布式事务相关的 SQL 异常</span><span class="sxs-lookup"><span data-stu-id="54378-104">SQL Exception relating to a distributed transaction</span></span>  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a><span data-ttu-id="54378-105">接收有关已完成的分布式的事务或事务描述符 SQL 异常</span><span class="sxs-lookup"><span data-stu-id="54378-105">You Receive a SQL Exception Concerning a Completed Distributed Transaction or a Transaction Descriptor</span></span>  
 <span data-ttu-id="54378-106">运行 BAM Windows Communication Framework (WCF) 侦听器时，可能会看到以下异常之一：</span><span class="sxs-lookup"><span data-stu-id="54378-106">You may see one of the following exceptions when running the BAM Windows Communication Framework (WCF) interceptor:</span></span>  
  
-   <span data-ttu-id="54378-107">分布式事务已完成。</span><span class="sxs-lookup"><span data-stu-id="54378-107">Distributed transaction completed.</span></span> <span data-ttu-id="54378-108">请将此会话登记到新事务或 NULL 事务中。</span><span class="sxs-lookup"><span data-stu-id="54378-108">Either enlist this session in a new transaction or the NULL transaction.</span></span>  
  
-   <span data-ttu-id="54378-109">新的请求不允许启动，因为它应该具有有效的事务描述符。</span><span class="sxs-lookup"><span data-stu-id="54378-109">New request is not allowed to start because it should come with a valid transaction descriptor.</span></span>  
  
 <span data-ttu-id="54378-110">有关解决此问题的一些建议是：</span><span class="sxs-lookup"><span data-stu-id="54378-110">Some suggestions for troubleshooting this problem are:</span></span>  
  
-   <span data-ttu-id="54378-111">启用 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="54378-111">Enable BAM tracing.</span></span> <span data-ttu-id="54378-112">此跟踪将包括相关的所有邮件，包括错误的根本原因。</span><span class="sxs-lookup"><span data-stu-id="54378-112">This trace will include all relevant messages including the root cause of the error.</span></span> <span data-ttu-id="54378-113">有关 BAM 跟踪的详细信息，请参阅[如何启用跟踪中 BAM](../core/how-to-enable-tracing-in-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="54378-113">For more information about BAM tracing, see [How to Enable Tracing in BAM](../core/how-to-enable-tracing-in-bam.md).</span></span>  
  
-   <span data-ttu-id="54378-114">当你看到此分布式的事务处理协调器 (DTC) 异常时，请尝试重新运行并且不包含事务相同的方案。</span><span class="sxs-lookup"><span data-stu-id="54378-114">When you see this distributed transaction coordinator (DTC) exception, try to rerun exactly the same scenario without transactions.</span></span>  
  
-   <span data-ttu-id="54378-115">使用 SQL Server 事件探查器，并查找在跟踪中将会导致事务中止的错误。</span><span class="sxs-lookup"><span data-stu-id="54378-115">Use SQL Server Profiler and look for errors in the trace that will cause the transaction to be aborted.</span></span>  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a><span data-ttu-id="54378-116">使用 WCF 侦听器时收到“侦听器配置轮询间隔‘0’必须至少为‘5’秒”的错误</span><span class="sxs-lookup"><span data-stu-id="54378-116">You receive an error similar to "interceptor configuration polling interval '0' must be at least '5' seconds" when using the WCF Interceptor</span></span>  
 <span data-ttu-id="54378-117">当未显式提供轮询间隔值在应用程序配置文件中，一个侦听器配置时或当你提供一个值，但它不超过 5 秒，可需最小值时，可能会遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="54378-117">You may encounter this error when you do not explicitly provide an interceptor configuration polling interval value in the application configuration file, or when you provide a value but it is less than 5 seconds, the required minimum.</span></span>  
  
 <span data-ttu-id="54378-118">若要解决此问题，请为 PollingIntervalSec 提供有效的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="54378-118">To fix the problem, provide a valid value for PollingIntervalSec as shown:</span></span>  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="54378-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54378-119">See Also</span></span>  
 [<span data-ttu-id="54378-120">故障排除 BAM 拦截器</span><span class="sxs-lookup"><span data-stu-id="54378-120">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)