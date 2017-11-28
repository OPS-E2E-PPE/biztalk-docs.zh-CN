---
title: "使用 WCF LOB 适配器 SDK 的性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b928eaf-2ab6-40a6-a1dd-804d4e89541e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead07059cac11f251d35fae18f0e228c4488c07a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="0e51b-102">使用具有 WCF LOB 适配器 SDK 的性能计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-102">Use performance counters with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="0e51b-103">你可以使用性能工具自动从正在运行的本地或远程计算机中收集性能数据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e51b-103">You can use the performance tool to automatically collect performance data from local or remote computers that are running the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="0e51b-104">你可以定义开始和停止自动日志生成时间、 从单个控制台窗口中，管理多个日志记录会话和上启用要发送的消息的计算机或要满足你的条件时启动的日志设置警报。</span><span class="sxs-lookup"><span data-stu-id="0e51b-104">You can define start and stop times for automatic log generation, manage multiple logging sessions from a single console window, and set an alert on a computer that enables a message to be sent or a log to be started when your criteria are met.</span></span> <span data-ttu-id="0e51b-105">本主题讨论的性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e51b-105">This topic discusses the performance counters for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>  
  
## <a name="performance-objects-and-counters"></a><span data-ttu-id="0e51b-106">性能对象和计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-106">Performance Objects and Counters</span></span>  
 <span data-ttu-id="0e51b-107">当你安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，安装名为"ServiceModel 适配器"的单个性能对象。</span><span class="sxs-lookup"><span data-stu-id="0e51b-107">When you install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], a single performance object named "ServiceModel Adapters" is installed.</span></span> <span data-ttu-id="0e51b-108">性能对象包含多个不同的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="0e51b-108">The performance object contains a number of different performance counters.</span></span> <span data-ttu-id="0e51b-109">性能对象测量给定的资源，应用程序或服务的活动。</span><span class="sxs-lookup"><span data-stu-id="0e51b-109">A performance object measures the activity for a given resource, application, or service.</span></span> <span data-ttu-id="0e51b-110">性能对象和计数器从其获取性能数据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、 功能，和服务计算机上的使用。</span><span class="sxs-lookup"><span data-stu-id="0e51b-110">Performance objects and counters obtain performance data from the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], features, and services on your computer as they are used.</span></span> <span data-ttu-id="0e51b-111">此性能数据通常名为组件生成数据。</span><span class="sxs-lookup"><span data-stu-id="0e51b-111">This performance data is typically named for the component that generates the data.</span></span> <span data-ttu-id="0e51b-112">性能计数器用于收集特定信息或指定的性能对象的数据。</span><span class="sxs-lookup"><span data-stu-id="0e51b-112">Performance counters are used for gathering specific information or data for a given performance object.</span></span>  
  
 <span data-ttu-id="0e51b-113">当从 ServiceModel 适配器性能对象中选择计数器，你可以选择仅通过从选择实例列表中选择的实例监视信息特定的适配器实例。</span><span class="sxs-lookup"><span data-stu-id="0e51b-113">When selecting counters from the ServiceModel Adapters performance object, you can choose to only monitor information specific adapter instances by selecting the instance from the Select Instances list.</span></span> <span data-ttu-id="0e51b-114">中的格式将列出每个适配器实例\<ProcessId > @\<ConnectionString >。</span><span class="sxs-lookup"><span data-stu-id="0e51b-114">Each adapter instance will be listed in the format of \<ProcessId>@\<ConnectionString>.</span></span> <span data-ttu-id="0e51b-115">例如， 115@echo:&#124; &#124; 主机 &#124; temp？ echoprefix = pre 指示 echo 适配器实例 115 的进程中运行。</span><span class="sxs-lookup"><span data-stu-id="0e51b-115">For example, 115@echo:&#124;&#124;host&#124;temp?echoprefix=pre indicates the echo adapter instance running in process 115.</span></span>  
  
 <span data-ttu-id="0e51b-116">有关在 WCF 中的性能计数器的信息，请参阅[WCF 性能计数器](https://msdn.microsoft.com/library/ms735098.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0e51b-116">For information about performance counters in WCF, see [WCF Performance Counters](https://msdn.microsoft.com/library/ms735098.aspx).</span></span>
  
### <a name="servicemodel-adapters-metadata-cache-performance-counters"></a><span data-ttu-id="0e51b-117">ServiceModel 适配器元数据缓存性能计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-117">ServiceModel Adapters Metadata Cache Performance Counters</span></span>  
 <span data-ttu-id="0e51b-118">下表总结了可以用于监视缓存性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e51b-118">The following table summarizes the cache performance counters that can be used to monitor the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>  
  
|<span data-ttu-id="0e51b-119">计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-119">Counter</span></span>|<span data-ttu-id="0e51b-120">Description</span><span class="sxs-lookup"><span data-stu-id="0e51b-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e51b-121">%缓存读取命中数</span><span class="sxs-lookup"><span data-stu-id="0e51b-121">% Cache read hits</span></span>|<span data-ttu-id="0e51b-122">读取适配器缓存中的命中的元数据的百分比。</span><span class="sxs-lookup"><span data-stu-id="0e51b-122">Percentage of metadata read hits in the adapter cache.</span></span>|  
|<span data-ttu-id="0e51b-123">解析的元数据</span><span class="sxs-lookup"><span data-stu-id="0e51b-123">Metadata Resolved</span></span>|<span data-ttu-id="0e51b-124">适配器已解决的元数据项目数。</span><span class="sxs-lookup"><span data-stu-id="0e51b-124">Number of metadata items resolved by the adapter.</span></span>|  
|<span data-ttu-id="0e51b-125">%缓存已满</span><span class="sxs-lookup"><span data-stu-id="0e51b-125">% Cache full</span></span>|<span data-ttu-id="0e51b-126">中使用的缓存大小限制的百分比。</span><span class="sxs-lookup"><span data-stu-id="0e51b-126">Percentage of the cache size limit in use.</span></span>|  
  
### <a name="servicemodel-adapters-connection-performance-counters"></a><span data-ttu-id="0e51b-127">ServiceModel 适配器连接性能计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-127">ServiceModel Adapters Connection Performance Counters</span></span>  
 <span data-ttu-id="0e51b-128">下表总结了可以用于监视的连接性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e51b-128">The following table summarizes the connection performance counters that can be used to monitor the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>  
  
|<span data-ttu-id="0e51b-129">计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-129">Counter</span></span>|<span data-ttu-id="0e51b-130">Description</span><span class="sxs-lookup"><span data-stu-id="0e51b-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e51b-131">中止的连接</span><span class="sxs-lookup"><span data-stu-id="0e51b-131">Aborted Connections</span></span>|<span data-ttu-id="0e51b-132">中止的目标系统连接数。</span><span class="sxs-lookup"><span data-stu-id="0e51b-132">Number of aborted target system connections.</span></span>|  
|<span data-ttu-id="0e51b-133">使用连接</span><span class="sxs-lookup"><span data-stu-id="0e51b-133">In-use Connections</span></span>|<span data-ttu-id="0e51b-134">当前正在使用目标系统连接数。</span><span class="sxs-lookup"><span data-stu-id="0e51b-134">Number of currently in-use target system connections.</span></span>|  
|<span data-ttu-id="0e51b-135">打开的连接</span><span class="sxs-lookup"><span data-stu-id="0e51b-135">Opened Connections</span></span>|<span data-ttu-id="0e51b-136">当前打开的目标系统连接数。</span><span class="sxs-lookup"><span data-stu-id="0e51b-136">Number of currently open target system connections.</span></span>|  
|<span data-ttu-id="0e51b-137">准备连接</span><span class="sxs-lookup"><span data-stu-id="0e51b-137">Ready Connections</span></span>|<span data-ttu-id="0e51b-138">可用目标系统连接数。</span><span class="sxs-lookup"><span data-stu-id="0e51b-138">Number of available target system connections.</span></span>|  
|<span data-ttu-id="0e51b-139">挂起的连接请求</span><span class="sxs-lookup"><span data-stu-id="0e51b-139">Pending Connection Requests</span></span>|<span data-ttu-id="0e51b-140">大挂起目标系统连接请求。</span><span class="sxs-lookup"><span data-stu-id="0e51b-140">Number of pending target system connection requests.</span></span>|  
  
### <a name="servicemodel-adapters-message-exchange-performance-counters"></a><span data-ttu-id="0e51b-141">ServiceModel 适配器消息交换性能计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-141">ServiceModel Adapters Message Exchange Performance Counters</span></span>  
 <span data-ttu-id="0e51b-142">下表总结了可以用于监视的消息交换性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e51b-142">The following table summarizes the message exchange performance counters that can be used to monitor the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>  
  
|<span data-ttu-id="0e51b-143">计数器</span><span class="sxs-lookup"><span data-stu-id="0e51b-143">Counter</span></span>|<span data-ttu-id="0e51b-144">Description</span><span class="sxs-lookup"><span data-stu-id="0e51b-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e51b-145">出站调用</span><span class="sxs-lookup"><span data-stu-id="0e51b-145">Outbound Calls</span></span>|<span data-ttu-id="0e51b-146">从适配器到目标系统的出站调用次数。</span><span class="sxs-lookup"><span data-stu-id="0e51b-146">Number of outbound calls from the adapter to the target system.</span></span>|  
|<span data-ttu-id="0e51b-147">出站 Calls/sec</span><span class="sxs-lookup"><span data-stu-id="0e51b-147">Outbound Calls/sec</span></span>|<span data-ttu-id="0e51b-148">出站调用数每秒从适配器到目标系统。</span><span class="sxs-lookup"><span data-stu-id="0e51b-148">Number of outbound calls per second from the adapter to the target system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e51b-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e51b-149">See Also</span></span>  
 [<span data-ttu-id="0e51b-150">解决使用 WCF LOB 适配器 SDK 创建的适配器</span><span class="sxs-lookup"><span data-stu-id="0e51b-150">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)