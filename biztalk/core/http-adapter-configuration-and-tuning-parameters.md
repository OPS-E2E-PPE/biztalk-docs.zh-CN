---
title: HTTP 适配器配置和优化参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaae6d5cf3a5f810a8c8340a07d1a94fab974afe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383024"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="d5fb2-102">HTTP 适配器配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="d5fb2-102">HTTP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="d5fb2-103">多个配置和优化参数都可以访问 HTTP 适配器通过注册表项和修改位于 BizTalk Server 安装目录的根目录的 BTSNTSvc.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-103">Several configuration and tuning parameters are accessible for the HTTP adapter through registry key entries and through the modification of the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
 <span data-ttu-id="d5fb2-104">**影响 HTTP 适配器性能的注册表设置**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-104">**Registry Settings That Affect HTTP Adapter Performance**</span></span>  
  
 <span data-ttu-id="d5fb2-105">下表介绍了影响 HTTP 适配器性能的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-105">The following table describes the registry settings that affect the performance of the HTTP adapter.</span></span> <span data-ttu-id="d5fb2-106">请注意，默认情况下有没有 HTTP 适配器项在注册表中，因此，HTTP 适配器使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-106">Note that by default there are no HTTP adapter keys in the registry, so the HTTP adapter uses the default settings.</span></span> <span data-ttu-id="d5fb2-107">如果需要更改默认设置，需要在注册表中创建以下注册表项下的以下位置：</span><span class="sxs-lookup"><span data-stu-id="d5fb2-107">If it is necessary to change the default settings, you need to create the following registry keys under the following locations in the registry:</span></span>  
  
-   <span data-ttu-id="d5fb2-108">**DisableChunkEncoding**， **RequestQueueSize**，和**HttpReceiveThreadsPerCpu**必须在定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-108">**DisableChunkEncoding**, **RequestQueueSize**, and **HttpReceiveThreadsPerCpu** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**.</span></span>  
  
-   <span data-ttu-id="d5fb2-109">**HttpOutTimeoutInterval**， **HttpOutInflightSize**，和**HttpOutCompleteSize**必须在定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 其中**GUID**是 HTTP 发送处理程序主机的 ID。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-109">**HttpOutTimeoutInterval**, **HttpOutInflightSize**, and **HttpOutCompleteSize** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{GUID}** where **GUID** is the ID of the host for the HTTP send handler.</span></span>  
  
|<span data-ttu-id="d5fb2-110">密钥名称</span><span class="sxs-lookup"><span data-stu-id="d5fb2-110">Key name</span></span>|<span data-ttu-id="d5fb2-111">类型</span><span class="sxs-lookup"><span data-stu-id="d5fb2-111">Type</span></span>|<span data-ttu-id="d5fb2-112">默认</span><span class="sxs-lookup"><span data-stu-id="d5fb2-112">Default</span></span>|<span data-ttu-id="d5fb2-113">解释</span><span class="sxs-lookup"><span data-stu-id="d5fb2-113">Explanation</span></span>|  
|--------------|----------|-------------|-----------------|  
|<span data-ttu-id="d5fb2-114">**DisableChunkEncoding**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-114">**DisableChunkEncoding**</span></span>|<span data-ttu-id="d5fb2-115">DWORD</span><span class="sxs-lookup"><span data-stu-id="d5fb2-115">DWORD</span></span>|<span data-ttu-id="d5fb2-116">0</span><span class="sxs-lookup"><span data-stu-id="d5fb2-116">0</span></span>|<span data-ttu-id="d5fb2-117">来控制是否 HTTP 接收适配器将使用 chunked 编码时将响应发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-117">Regulates whether or not the HTTP receive adapter uses chunked encoding when sending responses back to the client.</span></span><br /><br /> <span data-ttu-id="d5fb2-118">设置为非零值以关闭 chunked 编码为 HTTP 接收适配器的响应。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-118">Set to a nonzero value to turn off chunked encoding for HTTP receive adapter responses.</span></span><br /><br /> <span data-ttu-id="d5fb2-119">**最小值：** 0</span><span class="sxs-lookup"><span data-stu-id="d5fb2-119">**Minimum value:** 0</span></span><br /><br /> <span data-ttu-id="d5fb2-120">**最大值：** 任何非零值</span><span class="sxs-lookup"><span data-stu-id="d5fb2-120">**Maximum value:** Any nonzero value</span></span>|  
|<span data-ttu-id="d5fb2-121">**RequestQueueSize**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-121">**RequestQueueSize**</span></span>|<span data-ttu-id="d5fb2-122">DWORD</span><span class="sxs-lookup"><span data-stu-id="d5fb2-122">DWORD</span></span>|<span data-ttu-id="d5fb2-123">256</span><span class="sxs-lookup"><span data-stu-id="d5fb2-123">256</span></span>|<span data-ttu-id="d5fb2-124">定义 HTTP 一次接收适配器处理的并发请求数。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-124">Defines the number of concurrent requests that the HTTP receive adapter processes at one time.</span></span><br /><br /> <span data-ttu-id="d5fb2-125">**最小值：** 10</span><span class="sxs-lookup"><span data-stu-id="d5fb2-125">**Minimum value:**  10</span></span><br /><br /> <span data-ttu-id="d5fb2-126">**最大值：** 2048</span><span class="sxs-lookup"><span data-stu-id="d5fb2-126">**Maximum value:** 2048</span></span>|  
|<span data-ttu-id="d5fb2-127">**HttpReceiveThreadsPerCpu**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-127">**HttpReceiveThreadsPerCpu**</span></span>|<span data-ttu-id="d5fb2-128">DWORD</span><span class="sxs-lookup"><span data-stu-id="d5fb2-128">DWORD</span></span>|<span data-ttu-id="d5fb2-129">2</span><span class="sxs-lookup"><span data-stu-id="d5fb2-129">2</span></span>|<span data-ttu-id="d5fb2-130">定义接收适配器分配给 HTTP 每个 CPU 线程数。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-130">Defines the number of threads per CPU that are allocated to the HTTP receive adapter.</span></span><br /><br /> <span data-ttu-id="d5fb2-131">**最小值：** 1</span><span class="sxs-lookup"><span data-stu-id="d5fb2-131">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="d5fb2-132">**最大值：** 10</span><span class="sxs-lookup"><span data-stu-id="d5fb2-132">**Maximum value:** 10</span></span>|  
|<span data-ttu-id="d5fb2-133">**HttpOutTimeoutInterval**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-133">**HttpOutTimeoutInterval**</span></span>|<span data-ttu-id="d5fb2-134">DWORD</span><span class="sxs-lookup"><span data-stu-id="d5fb2-134">DWORD</span></span>|<span data-ttu-id="d5fb2-135">2000</span><span class="sxs-lookup"><span data-stu-id="d5fb2-135">2000</span></span>|<span data-ttu-id="d5fb2-136">定义 HTTP 发送适配器将超时之前等待的秒的间隔。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-136">Defines the interval in seconds that the HTTP send adapter will wait before timing out.</span></span><br /><br /> <span data-ttu-id="d5fb2-137">**最小值：** 500</span><span class="sxs-lookup"><span data-stu-id="d5fb2-137">**Minimum value:** 500</span></span><br /><br /> <span data-ttu-id="d5fb2-138">**最大值：** 10000000</span><span class="sxs-lookup"><span data-stu-id="d5fb2-138">**Maximum value:** 10000000</span></span>|  
|<span data-ttu-id="d5fb2-139">**HttpOutInflightSize**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-139">**HttpOutInflightSize**</span></span>|<span data-ttu-id="d5fb2-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="d5fb2-140">DWORD</span></span>|<span data-ttu-id="d5fb2-141">100</span><span class="sxs-lookup"><span data-stu-id="d5fb2-141">100</span></span>|<span data-ttu-id="d5fb2-142">这是 BizTalk Server HTTP 发送适配器实例将处理的并发 HTTP 请求的最大数目。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-142">This is the maximum number of concurrent HTTP requests that BizTalk Server HTTP send adapter instance will handle.</span></span><br /><br /> <span data-ttu-id="d5fb2-143">建议的延迟值是 3 到 5 倍的之间**maxconnection**如下所述的配置文件条目。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-143">The recommended value for latency is between 3 to 5 times that of the **maxconnection** configuration file entry discussed below.</span></span><br /><br /> <span data-ttu-id="d5fb2-144">**最小值：** 1</span><span class="sxs-lookup"><span data-stu-id="d5fb2-144">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="d5fb2-145">**最大值：** 1024</span><span class="sxs-lookup"><span data-stu-id="d5fb2-145">**Maximum value:** 1024</span></span>|  
|<span data-ttu-id="d5fb2-146">**HttpOutCompleteSize**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-146">**HttpOutCompleteSize**</span></span>|<span data-ttu-id="d5fb2-147">DWORD</span><span class="sxs-lookup"><span data-stu-id="d5fb2-147">DWORD</span></span>|<span data-ttu-id="d5fb2-148">5</span><span class="sxs-lookup"><span data-stu-id="d5fb2-148">5</span></span>|<span data-ttu-id="d5fb2-149">控件发送适配器从 HTTP 返回消息批的大小。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-149">Controls the size of the batch of messages that is returned from the HTTP send adapter.</span></span> <span data-ttu-id="d5fb2-150">如果缓冲区未满且存在未完成的响应，适配器将等待 1 秒，直到提交批处理。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-150">If the buffer is not full and there are outstanding responses then the adapter will wait for 1 second until it commits the batch.</span></span>  <span data-ttu-id="d5fb2-151">对于低延迟方案这应设置为 1，以允许适配器立即将发送响应消息到 messagebox，以进行处理。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-151">For low-latency scenarios this should be set to 1 which will allow the adapter to send response messages immediately to the message box for processing.</span></span><br /><br /> <span data-ttu-id="d5fb2-152">**最小值：** 1</span><span class="sxs-lookup"><span data-stu-id="d5fb2-152">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="d5fb2-153">**最大值：** 1024</span><span class="sxs-lookup"><span data-stu-id="d5fb2-153">**Maximum value:** 1024</span></span>|  
  
 <span data-ttu-id="d5fb2-154">**配置文件条目来控制对通过 HTTP 发送适配器的特定目标服务器的并发连接数**</span><span class="sxs-lookup"><span data-stu-id="d5fb2-154">**Configuration File Entry to Govern the Number of Concurrent Connections Made by the HTTP Send Adapter to a Particular Destination Server**</span></span>  
  
 <span data-ttu-id="d5fb2-155">可以在位于 BizTalk Server 安装目录的根目录的 BTSNTSvc.exe.config 文件中创建一项配置 HTTP 适配器打开为特定目标服务器的并发连接数。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-155">The number of concurrent connections that the HTTP adapter opens for a particular destination server can be configured by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5fb2-156">如果将消息发送到同一目标 HTTP 服务器时，才能将此属性应用于 HTTP 和 SOAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-156">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="d5fb2-157">"连接"属性的默认值为 2，可以为所有 Uri 设置为"maxconnection"属性的最大值为 20。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-157">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="d5fb2-158">下面是最大连接数属性配置的一个示例：</span><span class="sxs-lookup"><span data-stu-id="d5fb2-158">The following is an example of the configuration for the maximum connections property:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5fb2-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5fb2-159">See Also</span></span>  
 [<span data-ttu-id="d5fb2-160">配置 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="d5fb2-160">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)