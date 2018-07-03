---
title: 运行预定义的路线接入点示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e428a9106582e5bad3408cfb6643cc5da21ac74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996582"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a><span data-ttu-id="8ab02-102">运行预定义的路线接入点示例</span><span class="sxs-lookup"><span data-stu-id="8ab02-102">Run a Predefined Itinerary On-Ramp Sample</span></span>
<span data-ttu-id="8ab02-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括可以执行的 20 预定义的路线用例。</span><span class="sxs-lookup"><span data-stu-id="8ab02-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes 20 predefined Itinerary use cases you can execute.</span></span> <span data-ttu-id="8ab02-104">有关这些列表的用例，请参阅[示例路线方案](../esb-toolkit/the-sample-itinerary-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="8ab02-104">For a list of these use cases, see [The Sample Itinerary Scenarios](../esb-toolkit/the-sample-itinerary-scenarios.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ab02-105">在运行任何示例之前，您必须手动导入相应的路线的绑定文件从 \Source\Samples\Itinerary\Install\Binding 文件夹到 GlobalBank.ESB BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ab02-105">Before you run any of the samples, you must manually import the appropriate itinerary binding file from the \Source\Samples\Itinerary\Install\Binding folder into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="8ab02-106">此绑定文件将重置两个动态发送端口上的属性。</span><span class="sxs-lookup"><span data-stu-id="8ab02-106">This binding file resets the properties on the two dynamic send ports.</span></span> <span data-ttu-id="8ab02-107">导入名为 GlobalBank.ESB.Itinerary_Bindings.xml 的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8ab02-107">Import the binding file named GlobalBank.ESB.Itinerary_Bindings.xml.</span></span>  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a><span data-ttu-id="8ab02-108">若要运行其中一个预定义路线接入点示例</span><span class="sxs-lookup"><span data-stu-id="8ab02-108">To run one of the pre-defined Itinerary On-Ramp samples</span></span>  
  
1. <span data-ttu-id="8ab02-109">如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="8ab02-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="8ab02-110">在 Windows 资源管理器中，打开子文件夹 \Source\Samples\Itinerary\Source\ESB。Itinerary.Test\bin\Debug 其中您安装了 BizTalk ESB 工具包示例中，然后再开始应用程序名为 Esb.Itinerary.Test.exe。</span><span class="sxs-lookup"><span data-stu-id="8ab02-110">In Windows Explorer, open the subfolder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the BizTalk ESB Toolkit samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="8ab02-111">单击**LoadItinerary**按钮，并选择示例路线名为 TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8ab02-111">Click the **LoadItinerary** button, and then select the sample itinerary named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml from the \Source\Samples\Itinerary\Itineraries folder.</span></span>  
  
4. <span data-ttu-id="8ab02-112">在中**Web 服务选项**部分中，选择**双向服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="8ab02-112">In the **Web Service Options** section, select the **Two-Way Service** check box.</span></span> <span data-ttu-id="8ab02-113">这会指示测试客户端来执行请求-响应路线服务操作。</span><span class="sxs-lookup"><span data-stu-id="8ab02-113">This instructs the test client to perform a request-response itinerary service operation.</span></span>  
  
5. <span data-ttu-id="8ab02-114">（可选）选择**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而不是默认 OnRamp.Itinerary.Response.SOAP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="8ab02-114">(Optional) Select the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6. <span data-ttu-id="8ab02-115">单击**LoadMessage**按钮，并从 \Source\Samples\Itinerary\Test\Data 文件夹选择 NAOrderDoc.xml 示例消息。</span><span class="sxs-lookup"><span data-stu-id="8ab02-115">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="8ab02-116">单击**SubmitRequest**按钮以将请求发送到路线接入点服务。</span><span class="sxs-lookup"><span data-stu-id="8ab02-116">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="8ab02-117">图 1 显示的结果。</span><span class="sxs-lookup"><span data-stu-id="8ab02-117">Figure 1 shows the result.</span></span>  
  
   <span data-ttu-id="8ab02-118">![在负载增加路线](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")</span><span class="sxs-lookup"><span data-stu-id="8ab02-118">![Itinerary On Ramp](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")</span></span>  
  
   <span data-ttu-id="8ab02-119">**图 1**</span><span class="sxs-lookup"><span data-stu-id="8ab02-119">**Figure 1**</span></span>  
  
   <span data-ttu-id="8ab02-120">**运行路线接入点示例之一的路线接入点客户端应用程序**</span><span class="sxs-lookup"><span data-stu-id="8ab02-120">**The Itinerary On-Ramp client application running one of the Itinerary On-Ramp samples**</span></span>  
  
   <span data-ttu-id="8ab02-121">路线的定义中指定的服务的名称直接对应于**ServiceName**示例订阅的服务的属性。</span><span class="sxs-lookup"><span data-stu-id="8ab02-121">The name of the service specified in the itinerary definition corresponds directly to the **ServiceName** property of the service to which the sample subscribes.</span></span> <span data-ttu-id="8ab02-122">在上一过程 (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) 中执行路线示例中，执行的第一个服务是基于业务流程的服务，执行的转换。</span><span class="sxs-lookup"><span data-stu-id="8ab02-122">In the itinerary sample executed in the previous procedure (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml), the first service executed is an orchestration-based service that performs a transformation.</span></span> <span data-ttu-id="8ab02-123">路线的以下节指定此服务。</span><span class="sxs-lookup"><span data-stu-id="8ab02-123">The following section of the itinerary specifies this service.</span></span>  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 <span data-ttu-id="8ab02-124">在此业务流程服务**\<服务\>** 元素指定了图 2 所示的筛选器属性的直接绑定业务流程。</span><span class="sxs-lookup"><span data-stu-id="8ab02-124">The orchestration service in this **\<Service\>** element specifies the direct-bound orchestration that has the filter properties shown in Figure 2.</span></span> <span data-ttu-id="8ab02-125">请注意，业务流程订阅仅向具有的值的消息**Microsoft.Practices.ESB.Services.Transform**有关**ServiceName**上下文属性、 值**挂起**有关**ServiceState**上下文属性和值的业务流程用于**ServiceType**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="8ab02-125">Notice that the orchestration subscribes only to messages that have the value **Microsoft.Practices.ESB.Services.Transform** for the **ServiceName** context property, the value **Pending** for the **ServiceState** context property, and the value Orchestration for the **ServiceType** context property.</span></span>  
  
 <span data-ttu-id="8ab02-126">![筛选表达式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")</span><span class="sxs-lookup"><span data-stu-id="8ab02-126">![Filter Expression](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")</span></span>  
  
 <span data-ttu-id="8ab02-127">**图 2**</span><span class="sxs-lookup"><span data-stu-id="8ab02-127">**Figure 2**</span></span>  
  
 <span data-ttu-id="8ab02-128">**路线接入点示例中使用直接绑定业务流程筛选器表达式**</span><span class="sxs-lookup"><span data-stu-id="8ab02-128">**The filter expression for the direct-bound orchestration used in the Itinerary On-Ramp sample**</span></span>