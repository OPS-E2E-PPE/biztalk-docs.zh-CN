---
title: "运行预定义的路线上负载增加示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 167d18f0eba624d62b03b3b0a5386fcac04e5b18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a><span data-ttu-id="b5266-102">运行预定义的路线上负载增加示例</span><span class="sxs-lookup"><span data-stu-id="b5266-102">Run a Predefined Itinerary On-Ramp Sample</span></span>
<span data-ttu-id="b5266-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括预定义的 20 路线用例可以执行。</span><span class="sxs-lookup"><span data-stu-id="b5266-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes 20 predefined Itinerary use cases you can execute.</span></span> <span data-ttu-id="b5266-104">有关这些列表用例，请参阅[示例路线方案](../esb-toolkit/the-sample-itinerary-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="b5266-104">For a list of these use cases, see [The Sample Itinerary Scenarios](../esb-toolkit/the-sample-itinerary-scenarios.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5266-105">在运行任何示例之前，你必须手动从导入合适的路线绑定文件 \Source\Samples\Itinerary\Install\Binding 文件夹到 GlobalBank.ESB BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5266-105">Before you run any of the samples, you must manually import the appropriate itinerary binding file from the \Source\Samples\Itinerary\Install\Binding folder into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="b5266-106">此绑定文件将重置两个动态发送端口上的属性。</span><span class="sxs-lookup"><span data-stu-id="b5266-106">This binding file resets the properties on the two dynamic send ports.</span></span> <span data-ttu-id="b5266-107">导入名为 GlobalBank.ESB.Itinerary_Bindings.xml 的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="b5266-107">Import the binding file named GlobalBank.ESB.Itinerary_Bindings.xml.</span></span>  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a><span data-ttu-id="b5266-108">若要运行的预定义的路线入口示例之一</span><span class="sxs-lookup"><span data-stu-id="b5266-108">To run one of the pre-defined Itinerary On-Ramp samples</span></span>  
  
1.  <span data-ttu-id="b5266-109">如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="b5266-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="b5266-110">在 Windows 资源管理器，打开子文件夹 \Source\Samples\Itinerary\Source\ESB。Itinerary.Test\bin\Debug 其中您安装了 BizTalk ESB 工具包示例中，然后再开始应用程序名为 Esb.Itinerary.Test.exe。</span><span class="sxs-lookup"><span data-stu-id="b5266-110">In Windows Explorer, open the subfolder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the BizTalk ESB Toolkit samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="b5266-111">单击**LoadItinerary**按钮，，然后选择名为双向-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries 文件夹中的示例路线。</span><span class="sxs-lookup"><span data-stu-id="b5266-111">Click the **LoadItinerary** button, and then select the sample itinerary named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml from the \Source\Samples\Itinerary\Itineraries folder.</span></span>  
  
4.  <span data-ttu-id="b5266-112">在**Web 服务选项**部分中，选择**双向服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="b5266-112">In the **Web Service Options** section, select the **Two-Way Service** check box.</span></span> <span data-ttu-id="b5266-113">这会指示测试客户端来执行的请求-响应路线服务操作。</span><span class="sxs-lookup"><span data-stu-id="b5266-113">This instructs the test client to perform a request-response itinerary service operation.</span></span>  
  
5.  <span data-ttu-id="b5266-114">（可选）选择**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而非默认 OnRamp.Itinerary.Response.SOAP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="b5266-114">(Optional) Select the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6.  <span data-ttu-id="b5266-115">单击**LoadMessage**按钮，然后从 \Source\Samples\Itinerary\Test\Data 文件夹然后选择 NAOrderDoc.xml 示例消息。</span><span class="sxs-lookup"><span data-stu-id="b5266-115">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="b5266-116">单击**SubmitRequest**按钮以将请求发送到路线提升服务。</span><span class="sxs-lookup"><span data-stu-id="b5266-116">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="b5266-117">图 1 显示的结果。</span><span class="sxs-lookup"><span data-stu-id="b5266-117">Figure 1 shows the result.</span></span>  
  
 <span data-ttu-id="b5266-118">![在负载增加路线](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6 ItineraryOnRamp")</span><span class="sxs-lookup"><span data-stu-id="b5266-118">![Itinerary On Ramp](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")</span></span>  
  
 <span data-ttu-id="b5266-119">**图 1**</span><span class="sxs-lookup"><span data-stu-id="b5266-119">**Figure 1**</span></span>  
  
 <span data-ttu-id="b5266-120">**运行路线入口示例之一的路线负载技术增加客户端应用程序**</span><span class="sxs-lookup"><span data-stu-id="b5266-120">**The Itinerary On-Ramp client application running one of the Itinerary On-Ramp samples**</span></span>  
  
 <span data-ttu-id="b5266-121">路线的定义中指定的服务名称直接对应**ServiceName**示例订阅的服务的属性。</span><span class="sxs-lookup"><span data-stu-id="b5266-121">The name of the service specified in the itinerary definition corresponds directly to the **ServiceName** property of the service to which the sample subscribes.</span></span> <span data-ttu-id="b5266-122">在前面的过程 (双向-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) 中执行路线示例中，执行第一个服务是一种基于业务流程的服务执行转换。</span><span class="sxs-lookup"><span data-stu-id="b5266-122">In the itinerary sample executed in the previous procedure (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml), the first service executed is an orchestration-based service that performs a transformation.</span></span> <span data-ttu-id="b5266-123">路线的以下节指定此服务。</span><span class="sxs-lookup"><span data-stu-id="b5266-123">The following section of the itinerary specifies this service.</span></span>  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 <span data-ttu-id="b5266-124">在此业务流程服务**\<服务 >**元素指定直接绑定业务流程具有图 2 所示的筛选器属性。</span><span class="sxs-lookup"><span data-stu-id="b5266-124">The orchestration service in this **\<Service>** element specifies the direct-bound orchestration that has the filter properties shown in Figure 2.</span></span> <span data-ttu-id="b5266-125">请注意业务流程订阅仅对具有值的消息**Microsoft.Practices.ESB.Services.Transform**为**ServiceName**上下文属性、 值**挂起**为**ServiceState**上下文属性和值业务流程的**ServiceType**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b5266-125">Notice that the orchestration subscribes only to messages that have the value **Microsoft.Practices.ESB.Services.Transform** for the **ServiceName** context property, the value **Pending** for the **ServiceState** context property, and the value Orchestration for the **ServiceType** context property.</span></span>  
  
 <span data-ttu-id="b5266-126">![筛选器表达式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6 FilterExpression")</span><span class="sxs-lookup"><span data-stu-id="b5266-126">![Filter Expression](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")</span></span>  
  
 <span data-ttu-id="b5266-127">**图 2**</span><span class="sxs-lookup"><span data-stu-id="b5266-127">**Figure 2**</span></span>  
  
 <span data-ttu-id="b5266-128">**直接绑定业务流程路线入口示例中使用筛选器表达式**</span><span class="sxs-lookup"><span data-stu-id="b5266-128">**The filter expression for the direct-bound orchestration used in the Itinerary On-Ramp sample**</span></span>