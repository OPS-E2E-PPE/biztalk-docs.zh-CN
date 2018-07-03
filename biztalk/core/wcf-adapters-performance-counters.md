---
title: WCF 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b916b6212da18dcf4aa48d4ca941e23413513d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016248"
---
# <a name="wcf-adapters-performance-counters"></a><span data-ttu-id="6a3a1-102">WCF 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="6a3a1-102">WCF Adapters Performance Counters</span></span>
<span data-ttu-id="6a3a1-103">性能计数器可用于监视的系统的站点上的服务执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-103">Performance counters enable you to monitor specific aspects of work performed on the site or system by a service.</span></span> <span data-ttu-id="6a3a1-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span> <span data-ttu-id="6a3a1-105">WCF 适配器不提供自己的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-105">The WCF adapters do not provide their own performance counters.</span></span> <span data-ttu-id="6a3a1-106">但是，您可以监控 Windows Communication Foundation (WCF) 性能计数器以衡量 WCF 接收位置的性能。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-106">However, you can monitor the performance counters of Windows Communication Foundation (WCF) to gauge the performance of the WCF receive locations.</span></span> <span data-ttu-id="6a3a1-107">若要将 WCF 性能计数器用于 WCF 接收位置，则必须为运行接收位置的主机实例启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-107">To use the WCF performance counters for the WCF receive locations, you have to enable the performance counters for the host instances running the receive locations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a3a1-108">WCF 性能计数器不可用于 WCF 发送端口。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-108">The WCF performance counters are not available for WCF send ports.</span></span>  
  
 <span data-ttu-id="6a3a1-109">对于进程内 WCF 适配器，可以通过 BTSNTSvc.exe.config 文件启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-109">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="6a3a1-110">对于独立 WCF 适配器，可以修改 Web.config 文件以启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-110">For the isolated WCF adapters, you can modify the Web.config file to enable the performance counters.</span></span> <span data-ttu-id="6a3a1-111">有关 WCF 性能计数器的详细信息，请参阅"WCF 性能计数器"处[ http://go.microsoft.com/fwlink/?LinkID=87245 ](http://go.microsoft.com/fwlink/?LinkID=87245)。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-111">For more information about the WCF performance counters, see "WCF Performance Counters" at [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245).</span></span>  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a><span data-ttu-id="6a3a1-112">为 WCF 接收位置启用 WCF 性能计数器</span><span class="sxs-lookup"><span data-stu-id="6a3a1-112">Enabling the WCF Performance Counters for the WCF Receive Locations</span></span>  
 <span data-ttu-id="6a3a1-113">对于进程内 WCF 适配器，可以通过 BTSNTSvc.exe.config 文件启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-113">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span>  
  
 <span data-ttu-id="6a3a1-114">对于独立 WCF 适配器，可以通过修改 BizTalk WCF 服务发布向导在 Web 应用程序文件夹中创建的 Web.config 文件来启用 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-114">For the isolated WCF adapters, you can enable WCF tracing by modifying the Web.config file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder</span></span>  
  
 <span data-ttu-id="6a3a1-115">若要修改 BTSNtSvc.exe.config 或 Web.config，请打开相应配置文件，然后配置 WCF 跟踪，如下面的配置示例所示：</span><span class="sxs-lookup"><span data-stu-id="6a3a1-115">To modify BTSNtSvc.exe.config or Web.config, open the configuration file, and then configure WCF tracing, as indicated in the following configuration example:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a3a1-116">BTSNTSvc.exe.config 文件始终与 BTSNTSvc.exe 文件位于同一目录中，所在目录通常为 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-116">The BTSNTSvc.exe.config file is always located in the same directory as the BTSNTSvc.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 <span data-ttu-id="6a3a1-117">**PerformanceCounters**属性可设置为启用特定类型的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-117">The **performanceCounters** attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="6a3a1-118">有效值为</span><span class="sxs-lookup"><span data-stu-id="6a3a1-118">Valid values are</span></span>  
  
- <span data-ttu-id="6a3a1-119">**所有**： 所有类别计数器 (**ServiceModelService**， **ServiceModelEndpoint**，并且**ServiceModelOperation**) 启用。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-119">**All**: All category counters (**ServiceModelService**, **ServiceModelEndpoint**, and **ServiceModelOperation**) are enabled.</span></span>  
  
- <span data-ttu-id="6a3a1-120">**ServiceOnly**： 仅**ServiceModelService**启用类别计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-120">**ServiceOnly**: Only **ServiceModelService** category counters are enabled.</span></span>  
  
- <span data-ttu-id="6a3a1-121">**关闭**： 禁用 ServiceModel \* 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-121">**Off**: ServiceModel\* performance counters are disabled.</span></span> <span data-ttu-id="6a3a1-122">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-122">This is the default value.</span></span>  
  
  <span data-ttu-id="6a3a1-123">修改 BTSNTSvc.exe.config 文件之后，必须重新启动运行进程内 WCF 接收位置的主机实例。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-123">After modifying the BTSNTSvc.exe.config file, you must restart the host instances running the in-process WCF receive locations.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="6a3a1-124">性能计数器的类型</span><span class="sxs-lookup"><span data-stu-id="6a3a1-124">Types of Performance Counters</span></span>  
 <span data-ttu-id="6a3a1-125">WCF 性能计数器可分为三个不同级别： 服务、 终结点和操作。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-125">WCF performance counters are scoped to three different levels: service, endpoint, and operation.</span></span>  
  
 <span data-ttu-id="6a3a1-126">**服务性能计数器**</span><span class="sxs-lookup"><span data-stu-id="6a3a1-126">**Service performance counters**</span></span>  
  
 <span data-ttu-id="6a3a1-127">服务性能计数器评估整个服务行为，可用于诊断整个服务的性能。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-127">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="6a3a1-128">下可找到这些**ServiceModelService 3.0.0.0**性能对象时使用性能监视器查看。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-128">They are found under the **ServiceModelService 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="6a3a1-129">实例使用以下模式进行命名：</span><span class="sxs-lookup"><span data-stu-id="6a3a1-129">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 <span data-ttu-id="6a3a1-130">因为 WCF 适配器为每个接收位置创建一个单独的服务主机，所以会为每个接收位置创建一个性能计数器实例。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-130">Because the WCF adapters create a separate service host for each receive location, a performance counter instance is created for each receive location.</span></span> <span data-ttu-id="6a3a1-131">有关实现 WCF 的服务类的详细信息的服务协定，请参阅**BizTalkServiceInstance 类** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-131">For more information about the service class implementing the WCF service contracts, see the **BizTalkServiceInstance Class** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
 <span data-ttu-id="6a3a1-132">**终结点性能计数器**</span><span class="sxs-lookup"><span data-stu-id="6a3a1-132">**Endpoint performance counters**</span></span>  
  
 <span data-ttu-id="6a3a1-133">使用终结点性能计数器可以查看反映终结点接受消息时所采用方式的数据。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-133">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="6a3a1-134">下可找到这些**ServiceModelEndpoint 3.0.0.0**性能对象时使用性能监视器查看。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-134">They are found under the **ServiceModelEndpoint 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="6a3a1-135">实例使用以下模式进行命名：</span><span class="sxs-lookup"><span data-stu-id="6a3a1-135">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 <span data-ttu-id="6a3a1-136">对每个接收位置均会创建一个性能计数器实例。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-136">A performance counter instance is created for each receive location.</span></span> <span data-ttu-id="6a3a1-137">在上面的模式中，WCF 服务约定的名称表示 WCF 适配器选择用于通过接收位置接收消息的服务约定。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-137">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="6a3a1-138">有关 WCF 适配器如何选择服务协定从可用 WCF 服务协定，请参阅**WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-138">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="6a3a1-139">**操作性能计数器**</span><span class="sxs-lookup"><span data-stu-id="6a3a1-139">**Operation performance counters**</span></span>  
  
 <span data-ttu-id="6a3a1-140">下找到操作性能计数器**ServiceModelOperation 3.0.0.0**性能对象时使用性能监视器查看。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-140">Operation performance counters are found under the **ServiceModelOperation 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="6a3a1-141">对每个接收位置会创建两个性能计数器实例。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-141">Two performance counter instances are created for each receive location.</span></span> <span data-ttu-id="6a3a1-142">其中一个对象实例使用以下模式进行命名：</span><span class="sxs-lookup"><span data-stu-id="6a3a1-142">One of the object instances is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 <span data-ttu-id="6a3a1-143">在上面的模式中，WCF 服务约定的名称表示 WCF 适配器选择用于通过接收位置接收消息的服务约定。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-143">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="6a3a1-144">**biztalksubmit**是服务协定中声明的操作名称，将导致运行时元数据中创建 WSDL 操作。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-144">**biztalksubmit** is an operation name declared in the service contract, and causes the runtime to create WSDL operations in the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a3a1-145">有关 WCF 适配器如何选择服务协定从可用 WCF 服务协定，请参阅**WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-145">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="6a3a1-146">另一个对象实例使用以下模式进行命名：</span><span class="sxs-lookup"><span data-stu-id="6a3a1-146">The other object instance is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 <span data-ttu-id="6a3a1-147">此性能计数器实例表示异步处理通过接收位置传入的消息的操作。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-147">This performance counter instance represents the operation that asynchronously processes messages incoming through the receive location.</span></span> <span data-ttu-id="6a3a1-148">此实例的操作名称部分可以是**twowaymethod**或**onewaymethod**根据 WCF 适配器的接收位置中使用的类型。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-148">The operation name part of this instance can be **twowaymethod** or **onewaymethod** depending on the type of WCF adapter used in the receive location.</span></span> <span data-ttu-id="6a3a1-149">如果使用 Wcf-netmsmq 适配器，实例拥有**onewaymethod**创建操作名称。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-149">If you use the WCF-NetMsmq adapter, an instance having the **onewaymethod** operation name is created.</span></span> <span data-ttu-id="6a3a1-150">对于其他适配器， **twowaymethod**用于操作名称部分。</span><span class="sxs-lookup"><span data-stu-id="6a3a1-150">For the other adapters, **twowaymethod** is used for the operation name part.</span></span>