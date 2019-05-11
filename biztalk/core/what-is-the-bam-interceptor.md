---
title: 什么是 BAM 侦听器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dbd9b3a2bff2d6a858de372de5e06b1ff6cbbde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243061"
---
# <a name="what-is-the-bam-interceptor"></a><span data-ttu-id="16537-103">什么是 BAM 侦听器？</span><span class="sxs-lookup"><span data-stu-id="16537-103">What Is the BAM Interceptor?</span></span>
## <a name="overview"></a><span data-ttu-id="16537-104">概述</span><span class="sxs-lookup"><span data-stu-id="16537-104">Overview</span></span> 

<span data-ttu-id="16537-105">BAM 侦听器是一个对象，它可以装备应用程序以捕获感兴趣的数据。</span><span class="sxs-lookup"><span data-stu-id="16537-105">The BAM Interceptor is an object that lets you instrument your application to capture data of interest.</span></span> <span data-ttu-id="16537-106">下图显示了 BAM 侦听器和及其与其他 BAM 组件的交互的角色：</span><span class="sxs-lookup"><span data-stu-id="16537-106">The following diagram shows the role of the BAM interceptor and its interaction with the other BAM components:</span></span>  
  
 <span data-ttu-id="16537-107">![](../core/media/bam-config-api.gif "bam_config_api")</span><span class="sxs-lookup"><span data-stu-id="16537-107">![](../core/media/bam-config-api.gif "bam_config_api")</span></span>  
<span data-ttu-id="16537-108">BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="16537-108">BAM Interceptor</span></span>  
  
 <span data-ttu-id="16537-109">在应用程序可能有感兴趣的数据的位置的每个步骤中，调用侦听器 OnStep、 步骤中，提供标识符和提供某些数据或使用应用程序中的任意对象。</span><span class="sxs-lookup"><span data-stu-id="16537-109">In each step of your application where you could have data of interest, you call Interceptor OnStep, provide an identifier for the step, and provide some data or arbitrary object that you are using in your application.</span></span>  
  
 <span data-ttu-id="16537-110">必须实现一个回调函数，当回调发生时，回调过程获取当前步骤 ID 和数据对象。</span><span class="sxs-lookup"><span data-stu-id="16537-110">You must implement a callback function so when the callback occurs, your callback procedure gets the current step ID and your data object.</span></span> <span data-ttu-id="16537-111">从根本上讲，BAM 侦听器只需将传播到回调的数据对象。</span><span class="sxs-lookup"><span data-stu-id="16537-111">Essentially, the BAM interceptor is simply propagating the data object to the callback.</span></span> <span data-ttu-id="16537-112">提取数据的实际逻辑驻留在你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="16537-112">The actual logic of extracting data resides in your application.</span></span> <span data-ttu-id="16537-113">例如，如果数据采用 XML 消息形式，回调将使用的 Xpath。</span><span class="sxs-lookup"><span data-stu-id="16537-113">For example, if your data takes the form of XML messages, then the callback will use XPaths.</span></span> <span data-ttu-id="16537-114">有关 Xpath 的详细信息，请参阅[在消息赋值中使用 Xpath](../core/using-xpaths-in-message-assignments.md)。</span><span class="sxs-lookup"><span data-stu-id="16537-114">For more information about XPaths, see [Using XPaths in Message Assignment](../core/using-xpaths-in-message-assignments.md).</span></span>  
  
 <span data-ttu-id="16537-115">BAM 侦听器决定要在每一步，基于可以以编程方式创建的配置数据。</span><span class="sxs-lookup"><span data-stu-id="16537-115">The BAM interceptor decides which data to request at each step, based on the configuration that you can create programmatically.</span></span> <span data-ttu-id="16537-116">BAM 侦听器使用获得的数据来调用 DirectEventStream 或 BufferedEventStream 需要作为自变量的每次传递给 OnStep 的。</span><span class="sxs-lookup"><span data-stu-id="16537-116">The BAM Interceptor then uses the obtained data to call either DirectEventStream or BufferedEventStream that you need to keep around and pass each time as an argument to OnStep.</span></span>  
  
 <span data-ttu-id="16537-117">为每个步骤调用侦听器不占用大量资源的操作。</span><span class="sxs-lookup"><span data-stu-id="16537-117">Calling the interceptor for each step is not a resource-intensive operation.</span></span> <span data-ttu-id="16537-118">如果您调用并注册任何关于此步骤的信息，则侦听器立即返回。</span><span class="sxs-lookup"><span data-stu-id="16537-118">If you call and you register nothing for this step, the interceptor returns immediately.</span></span> <span data-ttu-id="16537-119">这意味着有没有磁盘操作，没有事务，甚至没有内存分配，因此性能几乎没有影响。</span><span class="sxs-lookup"><span data-stu-id="16537-119">This means that there are no disk operations, no transactions, not even memory allocations, and thus almost no performance impact.</span></span> <span data-ttu-id="16537-120">同时，您将有机会为 BAM 提取的任何数据，如有必要。</span><span class="sxs-lookup"><span data-stu-id="16537-120">At the same time, you have the opportunity to extract any data for BAM if necessary.</span></span> <span data-ttu-id="16537-121">涉及数据提取和数据的可用性的步骤对性能的影响取决于您的实现的`IBAMDataExtractor Interface`。</span><span class="sxs-lookup"><span data-stu-id="16537-121">The performance impact on the steps involving data extraction and the availability of the data will depend on your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="16537-122">下面的代码示例演示使用侦听器配置期间和运行时。</span><span class="sxs-lookup"><span data-stu-id="16537-122">The following code examples demonstrate the use of the interceptor during configuration and run time.</span></span>  
  
## <a name="configuration-time"></a><span data-ttu-id="16537-123">配置时间</span><span class="sxs-lookup"><span data-stu-id="16537-123">Configuration time</span></span>  
 <span data-ttu-id="16537-124">下面的代码演示如何配置侦听器，以便该应用程序的 recvPO 步骤处停止，并请求客户名称和客户 SSN:</span><span class="sxs-lookup"><span data-stu-id="16537-124">The following code shows how you configure the Interceptor to stop at step recvPO of the application, and ask for Customer Name and Customer SSN:</span></span>  
  
```  
ActivityInterceptorConfiguration cfg= new ActivityInterceptorConfiguration ("PurchaseOrder");  
...  
cfg.RegisterDataExtraction("CustomerName",recvPO,XpathName);  
cfg.RegisterDataExtraction("CustomerSSN",recvPO,XpathSSN);  
...  
BAMInterceptor interceptor=new BAMInterceptor();  
cfg.UpdateInterceptor(interceptor);  
...  
// The interceptor instance is ready.  
```  
  
 <span data-ttu-id="16537-125">创建某个侦听器实例后，可以将其存储在运行时的更高版本使用。</span><span class="sxs-lookup"><span data-stu-id="16537-125">After you create an interceptor instance, you can store it for later use at runtime.</span></span>  
  
 <span data-ttu-id="16537-126">您可以保存代表不同数据首选项和 BAM 里程碑的不同预创建的侦听器。</span><span class="sxs-lookup"><span data-stu-id="16537-126">You may keep different pre-created interceptors representing different preferences for the data and milestones for BAM.</span></span> <span data-ttu-id="16537-127">为了获得最佳性能，序列化侦听器实例使用 BinaryFormatter 类。</span><span class="sxs-lookup"><span data-stu-id="16537-127">For best performance, serialize the Interceptor instances using the BinaryFormatter class.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="16537-128">运行的时</span><span class="sxs-lookup"><span data-stu-id="16537-128">Run time</span></span>  
 <span data-ttu-id="16537-129">使用以下代码在生产环境中运行时使用的侦听器：</span><span class="sxs-lookup"><span data-stu-id="16537-129">Use this code to use the interceptor at runtime in a production environment:</span></span>  
  
```  
// Deserialize the Interceptor that was prepared before  
...  
es=new DirectEventStream(...)  
...  
Interceptor.OnStep(recvPO, data1, es, callback)  
...  
Interceptor.OnStep(approvePO, data2, es, callback)  
...  
```  
  
 <span data-ttu-id="16537-130">其中：</span><span class="sxs-lookup"><span data-stu-id="16537-130">Where:</span></span>  
  
- <span data-ttu-id="16537-131">*recvPO*并*approvePO*是用于标识你的应用程序中的步骤的任意对象。</span><span class="sxs-lookup"><span data-stu-id="16537-131">*recvPO* and *approvePO* are arbitrary objects you use to identify the steps in your application.</span></span>  
  
- <span data-ttu-id="16537-132">*data1*并*data2*是任意对象已存在的可能包含感兴趣的数据 – 例如采购订单的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="16537-132">*data1* and *data2* are arbitrary objects that you have at that point and may contain interesting data – for example the XML document of the purchase order.</span></span>  
  
- <span data-ttu-id="16537-133">*es*是 DirectEventStream 或 BufferedEvent 流，具体取决于你的性能要求。</span><span class="sxs-lookup"><span data-stu-id="16537-133">*es* is either DirectEventStream or BufferedEvent stream depending on your performance requirements.</span></span>  
  
- <span data-ttu-id="16537-134">*回调*是的实现`IBAMDataExtractor Interface`。</span><span class="sxs-lookup"><span data-stu-id="16537-134">*callback* is your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
  <span data-ttu-id="16537-135">SDK 示例中， [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)，演示了如何使用侦听器，其中包含这两种配置工具和示例运行时应用程序。</span><span class="sxs-lookup"><span data-stu-id="16537-135">The SDK sample, [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md), demonstrates using the Interceptor, which contains both a configuration tool and example runtime application.</span></span>  
  
  <span data-ttu-id="16537-136">BizTalk 业务流程引擎允许进行侦听，这样就能够更改在运行时使用跟踪配置文件编辑器为 BAM 收集哪些数据。</span><span class="sxs-lookup"><span data-stu-id="16537-136">The BizTalk Orchestration Engine accommodates interception, which allows changing what data is collected for BAM at runtime using the Tracking Profile Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16537-137">本节内容</span><span class="sxs-lookup"><span data-stu-id="16537-137">In This Section</span></span>  
  
-   [<span data-ttu-id="16537-138">如何确定和设置活动的事件写入者角色</span><span class="sxs-lookup"><span data-stu-id="16537-138">How to Determine and Set Event Writer Roles for Activities</span></span>](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="16537-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="16537-139">See Also</span></span>  
 [<span data-ttu-id="16537-140">BAM API（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="16537-140">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)