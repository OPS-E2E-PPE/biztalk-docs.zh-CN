---
title: 端口绑定 |Microsoft Docs
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
ms.openlocfilehash: c39dbaa807c68d5964dde973ab12c6fc91f7805c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394883"
---
# <a name="port-bindings"></a><span data-ttu-id="f7c57-102">端口绑定</span><span class="sxs-lookup"><span data-stu-id="f7c57-102">Port Bindings</span></span>
<span data-ttu-id="f7c57-103">端口绑定是确定在何处以及如何将发送或接收消息的配置信息。</span><span class="sxs-lookup"><span data-stu-id="f7c57-103">A port binding is the configuration information that determines where and how a message will be sent or received.</span></span> <span data-ttu-id="f7c57-104">根据其类型，端口绑定可能指物理位置、 管道或其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="f7c57-104">Depending on its type, a port binding might refer to physical locations, pipelines, or other orchestrations.</span></span>  
  
 <span data-ttu-id="f7c57-105">有三种类型的接收消息的端口的端口绑定：</span><span class="sxs-lookup"><span data-stu-id="f7c57-105">There are three types of port binding for ports that receive messages:</span></span>  
  
- <span data-ttu-id="f7c57-106">立即指定</span><span class="sxs-lookup"><span data-stu-id="f7c57-106">Specify now</span></span>  
  
- <span data-ttu-id="f7c57-107">以后指定</span><span class="sxs-lookup"><span data-stu-id="f7c57-107">Specify later</span></span>  
  
- <span data-ttu-id="f7c57-108">直接</span><span class="sxs-lookup"><span data-stu-id="f7c57-108">Direct</span></span>  
  
  <span data-ttu-id="f7c57-109">有四种类型的发送消息的端口的端口绑定：</span><span class="sxs-lookup"><span data-stu-id="f7c57-109">There are four types of port binding for ports that send messages:</span></span>  
  
- <span data-ttu-id="f7c57-110">立即指定</span><span class="sxs-lookup"><span data-stu-id="f7c57-110">Specify now</span></span>  
  
- <span data-ttu-id="f7c57-111">以后指定</span><span class="sxs-lookup"><span data-stu-id="f7c57-111">Specify later</span></span>  
  
- <span data-ttu-id="f7c57-112">直接</span><span class="sxs-lookup"><span data-stu-id="f7c57-112">Direct</span></span>  
  
- <span data-ttu-id="f7c57-113">动态</span><span class="sxs-lookup"><span data-stu-id="f7c57-113">Dynamic</span></span>  
  
## <a name="binding-at-deployment-time"></a><span data-ttu-id="f7c57-114">在部署时进行绑定</span><span class="sxs-lookup"><span data-stu-id="f7c57-114">Binding at Deployment Time</span></span>  
 <span data-ttu-id="f7c57-115">可以将端口绑定到接收位置或发送端口。</span><span class="sxs-lookup"><span data-stu-id="f7c57-115">You can bind your port to a receive location or to a send port.</span></span> <span data-ttu-id="f7c57-116">如果您不具备所有指定的物理位置所需的信息，则可以选择**以后指定**端口绑定选项，在业务流程设计器中，并且您只需指定描述该端口的端口类型。</span><span class="sxs-lookup"><span data-stu-id="f7c57-116">If you do not have all of the information you need to specify a physical location, you can select the **Specify later** port binding option in Orchestration Designer, and you only need to specify the port type that describes the port.</span></span> <span data-ttu-id="f7c57-117">部署应用程序后，你可以使用 BizTalk Server 管理控制台中，指定与位置有关的信息，或可以以编程方式配置位置信息。</span><span class="sxs-lookup"><span data-stu-id="f7c57-117">After the application has been deployed, you can specify information about the location by using the BizTalk Server Administration console, or you can configure the location information programmatically.</span></span>  
  
## <a name="binding-at-design-time"></a><span data-ttu-id="f7c57-118">在设计时绑定</span><span class="sxs-lookup"><span data-stu-id="f7c57-118">Binding at Design Time</span></span>  
 <span data-ttu-id="f7c57-119">可以选择**立即指定**端口绑定业务流程设计器中的选项以在设计时指定的传输和管道。</span><span class="sxs-lookup"><span data-stu-id="f7c57-119">You can select the **Specify now** port binding option in Orchestration Designer to specify the transport and pipeline at design time.</span></span> <span data-ttu-id="f7c57-120">指定此端口来接收消息，仅 HTTP、 SOAP 和文件传输时，可从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f7c57-120">When specifying the port for receiving messages, only HTTP, SOAP, and FILE transports are available from the drop-down list.</span></span> <span data-ttu-id="f7c57-121">指定用于将消息发送端口，仅 HTTP、 FILE 和 SMTP 传输时，可从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f7c57-121">When specifying the port for sending messages, only HTTP, FILE, and SMTP transports are available from the drop-down list.</span></span> <span data-ttu-id="f7c57-122">此选项非常有用，如果您事先知道源或目标的传输的消息。</span><span class="sxs-lookup"><span data-stu-id="f7c57-122">This option is useful if you know in advance the source or destination of transmitted messages.</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="f7c57-123">直接绑定</span><span class="sxs-lookup"><span data-stu-id="f7c57-123">Direct Binding</span></span>  
 <span data-ttu-id="f7c57-124">直接绑定的端口是您不显式绑定到任何物理端口的业务流程中的逻辑单向或双向端口。</span><span class="sxs-lookup"><span data-stu-id="f7c57-124">Direct bound ports are logical one-way or two-way ports in your orchestrations that are not explicitly bound to any physical ports.</span></span> <span data-ttu-id="f7c57-125">直接绑定的端口允许您具有在服务中的不同通信模式。</span><span class="sxs-lookup"><span data-stu-id="f7c57-125">Direct bound ports allow you to have different communication patterns among your services.</span></span> <span data-ttu-id="f7c57-126">若要实现直接绑定，请选择**直接**端口在业务流程设计器在设计时的绑定选项。</span><span class="sxs-lookup"><span data-stu-id="f7c57-126">To implement direct binding, select the **Direct** port binding option in Orchestration Designer at design time.</span></span>  
  
 <span data-ttu-id="f7c57-127">有三种类型的直接绑定端口：</span><span class="sxs-lookup"><span data-stu-id="f7c57-127">There are three types of direct bound ports:</span></span>  
  
- <span data-ttu-id="f7c57-128">MessageBox 直接绑定的端口</span><span class="sxs-lookup"><span data-stu-id="f7c57-128">MessageBox direct bound port</span></span>  
  
- <span data-ttu-id="f7c57-129">自相关直接绑定的端口</span><span class="sxs-lookup"><span data-stu-id="f7c57-129">Self-correlating direct bound port</span></span>  
  
- <span data-ttu-id="f7c57-130">合作伙伴业务流程直接绑定的端口</span><span class="sxs-lookup"><span data-stu-id="f7c57-130">Partner orchestration direct bound port</span></span>  
  
  <span data-ttu-id="f7c57-131">有关如何使用直接绑定端口的详细信息，请参阅[使用直接绑定端口在业务流程中](../core/working-with-direct-bound-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c57-131">For more information about how to work with direct bound ports, see [Working with Direct Bound Ports in Orchestrations](../core/working-with-direct-bound-ports-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7c57-132">在使用直接绑定时，您不能交换一个请求-响应端口和两个单向端口之间的消息。</span><span class="sxs-lookup"><span data-stu-id="f7c57-132">When you use direct binding, you cannot exchange messages between one request-response port and two one-way ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7c57-133">直接绑定不符合的 Web 服务 (BPEL4WS) 业务流程工程语言标准。</span><span class="sxs-lookup"><span data-stu-id="f7c57-133">Direct binding is not compliant with the standards of the Business Process Engineering Language for Web Services (BPEL4WS).</span></span> <span data-ttu-id="f7c57-134">如果需要符合 bpel4ws 规范，请使用其他类型的绑定。</span><span class="sxs-lookup"><span data-stu-id="f7c57-134">If you require BPEL4WS compliance, use another kind of binding.</span></span>  
  
## <a name="dynamic-binding"></a><span data-ttu-id="f7c57-135">动态绑定</span><span class="sxs-lookup"><span data-stu-id="f7c57-135">Dynamic Binding</span></span>  
 <span data-ttu-id="f7c57-136">如果你将无法知道直到运行时通信的目标，可以为发送端口使用动态绑定。</span><span class="sxs-lookup"><span data-stu-id="f7c57-136">If you will not know the destination of a communication until run time, you can use dynamic binding for a send port.</span></span> <span data-ttu-id="f7c57-137">位置，例如，可从传入消息上的属性确定，然后中指定**表达式**形状，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="f7c57-137">The location might, for example, be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following code:</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 <span data-ttu-id="f7c57-138">有关如何将值动态分配到端口的信息，请参阅[如何向动态端口分配值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c57-138">For information about how to dynamically assign values to ports, see [How to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md).</span></span>  
  
## <a name="web-ports"></a><span data-ttu-id="f7c57-139">Web 端口</span><span class="sxs-lookup"><span data-stu-id="f7c57-139">Web Ports</span></span>  
 <span data-ttu-id="f7c57-140">如果你的项目包含对 Web 服务的引用，业务流程设计器会将其检测并会将提供相应的 Web 端口类型。</span><span class="sxs-lookup"><span data-stu-id="f7c57-140">If your project contains a reference to a Web service, Orchestration Designer will detect it and will make available a corresponding Web port type.</span></span> <span data-ttu-id="f7c57-141">若要创建 Web 端口，只需将端口添加到您的业务流程中，并将其分配现有 Web 端口类型。</span><span class="sxs-lookup"><span data-stu-id="f7c57-141">To create a Web port, you simply add a port to your orchestration and assign it an existing Web port type.</span></span> <span data-ttu-id="f7c57-142">有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c57-142">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c57-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7c57-143">See Also</span></span>  
 <span data-ttu-id="f7c57-144">[如何使用端口类型](../core/how-to-work-with-port-types.md) </span><span class="sxs-lookup"><span data-stu-id="f7c57-144">[How to Work with Port Types](../core/how-to-work-with-port-types.md) </span></span>  
 <span data-ttu-id="f7c57-145">[通信模式](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="f7c57-145">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="f7c57-146">[通信方向](../core/communication-direction.md) </span><span class="sxs-lookup"><span data-stu-id="f7c57-146">[Communication Direction](../core/communication-direction.md) </span></span>  
 <span data-ttu-id="f7c57-147">[使用业务流程中端口](../core/using-ports-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="f7c57-147">[Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md) </span></span>  
 <span data-ttu-id="f7c57-148">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="f7c57-148">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="f7c57-149">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="f7c57-149">Consuming Web Services</span></span>](../core/consuming-web-services.md)