---
title: 使用 MSMQ 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce77cdac-79c1-4529-8f09-0fb1f87ca037
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4accec1f9bed8ade9270e0c33e868e55c6a21942
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752557"
---
# <a name="known-issues-with-the-msmq-adapter"></a><span data-ttu-id="6ca5c-102">MSMQ 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="6ca5c-102">Known Issues with the MSMQ Adapter</span></span>
<span data-ttu-id="6ca5c-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="6ca5c-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="6ca5c-104">Known Issues</span></span>  
  
#### <a name="msmq-adapter-receive-locations-do-not-process-documents"></a><span data-ttu-id="6ca5c-105">MSMQ 适配器接收位置不处理文档</span><span class="sxs-lookup"><span data-stu-id="6ca5c-105">MSMQ Adapter receive locations do not process documents</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6ca5c-106">问题</span><span class="sxs-lookup"><span data-stu-id="6ca5c-106">Problem</span></span>  
 <span data-ttu-id="6ca5c-107">MSMQ 适配器接收位置不处理文档。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-107">MSMQ Adapter receive locations will not process documents.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6ca5c-108">原因</span><span class="sxs-lookup"><span data-stu-id="6ca5c-108">Cause</span></span>  
 <span data-ttu-id="6ca5c-109">如果与运行 MSMQ 适配器接收处理程序的 BizTalk 主机实例相关联的 .NET 线程池中没有足够的线程，则 MSMQ 适配器接收位置将由于线程不足而无法处理文档。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-109">If there are insufficient threads available in the .NET thread pool associated with the BizTalk host instance that the MSMQ adapter receive handler is running in then MSMQ Adapter receive locations are unable to process documents due to thread starvation.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6ca5c-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="6ca5c-110">Resolution</span></span>  
 <span data-ttu-id="6ca5c-111">若要增加的主机实例的.NET 线程池的可用线程数，请按照中的步骤**宿主 CLR 宿主线程值**主题的部分[该影响适配器的配置参数性能](../core/configuration-parameters-that-affect-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-111">To increase the number of available threads in the .NET thread pool for the host instance, follow the steps in the **CLR Hosting thread values for the host** section of the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
 <span data-ttu-id="6ca5c-112">由于每个 MSMQ 接收位置绑定到 MSMQ 接收处理程序需要.NET 线程池中的线程，设置**MinIOThreads**并**MinWorkerThreads**为值大于或等于MSMQ 接收位置数将绑定到接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-112">Because each MSMQ receive location that is bound to an MSMQ receive handler requires a thread from the .NET thread pool, set **MinIOThreads** and **MinWorkerThreads** to a value that is greater than or equal to the number of MSMQ receive locations bound to the receive handler.</span></span> <span data-ttu-id="6ca5c-113">相应地，设置的值**MaxIOThreads**并**MaxWorkerThreads**的值等于数 MSMQ 接收位置绑定到接收处理程序\*2，以留出余量：</span><span class="sxs-lookup"><span data-stu-id="6ca5c-113">Accordingly, set the value for **MaxIOThreads** and **MaxWorkerThreads** to a value equal to the number of MSMQ receive locations bound to the receive handler \* 2 to allow for headroom:</span></span>  
  
|<span data-ttu-id="6ca5c-114">DWORD 项</span><span class="sxs-lookup"><span data-stu-id="6ca5c-114">DWORD Entry</span></span>|<span data-ttu-id="6ca5c-115">推荐值</span><span class="sxs-lookup"><span data-stu-id="6ca5c-115">Recommended value</span></span>|  
|-----------------|-----------------------|  
|<span data-ttu-id="6ca5c-116">MaxIOThreads</span><span class="sxs-lookup"><span data-stu-id="6ca5c-116">MaxIOThreads</span></span>|<span data-ttu-id="6ca5c-117">MSMQ 接收位置绑定到 MSMQ 适配器接收处理程序\*2。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-117">Number of MSMQ receive locations bound to the MSMQ adapter receive handler \* 2.</span></span>|  
|<span data-ttu-id="6ca5c-118">MaxWorkerThreads</span><span class="sxs-lookup"><span data-stu-id="6ca5c-118">MaxWorkerThreads</span></span>|<span data-ttu-id="6ca5c-119">MSMQ 接收位置绑定到 MSMQ 适配器接收处理程序\*2。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-119">Number of MSMQ receive locations bound to the MSMQ adapter receive handler \* 2.</span></span>|  
|<span data-ttu-id="6ca5c-120">MinIOThreads</span><span class="sxs-lookup"><span data-stu-id="6ca5c-120">MinIOThreads</span></span>|<span data-ttu-id="6ca5c-121">绑定到 MSMQ 适配器接收处理程序的 MSMQ 接收位置数量。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-121">Number of MSMQ receive locations bound to the MSMQ adapter receive handler.</span></span>|  
|<span data-ttu-id="6ca5c-122">MinWorkerThreads</span><span class="sxs-lookup"><span data-stu-id="6ca5c-122">MinWorkerThreads</span></span>|<span data-ttu-id="6ca5c-123">绑定到 MSMQ 适配器接收处理程序的 MSMQ 接收位置数量。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-123">Number of MSMQ receive locations bound to the MSMQ adapter receive handler.</span></span>|  
  
 <span data-ttu-id="6ca5c-124">由于这些建议值并不包括主机实例中运行的其他适配器处理程序或业务流程所使用的线程，因此应相应增大这些值。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-124">These recommended values do not factor in the threads used by other adapter handlers or orchestrations running in the host instance so the values should be increased accordingly.</span></span>  
  
#### <a name="msmq-adapter-receive-locations-shut-down-shortly-after-they-are-enabled"></a><span data-ttu-id="6ca5c-125">MSMQ 适配器接收位置在启用后立即关闭</span><span class="sxs-lookup"><span data-stu-id="6ca5c-125">MSMQ Adapter receive locations shut down shortly after they are enabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6ca5c-126">问题</span><span class="sxs-lookup"><span data-stu-id="6ca5c-126">Problem</span></span>  
 <span data-ttu-id="6ca5c-127">MSMQ 接收位置在启用后立即关闭。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-127">MSMQ receive locations shut down shortly after they are enabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6ca5c-128">原因</span><span class="sxs-lookup"><span data-stu-id="6ca5c-128">Cause</span></span>  
 <span data-ttu-id="6ca5c-129">如果消息队列服务的本地非群集实例没有在 MSMQ 接收处理程序的主机实例所运行的同一台计算机上运行，则可能发生此问题。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-129">This problem can occur if a local non-clustered instance of the Message Queuing service is not running on the same computer that the host instance for the MSMQ receive handler is running on.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6ca5c-130">解决方法</span><span class="sxs-lookup"><span data-stu-id="6ca5c-130">Resolution</span></span>  
 <span data-ttu-id="6ca5c-131">在 MSMQ 接收处理程序的主机实例所运行的计算机上启动消息队列服务。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-131">Start the Message Queuing service on the computer that the host instance for the MSMQ receive handler is running on.</span></span> <span data-ttu-id="6ca5c-132">MSMQ 适配器接收处理程序要求消息队列服务的本地实例处于运行状态，即使消息队列服务的群集实例在同一台计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-132">The MSMQ adapter receive handler requires that a local instance of the Message Queuing service is running even if a clustered instance of the Message Queuing service is running on the same computer.</span></span>  
  
#### <a name="sc-tool-causes-error-when-attempting-to-stop-service-for-host-instance"></a><span data-ttu-id="6ca5c-133">尝试停止主机实例的服务时，SC 工具导致了错误。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-133">SC tool causes error when attempting to stop service for host instance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6ca5c-134">问题</span><span class="sxs-lookup"><span data-stu-id="6ca5c-134">Problem</span></span>  
 <span data-ttu-id="6ca5c-135">尝试使用 SC 工具 (Sc.exe) 关闭 BizTalk 主机实例的服务时，您可能会收到类似于以下内容的错误消息：</span><span class="sxs-lookup"><span data-stu-id="6ca5c-135">When you try to use the SC tool (Sc.exe) to shut down the service for the BizTalk host instance, you may receive an error message that resembles the following:</span></span>  
  
 <span data-ttu-id="6ca5c-136">**Control 失败 1053年服务：**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-136">**ControlService FAILED 1053:**</span></span>  
  
 <span data-ttu-id="6ca5c-137">**该服务未响应及时的开始或控制请求。**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-137">**The service did not respond to the start or control request in a timely fashion.**</span></span>  
  
 <span data-ttu-id="6ca5c-138">您收到该错误消息之后，将停止 BizTalk 主机实例的服务。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-138">After you receive this error message, the service for the BizTalk host instance is stopped.</span></span> <span data-ttu-id="6ca5c-139">但是，SC 工具可能需要两分钟或更多时间才能关闭此服务。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-139">However, the SC tool may need two minutes or more to shut down the service.</span></span>  
  
 <span data-ttu-id="6ca5c-140">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中启用 Microsoft 消息队列接收位置后，发生了此问题。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-140">This problem occurs when a Microsoft Message Queuing receive location is enabled in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6ca5c-141">此外，可能会在系统日志中记录类似于以下内容的错误消息：</span><span class="sxs-lookup"><span data-stu-id="6ca5c-141">Additionally, an error message that resembles the following may be logged in the System log:</span></span>  
  
 <span data-ttu-id="6ca5c-142">**事件类型： 错误**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-142">**Event Type: Error**</span></span>  
  
 <span data-ttu-id="6ca5c-143">**事件源： 服务控制管理器**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-143">**Event Source: Service Control Manager**</span></span>  
  
 <span data-ttu-id="6ca5c-144">**事件类别： 无**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-144">**Event Category: None**</span></span>  
  
 <span data-ttu-id="6ca5c-145">**事件 ID: 7011**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-145">**Event ID: 7011**</span></span>  
  
 <span data-ttu-id="6ca5c-146">**说明：**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-146">**Description:**</span></span>  
  
 <span data-ttu-id="6ca5c-147">**超时 （30000 毫秒） 等待来自 BTSSvc$ BizTalkServerApplication 服务的事务响应。**</span><span class="sxs-lookup"><span data-stu-id="6ca5c-147">**Timeout (30000 milliseconds) waiting for a transaction response from the BTSSvc$BizTalkServerApplication service.**</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6ca5c-148">解决方法</span><span class="sxs-lookup"><span data-stu-id="6ca5c-148">Resolution</span></span>  
 <span data-ttu-id="6ca5c-149">现在可以从 Microsoft 获得受支持的修补程序。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-149">A supported hotfix is now available from Microsoft.</span></span> <span data-ttu-id="6ca5c-150">但是，本修补程序仅用于解决本文章中介绍的问题。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-150">However, this hotfix is intended to correct only the problem that is described in this article.</span></span> <span data-ttu-id="6ca5c-151">仅将此修补程序应用于正经历此特定问题的系统。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-151">Apply this hotfix only to systems that are experiencing this specific problem.</span></span> <span data-ttu-id="6ca5c-152">此修补程序可能会接收其他测试。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-152">This hotfix might receive additional testing.</span></span> <span data-ttu-id="6ca5c-153">因此，如果您没有严重受到本问题的影响，我们建议您等待包含本修补程序的下一 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-153">Therefore, if you are not severely affected by this problem, we recommend that you wait for the next service pack that contains this hotfix.</span></span>  
  
 <span data-ttu-id="6ca5c-154">若要解决此问题，请提交请求到 Microsoft 联机客户服务，以获取修补程序。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-154">To resolve this problem, submit a request to Microsoft Online Customer Services to obtain the hotfix.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ca5c-155">如果发生其他问题或需要任何疑难解答，您可能必须创建一个单独的服务请求。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-155">If additional issues occur or any troubleshooting is required, you might have to create a separate service request.</span></span> <span data-ttu-id="6ca5c-156">对于不符合本特定修补程序的其他支持问题，需要支付常规支持费用。</span><span class="sxs-lookup"><span data-stu-id="6ca5c-156">The usual support costs will apply to additional support questions and issues that do not qualify for this specific hotfix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca5c-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ca5c-157">See Also</span></span>  
 [<span data-ttu-id="6ca5c-158">MSMQ 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="6ca5c-158">Troubleshooting the MSMQ Adapter</span></span>](../core/troubleshooting-the-msmq-adapter.md)