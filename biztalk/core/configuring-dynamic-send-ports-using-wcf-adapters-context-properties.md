---
title: 配置动态发送端口使用 WCF 适配器上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, send ports
- send ports, WCF services
- dynamic send ports, WCF services
- send ports, dynamic
ms.assetid: 2a7e2cd2-fa2d-45da-bb8e-eb8bab21bfa3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca781dc1d101e3eef0976229b3d1b986c2f4498d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995270"
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a><span data-ttu-id="fca6f-102">配置动态发送端口使用 WCF 适配器上下文属性</span><span class="sxs-lookup"><span data-stu-id="fca6f-102">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>
<span data-ttu-id="fca6f-103">可以为 WCF 适配器配置动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="fca6f-103">You can configure dynamic send ports for WCF adapters.</span></span> <span data-ttu-id="fca6f-104">URI、 操作和绑定可能会确定传入消息上的属性，然后中指定**表达式**形状，如以下 Wcf-nettcp 适配器中所示：</span><span class="sxs-lookup"><span data-stu-id="fca6f-104">The URI, action, and binding might be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following WCF-NetTcp adapter:</span></span>  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.SecurityMode)="Transport";  
MessageOut(WCF.TransportClientCredentialType)="Windows";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/netTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-NetTcp";  
```  
  
 <span data-ttu-id="fca6f-105">下面的代码演示如何指定 WCF 上下文属性中的示例**表达式**WCF 自定义适配器的形状：</span><span class="sxs-lookup"><span data-stu-id="fca6f-105">The following code shows an example of how to specify the WCF context properties in the **Expression** shape for a WCF-Custom adapter:</span></span>  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.BindingType)="customBinding";  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.BindingConfiguration)=@"<binding name=""customBinding""><binaryMessageEncoding /><tcpTransport /></binding>";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/customNetTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
 <span data-ttu-id="fca6f-106">指定 WCF 上下文属性的注意事项如下：</span><span class="sxs-lookup"><span data-stu-id="fca6f-106">Considerations when specifying WCF context properties are as follows:</span></span>  
  
- <span data-ttu-id="fca6f-107">有些地址可以映射到多个适配器。</span><span class="sxs-lookup"><span data-stu-id="fca6f-107">There are addresses that can be mapped to multiple adapters.</span></span> <span data-ttu-id="fca6f-108">例如，以 http:// 或 https:// 开头的地址可以由 HTTP 适配器处理，也可以由 WCF-BasicHttp、WCF-WsHttp 或 WCF-Custom 适配器处理。</span><span class="sxs-lookup"><span data-stu-id="fca6f-108">For example, an address that starts with http:// or https:// can be handled by the HTTP adapter as well as by the WCF-BasicHttp, WCF-WsHttp, or WCF-Custom adapters.</span></span> <span data-ttu-id="fca6f-109">再例如，在上述两个示例代码中，它们都使用了以 net.tcp:// 开头的地址，不过由于第二个示例代码使用了自定义绑定，因而应使用 WCF-Custom 适配器处理该地址。</span><span class="sxs-lookup"><span data-stu-id="fca6f-109">For another example, in the above sample code, both of them are using the address starts with net.tcp://, yet because the second sample code uses custom binding, WCF-Custom adapter should be used to handle the address.</span></span> <span data-ttu-id="fca6f-110">因此，若要标识正确的适配器，您必须配置可选**Microsoft.XLANGs.BaseTypes.TransportType**字段中**表达式**形状与你想要使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="fca6f-110">Therefore, to identify the correct adapter, you must configure the optional **Microsoft.XLANGs.BaseTypes.TransportType** field in an **Expression** shape with the adapter that you want to use.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fca6f-111">如果地址以 http:// 或 https:// 开头，并且如果未指定**Microsoft.XLANGs.BaseTypes.TransportType**字段中，默认情况下，BizTalk 引擎将使用 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="fca6f-111">If the address starts with http:// or https://, and if you do not specify the **Microsoft.XLANGs.BaseTypes.TransportType** field, by default, the BizTalk engine will use the HTTP adapter.</span></span>  
  
- <span data-ttu-id="fca6f-112">**WCF。BindingType**按名称标识的绑定。</span><span class="sxs-lookup"><span data-stu-id="fca6f-112">The **WCF.BindingType** identifies the binding by name.</span></span> <span data-ttu-id="fca6f-113">该参数可以是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="fca6f-113">It can be one of the following:</span></span>  
  
  - <span data-ttu-id="fca6f-114">basicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-114">basicHttpBinding</span></span>  
  
  - <span data-ttu-id="fca6f-115">customBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-115">customBinding</span></span>  
  
  - <span data-ttu-id="fca6f-116">netMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-116">netMsmqBinding</span></span>  
  
  - <span data-ttu-id="fca6f-117">netNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-117">netNamedPipeBinding</span></span>  
  
  - <span data-ttu-id="fca6f-118">netTcpBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-118">netTcpBinding</span></span>  
  
  - <span data-ttu-id="fca6f-119">wsFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-119">wsFederationHttpBinding</span></span>  
  
  - <span data-ttu-id="fca6f-120">wsHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fca6f-120">wsHttpBinding</span></span>  
  
    <span data-ttu-id="fca6f-121">上述列表可以扩展。</span><span class="sxs-lookup"><span data-stu-id="fca6f-121">The above list can be extended.</span></span> <span data-ttu-id="fca6f-122">例如，您可以向其中自行添加绑定，如 FtpBinding。</span><span class="sxs-lookup"><span data-stu-id="fca6f-122">For example, you can add your own binding to it such as FtpBinding.</span></span>  
  
- <span data-ttu-id="fca6f-123">**WCF。BindingConfiguration**指定绑定类型的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="fca6f-123">The **WCF.BindingConfiguration** specifies the binding configuration for the binding type.</span></span> <span data-ttu-id="fca6f-124">它会获取在计算机配置文件中注册的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="fca6f-124">It takes any binding that are registered in the machine configuration file.</span></span> <span data-ttu-id="fca6f-125">它还会以 WCF 配置文件的绑定配置中所用的相同格式获取 XML 配置。</span><span class="sxs-lookup"><span data-stu-id="fca6f-125">It also takes the XML configuration in the same format as used in the binding configuration in the WCF configuration file.</span></span>  
  
- <span data-ttu-id="fca6f-126">您可能需要指定其他 WCF 属性。</span><span class="sxs-lookup"><span data-stu-id="fca6f-126">You may need to specify additional WCF properties.</span></span> <span data-ttu-id="fca6f-127">您可以键入**WCF**在表达式编辑器和 IntelliSense 功能将列出所有可用的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="fca6f-127">You can type **WCF** in the Expression Editor, and the IntelliSense feature should list all the available context properties.</span></span> <span data-ttu-id="fca6f-128">有关 WCF 上下文属性的详细信息，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fca6f-128">For more information about WCF context properties, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>  
  
  <span data-ttu-id="fca6f-129">前面的示例演示如何配置**WCF。操作**通过一个操作。</span><span class="sxs-lookup"><span data-stu-id="fca6f-129">The preceding examples show how to configure **WCF.Action** with a single action.</span></span> <span data-ttu-id="fca6f-130">对于具有多个操作映射的情况，WCF 适配器不支持将多个操作映射与动态发送端口一起使用。</span><span class="sxs-lookup"><span data-stu-id="fca6f-130">For multiple actions mapping scenarios, WCF adapter do not support using multiple actions mapping with dynamic send ports.</span></span> <span data-ttu-id="fca6f-131">您可以在中设置实际操作**WCF。操作**为在上面显示的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="fca6f-131">You can just set the actual action in the **WCF.Action** context property as showing in above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca6f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="fca6f-132">See Also</span></span>  
 <span data-ttu-id="fca6f-133">[指定 SOAP 操作，为 WCF 发送适配器](../core/specifying-soap-actions-for-wcf-send-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="fca6f-133">[Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md) </span></span>  
 <span data-ttu-id="fca6f-134">[如何使用表达式向动态端口赋值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md) </span><span class="sxs-lookup"><span data-stu-id="fca6f-134">[How to Use Expressions to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md) </span></span>  
 [<span data-ttu-id="fca6f-135">端口绑定</span><span class="sxs-lookup"><span data-stu-id="fca6f-135">Port Bindings</span></span>](../core/port-bindings.md)