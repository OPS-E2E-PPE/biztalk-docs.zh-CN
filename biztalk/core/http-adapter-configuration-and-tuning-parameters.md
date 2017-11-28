---
title: "HTTP 适配器配置和优化参数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, parameters
- configuring [HTTP adapters], parameters
- HTTP adapters, tuning
- RequestQueueSize key [HTTP adapters]
- HttpReceiveThreadsPerCpu key [HTTP adapters]
- HttpOutTimeoutInterval key [HTTP adapters]
- HttpOutInflightSize key [HTTP adapters]
- configuring [HTTP adapters], tuning
- DisableChunkEncoding key [HTTP adapters]
- HttpOutCompleteSize key [HTTP adapters]
ms.assetid: c8989a88-722a-40b5-94cf-4b6840add02e
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db4f4dc4403ddfbf677ac2729c00e2b1976db61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="52911-102">HTTP 适配器配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="52911-102">HTTP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="52911-103">通过注册表项和修改 BizTalk Server 安装根目录中的 BTSNTSvc.exe.config 文件，可以访问 HTTP 适配器的一些配置和优化参数。</span><span class="sxs-lookup"><span data-stu-id="52911-103">Several configuration and tuning parameters are accessible for the HTTP adapter through registry key entries and through the modification of the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
 <span data-ttu-id="52911-104">**对 HTTP 适配器性能影响的注册表设置**</span><span class="sxs-lookup"><span data-stu-id="52911-104">**Registry Settings That Affect HTTP Adapter Performance**</span></span>  
  
 <span data-ttu-id="52911-105">下表介绍了影响 HTTP 适配器性能的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="52911-105">The following table describes the registry settings that affect the performance of the HTTP adapter.</span></span> <span data-ttu-id="52911-106">注意，默认情况下，注册表中没有 HTTP 适配器项，因此，HTTP 适配器将使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="52911-106">Note that by default there are no HTTP adapter keys in the registry, so the HTTP adapter uses the default settings.</span></span> <span data-ttu-id="52911-107">如果需要更改默认设置，则需要在注册表的以下位置下创建下列注册表项：</span><span class="sxs-lookup"><span data-stu-id="52911-107">If it is necessary to change the default settings, you need to create the following registry keys under the following locations in the registry:</span></span>  
  
-   <span data-ttu-id="52911-108">**DisableChunkEncoding**， **RequestQueueSize**，和**HttpReceiveThreadsPerCpu**中必须定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**。</span><span class="sxs-lookup"><span data-stu-id="52911-108">**DisableChunkEncoding**, **RequestQueueSize**, and **HttpReceiveThreadsPerCpu** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**.</span></span>  
  
-   <span data-ttu-id="52911-109">**HttpOutTimeoutInterval**， **HttpOutInflightSize**，和**HttpOutCompleteSize**中必须定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}**其中**GUID**是 HTTP 发送处理程序的主机的 ID。</span><span class="sxs-lookup"><span data-stu-id="52911-109">**HttpOutTimeoutInterval**, **HttpOutInflightSize**, and **HttpOutCompleteSize** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{GUID}** where **GUID** is the ID of the host for the HTTP send handler.</span></span>  
  
|<span data-ttu-id="52911-110">项名</span><span class="sxs-lookup"><span data-stu-id="52911-110">Key name</span></span>|<span data-ttu-id="52911-111">类型</span><span class="sxs-lookup"><span data-stu-id="52911-111">Type</span></span>|<span data-ttu-id="52911-112">默认</span><span class="sxs-lookup"><span data-stu-id="52911-112">Default</span></span>|<span data-ttu-id="52911-113">解释</span><span class="sxs-lookup"><span data-stu-id="52911-113">Explanation</span></span>|  
|--------------|----------|-------------|-----------------|  
|<span data-ttu-id="52911-114">**DisableChunkEncoding**</span><span class="sxs-lookup"><span data-stu-id="52911-114">**DisableChunkEncoding**</span></span>|<span data-ttu-id="52911-115">DWORD</span><span class="sxs-lookup"><span data-stu-id="52911-115">DWORD</span></span>|<span data-ttu-id="52911-116">0</span><span class="sxs-lookup"><span data-stu-id="52911-116">0</span></span>|<span data-ttu-id="52911-117">规定 HTTP 接收适配器在将响应发送回客户端时是否使用 Chunked 编码。</span><span class="sxs-lookup"><span data-stu-id="52911-117">Regulates whether or not the HTTP receive adapter uses chunked encoding when sending responses back to the client.</span></span><br /><br /> <span data-ttu-id="52911-118">设置为非零值可为 HTTP 接收适配器响应关闭 Chunked 编码。</span><span class="sxs-lookup"><span data-stu-id="52911-118">Set to a nonzero value to turn off chunked encoding for HTTP receive adapter responses.</span></span><br /><br /> <span data-ttu-id="52911-119">**最小值：** 0</span><span class="sxs-lookup"><span data-stu-id="52911-119">**Minimum value:** 0</span></span><br /><br /> <span data-ttu-id="52911-120">**最大值：**任何非零值</span><span class="sxs-lookup"><span data-stu-id="52911-120">**Maximum value:** Any nonzero value</span></span>|  
|<span data-ttu-id="52911-121">**RequestQueueSize**</span><span class="sxs-lookup"><span data-stu-id="52911-121">**RequestQueueSize**</span></span>|<span data-ttu-id="52911-122">DWORD</span><span class="sxs-lookup"><span data-stu-id="52911-122">DWORD</span></span>|<span data-ttu-id="52911-123">256</span><span class="sxs-lookup"><span data-stu-id="52911-123">256</span></span>|<span data-ttu-id="52911-124">指定 HTTP 接收适配器一次可处理的并行请求数。</span><span class="sxs-lookup"><span data-stu-id="52911-124">Defines the number of concurrent requests that the HTTP receive adapter processes at one time.</span></span><br /><br /> <span data-ttu-id="52911-125">**最小值：** 10</span><span class="sxs-lookup"><span data-stu-id="52911-125">**Minimum value:**  10</span></span><br /><br /> <span data-ttu-id="52911-126">**最大值：** 2048年</span><span class="sxs-lookup"><span data-stu-id="52911-126">**Maximum value:** 2048</span></span>|  
|<span data-ttu-id="52911-127">**HttpReceiveThreadsPerCpu**</span><span class="sxs-lookup"><span data-stu-id="52911-127">**HttpReceiveThreadsPerCpu**</span></span>|<span data-ttu-id="52911-128">DWORD</span><span class="sxs-lookup"><span data-stu-id="52911-128">DWORD</span></span>|<span data-ttu-id="52911-129">2</span><span class="sxs-lookup"><span data-stu-id="52911-129">2</span></span>|<span data-ttu-id="52911-130">定义每个 CPU 为 HTTP 接收适配器分配的线程数。</span><span class="sxs-lookup"><span data-stu-id="52911-130">Defines the number of threads per CPU that are allocated to the HTTP receive adapter.</span></span><br /><br /> <span data-ttu-id="52911-131">**最小值：** 1</span><span class="sxs-lookup"><span data-stu-id="52911-131">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="52911-132">**最大值：** 10</span><span class="sxs-lookup"><span data-stu-id="52911-132">**Maximum value:** 10</span></span>|  
|<span data-ttu-id="52911-133">**HttpOutTimeoutInterval**</span><span class="sxs-lookup"><span data-stu-id="52911-133">**HttpOutTimeoutInterval**</span></span>|<span data-ttu-id="52911-134">DWORD</span><span class="sxs-lookup"><span data-stu-id="52911-134">DWORD</span></span>|<span data-ttu-id="52911-135">2000</span><span class="sxs-lookup"><span data-stu-id="52911-135">2000</span></span>|<span data-ttu-id="52911-136">定义 HTTP 发送适配器在超时之前等待的时间间隔（秒）。</span><span class="sxs-lookup"><span data-stu-id="52911-136">Defines the interval in seconds that the HTTP send adapter will wait before timing out.</span></span><br /><br /> <span data-ttu-id="52911-137">**最小值：** 500</span><span class="sxs-lookup"><span data-stu-id="52911-137">**Minimum value:** 500</span></span><br /><br /> <span data-ttu-id="52911-138">**最大值：** 10000000</span><span class="sxs-lookup"><span data-stu-id="52911-138">**Maximum value:** 10000000</span></span>|  
|<span data-ttu-id="52911-139">**HttpOutInflightSize**</span><span class="sxs-lookup"><span data-stu-id="52911-139">**HttpOutInflightSize**</span></span>|<span data-ttu-id="52911-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="52911-140">DWORD</span></span>|<span data-ttu-id="52911-141">100</span><span class="sxs-lookup"><span data-stu-id="52911-141">100</span></span>|<span data-ttu-id="52911-142">此为 BizTalk Server HTTP 发送适配器实例将并行处理的最大 HTTP 请求数。</span><span class="sxs-lookup"><span data-stu-id="52911-142">This is the maximum number of concurrent HTTP requests that BizTalk Server HTTP send adapter instance will handle.</span></span><br /><br /> <span data-ttu-id="52911-143">延迟的建议的值是之间的 3 到 5 倍， **maxconnection**如下所述的配置文件条目。</span><span class="sxs-lookup"><span data-stu-id="52911-143">The recommended value for latency is between 3 to 5 times that of the **maxconnection** configuration file entry discussed below.</span></span><br /><br /> <span data-ttu-id="52911-144">**最小值：** 1</span><span class="sxs-lookup"><span data-stu-id="52911-144">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="52911-145">**最大值：** 1024年</span><span class="sxs-lookup"><span data-stu-id="52911-145">**Maximum value:** 1024</span></span>|  
|<span data-ttu-id="52911-146">**HttpOutCompleteSize**</span><span class="sxs-lookup"><span data-stu-id="52911-146">**HttpOutCompleteSize**</span></span>|<span data-ttu-id="52911-147">DWORD</span><span class="sxs-lookup"><span data-stu-id="52911-147">DWORD</span></span>|<span data-ttu-id="52911-148">5</span><span class="sxs-lookup"><span data-stu-id="52911-148">5</span></span>|<span data-ttu-id="52911-149">控制从 HTTP 发送适配器返回的消息批的大小。</span><span class="sxs-lookup"><span data-stu-id="52911-149">Controls the size of the batch of messages that is returned from the HTTP send adapter.</span></span> <span data-ttu-id="52911-150">如果缓冲区未满且有未完成的响应适配器将等待 1 秒，直到它会将提交批处理。</span><span class="sxs-lookup"><span data-stu-id="52911-150">If the buffer is not full and there are outstanding responses then the adapter will wait for 1 second until it commits the batch.</span></span>  <span data-ttu-id="52911-151">低延迟方案这应设置为 1，这将允许立即将发送响应消息到的消息框处理的适配器。</span><span class="sxs-lookup"><span data-stu-id="52911-151">For low-latency scenarios this should be set to 1 which will allow the adapter to send response messages immediately to the message box for processing.</span></span><br /><br /> <span data-ttu-id="52911-152">**最小值：** 1</span><span class="sxs-lookup"><span data-stu-id="52911-152">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="52911-153">**最大值：** 1024年</span><span class="sxs-lookup"><span data-stu-id="52911-153">**Maximum value:** 1024</span></span>|  
  
 <span data-ttu-id="52911-154">**配置文件条目以控制对特定的目标服务器通过 HTTP 发送适配器进行的并发连接数**</span><span class="sxs-lookup"><span data-stu-id="52911-154">**Configuration File Entry to Govern the Number of Concurrent Connections Made by the HTTP Send Adapter to a Particular Destination Server**</span></span>  
  
 <span data-ttu-id="52911-155">通过在位于 BizTalk Server 安装根目录的 BTSNTSvc.exe.config 文件中创建一项，可以配置 HTTP 适配器为特定的目标服务器并行打开的连接数。</span><span class="sxs-lookup"><span data-stu-id="52911-155">The number of concurrent connections that the HTTP adapter opens for a particular destination server can be configured by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52911-156">如果 HTTP 和 SOAP 适配器将消息发送到同一目标 HTTP 服务器，则此属性将同时应用于这两个适配器。</span><span class="sxs-lookup"><span data-stu-id="52911-156">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="52911-157">“最大连接”属性的默认值为 2，可以为所有 URI 设置的“最大连接”属性的最大值为 20。</span><span class="sxs-lookup"><span data-stu-id="52911-157">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="52911-158">以下为最大连接数属性的配置示例：</span><span class="sxs-lookup"><span data-stu-id="52911-158">The following is an example of the configuration for the maximum connections property:</span></span>  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="52911-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52911-159">See Also</span></span>  
 [<span data-ttu-id="52911-160">配置 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="52911-160">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)