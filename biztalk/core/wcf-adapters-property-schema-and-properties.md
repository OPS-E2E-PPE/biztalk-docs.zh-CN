---
title: "WCF 适配器属性架构和属性 |Microsoft 文档"
ms.custom: 
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bb48f54347eabeb886d91fa245bae18c34de55
ms.sourcegitcommit: 50798e04fdcaf5dce5288aa18608e2a981b162fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2018
---
# <a name="wcf-adapters-property-schema-and-properties"></a><span data-ttu-id="1f483-102">WCF 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="1f483-102">WCF Adapters Property Schema and Properties</span></span>
<span data-ttu-id="1f483-103">阅读有关 WCF 适配器属性架构中提升的属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-103">Read about the promoted properties in the WCF adapter property schema.</span></span> <span data-ttu-id="1f483-104">WCF 适配器对应用程序中可使用的属性进行赋值。</span><span class="sxs-lookup"><span data-stu-id="1f483-104">The WCF adapters assign values to the properties that you can use in your application.</span></span> <span data-ttu-id="1f483-105">WCF 适配器还提供了一种用于将自定义属性写入 BizTalk 消息上下文但不进行升级的机制，以及一种用于将自定义属性升级到 BizTalk 消息上下文的机制。</span><span class="sxs-lookup"><span data-stu-id="1f483-105">WCF adapter also provides a mechanism to write but not promote the custom properties to the BizTalk message context, and a mechanism to promote the custom properties to the BizTalk message context.</span></span> <span data-ttu-id="1f483-106">有关更多详细信息，请参阅[发布 WCF 服务使用的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-106">For more details, see [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md).</span></span>  

## <a name="promoted-properties"></a><span data-ttu-id="1f483-107">提升的属性</span><span class="sxs-lookup"><span data-stu-id="1f483-107">Promoted properties</span></span>  
<span data-ttu-id="1f483-108">**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span><span class="sxs-lookup"><span data-stu-id="1f483-108">**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span></span>  

#### <a name="action"></a><span data-ttu-id="1f483-109">操作</span><span class="sxs-lookup"><span data-stu-id="1f483-109">Action</span></span>
<span data-ttu-id="1f483-110">指定 **SOAPAction** 传出消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="1f483-110">Specify the **SOAPAction** header field for outgoing messages.</span></span> <span data-ttu-id="1f483-111">你可以通过两种方式指定此值︰ 单个操作格式和操作映射格式。</span><span class="sxs-lookup"><span data-stu-id="1f483-111">You can specify this value in two different ways: the single action format and the action mapping format.</span></span> <span data-ttu-id="1f483-112">如果将此属性设置中的单个操作格式-例如，http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。</span><span class="sxs-lookup"><span data-stu-id="1f483-112">If you set this property in the single action format—for example, http://contoso.com/Svc/Op1 — the **SOAPAction** header for outgoing messages is always set to the value specified in this property.</span></span>

<span data-ttu-id="1f483-113">如果在操作映射格式，传出中设置此属性 **SOAPAction** 标头由 **BTS。操作** 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-113">If you set this property in the action mapping format, the outgoing **SOAPAction** header is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="1f483-114">例如，如果此属性设置为以下 XML 格式和 **BTS。操作** 属性设置为 Op1，WCF 发送适配器使用 `http://contoso.com/Svc/Op1` 为传出 **SOAPAction** 标头。</span><span class="sxs-lookup"><span data-stu-id="1f483-114">For example, if this property is set to the following XML format and the **BTS.Operation** property is set to Op1, the WCF send adapter uses `http://contoso.com/Svc/Op1` for the outgoing **SOAPAction** header.</span></span>

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

<span data-ttu-id="1f483-115">如果传出消息来自的业务流程端口时，动态设置业务流程实例 **BTS。操作** 与操作名称的端口的属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-115">If outgoing messages come from an orchestration port, orchestration instances dynamically set the **BTS.Operation** property with the operation name of the port.</span></span> <span data-ttu-id="1f483-116">如果使用基于内容的路由路由传出消息，则可以设置 **BTS。操作** 管道组件中的属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-116">If outgoing messages are routed with content-based routing, you can set the **BTS.Operation** property in pipeline components.</span></span>
<span data-ttu-id="1f483-117">此属性将自动从传入消息以单一操作格式进行升级。</span><span class="sxs-lookup"><span data-stu-id="1f483-117">This property is automatically promoted from incoming messages with the single action format.</span></span>

<span data-ttu-id="1f483-118">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-118">Type: String</span></span>  
<span data-ttu-id="1f483-119">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-119">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-120">适用于： 所有 WCF 都发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-120">Applies to: All WCF send adapters</span></span>

#### <a name="affiliateapplicationname"></a><span data-ttu-id="1f483-121">AffiliateApplicationName</span><span class="sxs-lookup"><span data-stu-id="1f483-121">AffiliateApplicationName</span></span>
<span data-ttu-id="1f483-122">指定用于企业单一登录 (SSO) 的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="1f483-122">Specify the affiliate application to use for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="1f483-123">此属性是必需的如果 **UseSSO** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="1f483-123">This property is required if the **UseSSO** property is set to **True**.</span></span> 

<span data-ttu-id="1f483-124">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-124">Type: String</span></span>  
<span data-ttu-id="1f483-125">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-125">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-126">适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-126">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="algorithmsuite"></a><span data-ttu-id="1f483-127">AlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="1f483-127">AlgorithmSuite</span></span>
<span data-ttu-id="1f483-128">指定訊息加密和 Key Wrap 演算法。</span><span class="sxs-lookup"><span data-stu-id="1f483-128">Specify the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="1f483-129">這些演算法會對應到安全性原則語言 (WS-SecurityPolicy) 規格中所指定的演算法。</span><span class="sxs-lookup"><span data-stu-id="1f483-129">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>

<span data-ttu-id="1f483-130">有关详细信息有关的适用值**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-nettcp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f483-130">For more information about the applicable values for the **AlgorithmSuite** property, see the **Algorithm suite** property in the **WCF-NetTcp Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="1f483-131">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-131">Type: String</span></span>  
<span data-ttu-id="1f483-132">默认值︰ **Basic256**</span><span class="sxs-lookup"><span data-stu-id="1f483-132">Default value: **Basic256**</span></span>  
<span data-ttu-id="1f483-133">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-133">Applies to:</span></span> 

- <span data-ttu-id="1f483-134">WCF BasicHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-134">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="1f483-135">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-135">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="1f483-136">WCF-NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-136">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="1f483-137">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-137">WCF-WSHttp adapter</span></span>

#### <a name="bindingconfiguration"></a><span data-ttu-id="1f483-138">BindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f483-138">BindingConfiguration</span></span>
<span data-ttu-id="1f483-139">指定使用的 XML 字符串**\<绑定\>**元素来配置不同类型的预定义的绑定所提供的 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="1f483-139">Specify an XML string with the **\<binding\>** element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1f483-140">有关系统提供的绑定和自定义绑定的详细信息，请参阅“另请参见”部分中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="1f483-140">For more information about the system-provided binding and custom binding, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="1f483-141">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-141">Example:</span></span>

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

<span data-ttu-id="1f483-142">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-142">Type: String</span></span>  
<span data-ttu-id="1f483-143">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-143">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-144">适用于： WCF 自定义适配器，WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-144">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="bindingtype"></a><span data-ttu-id="1f483-145">BindingType</span><span class="sxs-lookup"><span data-stu-id="1f483-145">BindingType</span></span>
<span data-ttu-id="1f483-146">指定要用于终结点的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="1f483-146">Specify the type of the binding to use for the endpoint.</span></span> <span data-ttu-id="1f483-147">有关详细信息有关的适用值**BindingType**属性，请参阅**绑定类型**中的属性**WCF 自定义传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f483-147">For more information about the applicable values for the **BindingType** property, see the **Binding Type** property in the **WCF-Custom Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="1f483-148">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-148">Type: String</span></span>  
<span data-ttu-id="1f483-149">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-149">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-150">适用于： WCF 自定义适配器，WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-150">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="clientcertificate"></a><span data-ttu-id="1f483-151">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="1f483-151">ClientCertificate</span></span>
<span data-ttu-id="1f483-152">指定用于向服务验证此发送端口的 X.509 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="1f483-152">Specify the thumbprint of the X.509 certificate for authenticating this send port to services.</span></span> <span data-ttu-id="1f483-153">此属性是必需的如果 **ClientCredentialsType** 属性设置为 **证书**。</span><span class="sxs-lookup"><span data-stu-id="1f483-153">This property is required if the **ClientCredentialsType** property is set to **Certificate**.</span></span> <span data-ttu-id="1f483-154">此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。</span><span class="sxs-lookup"><span data-stu-id="1f483-154">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="1f483-155">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-155">Type: String</span></span>  
<span data-ttu-id="1f483-156">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-156">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-157">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-157">Applies to:</span></span> 

- <span data-ttu-id="1f483-158">WCF-BasicHttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-158">WCF-BasicHttp send adapter</span></span>
- <span data-ttu-id="1f483-159">WCF-WSHttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-159">WCF-WSHttp send adapter</span></span>
- <span data-ttu-id="1f483-160">WCF NetTcp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-160">WCF-NetTcp send adapter</span></span>
- <span data-ttu-id="1f483-161">WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-161">WCF-NetMsmq send adapter</span></span>

#### <a name="closetimeout"></a><span data-ttu-id="1f483-162">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="1f483-162">CloseTimeout</span></span>
<span data-ttu-id="1f483-163">指定時間值，表示可供完成通道關閉作業的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="1f483-163">Specify a time span value that indicates the interval of time provided for a channel close operation to complete.</span></span>

<span data-ttu-id="1f483-164">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-164">Type: String</span></span>  
<span data-ttu-id="1f483-165">預設值：00:01:00</span><span class="sxs-lookup"><span data-stu-id="1f483-165">Default value: 00:01:00</span></span>  
<span data-ttu-id="1f483-166">适用于： 所有 WCF 适配器*除*WCF 自定义和 WCF CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="1f483-166">Applies to: All WCF adapters *except* WCF-Custom and WCF-CustomIsolated</span></span>

#### <a name="customdeadletterqueue"></a><span data-ttu-id="1f483-167">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="1f483-167">CustomDeadLetterQueue</span></span>
<span data-ttu-id="1f483-168">指定完全限定的 URI 与 **net.msmq** 方案的每个应用程序死信队列，消息已过期或者传输或传递失败的存放位置。</span><span class="sxs-lookup"><span data-stu-id="1f483-168">Specify the fully qualified URI with the **net.msmq** scheme for the location of the per-application dead-letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span> <span data-ttu-id="1f483-169">例如 net.msmq://localhost/deadLetterQueueName。</span><span class="sxs-lookup"><span data-stu-id="1f483-169">For example, net.msmq://localhost/deadLetterQueueName.</span></span> <span data-ttu-id="1f483-170">死信队列是发送应用程序的队列管理器上的一种队列，用于未能送达的到期的消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-170">The dead-letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span> <span data-ttu-id="1f483-171">此属性是必需的如果 **DeadLetterQueue** 属性设置为 **自定义**。</span><span class="sxs-lookup"><span data-stu-id="1f483-171">This property is required if the **DeadLetterQueue** property is set to **Custom**.</span></span>

<span data-ttu-id="1f483-172">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-172">Type: String</span></span>  
<span data-ttu-id="1f483-173">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-173">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-174">适用于： WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-174">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="deadletterqueue"></a><span data-ttu-id="1f483-175">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="1f483-175">DeadLetterQueue</span></span>
<span data-ttu-id="1f483-176">指定死信队列，未能传输到应用程序的消息将传输到死信队列中。</span><span class="sxs-lookup"><span data-stu-id="1f483-176">Specify the dead-letter queue where messages that have failed to be delivered to the application will be transferred.</span></span> <span data-ttu-id="1f483-177">有关传递到死信队列的消息的详细信息，请参阅**WCF NetMsmq 传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f483-177">For more information about the messages delivered to the dead-letter queue, see the **WCF-NetMsmq Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="1f483-178">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-178">Type: String</span></span>  
<span data-ttu-id="1f483-179">默认值︰ **系统**</span><span class="sxs-lookup"><span data-stu-id="1f483-179">Default value: **System**</span></span>  
<span data-ttu-id="1f483-180">适用于： WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-180">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="disablelocationonfailure"></a><span data-ttu-id="1f483-181">DisableLocationOnFailure</span><span class="sxs-lookup"><span data-stu-id="1f483-181">DisableLocationOnFailure</span></span>
<span data-ttu-id="1f483-182">指定是否禁用由于接收管道故障或路由故障而导致入站处理失败的接收位置。</span><span class="sxs-lookup"><span data-stu-id="1f483-182">Specify whether to disable the receive location that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span> <span data-ttu-id="1f483-183">你可能想要将此属性设置为 **True** 时接收位置可以被禁用，而且拒绝服务 (DoS) 并不是问题。</span><span class="sxs-lookup"><span data-stu-id="1f483-183">You may want to set this property to **True** when receive locations can be disabled and Denial-of-Service (DoS) is not a concern.</span></span>

<span data-ttu-id="1f483-184">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-184">For example:</span></span>  
- <span data-ttu-id="1f483-185">WCF 自定义适配器： 时**BindingType**属性设置为**netMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="1f483-185">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**.</span></span>
- <span data-ttu-id="1f483-186">WCF 自定义适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道依赖如 MSMQ 排队传输。</span><span class="sxs-lookup"><span data-stu-id="1f483-186">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ.</span></span>
- <span data-ttu-id="1f483-187">WCF CustomIsolated 适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道利用如 MSMQ 排队传输</span><span class="sxs-lookup"><span data-stu-id="1f483-187">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ</span></span>
- <span data-ttu-id="1f483-188">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-188">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="1f483-189">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-189">Type: Boolean</span></span>  
<span data-ttu-id="1f483-190">默认值︰ **False**</span><span class="sxs-lookup"><span data-stu-id="1f483-190">Default: **False**</span></span>  
<span data-ttu-id="1f483-191">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-191">Applies to:</span></span>  
- <span data-ttu-id="1f483-192">WCF NetMsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-192">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="1f483-193">WCF 自定义接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-193">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="1f483-194">WCF-CustomIsolated 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-194">WCF-CustomIsolated receive adapter</span></span>

#### <a name="enabletransaction"></a><span data-ttu-id="1f483-195">EnableTransaction</span><span class="sxs-lookup"><span data-stu-id="1f483-195">EnableTransaction</span></span>
<span data-ttu-id="1f483-196">此属性的效果依 WCF 适配器的不同而变化。</span><span class="sxs-lookup"><span data-stu-id="1f483-196">The effect of this property varies depending on the WCF adapter.</span></span> <span data-ttu-id="1f483-197">有关此属性的详细信息，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-197">For more information about this property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="1f483-198">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-198">Type: Boolean</span></span>  
<span data-ttu-id="1f483-199">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-199">Applies to:</span></span> 

- <span data-ttu-id="1f483-200">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-200">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="1f483-201">WCF-NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-201">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="1f483-202">WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-202">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="1f483-203">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-203">WCF-NetMsmq adapter</span></span>

#### <a name="endpointbehaviorconfiguration"></a><span data-ttu-id="1f483-204">EndpointBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f483-204">EndpointBehaviorConfiguration</span></span>
<span data-ttu-id="1f483-205">指定使用的 XML 字符串**\<行为\>**元素 **\<endpointBehaviors\>** 元素来配置的行为设置WCF 终结点。</span><span class="sxs-lookup"><span data-stu-id="1f483-205">Specify an XML string with the **\<behavior\>** element of the **\<endpointBehaviors\>** element to configure the behavior settings of a WCF endpoint.</span></span> <span data-ttu-id="1f483-206">有关详细信息 **\<endpointBehaviors\>** 元素，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="1f483-206">For more information about the **\<endpointBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="1f483-207">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-207">Example:</span></span> 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

<span data-ttu-id="1f483-208">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-208">Type: String</span></span>  
<span data-ttu-id="1f483-209">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-209">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-210">适用于： WCF 自定义发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-210">Applies to: WCF-Custom send adapter</span></span>

#### <a name="establishsecuritycontext"></a><span data-ttu-id="1f483-211">EstablishSecurityContext</span><span class="sxs-lookup"><span data-stu-id="1f483-211">EstablishSecurityContext</span></span>
<span data-ttu-id="1f483-212">指定安全通道是否建立安全会话。</span><span class="sxs-lookup"><span data-stu-id="1f483-212">Specify whether the security channel establishes a secure session.</span></span> <span data-ttu-id="1f483-213">安全会话在交换应用程序消息之前建立安全上下文标记 (SCT)。</span><span class="sxs-lookup"><span data-stu-id="1f483-213">A secure session establishes a Security Context Token (SCT) before exchanging the application messages.</span></span>

<span data-ttu-id="1f483-214">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-214">Type: Boolean</span></span>  
<span data-ttu-id="1f483-215">默认值：True</span><span class="sxs-lookup"><span data-stu-id="1f483-215">Default value: True</span></span>  
<span data-ttu-id="1f483-216">应用于： WCF WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-216">Applied to: WCF-WSHttp adapter</span></span>

#### <a name="fromaddress"></a><span data-ttu-id="1f483-217">FromAddress</span><span class="sxs-lookup"><span data-stu-id="1f483-217">FromAddress</span></span>
<span data-ttu-id="1f483-218">指示发送传入 WCF 消息的源终结点地址。</span><span class="sxs-lookup"><span data-stu-id="1f483-218">Indicate the source endpoint address through which the incoming WCF messages are sent.</span></span> <span data-ttu-id="1f483-219">该属性将自动提升从传入消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-219">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="1f483-220">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-220">Type: String</span></span>  
<span data-ttu-id="1f483-221">适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-221">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>
  
#### <a name="headers"></a><span data-ttu-id="1f483-222">标头</span><span class="sxs-lookup"><span data-stu-id="1f483-222">Headers</span></span>
<span data-ttu-id="1f483-223">指定用于提供除 URI 外的其他寻址信息的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="1f483-223">Specify the endpoint references used to provide additional addressing information beyond the URI.</span></span> <span data-ttu-id="1f483-224">当使用此属性时，此属性必须具有\<**标头**\>作为根元素的元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-224">When this property is used, this property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="1f483-225">所有地址标头必须放置在\<**标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-225">All of the address headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="1f483-226">该属性自动从传入消息进行升级。</span><span class="sxs-lookup"><span data-stu-id="1f483-226">This property is automatically promoted for incoming messages.</span></span>

<span data-ttu-id="1f483-227">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-227">Example:</span></span>
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

<span data-ttu-id="1f483-228">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-228">Type: String</span></span>  
<span data-ttu-id="1f483-229">适用于： 所有 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-229">Applies to: All WCF adapters</span></span>
  
#### <a name="identity"></a><span data-ttu-id="1f483-230">标识</span><span class="sxs-lookup"><span data-stu-id="1f483-230">Identity</span></span>
<span data-ttu-id="1f483-231">指定接收位置提供或发送端口预期的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="1f483-231">Specify the identity of the service that a receive location provides or a send port expects.</span></span> <span data-ttu-id="1f483-232">可以为指定的值 **标识** 属性而异的安全配置。</span><span class="sxs-lookup"><span data-stu-id="1f483-232">The values that can be specified for the **Identity** property differ according to the security configuration.</span></span> <span data-ttu-id="1f483-233">这些设置使客户端能够对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1f483-233">These settings enable clients to authenticate services.</span></span> <span data-ttu-id="1f483-234">在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保服务的标识与客户端的值保持一致。</span><span class="sxs-lookup"><span data-stu-id="1f483-234">In the handshake process between clients and services, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the services matches the values of the clients.</span></span>

<span data-ttu-id="1f483-235">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-235">Example:</span></span>
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

<span data-ttu-id="1f483-236">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-236">Type: String</span></span>  
<span data-ttu-id="1f483-237">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-237">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-238">适用于： 所有 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-238">Applies to: All WCF adapters</span></span>

#### <a name="inboundbodylocation"></a><span data-ttu-id="1f483-239">InboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="1f483-239">InboundBodyLocation</span></span>
<span data-ttu-id="1f483-240">指定 SOAP 数据选择 **正文** 传入 WCF 消息的元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-240">Specify the data selection for the SOAP **Body** element of incoming WCF messages.</span></span> <span data-ttu-id="1f483-241">有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-241">For more information about how to use the **InboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="1f483-242">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-242">Type: String</span></span>  
<span data-ttu-id="1f483-243">默认值： UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="1f483-243">Default value: UseBodyElement</span></span>  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

<span data-ttu-id="1f483-244">适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送</span><span class="sxs-lookup"><span data-stu-id="1f483-244">Applies to: All WCF adapters *except* WCF-NetMsmq send</span></span>  

#### <a name="inboundbodypathexpression"></a><span data-ttu-id="1f483-245">InboundBodyPathExpression</span><span class="sxs-lookup"><span data-stu-id="1f483-245">InboundBodyPathExpression</span></span>
<span data-ttu-id="1f483-246">指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。</span><span class="sxs-lookup"><span data-stu-id="1f483-246">Specify the body path expression to identify a specific part of an incoming message used to create the BizTalk message body part.</span></span> <span data-ttu-id="1f483-247">此正文路径表达式针对 SOAP 的即时子元素进行评估 **正文** 传入消息的节点。</span><span class="sxs-lookup"><span data-stu-id="1f483-247">This body path expression is evaluated against the immediate child element of the SOAP **Body** node of an incoming message.</span></span> <span data-ttu-id="1f483-248">如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="1f483-248">If this body path expression returns more than one node, only the first node is chosen for the BizTalk message body part.</span></span> <span data-ttu-id="1f483-249">此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。</span><span class="sxs-lookup"><span data-stu-id="1f483-249">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span> <span data-ttu-id="1f483-250">有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-250">For more information about how to use the **InboundBodyPathExpression** property, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>

<span data-ttu-id="1f483-251">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-251">Type: String</span></span>  
<span data-ttu-id="1f483-252">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-252">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-253">适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-253">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundheaders"></a><span data-ttu-id="1f483-254">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="1f483-254">InboundHeaders</span></span>
<span data-ttu-id="1f483-255">使用 **InboundHeaders** 属性访问传入的 WCF 消息的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="1f483-255">Use the **InboundHeaders** property to access the SOAP headers of incoming WCF messages.</span></span> <span data-ttu-id="1f483-256">WCF 适配器将入站消息中的所有 SOAP 标头值复制到此属性，其中包括 WCF 基础结构用于诸如 WS-Addressing、WS-Security 和 WS-AtomicTransaction 的自定义 SOAP 标头和标准 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="1f483-256">The WCF adapters copy all the SOAP header values in inbound messages to this property, which include custom SOAP headers and standard SOAP headers that the WCF infrastructure uses for such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="1f483-257">上下文属性中包含的值是一个包含与 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头将复制作为子元素的\< **标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-257">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="1f483-258">有关如何对访问 SOAP 标头与 WCF 适配器的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从 [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="1f483-258">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="1f483-259">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-259">Type: String</span></span>  
<span data-ttu-id="1f483-260">适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-260">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundnodeencoding"></a><span data-ttu-id="1f483-261">InboundNodeEncoding</span><span class="sxs-lookup"><span data-stu-id="1f483-261">InboundNodeEncoding</span></span>
<span data-ttu-id="1f483-262">指定的编码 WCF 接收适配器使用要解码识别由正文路径表达式中指定的节点类型 **InboundBodyPathExpression**。</span><span class="sxs-lookup"><span data-stu-id="1f483-262">Specify the type of encoding that the WCF receive adapter uses to decode the node identified by the body path expression specified in **InboundBodyPathExpression**.</span></span> <span data-ttu-id="1f483-263">此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。</span><span class="sxs-lookup"><span data-stu-id="1f483-263">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span>

<span data-ttu-id="1f483-264">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-264">Type: String</span></span>  
<span data-ttu-id="1f483-265">默认值： XML</span><span class="sxs-lookup"><span data-stu-id="1f483-265">Default value: XML</span></span>  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

<span data-ttu-id="1f483-266">适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-266">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="isfault"></a><span data-ttu-id="1f483-267">IsFault</span><span class="sxs-lookup"><span data-stu-id="1f483-267">IsFault</span></span>
<span data-ttu-id="1f483-268">指示是否接收 SOAP 错误消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-268">Indicate whether SOAP fault messages are received.</span></span> <span data-ttu-id="1f483-269">该属性将自动提升从传入消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-269">The property is automatically promoted from incoming messages.</span></span> 

<span data-ttu-id="1f483-270">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-270">**Note**</span></span>  
<span data-ttu-id="1f483-271">**IsFault**属性不能用于检查收到的消息，例如 HTTP 404 （文件或找不到目录） 错误的传输错误。</span><span class="sxs-lookup"><span data-stu-id="1f483-271">The **IsFault** property cannot be used to check the received messages for transport errors such as the HTTP 404 (File or Directory Not Found) error.</span></span>

<span data-ttu-id="1f483-272">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-272">Type: Boolean</span></span>  
<span data-ttu-id="1f483-273">适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-273">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="leasetimeout"></a><span data-ttu-id="1f483-274">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="1f483-274">LeaseTimeout</span></span>
<span data-ttu-id="1f483-275">指定活动的池连接的最大生存期。</span><span class="sxs-lookup"><span data-stu-id="1f483-275">Specify the maximum lifetime of an active pooled connection.</span></span> <span data-ttu-id="1f483-276">指定的时间过后，则连接将关闭后当前的请求已得到处理。</span><span class="sxs-lookup"><span data-stu-id="1f483-276">After the specified time elapses, the connection closes after the current request is serviced.</span></span>

<span data-ttu-id="1f483-277">WCF NetTcp 适配器利用 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 类与终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="1f483-277">The WCF-NetTcp adapter leverages the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) class to communicate with an endpoint.</span></span> <span data-ttu-id="1f483-278">使用时 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 在负载平衡方案中，请考虑减少的默认租约超时值。有关负载平衡时使用的详细信息[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="1f483-278">When using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) in load-balanced scenarios, consider reducing the default lease time-out. For more information about load balancing when using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), see the appropriate topic in See Also.</span></span>

<span data-ttu-id="1f483-279">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-279">Type: String</span></span>  
<span data-ttu-id="1f483-280">默认值：00:05:00</span><span class="sxs-lookup"><span data-stu-id="1f483-280">Default value: 00:05:00</span></span>  
<span data-ttu-id="1f483-281">适用于： WCF NetTcp 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-281">Applies to: WCF-NetTcp receive adapter</span></span>  

#### <a name="maxconcurrentcalls"></a><span data-ttu-id="1f483-282">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="1f483-282">MaxConcurrentCalls</span></span>
<span data-ttu-id="1f483-283">指定對單一服務執行個體的並行呼叫數目。</span><span class="sxs-lookup"><span data-stu-id="1f483-283">Specify the number of concurrent calls to a single service instance.</span></span> <span data-ttu-id="1f483-284">超出上限的呼叫將排入佇列。</span><span class="sxs-lookup"><span data-stu-id="1f483-284">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="1f483-285">將這個值設定為 0 的效果與設定為 **Int32.MaxValue**相同。</span><span class="sxs-lookup"><span data-stu-id="1f483-285">Setting this value to 0 is equivalent to setting it to **Int32.MaxValue**.</span></span> 

<span data-ttu-id="1f483-286">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-286">**Note**</span></span>  
<span data-ttu-id="1f483-287">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-287">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="1f483-288">类型： 整数</span><span class="sxs-lookup"><span data-stu-id="1f483-288">Type: Integer</span></span>  
<span data-ttu-id="1f483-289">默认值：200</span><span class="sxs-lookup"><span data-stu-id="1f483-289">Default value: 200</span></span>  
<span data-ttu-id="1f483-290">适用于： 所有 WCF 都接收适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-290">Applies to: All WCF receive adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="maxconnections"></a><span data-ttu-id="1f483-291">MaxConnections</span><span class="sxs-lookup"><span data-stu-id="1f483-291">MaxConnections</span></span>
<span data-ttu-id="1f483-292">指定监听程序可以拥有的等待应用程序接受的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="1f483-292">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="1f483-293">在超过此配额值时，将删除新的传入连接，而不是等待接受这些连接。</span><span class="sxs-lookup"><span data-stu-id="1f483-293">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> 

<span data-ttu-id="1f483-294">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-294">**Note**</span></span>  
<span data-ttu-id="1f483-295">由于这是一个适配器处理程序属性，因此该属性无法在管道组件和业务流程中进行配置。</span><span class="sxs-lookup"><span data-stu-id="1f483-295">Because this is an adapter handler property, this property cannot be configured in pipeline components and orchestrations.</span></span> 

<span data-ttu-id="1f483-296">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-296">**Note**</span></span>  
<span data-ttu-id="1f483-297">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-297">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="1f483-298">类型： 整数</span><span class="sxs-lookup"><span data-stu-id="1f483-298">Type: Integer</span></span>  
<span data-ttu-id="1f483-299">默认值： 10</span><span class="sxs-lookup"><span data-stu-id="1f483-299">Default value: 10</span></span>  
<span data-ttu-id="1f483-300">适用于： WCF NetNamedPipe 适配器，WCF NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-300">Applies to: WCF-NetNamedPipe adapter, WCF-NetTcp adapter</span></span>  

#### <a name="maxreceivedmessagesize"></a><span data-ttu-id="1f483-301">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="1f483-301">MaxReceivedMessageSize</span></span>
<span data-ttu-id="1f483-302">指定网络上可接收的消息的最大大小（包括标头），以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="1f483-302">Specify the maximum size, in bytes, for a message (including headers) that can be received on the wire.</span></span> <span data-ttu-id="1f483-303">消息的大小受为每条消息分配的内存量的限制。</span><span class="sxs-lookup"><span data-stu-id="1f483-303">The size of the messages is bounded by the amount of memory allocated for each message.</span></span> <span data-ttu-id="1f483-304">您可以使用這個屬性來限制遭受拒絕服務 (DoS) 攻擊的風險程度。</span><span class="sxs-lookup"><span data-stu-id="1f483-304">You can use this property to limit exposure to denial of service (DoS) attacks.</span></span>

<span data-ttu-id="1f483-305">类型： 整数</span><span class="sxs-lookup"><span data-stu-id="1f483-305">Type: Integer</span></span>  
<span data-ttu-id="1f483-306">預設值：65536</span><span class="sxs-lookup"><span data-stu-id="1f483-306">Default value: 65536</span></span>  
<span data-ttu-id="1f483-307">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-307">Applies to:</span></span> 
- <span data-ttu-id="1f483-308">WCF BasicHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-308">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="1f483-309">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-309">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="1f483-310">WCF-NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-310">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="1f483-311">WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-311">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="1f483-312">WCF NetMsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-312">WCF-NetMsmq receive adapter</span></span>

#### <a name="messageclientcredentialtype"></a><span data-ttu-id="1f483-313">MessageClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="1f483-313">MessageClientCredentialType</span></span>
<span data-ttu-id="1f483-314">指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="1f483-314">Specify the type of credential to be used when performing client authentication using message-based security.</span></span>

<span data-ttu-id="1f483-315">适用值因每个 WCF 适配器的不同而异。</span><span class="sxs-lookup"><span data-stu-id="1f483-315">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="1f483-316">有关详细信息**MessageClientCredentialType**属性，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-316">For more information about the **MessageClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="1f483-317">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-317">Type: String</span></span>  
<span data-ttu-id="1f483-318">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-318">Applies to:</span></span> 
- <span data-ttu-id="1f483-319">WCF BasicHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-319">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="1f483-320">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-320">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="1f483-321">WCF-NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-321">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="1f483-322">WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-322">WCF-NetNamedPipe adapter</span></span>

#### <a name="messageencoding"></a><span data-ttu-id="1f483-323">MessageEncoding</span><span class="sxs-lookup"><span data-stu-id="1f483-323">MessageEncoding</span></span>
<span data-ttu-id="1f483-324">指定用來為 SOAP 訊息編碼的編碼器。</span><span class="sxs-lookup"><span data-stu-id="1f483-324">Specify the encoder used to encode the SOAP message.</span></span>

<span data-ttu-id="1f483-325">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-325">Type: String</span></span>  
<span data-ttu-id="1f483-326">默认值︰ 文本</span><span class="sxs-lookup"><span data-stu-id="1f483-326">Default value: Text</span></span>  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

<span data-ttu-id="1f483-327">适用于： WCF BasicHttp 适配器，WCF WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-327">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>


#### <a name="msmqauthenticationmode"></a><span data-ttu-id="1f483-328">MsmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="1f483-328">MsmqAuthenticationMode</span></span>
<span data-ttu-id="1f483-329">指定如何通过 MSMQ 传输对消息进行验证。</span><span class="sxs-lookup"><span data-stu-id="1f483-329">Specify how the message must be authenticated by the MSMQ transport.</span></span>

<span data-ttu-id="1f483-330">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-330">Type: String</span></span>  
<span data-ttu-id="1f483-331">默认值︰ **WindowsDomain**</span><span class="sxs-lookup"><span data-stu-id="1f483-331">Default value: **WindowsDomain**</span></span>  
    <span data-ttu-id="1f483-332">有关详细信息有关的适用值**MsmqAuthenticationMode**属性，请参阅**MSMQ 身份验证模式**中的属性**WCF NetMsmq 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f483-332">For more information about the applicable values for the **MsmqAuthenticationMode** property, see the **MSMQ authentication mode** property in the **WCF-NetMsmq Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
<span data-ttu-id="1f483-333">适用于： WCF NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-333">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqencryptionalgorithm"></a><span data-ttu-id="1f483-334">MsmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="1f483-334">MsmqEncryptionAlgorithm</span></span>
<span data-ttu-id="1f483-335">指定在消息队列管理器之间传输消息时，将在网络上使用的消息加密算法。</span><span class="sxs-lookup"><span data-stu-id="1f483-335">Specify the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="1f483-336">此属性才可用才 **而 MsmqProtectionLevel** 属性设置为 **EncryptAndSign**。</span><span class="sxs-lookup"><span data-stu-id="1f483-336">This property is available only if the **MsmqProtectionLevel** property is set to **EncryptAndSign**.</span></span>

<span data-ttu-id="1f483-337">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-337">Type: String</span></span>  
<span data-ttu-id="1f483-338">默认值︰ **RC4Stream**</span><span class="sxs-lookup"><span data-stu-id="1f483-338">Default value: **RC4Stream**</span></span>  

    Applicable values are: RC4Stream, AES

<span data-ttu-id="1f483-339">适用于： WCF NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-339">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqprotectionlevel"></a><span data-ttu-id="1f483-340">MsmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="1f483-340">MsmqProtectionLevel</span></span>
<span data-ttu-id="1f483-341">指定消息在 MSMQ 传输一级的保护方式。</span><span class="sxs-lookup"><span data-stu-id="1f483-341">Specify the way messages are secured at the level of the MSMQ transport.</span></span>

<span data-ttu-id="1f483-342">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-342">Type: String</span></span>  
<span data-ttu-id="1f483-343">默认值︰ **登录**</span><span class="sxs-lookup"><span data-stu-id="1f483-343">Default value: **Sign**</span></span>  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

<span data-ttu-id="1f483-344">适用于： WCF NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-344">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqsecurehashalgorithm"></a><span data-ttu-id="1f483-345">MsmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="1f483-345">MsmqSecureHashAlgorithm</span></span>
<span data-ttu-id="1f483-346">指定使用哈希算法计算消息摘要。</span><span class="sxs-lookup"><span data-stu-id="1f483-346">Specify the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="1f483-347">此属性不可用如果 **而 MsmqProtectionLevel** 属性设置为 **无**。</span><span class="sxs-lookup"><span data-stu-id="1f483-347">This property is not available if the **MsmqProtectionLevel** property is set to **None**.</span></span>

<span data-ttu-id="1f483-348">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-348">Type: String</span></span>  
<span data-ttu-id="1f483-349">默认值︰ **SHA1**</span><span class="sxs-lookup"><span data-stu-id="1f483-349">Default value: **SHA1**</span></span>  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

<span data-ttu-id="1f483-350">适用于： WCF NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-350">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="negotiateservicecredential"></a><span data-ttu-id="1f483-351">NegotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="1f483-351">NegotiateServiceCredential</span></span>
<span data-ttu-id="1f483-352">指定是在带外客户端提供服务凭据，还是通过协商过程从服务将服务凭据提供给客户端。</span><span class="sxs-lookup"><span data-stu-id="1f483-352">Specify whether the service credential is provisioned at the client out of band, or is obtained from the service to the client through a process of negotiation.</span></span> <span data-ttu-id="1f483-353">这种协商是正常消息交换开始前的准备过程。</span><span class="sxs-lookup"><span data-stu-id="1f483-353">Such a negotiation is a precursor to the usual message exchange.</span></span>

<span data-ttu-id="1f483-354">如果 **MessageClientCredentialType** 属性等于 **无**, ，**用户名**, ，或 **证书**, ，此属性设置为 **False** 意味着服务证书位于带外客户端和客户端需要指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="1f483-354">If the **MessageClientCredentialType** property equals **None**, **Username**, or **Certificate**, setting this property to **False** implies that the service certificate is available at the client out of band and that the client needs to specify the service certificate.</span></span> <span data-ttu-id="1f483-355">此模式可与实现 WS-Trust 和 WS-SecureConversation 的 SOAP 堆栈交互操作。</span><span class="sxs-lookup"><span data-stu-id="1f483-355">This mode is interoperable with SOAP stacks that implement WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="1f483-356">如果 **MessageClientCredentialType** 属性设置为 **Windows**, ，此属性设置为 **False** 指定基于 Kerberos 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="1f483-356">If the **MessageClientCredentialType** property is set to **Windows**, setting this property to **False** specifies Kerberos-based authentication.</span></span> <span data-ttu-id="1f483-357">这意味着客户端和服务必须属于同一个 Kerberos 域。</span><span class="sxs-lookup"><span data-stu-id="1f483-357">This means that the client and service must be part of the same Kerberos domain.</span></span> <span data-ttu-id="1f483-358">此模式可与实现 Kerberos 标记配置文件（在 OASIS WSS TC 中定义）以及 WS-Trust 和 WS-SecureConversation 的 SOAP 堆栈交互操作。</span><span class="sxs-lookup"><span data-stu-id="1f483-358">This mode is interoperable with SOAP stacks that implement the Kerberos token profile (as defined at OASIS WSS TC) as well as WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="1f483-359">当此属性是 **True**, ，会引起通过 SOAP 消息隧道 SPNego 交换的.NET SOAP 协商。</span><span class="sxs-lookup"><span data-stu-id="1f483-359">When this property is **True**, it causes a .NET SOAP negotiation that tunnels SPNego exchange over SOAP messages.</span></span>

<span data-ttu-id="1f483-360">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-360">Type: Boolean</span></span>  
<span data-ttu-id="1f483-361">默认值：True</span><span class="sxs-lookup"><span data-stu-id="1f483-361">Default value: True</span></span>  
<span data-ttu-id="1f483-362">适用于： WCF WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-362">Applies to: WCF-WSHttp adapter</span></span>  

#### <a name="opentimeout"></a><span data-ttu-id="1f483-363">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="1f483-363">OpenTimeout</span></span>
<span data-ttu-id="1f483-364">指定時間值，表示可供完成通道開啟作業的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="1f483-364">Specify a time span value that indicates the interval of time provided for a channel open operation to complete.</span></span> 

<span data-ttu-id="1f483-365">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-365">**Note**</span></span>  
<span data-ttu-id="1f483-366">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-366">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="1f483-367">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-367">Type: String</span></span>  
<span data-ttu-id="1f483-368">預設值：00:01:00</span><span class="sxs-lookup"><span data-stu-id="1f483-368">Default value: 00:01:00</span></span>  
<span data-ttu-id="1f483-369">适用于： 所有 WCF 适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-369">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="orderedprocessing"></a><span data-ttu-id="1f483-370">OrderedProcessing</span><span class="sxs-lookup"><span data-stu-id="1f483-370">OrderedProcessing</span></span>
<span data-ttu-id="1f483-371">指定是否按顺序处理消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-371">Specify whether to process messages serially.</span></span> <span data-ttu-id="1f483-372">当选中此属性时，此接收位置与拥有的 BizTalk 消息传递或业务流程发送端口结合使用时的有序的消息传递 **按序送达** 选项设置为 `True`。</span><span class="sxs-lookup"><span data-stu-id="1f483-372">When this property is selected, this receive location accommodates ordered message delivery when used in conjunction with a BizTalk messaging or orchestration send port that has the **Ordered Delivery** option set to `True`.</span></span> <span data-ttu-id="1f483-373">有关详细信息 **按序送达** 选项，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="1f483-373">For more information about the **Ordered Delivery** option, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="1f483-374">此属性适用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="1f483-374">This property is applicable in the following cases:</span></span>
- <span data-ttu-id="1f483-375">WCF 自定义适配器： 时**BindingType**属性设置为**netMsmqBinding**</span><span class="sxs-lookup"><span data-stu-id="1f483-375">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**</span></span>
- <span data-ttu-id="1f483-376">WCF 自定义适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道依赖支持有序的传递，如 MSMQ 传输。</span><span class="sxs-lookup"><span data-stu-id="1f483-376">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery such as MSMQ.</span></span>
- <span data-ttu-id="1f483-377">WCF CustomIsolated 适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道利用支持有序的传递的传输。</span><span class="sxs-lookup"><span data-stu-id="1f483-377">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery.</span></span>
- <span data-ttu-id="1f483-378">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-378">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="1f483-379">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-379">Type: String</span></span>  
<span data-ttu-id="1f483-380">默认值︰ **False**</span><span class="sxs-lookup"><span data-stu-id="1f483-380">Default value: **False**</span></span>  
<span data-ttu-id="1f483-381">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-381">Applies to:</span></span> 
- <span data-ttu-id="1f483-382">WCF NetMsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-382">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="1f483-383">WCF 自定义接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-383">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="1f483-384">WCF-CustomIsolated 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-384">WCF-CustomIsolated receive adapter</span></span>

#### <a name="outboundbodylocation"></a><span data-ttu-id="1f483-385">OutboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="1f483-385">OutboundBodyLocation</span></span>
<span data-ttu-id="1f483-386">指定 SOAP 数据选择 **正文** 传出的 WCF 消息的元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-386">Specify the data selection for the SOAP **Body** element of outgoing WCF messages.</span></span> <span data-ttu-id="1f483-387">有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-387">For more information about how to use the **OutboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="1f483-388">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-388">Type: String</span></span>  
<span data-ttu-id="1f483-389">默认值： UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="1f483-389">Default value: UseBodyElement</span></span>  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

<span data-ttu-id="1f483-390">适用于： 所有 WCF 适配器*除*WCF NetMsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-390">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundcustomheaders"></a><span data-ttu-id="1f483-391">OutboundCustomHeaders</span><span class="sxs-lookup"><span data-stu-id="1f483-391">OutboundCustomHeaders</span></span>
<span data-ttu-id="1f483-392">指定传出消息的自定义 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="1f483-392">Specify the custom SOAP headers for outgoing messages.</span></span> <span data-ttu-id="1f483-393">当使用此属性时，该属性必须具有\<**标头**\>作为根元素的元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-393">When this property is used, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="1f483-394">所有自定义 SOAP 标头必须放置在\<**标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-394">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="1f483-395">如果自定义 SOAP 标头的值为空字符串，则必须分配\<**标头**\>\</**标头**\>或\<**标头**\>到此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-395">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**\> to this property.</span></span> <span data-ttu-id="1f483-396">有关如何使用 WCF 适配器使用 SOAP 标头的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从 [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="1f483-396">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="1f483-397">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-397">Type: String</span></span>  
<span data-ttu-id="1f483-398">适用于： 所有 WCF 适配器*除*WCF NetMsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-398">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundxmltemplate"></a><span data-ttu-id="1f483-399">OutboundXmlTemplate</span><span class="sxs-lookup"><span data-stu-id="1f483-399">OutboundXmlTemplate</span></span>
<span data-ttu-id="1f483-400">指定的 SOAP 内容的 XML 格式模板 **正文** 的传出消息的元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-400">Specify the XML-formatted template for the content of the SOAP **Body** element of an outgoing message.</span></span> <span data-ttu-id="1f483-401">此属性是必需的如果 **OutboundBodyLocation** 属性设置为 **UseTemplate**。</span><span class="sxs-lookup"><span data-stu-id="1f483-401">This property is required if the **OutboundBodyLocation** property is set to **UseTemplate**.</span></span> <span data-ttu-id="1f483-402">有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-402">For more information about how to use the **OutboundXMLTemplate** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="1f483-403">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-403">Type: String</span></span>  
<span data-ttu-id="1f483-404">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-404">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-405">适用于： 所有 WCF 适配器*除*WCF NetMsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-405">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="password"></a><span data-ttu-id="1f483-406">密码</span><span class="sxs-lookup"><span data-stu-id="1f483-406">Password</span></span>
<span data-ttu-id="1f483-407">指定要用于目标服务器的身份验证的密码时 **UseSSO** 属性设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="1f483-407">Specify the password to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span>

<span data-ttu-id="1f483-408">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-408">Type: String</span></span>  
<span data-ttu-id="1f483-409">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-409">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-410">适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-410">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>  

#### <a name="propagatefaultmessage"></a><span data-ttu-id="1f483-411">PropagateFaultMessage</span><span class="sxs-lookup"><span data-stu-id="1f483-411">PropagateFaultMessage</span></span>
<span data-ttu-id="1f483-412">指定是否路由或挂起出站处理中失败的消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-412">Specify whether to route or suspend messages that fail in outbound processing.</span></span> <span data-ttu-id="1f483-413">此屬性只對請求-回應連接埠有效。</span><span class="sxs-lookup"><span data-stu-id="1f483-413">This property is valid only for solicit-response ports.</span></span> 

<span data-ttu-id="1f483-414">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-414">**Note**</span></span>  
<span data-ttu-id="1f483-415">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-415">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="1f483-416">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-416">Type: Boolean</span></span>  
<span data-ttu-id="1f483-417">默认值︰ **True**</span><span class="sxs-lookup"><span data-stu-id="1f483-417">Default value: **True**</span></span>  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

<span data-ttu-id="1f483-418">适用于： 所有 WCF 都发送适配器*除*WCF NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-418">Applies to: All WCF send adapters *except* the WCF-NetMsmq adapter</span></span>
  
#### <a name="proxyaddress"></a><span data-ttu-id="1f483-419">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="1f483-419">ProxyAddress</span></span>
<span data-ttu-id="1f483-420">指定 Proxy 伺服器的位址。</span><span class="sxs-lookup"><span data-stu-id="1f483-420">Specify the address of the proxy server.</span></span> <span data-ttu-id="1f483-421">使用 **https** 或 **http** 根据安全配置的方案。</span><span class="sxs-lookup"><span data-stu-id="1f483-421">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="1f483-422">這個位址後面可以加上冒號和連接埠編號，</span><span class="sxs-lookup"><span data-stu-id="1f483-422">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="1f483-423">该属性是必需的如果**ProxyToUse**属性设置为**UserSpecified** (例如，http://127.0.0.1:8080)</span><span class="sxs-lookup"><span data-stu-id="1f483-423">The property is required if the **ProxyToUse** property is set to **UserSpecified** (For example, http://127.0.0.1:8080)</span></span>

<span data-ttu-id="1f483-424">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-424">Type: String</span></span>  
<span data-ttu-id="1f483-425">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-425">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-426">适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-426">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxypassword"></a><span data-ttu-id="1f483-427">ProxyPassword</span><span class="sxs-lookup"><span data-stu-id="1f483-427">ProxyPassword</span></span>
<span data-ttu-id="1f483-428">指定要用于中指定的代理服务器密码 **ProxyAddress** 属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-428">Specify the password to use for the proxy server specified in the **ProxyAddress** property.</span></span>

<span data-ttu-id="1f483-429">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-429">Type: String</span></span>  
<span data-ttu-id="1f483-430">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-430">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-431">适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-431">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="proxytouse"></a><span data-ttu-id="1f483-432">ProxyToUse</span><span class="sxs-lookup"><span data-stu-id="1f483-432">ProxyToUse</span></span>
<span data-ttu-id="1f483-433">指定要用于传出 HTTP 通信的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="1f483-433">Specify which proxy server to use for outgoing HTTP traffic.</span></span>

<span data-ttu-id="1f483-434">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-434">Type: String</span></span>  
<span data-ttu-id="1f483-435">默认值︰ **无**</span><span class="sxs-lookup"><span data-stu-id="1f483-435">Default value: **None**</span></span>  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

<span data-ttu-id="1f483-436">适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-436">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxyusername"></a><span data-ttu-id="1f483-437">ProxyUserName</span><span class="sxs-lookup"><span data-stu-id="1f483-437">ProxyUserName</span></span>
<span data-ttu-id="1f483-438">指定要用于代理服务器中指定的用户名称 **ProxyAddress** 属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-438">Specify the user name to use for the proxy server specified in the **ProxyAddress** property.</span></span> <span data-ttu-id="1f483-439">该属性是必需的如果 **ProxyToUse** 属性设置为 **UserSpecified**。</span><span class="sxs-lookup"><span data-stu-id="1f483-439">The property is required if the **ProxyToUse** property is set to **UserSpecified**.</span></span>

<span data-ttu-id="1f483-440">有关此属性的详细信息，请参阅[如何配置 WCF WSHttp 发送端口](../core/how-to-configure-a-wcf-wshttp-send-port.md)和[如何配置 WCF BasicHttp 发送端口](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)。</span><span class="sxs-lookup"><span data-stu-id="1f483-440">For more information about this property, see [How to Configure a WCF-WSHttp Send Port](../core/how-to-configure-a-wcf-wshttp-send-port.md) and [How to Configure a WCF-BasicHttp Send Port](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f).</span></span>

<span data-ttu-id="1f483-441">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-441">Type: String</span></span>  
<span data-ttu-id="1f483-442">适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-442">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="replytoaddress"></a><span data-ttu-id="1f483-443">ReplyToAddress</span><span class="sxs-lookup"><span data-stu-id="1f483-443">ReplyToAddress</span></span>
<span data-ttu-id="1f483-444">指示与通过请求响应接收位置接收的传入消息相对应的传出 WCF 消息的回复终结点地址。</span><span class="sxs-lookup"><span data-stu-id="1f483-444">Indicate the reply endpoint address for the outgoing WCF messages corresponding to incoming messages received through the request-response receive locations.</span></span> <span data-ttu-id="1f483-445">该属性将自动提升从传入消息。</span><span class="sxs-lookup"><span data-stu-id="1f483-445">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="1f483-446">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-446">Type: String</span></span>  
<span data-ttu-id="1f483-447">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-447">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-448">适用于： 所有 WCF 适配器*除*WCF NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-448">Applies to: All WCF adapters *except* the WCF-NetMsmq adapter</span></span>

#### <a name="securitymode"></a><span data-ttu-id="1f483-449">SecurityMode</span><span class="sxs-lookup"><span data-stu-id="1f483-449">SecurityMode</span></span>
<span data-ttu-id="1f483-450">指定使用的安全性類型。</span><span class="sxs-lookup"><span data-stu-id="1f483-450">Specify the type of security that is used.</span></span> <span data-ttu-id="1f483-451">适用值因每个 WCF 适配器的不同而异。</span><span class="sxs-lookup"><span data-stu-id="1f483-451">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="1f483-452">有关详细信息**SecurityMode**属性，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-452">For more information about the **SecurityMode** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span> 

<span data-ttu-id="1f483-453">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-453">**Note**</span></span>  
<span data-ttu-id="1f483-454">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-454">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="1f483-455">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-455">Type: String</span></span>  
<span data-ttu-id="1f483-456">适用于： 所有 WCF 适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-456">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="sendtimeout"></a><span data-ttu-id="1f483-457">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="1f483-457">SendTimeout</span></span>
<span data-ttu-id="1f483-458">指定時間值，表示可供完成傳送作業的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="1f483-458">Specify a time span value that indicates the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1f483-459">此值指定完成整个交互的时间跨度（即使响应方返回一条大消息）。</span><span class="sxs-lookup"><span data-stu-id="1f483-459">This value specifies a time span for the whole interaction to complete, even if the correspondent sends a large message.</span></span>

<span data-ttu-id="1f483-460">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-460">Type: String</span></span>  
<span data-ttu-id="1f483-461">預設值：00:01:00</span><span class="sxs-lookup"><span data-stu-id="1f483-461">Default value: 00:01:00</span></span>  
<span data-ttu-id="1f483-462">适用于： 所有 WCF 适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-462">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="servicebehaviorconfiguration"></a><span data-ttu-id="1f483-463">ServiceBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f483-463">ServiceBehaviorConfiguration</span></span>
<span data-ttu-id="1f483-464">指定使用的 XML 字符串**\<行为\>**元素 **\<serviceBehaviors\>** 元素来配置 WCF 行为设置服务。</span><span class="sxs-lookup"><span data-stu-id="1f483-464">Specify an XML string with the **\<behavior\>** element of the **\<serviceBehaviors\>** element to configure the behavior settings of a WCF service.</span></span> <span data-ttu-id="1f483-465">有关详细信息 **\<serviceBehaviors\>** 元素，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="1f483-465">For more information about the **\<serviceBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="1f483-466">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-466">Example:</span></span>

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

<span data-ttu-id="1f483-467">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-467">Type: String</span></span>  
<span data-ttu-id="1f483-468">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-468">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-469">适用于： WCF 自定义接收适配器，WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-469">Applies to: WCF-Custom receive adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="servicecertificate"></a><span data-ttu-id="1f483-470">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="1f483-470">ServiceCertificate</span></span>
<span data-ttu-id="1f483-471">如果此属性用于接收位置，则为接收位置指定 X.509 证书的指纹，客户端利用该指纹验证服务。</span><span class="sxs-lookup"><span data-stu-id="1f483-471">If this property is used for receive locations, specify the thumbprint of the X.509 certificate for the receive locations that clients use to authenticate the service.</span></span> <span data-ttu-id="1f483-472">此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。</span><span class="sxs-lookup"><span data-stu-id="1f483-472">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="1f483-473">如果此属性用于发送端口，请指定 X.509 证书的指纹，用于验证此发送端口将消息发送到的服务。</span><span class="sxs-lookup"><span data-stu-id="1f483-473">If this property is used for send ports, specify the thumbprint of the X.509 certificate for authenticating the service to which this send port sends messages.</span></span> <span data-ttu-id="1f483-474">此属性使用的证书必须安装到 **其他人** 将存储在 **本地计算机** 位置。</span><span class="sxs-lookup"><span data-stu-id="1f483-474">The certificate to be used for this property must be installed into the **Other People** store in the **Local Machine** location.</span></span>

<span data-ttu-id="1f483-475">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-475">Type: String</span></span>  
<span data-ttu-id="1f483-476">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-476">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-477">适用范围：</span><span class="sxs-lookup"><span data-stu-id="1f483-477">Applies to:</span></span> 
- <span data-ttu-id="1f483-478">WCF BasicHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-478">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="1f483-479">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-479">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="1f483-480">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-480">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="1f483-481">WCF-NetTcp 接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-481">WCF-NetTcp receive adapter</span></span>

#### <a name="suspendmessageonfailure"></a><span data-ttu-id="1f483-482">SuspendMessageOnFailure</span><span class="sxs-lookup"><span data-stu-id="1f483-482">SuspendMessageOnFailure</span></span>
<span data-ttu-id="1f483-483">指定是否擱置因接收管線失敗或路由失敗而造成輸入處理失敗的要求訊息。</span><span class="sxs-lookup"><span data-stu-id="1f483-483">Specify whether to suspend the request message that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span>

<span data-ttu-id="1f483-484">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-484">Type: Boolean</span></span>  
<span data-ttu-id="1f483-485">默认值：True</span><span class="sxs-lookup"><span data-stu-id="1f483-485">Default value: True</span></span>  
<span data-ttu-id="1f483-486">适用于： 所有 WCF 都接收适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-486">Applies to: All WCF receive adapters</span></span>  

#### <a name="textencoding"></a><span data-ttu-id="1f483-487">TextEncoding</span><span class="sxs-lookup"><span data-stu-id="1f483-487">TextEncoding</span></span>
<span data-ttu-id="1f483-488">指定的字符集编码要用于在绑定上发出消息时 **MessageEncoding** 属性设置为 **文本**。</span><span class="sxs-lookup"><span data-stu-id="1f483-488">Specify the character set encoding to be used for emitting messages on the binding when the **MessageEncoding** property is set to **Text**.</span></span> 

<span data-ttu-id="1f483-489">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-489">**Note**</span></span>  
<span data-ttu-id="1f483-490">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-490">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="1f483-491">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-491">Type: String</span></span>  
<span data-ttu-id="1f483-492">默认值： utf-8</span><span class="sxs-lookup"><span data-stu-id="1f483-492">Default value: utf-8</span></span>  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

<span data-ttu-id="1f483-493">适用于： WCF BasicHttp 适配器，WCF WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-493">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>
  
#### <a name="timetolive"></a><span data-ttu-id="1f483-494">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="1f483-494">TimeToLive</span></span>
<span data-ttu-id="1f483-495">指定一个时间范围，在此范围内消息有效，一旦超出此范围，消息将到期并被置于死信队列。</span><span class="sxs-lookup"><span data-stu-id="1f483-495">Specify a time span for how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="1f483-496">设置此属性是为了确保时间敏感消息在被发送端口处理前不会变得陈旧。</span><span class="sxs-lookup"><span data-stu-id="1f483-496">This property is set to ensure that time-sensitive messages do not become stale before they are processed by a send port.</span></span> <span data-ttu-id="1f483-497">队列中在指定的时间间隔内未由此发送端口使用的消息将被认为到期。</span><span class="sxs-lookup"><span data-stu-id="1f483-497">A message in a queue that is not consumed by this send port within the time interval specified is said to be expired.</span></span> <span data-ttu-id="1f483-498">到期的消息将发送到称为死信队列的特殊队列。</span><span class="sxs-lookup"><span data-stu-id="1f483-498">Expired messages are sent to special queue called the dead-letter queue.</span></span> <span data-ttu-id="1f483-499">死信队列的位置设置 **DeadLetterQueue** 属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-499">The location of the dead-letter queue is set with the **DeadLetterQueue** property.</span></span>

<span data-ttu-id="1f483-500">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-500">Type: String</span></span>  
<span data-ttu-id="1f483-501">默认值︰ 1.00:00:00</span><span class="sxs-lookup"><span data-stu-id="1f483-501">Default value: 1.00:00:00</span></span>  
<span data-ttu-id="1f483-502">适用于： WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-502">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="to"></a><span data-ttu-id="1f483-503">若要</span><span class="sxs-lookup"><span data-stu-id="1f483-503">To</span></span>
<span data-ttu-id="1f483-504">为 WCF 发送端口发送的传出 WCF 消息指定目标终结点地址。</span><span class="sxs-lookup"><span data-stu-id="1f483-504">Specify the destination endpoint address for outgoing WCF messages that the WCF send ports send.</span></span>

<span data-ttu-id="1f483-505">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-505">Type: String</span></span>  
<span data-ttu-id="1f483-506">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-506">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-507">适用于： 所有 WCF 都发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-507">Applies to: All WCF send adapters</span></span>  

#### <a name="transactionprotocol"></a><span data-ttu-id="1f483-508">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="1f483-508">TransactionProtocol</span></span>
<span data-ttu-id="1f483-509">指定要与此绑定一起使用的事务协议。</span><span class="sxs-lookup"><span data-stu-id="1f483-509">Specify the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="1f483-510">此属性是必需的如果 **EnableTransaction** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="1f483-510">This property is required if the **EnableTransaction** property is set to **True**.</span></span>

<span data-ttu-id="1f483-511">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-511">Type: String</span></span>  
<span data-ttu-id="1f483-512">默认值： OleTransaction</span><span class="sxs-lookup"><span data-stu-id="1f483-512">Default value: OleTransaction</span></span>  

    Applicable values are: OleTransaction, WS-AtomicTransaction

<span data-ttu-id="1f483-513">适用于： WCF NetNamedPipe 适配器，WCF NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-513">Applies to: WCF-NetNamedPipe adapter,  WCF-NetTcp adapter</span></span>  

#### <a name="transportclientcredentialtype"></a><span data-ttu-id="1f483-514">TransportClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="1f483-514">TransportClientCredentialType</span></span>
<span data-ttu-id="1f483-515">指定执行发送端口验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="1f483-515">Specify the type of credential to be used when performing the send port authentication.</span></span> <span data-ttu-id="1f483-516">适用值因每个 WCF 适配器的不同而异。</span><span class="sxs-lookup"><span data-stu-id="1f483-516">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="1f483-517">有关详细信息**TransportClientCredentialType**属性，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1f483-517">For more information about the **TransportClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="1f483-518">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-518">Type: String</span></span>  
<span data-ttu-id="1f483-519">适用于： WCF Basic 适配器，WCF NetTcp 适配器，WCF WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-519">Applies to: WCF-Basic adapter, WCF-NetTcp adapter, WCF-WSHttp adapter</span></span>  

#### <a name="transportprotectionlevel"></a><span data-ttu-id="1f483-520">TransportProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="1f483-520">TransportProtectionLevel</span></span>
<span data-ttu-id="1f483-521">指定 TCP 传输级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="1f483-521">Specify security at the level of the TCP transport.</span></span> <span data-ttu-id="1f483-522">消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="1f483-522">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="1f483-523">加密为传输过程提供了数据级保密功能。</span><span class="sxs-lookup"><span data-stu-id="1f483-523">Encryption provides data-level privacy during transport.</span></span>

<span data-ttu-id="1f483-524">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-524">Type: String</span></span>  
<span data-ttu-id="1f483-525">默认值︰ **EncryptAndSign**</span><span class="sxs-lookup"><span data-stu-id="1f483-525">Default value: **EncryptAndSign**</span></span>  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

<span data-ttu-id="1f483-526">适用于： WCF NetTcp 适配器，WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-526">Applies to: WCF-NetTcp adapter, WCF-NetNamedPipe adapter</span></span>  

#### <a name="username"></a><span data-ttu-id="1f483-527">UserName</span><span class="sxs-lookup"><span data-stu-id="1f483-527">UserName</span></span>
<span data-ttu-id="1f483-528">指定要用于目标服务器的身份验证的用户名称时 **UseSSO** 属性设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="1f483-528">Specify the user name to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span> <span data-ttu-id="1f483-529">不必采用“域\用户”格式设置此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-529">You do not have to use the domain\user format for this property.</span></span>

<span data-ttu-id="1f483-530">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-530">Type: String</span></span>  
<span data-ttu-id="1f483-531">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-531">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-532">适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-532">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="usesourcejournal"></a><span data-ttu-id="1f483-533">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="1f483-533">UseSourceJournal</span></span>
<span data-ttu-id="1f483-534">指定是否应将此发送端口所处理的消息副本存储到源日记队列中。</span><span class="sxs-lookup"><span data-stu-id="1f483-534">Specify whether copies of messages processed by this send port should be stored in the source journal queue.</span></span>

<span data-ttu-id="1f483-535">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-535">Type: Boolean</span></span>  
<span data-ttu-id="1f483-536">默认值：False</span><span class="sxs-lookup"><span data-stu-id="1f483-536">Default value: False</span></span>  
<span data-ttu-id="1f483-537">适用于： WCF NetMsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-537">Applies to: WCF-NetMsmq send adapter</span></span>  

#### <a name="usesso"></a><span data-ttu-id="1f483-538">UseSSO</span><span class="sxs-lookup"><span data-stu-id="1f483-538">UseSSO</span></span>
<span data-ttu-id="1f483-539">指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。</span><span class="sxs-lookup"><span data-stu-id="1f483-539">Specify whether to use Single Sign-On to retrieve client credentials for authentication with the destination server.</span></span> 

<span data-ttu-id="1f483-540">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-540">**Note**</span></span>  
<span data-ttu-id="1f483-541">在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-541">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="1f483-542">类型︰ Boolean</span><span class="sxs-lookup"><span data-stu-id="1f483-542">Type: Boolean</span></span>  
<span data-ttu-id="1f483-543">默认值：False</span><span class="sxs-lookup"><span data-stu-id="1f483-543">Default value: False</span></span>  
<span data-ttu-id="1f483-544">适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-544">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="referencedbindings"></a><span data-ttu-id="1f483-545">ReferencedBindings</span><span class="sxs-lookup"><span data-stu-id="1f483-545">ReferencedBindings</span></span>
<span data-ttu-id="1f483-546">指定引用的绑定配置**bindingConfiguration**属性**\<颁发者\>**元素**wsFederationHttpBinding**和**customBinding**，表示安全令牌服务 (STS) 颁发安全令牌。</span><span class="sxs-lookup"><span data-stu-id="1f483-546">Specify the binding configurations referenced by the **bindingConfiguration** attribute of the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding**, which indicates the Security Token Service (STS) that issues security tokens.</span></span> <span data-ttu-id="1f483-547">有关详细信息**\<颁发者\>**元素，请参阅主题中，"\<颁发者\>"在[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)。</span><span class="sxs-lookup"><span data-stu-id="1f483-547">For more information about the **\<issuer\>** element, see the topic, "\<issuer\>" at [http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476).</span></span>

<span data-ttu-id="1f483-548">绑定信息包括**\<颁发者\>**元素**wsFederationHttpBinding**和**customBinding**可以是通过配置**BindingConfiguration**的 WCF 自定义和 WCF CustomIsolated 适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-548">The binding information including the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding** can be configured through the **BindingConfiguration** property of the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="1f483-549">此属性的引用的绑定配置的所有必须置于窗体的[\<绑定\>](http://go.microsoft.com/fwlink/?LinkID=80878)元素。</span><span class="sxs-lookup"><span data-stu-id="1f483-549">All of the referenced binding configurations for this property must be placed in the form of the [\<bindings\>](http://go.microsoft.com/fwlink/?LinkID=80878) element.</span></span> 

<span data-ttu-id="1f483-550">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-550">**Note**</span></span>  
<span data-ttu-id="1f483-551">**BindingConfiguration**属性**\<颁发者\>**元素必须引用此属性中的一个有效的绑定名称。</span><span class="sxs-lookup"><span data-stu-id="1f483-551">The **bindingConfiguration** attribute of the **\<issuer\>** element must refer to a valid binding name in this property.</span></span> 

<span data-ttu-id="1f483-552">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-552">**Note**</span></span>  
<span data-ttu-id="1f483-553">**\<颁发者\>**如果此引用链不会进行一个循环依赖关系中的引用的绑定配置元素还可以引用到此属性中的不同绑定配置。</span><span class="sxs-lookup"><span data-stu-id="1f483-553">The **\<issuer\>** element in the referenced binding configurations can also refer to a different binding configuration in this property if this reference chain does not make a circular dependency.</span></span> 

<span data-ttu-id="1f483-554">例如：</span><span class="sxs-lookup"><span data-stu-id="1f483-554">Example:</span></span> 

```
WCF.BindingConfiguration = @"<wsFederationHttpBinding>
<binding name=""sampleBinding"">
<security mode=""Message"">
<message issuedKeyType=""AsymmetricKey"">
<issuer address=""http://www.contoso.com/samplests"" binding=""wsFederationHttpBinding"" bindingConfiguration=""**contosoSTSBinding**""/>
</message>
</security>
</binding>
</wsFederationHttpBinding>";
WCF.ReferencedBinding =@"<bindings>
<wsFederationHttpBinding>
<binding name=""**contosoSTSBinding**"">
<security mode=""Message"">
<message negotiateServiceCredential=""false"">
<issuer address=""http://northwind.com/samplests"" bindingConfiguration=""**northwindBinding**"" binding=""wsHttpBinding"">
</issuer>
</message>
</security>
</binding>
</wsFederationHttpBinding>
<wsHttpBinding>
<binding name=""**northwindBinding**"">
<security mode=""Message"">
<message clientCredentialType=""Certificate""/>
</security>
</binding>
</wsHttpBinding>
</bindings>" 
``` 

<span data-ttu-id="1f483-555">**请注意**</span><span class="sxs-lookup"><span data-stu-id="1f483-555">**Note**</span></span>  
<span data-ttu-id="1f483-556">**ReferencedBinding**属性不能包含中使用的绑定配置**BindingConfiguration**属性。</span><span class="sxs-lookup"><span data-stu-id="1f483-556">**ReferencedBinding** property must not contain the binding configuration used in the **BindingConfiguration** property.</span></span>

<span data-ttu-id="1f483-557">類型：字串</span><span class="sxs-lookup"><span data-stu-id="1f483-557">Type: String</span></span>  
<span data-ttu-id="1f483-558">默认值： 空字符串</span><span class="sxs-lookup"><span data-stu-id="1f483-558">Default value: An empty string</span></span>  
<span data-ttu-id="1f483-559">适用于： WCF 自定义适配器，WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="1f483-559">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f483-560">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f483-560">See Also</span></span>  
 <span data-ttu-id="1f483-561">[WCF 适配器](../core/wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="1f483-561">[WCF Adapters](../core/wcf-adapters.md) </span></span>  
 <span data-ttu-id="1f483-562">[\<行为\>的\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span><span class="sxs-lookup"><span data-stu-id="1f483-562">[\<behavior\> of \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span></span>  
 <span data-ttu-id="1f483-563">[\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span><span class="sxs-lookup"><span data-stu-id="1f483-563">[\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span></span>  
 <span data-ttu-id="1f483-564">[\<behavior\> of \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span><span class="sxs-lookup"><span data-stu-id="1f483-564">[\<behavior\> of \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span></span>  
 <span data-ttu-id="1f483-565">[有序的消息传送](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="1f483-565">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="1f483-566">负载平衡</span><span class="sxs-lookup"><span data-stu-id="1f483-566">Load Balancing</span></span>](http://go.microsoft.com/fwlink/?LinkId=81089)
