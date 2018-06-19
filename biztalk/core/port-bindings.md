---
title: 端口绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, warnings
- ports, bindings
- bindings, Web ports
- bindings, design time
- Web ports, port bindings
- bindings, ports
- bindings, direct
- bindings, warnings
- bindings, deployment
- bindings, dynamic
ms.assetid: b61c725a-0082-42d3-b88a-533583161734
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943cbbaa6db9413ffad15bfcf3302d2216e3ab17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265197"
---
# <a name="port-bindings"></a><span data-ttu-id="6660d-102">端口绑定</span><span class="sxs-lookup"><span data-stu-id="6660d-102">Port Bindings</span></span>
<span data-ttu-id="6660d-103">端口绑定是用于确定发送或接收消息的位置及方式的配置信息。</span><span class="sxs-lookup"><span data-stu-id="6660d-103">A port binding is the configuration information that determines where and how a message will be sent or received.</span></span> <span data-ttu-id="6660d-104">根据绑定类型的不同，端口绑定可能是指物理位置、管道或其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="6660d-104">Depending on its type, a port binding might refer to physical locations, pipelines, or other orchestrations.</span></span>  
  
 <span data-ttu-id="6660d-105">对于接收消息的端口，存在三种类型的端口绑定：</span><span class="sxs-lookup"><span data-stu-id="6660d-105">There are three types of port binding for ports that receive messages:</span></span>  
  
-   <span data-ttu-id="6660d-106">立即指定</span><span class="sxs-lookup"><span data-stu-id="6660d-106">Specify now</span></span>  
  
-   <span data-ttu-id="6660d-107">指定更高版本</span><span class="sxs-lookup"><span data-stu-id="6660d-107">Specify later</span></span>  
  
-   <span data-ttu-id="6660d-108">直接</span><span class="sxs-lookup"><span data-stu-id="6660d-108">Direct</span></span>  
  
 <span data-ttu-id="6660d-109">对于发送消息的端口，存在四种类型的端口绑定：</span><span class="sxs-lookup"><span data-stu-id="6660d-109">There are four types of port binding for ports that send messages:</span></span>  
  
-   <span data-ttu-id="6660d-110">立即指定</span><span class="sxs-lookup"><span data-stu-id="6660d-110">Specify now</span></span>  
  
-   <span data-ttu-id="6660d-111">指定更高版本</span><span class="sxs-lookup"><span data-stu-id="6660d-111">Specify later</span></span>  
  
-   <span data-ttu-id="6660d-112">直接</span><span class="sxs-lookup"><span data-stu-id="6660d-112">Direct</span></span>  
  
-   <span data-ttu-id="6660d-113">Dynamic</span><span class="sxs-lookup"><span data-stu-id="6660d-113">Dynamic</span></span>  
  
## <a name="binding-at-deployment-time"></a><span data-ttu-id="6660d-114">在部署时进行绑定</span><span class="sxs-lookup"><span data-stu-id="6660d-114">Binding at Deployment Time</span></span>  
 <span data-ttu-id="6660d-115">您可以将端口绑定至接收位置或发送端口。</span><span class="sxs-lookup"><span data-stu-id="6660d-115">You can bind your port to a receive location or to a send port.</span></span> <span data-ttu-id="6660d-116">如果你没有所有需要指定物理位置的信息，则可以选择**稍后指定**端口绑定选项中业务流程设计器中，并且你只需指定描述该端口的端口类型。</span><span class="sxs-lookup"><span data-stu-id="6660d-116">If you do not have all of the information you need to specify a physical location, you can select the **Specify later** port binding option in Orchestration Designer, and you only need to specify the port type that describes the port.</span></span> <span data-ttu-id="6660d-117">在已经部署应用程序后，您可以通过使用 BizTalk Server 管理控制台指定与位置有关的信息，或者可以通过编程方式配置位置信息。</span><span class="sxs-lookup"><span data-stu-id="6660d-117">After the application has been deployed, you can specify information about the location by using the BizTalk Server Administration console, or you can configure the location information programmatically.</span></span>  
  
## <a name="binding-at-design-time"></a><span data-ttu-id="6660d-118">在设计时进行绑定</span><span class="sxs-lookup"><span data-stu-id="6660d-118">Binding at Design Time</span></span>  
 <span data-ttu-id="6660d-119">你可以选择**现在指定**端口业务流程设计器中的绑定选项在设计时指定的传输和管道。</span><span class="sxs-lookup"><span data-stu-id="6660d-119">You can select the **Specify now** port binding option in Orchestration Designer to specify the transport and pipeline at design time.</span></span> <span data-ttu-id="6660d-120">在为接收消息指定端口时，在下拉列表中只提供 HTTP、SOAP 和 FILE 传输。</span><span class="sxs-lookup"><span data-stu-id="6660d-120">When specifying the port for receiving messages, only HTTP, SOAP, and FILE transports are available from the drop-down list.</span></span> <span data-ttu-id="6660d-121">在为发送消息指定端口时，在下拉列表中只提供 HTTP、FILE 和 SMTP 传输。</span><span class="sxs-lookup"><span data-stu-id="6660d-121">When specifying the port for sending messages, only HTTP, FILE, and SMTP transports are available from the drop-down list.</span></span> <span data-ttu-id="6660d-122">如果您事先知道所传输消息的源或目标，此选项将非常有用。</span><span class="sxs-lookup"><span data-stu-id="6660d-122">This option is useful if you know in advance the source or destination of transmitted messages.</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="6660d-123">直接绑定</span><span class="sxs-lookup"><span data-stu-id="6660d-123">Direct Binding</span></span>  
 <span data-ttu-id="6660d-124">直接绑定端口是您的业务流程中的逻辑单向或双向端口，并不显式绑定到任何物理端口。</span><span class="sxs-lookup"><span data-stu-id="6660d-124">Direct bound ports are logical one-way or two-way ports in your orchestrations that are not explicitly bound to any physical ports.</span></span> <span data-ttu-id="6660d-125">直接绑定端口允许您在服务中具有不同的通信模式。</span><span class="sxs-lookup"><span data-stu-id="6660d-125">Direct bound ports allow you to have different communication patterns among your services.</span></span> <span data-ttu-id="6660d-126">若要实现直接绑定，请选择**直接**端口业务流程设计器中在设计时的绑定选项。</span><span class="sxs-lookup"><span data-stu-id="6660d-126">To implement direct binding, select the **Direct** port binding option in Orchestration Designer at design time.</span></span>  
  
 <span data-ttu-id="6660d-127">直接绑定端口有三种类型：</span><span class="sxs-lookup"><span data-stu-id="6660d-127">There are three types of direct bound ports:</span></span>  
  
-   <span data-ttu-id="6660d-128">MessageBox 直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="6660d-128">MessageBox direct bound port</span></span>  
  
-   <span data-ttu-id="6660d-129">自相关直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="6660d-129">Self-correlating direct bound port</span></span>  
  
-   <span data-ttu-id="6660d-130">合作伙伴业务流程直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="6660d-130">Partner orchestration direct bound port</span></span>  
  
 <span data-ttu-id="6660d-131">有关如何使用直接绑定的端口的详细信息，请参阅[使用在业务流程中的直接绑定端口](../core/working-with-direct-bound-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="6660d-131">For more information about how to work with direct bound ports, see [Working with Direct Bound Ports in Orchestrations](../core/working-with-direct-bound-ports-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6660d-132">使用直接绑定时，您无法在一个请求响应端口和两个单向端口之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="6660d-132">When you use direct binding, you cannot exchange messages between one request-response port and two one-way ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6660d-133">直接绑定不符合 Web Services 的业务流程工程语言 (BPEL4WS) 标准。</span><span class="sxs-lookup"><span data-stu-id="6660d-133">Direct binding is not compliant with the standards of the Business Process Engineering Language for Web Services (BPEL4WS).</span></span> <span data-ttu-id="6660d-134">如果您需要符合 BPEL4WS，请使用其他类型的绑定。</span><span class="sxs-lookup"><span data-stu-id="6660d-134">If you require BPEL4WS compliance, use another kind of binding.</span></span>  
  
## <a name="dynamic-binding"></a><span data-ttu-id="6660d-135">动态绑定</span><span class="sxs-lookup"><span data-stu-id="6660d-135">Dynamic Binding</span></span>  
 <span data-ttu-id="6660d-136">如果直到运行时才知道通信的目标，则可以对发送端口使用动态绑定。</span><span class="sxs-lookup"><span data-stu-id="6660d-136">If you will not know the destination of a communication until run time, you can use dynamic binding for a send port.</span></span> <span data-ttu-id="6660d-137">位置，例如，可从传入消息时，属性确定，然后中指定**表达式**形状，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="6660d-137">The location might, for example, be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following code:</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 <span data-ttu-id="6660d-138">有关如何将值动态分配给端口的信息，请参阅[如何将值分配到动态端口](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="6660d-138">For information about how to dynamically assign values to ports, see [How to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md).</span></span>  
  
## <a name="web-ports"></a><span data-ttu-id="6660d-139">Web 端口</span><span class="sxs-lookup"><span data-stu-id="6660d-139">Web Ports</span></span>  
 <span data-ttu-id="6660d-140">如果项目包含对 Web Services 的引用，则业务流程设计器将检测该引用并使相应的 Web 端口类型可用。</span><span class="sxs-lookup"><span data-stu-id="6660d-140">If your project contains a reference to a Web service, Orchestration Designer will detect it and will make available a corresponding Web port type.</span></span> <span data-ttu-id="6660d-141">若要创建某一 Web 端口，只需将某一端口添加到您的业务流程，然后向它分配某一现有 Web 端口类型。</span><span class="sxs-lookup"><span data-stu-id="6660d-141">To create a Web port, you simply add a port to your orchestration and assign it an existing Web port type.</span></span> <span data-ttu-id="6660d-142">有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="6660d-142">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6660d-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6660d-143">See Also</span></span>  
 <span data-ttu-id="6660d-144">[如何使用端口类型](../core/how-to-work-with-port-types.md) </span><span class="sxs-lookup"><span data-stu-id="6660d-144">[How to Work with Port Types](../core/how-to-work-with-port-types.md) </span></span>  
 <span data-ttu-id="6660d-145">[通信模式](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="6660d-145">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="6660d-146">[通信方向](../core/communication-direction.md) </span><span class="sxs-lookup"><span data-stu-id="6660d-146">[Communication Direction](../core/communication-direction.md) </span></span>  
 <span data-ttu-id="6660d-147">[使用在业务流程中的端口](../core/using-ports-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="6660d-147">[Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md) </span></span>  
 <span data-ttu-id="6660d-148">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="6660d-148">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="6660d-149">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="6660d-149">Consuming Web Services</span></span>](../core/consuming-web-services.md)