---
title: "BAM 侦听器是什么？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9400e80a2f8e8acfdeb12e3d6e61a046151d1e7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-bam-interceptor"></a><span data-ttu-id="84679-103">BAM 侦听器是什么？</span><span class="sxs-lookup"><span data-stu-id="84679-103">What Is the BAM Interceptor?</span></span>
## <a name="overview"></a><span data-ttu-id="84679-104">概述</span><span class="sxs-lookup"><span data-stu-id="84679-104">Overview</span></span> 

<span data-ttu-id="84679-105">BAM 侦听器是一种对象，使用它可以装备应用程序来捕获目标数据。</span><span class="sxs-lookup"><span data-stu-id="84679-105">The BAM Interceptor is an object that lets you instrument your application to capture data of interest.</span></span> <span data-ttu-id="84679-106">以下关系图显示 BAM 侦听器的角色以及它与其他 BAM 组件的交互过程：</span><span class="sxs-lookup"><span data-stu-id="84679-106">The following diagram shows the role of the BAM interceptor and its interaction with the other BAM components:</span></span>  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
<span data-ttu-id="84679-107">BAM 拦截器</span><span class="sxs-lookup"><span data-stu-id="84679-107">BAM Interceptor</span></span>  
  
 <span data-ttu-id="84679-108">在可能具有目标数据应用程序的每一步中，调用侦听器 OnStep，为每一步提供标识符，并提供应用程序中正使用的某个数据对象或任意对象。</span><span class="sxs-lookup"><span data-stu-id="84679-108">In each step of your application where you could have data of interest, you call Interceptor OnStep, provide an identifier for the step, and provide some data or arbitrary object that you are using in your application.</span></span>  
  
 <span data-ttu-id="84679-109">然后必须实现一个回调函数，当回调发生时，回调过程获取当前的步骤 ID 和数据对象。</span><span class="sxs-lookup"><span data-stu-id="84679-109">You must implement a callback function so when the callback occurs, your callback procedure gets the current step ID and your data object.</span></span> <span data-ttu-id="84679-110">实际上，BAM 侦听器只是将数据对象传播到回调中。</span><span class="sxs-lookup"><span data-stu-id="84679-110">Essentially, the BAM interceptor is simply propagating the data object to the callback.</span></span> <span data-ttu-id="84679-111">而提取数据的实际逻辑驻留在应用程序中。</span><span class="sxs-lookup"><span data-stu-id="84679-111">The actual logic of extracting data resides in your application.</span></span> <span data-ttu-id="84679-112">例如，如果数据采用 XML 消息形式，则回调将使用 XPath。</span><span class="sxs-lookup"><span data-stu-id="84679-112">For example, if your data takes the form of XML messages, then the callback will use XPaths.</span></span> <span data-ttu-id="84679-113">有关 Xpath 的详细信息，请参阅[消息分配中使用 Xpath](../core/using-xpaths-in-message-assignments.md)。</span><span class="sxs-lookup"><span data-stu-id="84679-113">For more information about XPaths, see [Using XPaths in Message Assignment](../core/using-xpaths-in-message-assignments.md).</span></span>  
  
 <span data-ttu-id="84679-114">BAM 侦听器基于可编程创建的配置在每一步中判断是否有需要的数据。</span><span class="sxs-lookup"><span data-stu-id="84679-114">The BAM interceptor decides which data to request at each step, based on the configuration that you can create programmatically.</span></span> <span data-ttu-id="84679-115">然后，BAM 侦听器使用获得的数据来调用需要使用的、每次作为参数传递给 OnStep 的 DirectEventStream 或 BufferedEventStream。</span><span class="sxs-lookup"><span data-stu-id="84679-115">The BAM Interceptor then uses the obtained data to call either DirectEventStream or BufferedEventStream that you need to keep around and pass each time as an argument to OnStep.</span></span>  
  
 <span data-ttu-id="84679-116">为每一步调用侦听器不会占用大量资源。</span><span class="sxs-lookup"><span data-stu-id="84679-116">Calling the interceptor for each step is not a resource-intensive operation.</span></span> <span data-ttu-id="84679-117">如果为此步骤调用侦听器但没有注册任何内容，则侦听器立即返回。</span><span class="sxs-lookup"><span data-stu-id="84679-117">If you call and you register nothing for this step, the interceptor returns immediately.</span></span> <span data-ttu-id="84679-118">这意味着没有磁盘操作，没有事务，甚至没有内存分配；因此，对性能几乎没有影响。</span><span class="sxs-lookup"><span data-stu-id="84679-118">This means that there are no disk operations, no transactions, not even memory allocations, and thus almost no performance impact.</span></span> <span data-ttu-id="84679-119">同时，还有机会在必要时为 BAM 提取数据。</span><span class="sxs-lookup"><span data-stu-id="84679-119">At the same time, you have the opportunity to extract any data for BAM if necessary.</span></span> <span data-ttu-id="84679-120">对数据提取和数据的可用性所涉及的步骤的性能影响将取决于你的实现`IBAMDataExtractor Interface`。</span><span class="sxs-lookup"><span data-stu-id="84679-120">The performance impact on the steps involving data extraction and the availability of the data will depend on your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="84679-121">以下代码示例演示在配置和运行时期间如何使用侦听器。</span><span class="sxs-lookup"><span data-stu-id="84679-121">The following code examples demonstrate the use of the interceptor during configuration and run time.</span></span>  
  
## <a name="configuration-time"></a><span data-ttu-id="84679-122">配置时</span><span class="sxs-lookup"><span data-stu-id="84679-122">Configuration time</span></span>  
 <span data-ttu-id="84679-123">以下代码显示如何配置侦听器，以便在应用程序的 recvPO 步骤处停止，然后要求输入 客户名称和客户 SSN：</span><span class="sxs-lookup"><span data-stu-id="84679-123">The following code shows how you configure the Interceptor to stop at step recvPO of the application, and ask for Customer Name and Customer SSN:</span></span>  
  
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
  
 <span data-ttu-id="84679-124">创建某个侦听器实例后，可以将其存储起来，以便将来在运行时使用。</span><span class="sxs-lookup"><span data-stu-id="84679-124">After you create an interceptor instance, you can store it for later use at runtime.</span></span>  
  
 <span data-ttu-id="84679-125">您可以保存代表不同数据首选项和 BAM 里程碑的、预先创建的不同侦听器。</span><span class="sxs-lookup"><span data-stu-id="84679-125">You may keep different pre-created interceptors representing different preferences for the data and milestones for BAM.</span></span> <span data-ttu-id="84679-126">为了获得最佳性能，请使用 BinaryFormatter 类序列化侦听器实例。</span><span class="sxs-lookup"><span data-stu-id="84679-126">For best performance, serialize the Interceptor instances using the BinaryFormatter class.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="84679-127">运行的时</span><span class="sxs-lookup"><span data-stu-id="84679-127">Run time</span></span>  
 <span data-ttu-id="84679-128">在生产环境中使用以下代码，以便在运行时使用侦听器：</span><span class="sxs-lookup"><span data-stu-id="84679-128">Use this code to use the interceptor at runtime in a production environment:</span></span>  
  
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
  
 <span data-ttu-id="84679-129">其中：</span><span class="sxs-lookup"><span data-stu-id="84679-129">Where:</span></span>  
  
-   <span data-ttu-id="84679-130">*recvPO*和*approvePO*是用于标识你的应用程序中的步骤的任意对象。</span><span class="sxs-lookup"><span data-stu-id="84679-130">*recvPO* and *approvePO* are arbitrary objects you use to identify the steps in your application.</span></span>  
  
-   <span data-ttu-id="84679-131">*data1*和*data2*是你已在该点，并可能包含有趣的数据 – 例如采购订单的 XML 文档的任意对象。</span><span class="sxs-lookup"><span data-stu-id="84679-131">*data1* and *data2* are arbitrary objects that you have at that point and may contain interesting data – for example the XML document of the purchase order.</span></span>  
  
-   <span data-ttu-id="84679-132">*es*是 DirectEventStream 或 BufferedEvent 流，具体取决于您的性能要求。</span><span class="sxs-lookup"><span data-stu-id="84679-132">*es* is either DirectEventStream or BufferedEvent stream depending on your performance requirements.</span></span>  
  
-   <span data-ttu-id="84679-133">*回调*是你实现`IBAMDataExtractor Interface`。</span><span class="sxs-lookup"><span data-stu-id="84679-133">*callback* is your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="84679-134">SDK 示例中， [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)，演示如何使用侦听器，其中包含两个配置工具和示例运行时应用程序。</span><span class="sxs-lookup"><span data-stu-id="84679-134">The SDK sample, [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md), demonstrates using the Interceptor, which contains both a configuration tool and example runtime application.</span></span>  
  
 <span data-ttu-id="84679-135">BizTalk 业务流程引擎允许进行侦听，这样就能够在运行时使用跟踪配置文件编辑器更改为 BAM 收集的数据。</span><span class="sxs-lookup"><span data-stu-id="84679-135">The BizTalk Orchestration Engine accommodates interception, which allows changing what data is collected for BAM at runtime using the Tracking Profile Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84679-136">本节内容</span><span class="sxs-lookup"><span data-stu-id="84679-136">In This Section</span></span>  
  
-   [<span data-ttu-id="84679-137">如何确定并设置为活动的事件写入者角色</span><span class="sxs-lookup"><span data-stu-id="84679-137">How to Determine and Set Event Writer Roles for Activities</span></span>](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="84679-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84679-138">See Also</span></span>  
 [<span data-ttu-id="84679-139">BAM API （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="84679-139">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)