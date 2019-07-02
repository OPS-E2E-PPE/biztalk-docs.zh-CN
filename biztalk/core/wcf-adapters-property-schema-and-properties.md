---
title: WCF 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10781e8743eeea68ff0be8993b3588d5ecd204d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399145"
---
# <a name="wcf-adapters-property-schema-and-properties"></a><span data-ttu-id="625ff-102">WCF 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="625ff-102">WCF Adapters Property Schema and Properties</span></span>
<span data-ttu-id="625ff-103">阅读有关 WCF 适配器属性架构中升级的属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-103">Read about the promoted properties in the WCF adapter property schema.</span></span> <span data-ttu-id="625ff-104">WCF 适配器将值分配给可以在应用程序中使用的属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-104">The WCF adapters assign values to the properties that you can use in your application.</span></span> <span data-ttu-id="625ff-105">WCF 适配器还提供了一种机制来编写，而不是升级到 BizTalk 消息上下文中，自定义属性和升级到 BizTalk 消息上下文的自定义属性的机制。</span><span class="sxs-lookup"><span data-stu-id="625ff-105">WCF adapter also provides a mechanism to write but not promote the custom properties to the BizTalk message context, and a mechanism to promote the custom properties to the BizTalk message context.</span></span> <span data-ttu-id="625ff-106">有关更多详细信息，请参阅[SOAP 标头发布 WCF 服务与](../core/soap-headers-with-published-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-106">For more details, see [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md).</span></span>  

## <a name="promoted-properties"></a><span data-ttu-id="625ff-107">升级的属性</span><span class="sxs-lookup"><span data-stu-id="625ff-107">Promoted properties</span></span>  
<span data-ttu-id="625ff-108">**Namespace**： http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span><span class="sxs-lookup"><span data-stu-id="625ff-108">**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span></span>  

#### <a name="action"></a><span data-ttu-id="625ff-109">操作</span><span class="sxs-lookup"><span data-stu-id="625ff-109">Action</span></span>
<span data-ttu-id="625ff-110">指定**SOAPAction**为传出消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="625ff-110">Specify the **SOAPAction** header field for outgoing messages.</span></span> <span data-ttu-id="625ff-111">可以通过两种方式指定此值： 单一操作格式和操作映射格式。</span><span class="sxs-lookup"><span data-stu-id="625ff-111">You can specify this value in two different ways: the single action format and the action mapping format.</span></span> <span data-ttu-id="625ff-112">如果将此属性设置在单一操作格式 — 例如， http://contoso.com/Svc/Op1 — **SOAPAction**标头传出消息将始终设置为此属性中指定的值。</span><span class="sxs-lookup"><span data-stu-id="625ff-112">If you set this property in the single action format—for example, http://contoso.com/Svc/Op1 — the **SOAPAction** header for outgoing messages is always set to the value specified in this property.</span></span>

<span data-ttu-id="625ff-113">如果将此属性设置采用操作映射格式，传出**SOAPAction**标头由**BTS。操作**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-113">If you set this property in the action mapping format, the outgoing **SOAPAction** header is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="625ff-114">例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器使用 `http://contoso.com/Svc/Op1` 为传出**SOAPAction**标头。</span><span class="sxs-lookup"><span data-stu-id="625ff-114">For example, if this property is set to the following XML format and the **BTS.Operation** property is set to Op1, the WCF send adapter uses `http://contoso.com/Svc/Op1` for the outgoing **SOAPAction** header.</span></span>

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

<span data-ttu-id="625ff-115">如果传出消息来自某个业务流程端口，业务流程实例动态设置**BTS。操作**使用的端口的操作名称的属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-115">If outgoing messages come from an orchestration port, orchestration instances dynamically set the **BTS.Operation** property with the operation name of the port.</span></span> <span data-ttu-id="625ff-116">如果使用基于内容的路由来路由传出消息，则可以设置**BTS。操作**管道组件中的属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-116">If outgoing messages are routed with content-based routing, you can set the **BTS.Operation** property in pipeline components.</span></span>
<span data-ttu-id="625ff-117">从传入消息以单一操作格式自动升级此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-117">This property is automatically promoted from incoming messages with the single action format.</span></span>

<span data-ttu-id="625ff-118">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-118">Type: String</span></span>  
<span data-ttu-id="625ff-119">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-119">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-120">适用范围：所有 WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-120">Applies to: All WCF send adapters</span></span>

#### <a name="affiliateapplicationname"></a><span data-ttu-id="625ff-121">AffiliateApplicationName</span><span class="sxs-lookup"><span data-stu-id="625ff-121">AffiliateApplicationName</span></span>
<span data-ttu-id="625ff-122">指定要使用的企业单一登录 (SSO) 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="625ff-122">Specify the affiliate application to use for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="625ff-123">此属性是必需的如果**UseSSO**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="625ff-123">This property is required if the **UseSSO** property is set to **True**.</span></span> 

<span data-ttu-id="625ff-124">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-124">Type: String</span></span>  
<span data-ttu-id="625ff-125">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-125">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-126">适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-126">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="algorithmsuite"></a><span data-ttu-id="625ff-127">AlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="625ff-127">AlgorithmSuite</span></span>
<span data-ttu-id="625ff-128">指定消息加密和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="625ff-128">Specify the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="625ff-129">这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。</span><span class="sxs-lookup"><span data-stu-id="625ff-129">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>

<span data-ttu-id="625ff-130">有关适合的值的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-nettcp 传输属性对话框，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="625ff-130">For more information about the applicable values for the **AlgorithmSuite** property, see the **Algorithm suite** property in the **WCF-NetTcp Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="625ff-131">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-131">Type: String</span></span>  
<span data-ttu-id="625ff-132">默认值：**Basic256**</span><span class="sxs-lookup"><span data-stu-id="625ff-132">Default value: **Basic256**</span></span>  
<span data-ttu-id="625ff-133">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-133">Applies to:</span></span> 

- <span data-ttu-id="625ff-134">Wcf-basichttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-134">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="625ff-135">Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-135">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="625ff-136">Wcf-nettcp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-136">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="625ff-137">Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-137">WCF-WSHttp adapter</span></span>

#### <a name="bindingconfiguration"></a><span data-ttu-id="625ff-138">BindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="625ff-138">BindingConfiguration</span></span>
<span data-ttu-id="625ff-139">指定 XML 字符串与 **\<绑定\>** 元素来配置不同类型的预定义的 Windows Communication Foundation (WCF) 提供的绑定。</span><span class="sxs-lookup"><span data-stu-id="625ff-139">Specify an XML string with the **\<binding\>** element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="625ff-140">有关系统提供的绑定和自定义绑定的详细信息，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="625ff-140">For more information about the system-provided binding and custom binding, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="625ff-141">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-141">Example:</span></span>

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

<span data-ttu-id="625ff-142">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-142">Type: String</span></span>  
<span data-ttu-id="625ff-143">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-143">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-144">适用范围：Wcf-custom 适配器，Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-144">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="bindingtype"></a><span data-ttu-id="625ff-145">BindingType</span><span class="sxs-lookup"><span data-stu-id="625ff-145">BindingType</span></span>
<span data-ttu-id="625ff-146">指定要用于终结点的绑定的类型。</span><span class="sxs-lookup"><span data-stu-id="625ff-146">Specify the type of the binding to use for the endpoint.</span></span> <span data-ttu-id="625ff-147">有关适合的值的详细信息**BindingType**属性，请参阅**绑定类型**中的属性**Wcf-custom 传输属性对话框，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="625ff-147">For more information about the applicable values for the **BindingType** property, see the **Binding Type** property in the **WCF-Custom Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="625ff-148">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-148">Type: String</span></span>  
<span data-ttu-id="625ff-149">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-149">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-150">适用范围：Wcf-custom 适配器，Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-150">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="clientcertificate"></a><span data-ttu-id="625ff-151">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="625ff-151">ClientCertificate</span></span>
<span data-ttu-id="625ff-152">指定此发送端口对服务进行身份验证的 X.509 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="625ff-152">Specify the thumbprint of the X.509 certificate for authenticating this send port to services.</span></span> <span data-ttu-id="625ff-153">此属性是必需的如果**ClientCredentialsType**属性设置为**证书**。</span><span class="sxs-lookup"><span data-stu-id="625ff-153">This property is required if the **ClientCredentialsType** property is set to **Certificate**.</span></span> <span data-ttu-id="625ff-154">要用于此属性的证书必须安装到**我**将存储在**当前用户**位置。</span><span class="sxs-lookup"><span data-stu-id="625ff-154">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="625ff-155">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-155">Type: String</span></span>  
<span data-ttu-id="625ff-156">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-156">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-157">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-157">Applies to:</span></span> 

- <span data-ttu-id="625ff-158">Wcf-basichttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-158">WCF-BasicHttp send adapter</span></span>
- <span data-ttu-id="625ff-159">Wcf-wshttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-159">WCF-WSHttp send adapter</span></span>
- <span data-ttu-id="625ff-160">Wcf-nettcp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-160">WCF-NetTcp send adapter</span></span>
- <span data-ttu-id="625ff-161">Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-161">WCF-NetMsmq send adapter</span></span>

#### <a name="closetimeout"></a><span data-ttu-id="625ff-162">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="625ff-162">CloseTimeout</span></span>
<span data-ttu-id="625ff-163">指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="625ff-163">Specify a time span value that indicates the interval of time provided for a channel close operation to complete.</span></span>

<span data-ttu-id="625ff-164">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-164">Type: String</span></span>  
<span data-ttu-id="625ff-165">默认值：00:01:00</span><span class="sxs-lookup"><span data-stu-id="625ff-165">Default value: 00:01:00</span></span>  
<span data-ttu-id="625ff-166">适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated</span><span class="sxs-lookup"><span data-stu-id="625ff-166">Applies to: All WCF adapters *except* WCF-Custom and WCF-CustomIsolated</span></span>

#### <a name="customdeadletterqueue"></a><span data-ttu-id="625ff-167">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="625ff-167">CustomDeadLetterQueue</span></span>
<span data-ttu-id="625ff-168">指定使用的完全限定的 URI **net.msmq**方案的每个应用程序的死信队列，消息已过期或失败传输或传递的放置位置的位置。</span><span class="sxs-lookup"><span data-stu-id="625ff-168">Specify the fully qualified URI with the **net.msmq** scheme for the location of the per-application dead-letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span> <span data-ttu-id="625ff-169">例如，net.msmq: //localhost/deadletterqueuename。</span><span class="sxs-lookup"><span data-stu-id="625ff-169">For example, net.msmq://localhost/deadLetterQueueName.</span></span> <span data-ttu-id="625ff-170">死信队列是发送应用程序的已用于放置传递失败的过期消息的队列管理器上的队列。</span><span class="sxs-lookup"><span data-stu-id="625ff-170">The dead-letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span> <span data-ttu-id="625ff-171">此属性是必需的如果**DeadLetterQueue**属性设置为**自定义**。</span><span class="sxs-lookup"><span data-stu-id="625ff-171">This property is required if the **DeadLetterQueue** property is set to **Custom**.</span></span>

<span data-ttu-id="625ff-172">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-172">Type: String</span></span>  
<span data-ttu-id="625ff-173">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-173">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-174">适用范围：Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-174">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="deadletterqueue"></a><span data-ttu-id="625ff-175">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="625ff-175">DeadLetterQueue</span></span>
<span data-ttu-id="625ff-176">指定要从中传输失败传递到应用程序的消息的死信队列。</span><span class="sxs-lookup"><span data-stu-id="625ff-176">Specify the dead-letter queue where messages that have failed to be delivered to the application will be transferred.</span></span> <span data-ttu-id="625ff-177">有关传递到死信队列的消息的详细信息，请参阅**Wcf-netmsmq 传输属性对话框，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="625ff-177">For more information about the messages delivered to the dead-letter queue, see the **WCF-NetMsmq Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="625ff-178">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-178">Type: String</span></span>  
<span data-ttu-id="625ff-179">默认值：**系统**</span><span class="sxs-lookup"><span data-stu-id="625ff-179">Default value: **System**</span></span>  
<span data-ttu-id="625ff-180">适用范围：Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-180">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="disablelocationonfailure"></a><span data-ttu-id="625ff-181">DisableLocationOnFailure</span><span class="sxs-lookup"><span data-stu-id="625ff-181">DisableLocationOnFailure</span></span>
<span data-ttu-id="625ff-182">指定是否禁用由于接收管道故障或路由故障而导致入站处理失败的接收位置。</span><span class="sxs-lookup"><span data-stu-id="625ff-182">Specify whether to disable the receive location that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span> <span data-ttu-id="625ff-183">你可能想要将此属性设置为 **，则返回 True**时接收位置可以禁用和拒绝服务 (DoS) 并不是问题。</span><span class="sxs-lookup"><span data-stu-id="625ff-183">You may want to set this property to **True** when receive locations can be disabled and Denial-of-Service (DoS) is not a concern.</span></span>

<span data-ttu-id="625ff-184">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-184">For example:</span></span>  
- <span data-ttu-id="625ff-185">Wcf-custom 适配器：当**BindingType**属性设置为**netMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="625ff-185">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**.</span></span>
- <span data-ttu-id="625ff-186">Wcf-custom 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于队列传输的自定义通道如 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="625ff-186">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ.</span></span>
- <span data-ttu-id="625ff-187">Wcf-customisolated 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于队列传输的自定义通道如 MSMQ</span><span class="sxs-lookup"><span data-stu-id="625ff-187">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ</span></span>
- <span data-ttu-id="625ff-188">Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-188">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="625ff-189">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-189">Type: Boolean</span></span>  
<span data-ttu-id="625ff-190">默认值：**False**</span><span class="sxs-lookup"><span data-stu-id="625ff-190">Default: **False**</span></span>  
<span data-ttu-id="625ff-191">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-191">Applies to:</span></span>  
- <span data-ttu-id="625ff-192">Wcf-netmsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-192">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="625ff-193">WCF 自定义接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-193">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="625ff-194">Wcf-customisolated 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-194">WCF-CustomIsolated receive adapter</span></span>

#### <a name="enabletransaction"></a><span data-ttu-id="625ff-195">EnableTransaction</span><span class="sxs-lookup"><span data-stu-id="625ff-195">EnableTransaction</span></span>
<span data-ttu-id="625ff-196">此属性的效果各不相同，具体取决于 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="625ff-196">The effect of this property varies depending on the WCF adapter.</span></span> <span data-ttu-id="625ff-197">有关此属性的详细信息，请参阅中每个 WCF 适配器的操作指南主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-197">For more information about this property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="625ff-198">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-198">Type: Boolean</span></span>  
<span data-ttu-id="625ff-199">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-199">Applies to:</span></span> 

- <span data-ttu-id="625ff-200">Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-200">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="625ff-201">Wcf-nettcp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-201">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="625ff-202">Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-202">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="625ff-203">Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-203">WCF-NetMsmq adapter</span></span>

#### <a name="endpointbehaviorconfiguration"></a><span data-ttu-id="625ff-204">EndpointBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="625ff-204">EndpointBehaviorConfiguration</span></span>
<span data-ttu-id="625ff-205">指定 XML 字符串与 **\<行为\>** 元素 **\<endpointBehaviors\>** 元素来配置的行为设置WCF 终结点。</span><span class="sxs-lookup"><span data-stu-id="625ff-205">Specify an XML string with the **\<behavior\>** element of the **\<endpointBehaviors\>** element to configure the behavior settings of a WCF endpoint.</span></span> <span data-ttu-id="625ff-206">有关详细信息 **\<endpointBehaviors\>** 元素，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="625ff-206">For more information about the **\<endpointBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="625ff-207">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-207">Example:</span></span> 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

<span data-ttu-id="625ff-208">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-208">Type: String</span></span>  
<span data-ttu-id="625ff-209">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-209">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-210">适用范围：WCF 自定义发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-210">Applies to: WCF-Custom send adapter</span></span>

#### <a name="establishsecuritycontext"></a><span data-ttu-id="625ff-211">EstablishSecurityContext</span><span class="sxs-lookup"><span data-stu-id="625ff-211">EstablishSecurityContext</span></span>
<span data-ttu-id="625ff-212">指定安全通道是否建立安全会话。</span><span class="sxs-lookup"><span data-stu-id="625ff-212">Specify whether the security channel establishes a secure session.</span></span> <span data-ttu-id="625ff-213">安全会话在交换应用程序消息之前建立安全上下文令牌 (SCT)。</span><span class="sxs-lookup"><span data-stu-id="625ff-213">A secure session establishes a Security Context Token (SCT) before exchanging the application messages.</span></span>

<span data-ttu-id="625ff-214">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-214">Type: Boolean</span></span>  
<span data-ttu-id="625ff-215">默认值：True</span><span class="sxs-lookup"><span data-stu-id="625ff-215">Default value: True</span></span>  
<span data-ttu-id="625ff-216">应用于：Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-216">Applied to: WCF-WSHttp adapter</span></span>

#### <a name="fromaddress"></a><span data-ttu-id="625ff-217">FromAddress</span><span class="sxs-lookup"><span data-stu-id="625ff-217">FromAddress</span></span>
<span data-ttu-id="625ff-218">指示通过其发送传入 WCF 消息的源终结点地址。</span><span class="sxs-lookup"><span data-stu-id="625ff-218">Indicate the source endpoint address through which the incoming WCF messages are sent.</span></span> <span data-ttu-id="625ff-219">从传入消息，则会自动升级该属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-219">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="625ff-220">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-220">Type: String</span></span>  
<span data-ttu-id="625ff-221">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-221">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>
  
#### <a name="headers"></a><span data-ttu-id="625ff-222">标头</span><span class="sxs-lookup"><span data-stu-id="625ff-222">Headers</span></span>
<span data-ttu-id="625ff-223">指定用于提供除 URI 外的其他寻址信息的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="625ff-223">Specify the endpoint references used to provide additional addressing information beyond the URI.</span></span> <span data-ttu-id="625ff-224">使用此属性时，此属性必须具有\<**标头**\>元素作为根元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-224">When this property is used, this property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="625ff-225">所有地址标头必须位于内部\<**标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-225">All of the address headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="625ff-226">此属性将自动提升为传入消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-226">This property is automatically promoted for incoming messages.</span></span>

<span data-ttu-id="625ff-227">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-227">Example:</span></span>
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

<span data-ttu-id="625ff-228">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-228">Type: String</span></span>  
<span data-ttu-id="625ff-229">适用范围：所有 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-229">Applies to: All WCF adapters</span></span>
  
#### <a name="identity"></a><span data-ttu-id="625ff-230">标识</span><span class="sxs-lookup"><span data-stu-id="625ff-230">Identity</span></span>
<span data-ttu-id="625ff-231">指定接收位置提供或发送端口预期的服务标识。</span><span class="sxs-lookup"><span data-stu-id="625ff-231">Specify the identity of the service that a receive location provides or a send port expects.</span></span> <span data-ttu-id="625ff-232">可以为指定的值**标识**属性不同的安全配置而异。</span><span class="sxs-lookup"><span data-stu-id="625ff-232">The values that can be specified for the **Identity** property differ according to the security configuration.</span></span> <span data-ttu-id="625ff-233">这些设置使客户端进行身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="625ff-233">These settings enable clients to authenticate services.</span></span> <span data-ttu-id="625ff-234">在客户端和服务之间的握手过程中，Windows Communication Foundation (WCF) 基础结构将确保服务的标识匹配的客户端的值。</span><span class="sxs-lookup"><span data-stu-id="625ff-234">In the handshake process between clients and services, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the services matches the values of the clients.</span></span>

<span data-ttu-id="625ff-235">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-235">Example:</span></span>
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

<span data-ttu-id="625ff-236">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-236">Type: String</span></span>  
<span data-ttu-id="625ff-237">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-237">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-238">适用范围：所有 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-238">Applies to: All WCF adapters</span></span>

#### <a name="inboundbodylocation"></a><span data-ttu-id="625ff-239">InboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="625ff-239">InboundBodyLocation</span></span>
<span data-ttu-id="625ff-240">指定数据选择 soap**正文**传入 WCF 消息的元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-240">Specify the data selection for the SOAP **Body** element of incoming WCF messages.</span></span> <span data-ttu-id="625ff-241">有关如何使用详细信息**InboundBodyLocation**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-241">For more information about how to use the **InboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="625ff-242">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-242">Type: String</span></span>  
<span data-ttu-id="625ff-243">默认值：UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="625ff-243">Default value: UseBodyElement</span></span>  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

<span data-ttu-id="625ff-244">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送</span><span class="sxs-lookup"><span data-stu-id="625ff-244">Applies to: All WCF adapters *except* WCF-NetMsmq send</span></span>  

#### <a name="inboundbodypathexpression"></a><span data-ttu-id="625ff-245">InboundBodyPathExpression</span><span class="sxs-lookup"><span data-stu-id="625ff-245">InboundBodyPathExpression</span></span>
<span data-ttu-id="625ff-246">指定正文路径表达式以标识用于创建 BizTalk 消息正文部分的传入消息的特定部分。</span><span class="sxs-lookup"><span data-stu-id="625ff-246">Specify the body path expression to identify a specific part of an incoming message used to create the BizTalk message body part.</span></span> <span data-ttu-id="625ff-247">针对 SOAP 的直接子元素计算此正文路径表达式**正文**传入消息的节点。</span><span class="sxs-lookup"><span data-stu-id="625ff-247">This body path expression is evaluated against the immediate child element of the SOAP **Body** node of an incoming message.</span></span> <span data-ttu-id="625ff-248">如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="625ff-248">If this body path expression returns more than one node, only the first node is chosen for the BizTalk message body part.</span></span> <span data-ttu-id="625ff-249">此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。</span><span class="sxs-lookup"><span data-stu-id="625ff-249">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span> <span data-ttu-id="625ff-250">有关如何使用详细信息**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-250">For more information about how to use the **InboundBodyPathExpression** property, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>

<span data-ttu-id="625ff-251">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-251">Type: String</span></span>  
<span data-ttu-id="625ff-252">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-252">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-253">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-253">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundheaders"></a><span data-ttu-id="625ff-254">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="625ff-254">InboundHeaders</span></span>
<span data-ttu-id="625ff-255">使用**InboundHeaders**属性访问传入 WCF 消息的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="625ff-255">Use the **InboundHeaders** property to access the SOAP headers of incoming WCF messages.</span></span> <span data-ttu-id="625ff-256">WCF 适配器将复制所有 SOAP 标头值入站消息中到此属性，包括自定义 SOAP 标头和标准 SOAP 标头，WCF 基础结构用于诸如 Ws-addressing、 Ws-security 和 WS-AtomicTransaction。</span><span class="sxs-lookup"><span data-stu-id="625ff-256">The WCF adapters copy all the SOAP header values in inbound messages to this property, which include custom SOAP headers and standard SOAP headers that the WCF infrastructure uses for such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="625ff-257">上下文属性中包含的值是一个包含 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头复制为子元素的\< **标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-257">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="625ff-258">有关如何对访问 SOAP 标头用于 WCF 适配器的详细信息，请参阅 SDK 示例中，将自定义 SOAP 标头用于 WCF 适配器中，从[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="625ff-258">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="625ff-259">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-259">Type: String</span></span>  
<span data-ttu-id="625ff-260">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-260">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundnodeencoding"></a><span data-ttu-id="625ff-261">InboundNodeEncoding</span><span class="sxs-lookup"><span data-stu-id="625ff-261">InboundNodeEncoding</span></span>
<span data-ttu-id="625ff-262">指定 WCF 接收适配器将使用由中指定的正文路径表达式标识的节点进行解码的编码类型**InboundBodyPathExpression**。</span><span class="sxs-lookup"><span data-stu-id="625ff-262">Specify the type of encoding that the WCF receive adapter uses to decode the node identified by the body path expression specified in **InboundBodyPathExpression**.</span></span> <span data-ttu-id="625ff-263">此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。</span><span class="sxs-lookup"><span data-stu-id="625ff-263">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span>

<span data-ttu-id="625ff-264">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-264">Type: String</span></span>  
<span data-ttu-id="625ff-265">默认值：XML</span><span class="sxs-lookup"><span data-stu-id="625ff-265">Default value: XML</span></span>  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

<span data-ttu-id="625ff-266">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-266">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="isfault"></a><span data-ttu-id="625ff-267">IsFault</span><span class="sxs-lookup"><span data-stu-id="625ff-267">IsFault</span></span>
<span data-ttu-id="625ff-268">指示是否接收 SOAP 错误消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-268">Indicate whether SOAP fault messages are received.</span></span> <span data-ttu-id="625ff-269">从传入消息，则会自动升级该属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-269">The property is automatically promoted from incoming messages.</span></span> 

<span data-ttu-id="625ff-270">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-270">**Note**</span></span>  
<span data-ttu-id="625ff-271">**IsFault**属性不能用于检查接收的消息传输错误，例如 HTTP 404 （文件或找不到目录） 错误。</span><span class="sxs-lookup"><span data-stu-id="625ff-271">The **IsFault** property cannot be used to check the received messages for transport errors such as the HTTP 404 (File or Directory Not Found) error.</span></span>

<span data-ttu-id="625ff-272">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-272">Type: Boolean</span></span>  
<span data-ttu-id="625ff-273">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-273">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="leasetimeout"></a><span data-ttu-id="625ff-274">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="625ff-274">LeaseTimeout</span></span>
<span data-ttu-id="625ff-275">指定活动的池连接的最大生存期。</span><span class="sxs-lookup"><span data-stu-id="625ff-275">Specify the maximum lifetime of an active pooled connection.</span></span> <span data-ttu-id="625ff-276">在指定的时间过后，则关闭连接后当前请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="625ff-276">After the specified time elapses, the connection closes after the current request is serviced.</span></span>

<span data-ttu-id="625ff-277">Wcf-nettcp 适配器利用[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)类与终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="625ff-277">The WCF-NetTcp adapter leverages the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) class to communicate with an endpoint.</span></span> <span data-ttu-id="625ff-278">使用时[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)在负载平衡方案中，请考虑缩短默认租约超时值。有关负载平衡时使用的详细信息[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="625ff-278">When using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) in load-balanced scenarios, consider reducing the default lease time-out. For more information about load balancing when using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), see the appropriate topic in See Also.</span></span>

<span data-ttu-id="625ff-279">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-279">Type: String</span></span>  
<span data-ttu-id="625ff-280">默认值：00:05:00</span><span class="sxs-lookup"><span data-stu-id="625ff-280">Default value: 00:05:00</span></span>  
<span data-ttu-id="625ff-281">适用范围：Wcf-nettcp 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-281">Applies to: WCF-NetTcp receive adapter</span></span>  

#### <a name="maxconcurrentcalls"></a><span data-ttu-id="625ff-282">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="625ff-282">MaxConcurrentCalls</span></span>
<span data-ttu-id="625ff-283">指定针对单个服务实例的并发调用的数目。</span><span class="sxs-lookup"><span data-stu-id="625ff-283">Specify the number of concurrent calls to a single service instance.</span></span> <span data-ttu-id="625ff-284">超出此限制的调用将在队列中排队。</span><span class="sxs-lookup"><span data-stu-id="625ff-284">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="625ff-285">将该值设置为 0 等效于将它设置为 **Int32.MaxValue**。</span><span class="sxs-lookup"><span data-stu-id="625ff-285">Setting this value to 0 is equivalent to setting it to **Int32.MaxValue**.</span></span> 

<span data-ttu-id="625ff-286">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-286">**Note**</span></span>  
<span data-ttu-id="625ff-287">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-287">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="625ff-288">键入：Integer</span><span class="sxs-lookup"><span data-stu-id="625ff-288">Type: Integer</span></span>  
<span data-ttu-id="625ff-289">默认值：200</span><span class="sxs-lookup"><span data-stu-id="625ff-289">Default value: 200</span></span>  
<span data-ttu-id="625ff-290">适用范围：所有 WCF 都接收适配器*除*Wcf-custom 和 Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-290">Applies to: All WCF receive adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="maxconnections"></a><span data-ttu-id="625ff-291">MaxConnections</span><span class="sxs-lookup"><span data-stu-id="625ff-291">MaxConnections</span></span>
<span data-ttu-id="625ff-292">指定的最大侦听器可以拥有等待接受的应用程序的连接数。</span><span class="sxs-lookup"><span data-stu-id="625ff-292">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="625ff-293">当超过此配额值时，会删除新的传入连接而不是等待接受。</span><span class="sxs-lookup"><span data-stu-id="625ff-293">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> 

<span data-ttu-id="625ff-294">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-294">**Note**</span></span>  
<span data-ttu-id="625ff-295">由于这是一个适配器处理程序属性，则此属性不能配置管道组件和业务流程中。</span><span class="sxs-lookup"><span data-stu-id="625ff-295">Because this is an adapter handler property, this property cannot be configured in pipeline components and orchestrations.</span></span> 

<span data-ttu-id="625ff-296">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-296">**Note**</span></span>  
<span data-ttu-id="625ff-297">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-297">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="625ff-298">键入：Integer</span><span class="sxs-lookup"><span data-stu-id="625ff-298">Type: Integer</span></span>  
<span data-ttu-id="625ff-299">默认值：10</span><span class="sxs-lookup"><span data-stu-id="625ff-299">Default value: 10</span></span>  
<span data-ttu-id="625ff-300">适用范围：Wcf-netnamedpipe 适配器，Wcf-nettcp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-300">Applies to: WCF-NetNamedPipe adapter, WCF-NetTcp adapter</span></span>  

#### <a name="maxreceivedmessagesize"></a><span data-ttu-id="625ff-301">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="625ff-301">MaxReceivedMessageSize</span></span>
<span data-ttu-id="625ff-302">指定的最大大小，以字节为单位，可以在网络上接收的消息 （包括标头）。</span><span class="sxs-lookup"><span data-stu-id="625ff-302">Specify the maximum size, in bytes, for a message (including headers) that can be received on the wire.</span></span> <span data-ttu-id="625ff-303">消息的大小受为每条消息分配的内存量的限制。</span><span class="sxs-lookup"><span data-stu-id="625ff-303">The size of the messages is bounded by the amount of memory allocated for each message.</span></span> <span data-ttu-id="625ff-304">你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。</span><span class="sxs-lookup"><span data-stu-id="625ff-304">You can use this property to limit exposure to denial of service (DoS) attacks.</span></span>

<span data-ttu-id="625ff-305">键入：Integer</span><span class="sxs-lookup"><span data-stu-id="625ff-305">Type: Integer</span></span>  
<span data-ttu-id="625ff-306">默认值：65536</span><span class="sxs-lookup"><span data-stu-id="625ff-306">Default value: 65536</span></span>  
<span data-ttu-id="625ff-307">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-307">Applies to:</span></span> 
- <span data-ttu-id="625ff-308">Wcf-basichttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-308">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="625ff-309">Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-309">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="625ff-310">Wcf-nettcp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-310">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="625ff-311">Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-311">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="625ff-312">Wcf-netmsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-312">WCF-NetMsmq receive adapter</span></span>

#### <a name="messageclientcredentialtype"></a><span data-ttu-id="625ff-313">MessageClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="625ff-313">MessageClientCredentialType</span></span>
<span data-ttu-id="625ff-314">指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="625ff-314">Specify the type of credential to be used when performing client authentication using message-based security.</span></span>

<span data-ttu-id="625ff-315">每个 WCF 适配器不同的值。</span><span class="sxs-lookup"><span data-stu-id="625ff-315">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="625ff-316">有关详细信息**MessageClientCredentialType**属性，每个 WCF 适配器中，请参阅操作指南主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-316">For more information about the **MessageClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="625ff-317">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-317">Type: String</span></span>  
<span data-ttu-id="625ff-318">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-318">Applies to:</span></span> 
- <span data-ttu-id="625ff-319">Wcf-basichttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-319">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="625ff-320">Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-320">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="625ff-321">Wcf-nettcp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-321">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="625ff-322">Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-322">WCF-NetNamedPipe adapter</span></span>

#### <a name="messageencoding"></a><span data-ttu-id="625ff-323">MessageEncoding</span><span class="sxs-lookup"><span data-stu-id="625ff-323">MessageEncoding</span></span>
<span data-ttu-id="625ff-324">指定用于对 SOAP 消息进行编码的编码器。</span><span class="sxs-lookup"><span data-stu-id="625ff-324">Specify the encoder used to encode the SOAP message.</span></span>

<span data-ttu-id="625ff-325">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-325">Type: String</span></span>  
<span data-ttu-id="625ff-326">默认值：Text</span><span class="sxs-lookup"><span data-stu-id="625ff-326">Default value: Text</span></span>  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

<span data-ttu-id="625ff-327">适用范围：Wcf-basichttp 适配器，Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-327">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>


#### <a name="msmqauthenticationmode"></a><span data-ttu-id="625ff-328">MsmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="625ff-328">MsmqAuthenticationMode</span></span>
<span data-ttu-id="625ff-329">指定 MSMQ 传输必须如何验证消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-329">Specify how the message must be authenticated by the MSMQ transport.</span></span>

<span data-ttu-id="625ff-330">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-330">Type: String</span></span>  
<span data-ttu-id="625ff-331">默认值：**WindowsDomain**</span><span class="sxs-lookup"><span data-stu-id="625ff-331">Default value: **WindowsDomain**</span></span>  
    <span data-ttu-id="625ff-332">有关适合的值的详细信息**MsmqAuthenticationMode**属性，请参阅**MSMQ 身份验证模式**中的属性**Wcf-netmsmq 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="625ff-332">For more information about the applicable values for the **MsmqAuthenticationMode** property, see the **MSMQ authentication mode** property in the **WCF-NetMsmq Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
<span data-ttu-id="625ff-333">适用范围：Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-333">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqencryptionalgorithm"></a><span data-ttu-id="625ff-334">MsmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="625ff-334">MsmqEncryptionAlgorithm</span></span>
<span data-ttu-id="625ff-335">指定消息队列管理器之间传输消息时要使用在网络上进行消息加密算法。</span><span class="sxs-lookup"><span data-stu-id="625ff-335">Specify the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="625ff-336">提供了该属性才**MsmqProtectionLevel**属性设置为**EncryptAndSign**。</span><span class="sxs-lookup"><span data-stu-id="625ff-336">This property is available only if the **MsmqProtectionLevel** property is set to **EncryptAndSign**.</span></span>

<span data-ttu-id="625ff-337">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-337">Type: String</span></span>  
<span data-ttu-id="625ff-338">默认值：**RC4Stream**</span><span class="sxs-lookup"><span data-stu-id="625ff-338">Default value: **RC4Stream**</span></span>  

    Applicable values are: RC4Stream, AES

<span data-ttu-id="625ff-339">适用范围：Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-339">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqprotectionlevel"></a><span data-ttu-id="625ff-340">MsmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="625ff-340">MsmqProtectionLevel</span></span>
<span data-ttu-id="625ff-341">指定在 MSMQ 传输级别保护消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-341">Specify the way messages are secured at the level of the MSMQ transport.</span></span>

<span data-ttu-id="625ff-342">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-342">Type: String</span></span>  
<span data-ttu-id="625ff-343">默认值：**签名**</span><span class="sxs-lookup"><span data-stu-id="625ff-343">Default value: **Sign**</span></span>  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

<span data-ttu-id="625ff-344">适用范围：Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-344">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqsecurehashalgorithm"></a><span data-ttu-id="625ff-345">MsmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="625ff-345">MsmqSecureHashAlgorithm</span></span>
<span data-ttu-id="625ff-346">指定要用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="625ff-346">Specify the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="625ff-347">此属性不可用如果**MsmqProtectionLevel**属性设置为**None**。</span><span class="sxs-lookup"><span data-stu-id="625ff-347">This property is not available if the **MsmqProtectionLevel** property is set to **None**.</span></span>

<span data-ttu-id="625ff-348">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-348">Type: String</span></span>  
<span data-ttu-id="625ff-349">默认值：**SHA1**</span><span class="sxs-lookup"><span data-stu-id="625ff-349">Default value: **SHA1**</span></span>  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

<span data-ttu-id="625ff-350">适用范围：Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-350">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="negotiateservicecredential"></a><span data-ttu-id="625ff-351">NegotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="625ff-351">NegotiateServiceCredential</span></span>
<span data-ttu-id="625ff-352">指定服务凭据在带外，客户端设置还是通过协商过程由客户端从服务中获取。</span><span class="sxs-lookup"><span data-stu-id="625ff-352">Specify whether the service credential is provisioned at the client out of band, or is obtained from the service to the client through a process of negotiation.</span></span> <span data-ttu-id="625ff-353">这种协商是正常消息交换的前提。</span><span class="sxs-lookup"><span data-stu-id="625ff-353">Such a negotiation is a precursor to the usual message exchange.</span></span>

<span data-ttu-id="625ff-354">如果**MessageClientCredentialType**属性等于**None**，**用户名**，或者**证书**，设置此属性设置为**False**意味着服务证书可在带外客户端，并且客户端需要指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="625ff-354">If the **MessageClientCredentialType** property equals **None**, **Username**, or **Certificate**, setting this property to **False** implies that the service certificate is available at the client out of band and that the client needs to specify the service certificate.</span></span> <span data-ttu-id="625ff-355">此模式是可与实现 Ws-trust 和 Ws-secureconversation 的 SOAP 堆栈交互操作。</span><span class="sxs-lookup"><span data-stu-id="625ff-355">This mode is interoperable with SOAP stacks that implement WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="625ff-356">如果**MessageClientCredentialType**属性设置为**Windows**，此属性设置为**False**指定基于 Kerberos 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="625ff-356">If the **MessageClientCredentialType** property is set to **Windows**, setting this property to **False** specifies Kerberos-based authentication.</span></span> <span data-ttu-id="625ff-357">这意味着，客户端和服务必须是相同 Kerberos 域的一部分。</span><span class="sxs-lookup"><span data-stu-id="625ff-357">This means that the client and service must be part of the same Kerberos domain.</span></span> <span data-ttu-id="625ff-358">此模式是可与实现 Kerberos 令牌配置文件 （如 OASIS WSS tc 中定义） 以及 Ws-trust 和 Ws-secureconversation 的 SOAP 堆栈交互操作。</span><span class="sxs-lookup"><span data-stu-id="625ff-358">This mode is interoperable with SOAP stacks that implement the Kerberos token profile (as defined at OASIS WSS TC) as well as WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="625ff-359">当此属性是 **，则返回 True**，会引起通过 SOAP 消息传送 SPNego 交换的.NET SOAP 协商。</span><span class="sxs-lookup"><span data-stu-id="625ff-359">When this property is **True**, it causes a .NET SOAP negotiation that tunnels SPNego exchange over SOAP messages.</span></span>

<span data-ttu-id="625ff-360">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-360">Type: Boolean</span></span>  
<span data-ttu-id="625ff-361">默认值：True</span><span class="sxs-lookup"><span data-stu-id="625ff-361">Default value: True</span></span>  
<span data-ttu-id="625ff-362">适用范围：Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-362">Applies to: WCF-WSHttp adapter</span></span>  

#### <a name="opentimeout"></a><span data-ttu-id="625ff-363">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="625ff-363">OpenTimeout</span></span>
<span data-ttu-id="625ff-364">指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="625ff-364">Specify a time span value that indicates the interval of time provided for a channel open operation to complete.</span></span> 

<span data-ttu-id="625ff-365">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-365">**Note**</span></span>  
<span data-ttu-id="625ff-366">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-366">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="625ff-367">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-367">Type: String</span></span>  
<span data-ttu-id="625ff-368">默认值：00:01:00</span><span class="sxs-lookup"><span data-stu-id="625ff-368">Default value: 00:01:00</span></span>  
<span data-ttu-id="625ff-369">适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-369">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="orderedprocessing"></a><span data-ttu-id="625ff-370">OrderedProcessing</span><span class="sxs-lookup"><span data-stu-id="625ff-370">OrderedProcessing</span></span>
<span data-ttu-id="625ff-371">指定是否按顺序处理消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-371">Specify whether to process messages serially.</span></span> <span data-ttu-id="625ff-372">选中此属性后，此接收位置会按序送达的消息传递中具有的 BizTalk 消息传送或业务流程发送端口一起使用时**按序送达**选项设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="625ff-372">When this property is selected, this receive location accommodates ordered message delivery when used in conjunction with a BizTalk messaging or orchestration send port that has the **Ordered Delivery** option set to `True`.</span></span> <span data-ttu-id="625ff-373">有关详细信息**按序送达**选项，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="625ff-373">For more information about the **Ordered Delivery** option, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="625ff-374">此属性是在以下情况下适用：</span><span class="sxs-lookup"><span data-stu-id="625ff-374">This property is applicable in the following cases:</span></span>
- <span data-ttu-id="625ff-375">Wcf-custom 适配器：当**BindingType**属性设置为**netMsmqBinding**</span><span class="sxs-lookup"><span data-stu-id="625ff-375">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**</span></span>
- <span data-ttu-id="625ff-376">Wcf-custom 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于传输的自定义通道支持如 MSMQ 的按序的送达。</span><span class="sxs-lookup"><span data-stu-id="625ff-376">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery such as MSMQ.</span></span>
- <span data-ttu-id="625ff-377">Wcf-customisolated 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于传输的自定义通道支持按序的送达。</span><span class="sxs-lookup"><span data-stu-id="625ff-377">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery.</span></span>
- <span data-ttu-id="625ff-378">Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-378">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="625ff-379">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-379">Type: String</span></span>  
<span data-ttu-id="625ff-380">默认值：**False**</span><span class="sxs-lookup"><span data-stu-id="625ff-380">Default value: **False**</span></span>  
<span data-ttu-id="625ff-381">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-381">Applies to:</span></span> 
- <span data-ttu-id="625ff-382">Wcf-netmsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-382">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="625ff-383">WCF 自定义接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-383">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="625ff-384">Wcf-customisolated 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-384">WCF-CustomIsolated receive adapter</span></span>

#### <a name="outboundbodylocation"></a><span data-ttu-id="625ff-385">OutboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="625ff-385">OutboundBodyLocation</span></span>
<span data-ttu-id="625ff-386">指定数据选择 soap**正文**的传出 WCF 消息的元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-386">Specify the data selection for the SOAP **Body** element of outgoing WCF messages.</span></span> <span data-ttu-id="625ff-387">有关如何使用详细信息**OutboundBodyLocation**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-387">For more information about how to use the **OutboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="625ff-388">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-388">Type: String</span></span>  
<span data-ttu-id="625ff-389">默认值：UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="625ff-389">Default value: UseBodyElement</span></span>  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

<span data-ttu-id="625ff-390">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-390">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundcustomheaders"></a><span data-ttu-id="625ff-391">OutboundCustomHeaders</span><span class="sxs-lookup"><span data-stu-id="625ff-391">OutboundCustomHeaders</span></span>
<span data-ttu-id="625ff-392">指定传出消息的自定义 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="625ff-392">Specify the custom SOAP headers for outgoing messages.</span></span> <span data-ttu-id="625ff-393">使用此属性时，该属性必须具有\<**标头**\>元素作为根元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-393">When this property is used, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="625ff-394">所有自定义 SOAP 标头必须位于内部\<**标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-394">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="625ff-395">如果自定义 SOAP 标头值为空字符串，则必须分配\<**标头**\>\</**标头**\>或\<**标头**\>给此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-395">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**\> to this property.</span></span> <span data-ttu-id="625ff-396">有关如何通过 WCF 适配器将 SOAP 标头的详细信息，请参阅 SDK 示例中，将自定义 SOAP 标头用于 WCF 适配器中，从[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="625ff-396">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="625ff-397">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-397">Type: String</span></span>  
<span data-ttu-id="625ff-398">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-398">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundxmltemplate"></a><span data-ttu-id="625ff-399">OutboundXmlTemplate</span><span class="sxs-lookup"><span data-stu-id="625ff-399">OutboundXmlTemplate</span></span>
<span data-ttu-id="625ff-400">指定内容的 SOAP XML 格式的模板**正文**传出的消息的元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-400">Specify the XML-formatted template for the content of the SOAP **Body** element of an outgoing message.</span></span> <span data-ttu-id="625ff-401">此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。</span><span class="sxs-lookup"><span data-stu-id="625ff-401">This property is required if the **OutboundBodyLocation** property is set to **UseTemplate**.</span></span> <span data-ttu-id="625ff-402">有关如何使用详细信息**OutboundXMLTemplate**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-402">For more information about how to use the **OutboundXMLTemplate** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="625ff-403">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-403">Type: String</span></span>  
<span data-ttu-id="625ff-404">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-404">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-405">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-405">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="password"></a><span data-ttu-id="625ff-406">Password</span><span class="sxs-lookup"><span data-stu-id="625ff-406">Password</span></span>
<span data-ttu-id="625ff-407">指定要用于目标服务器的身份验证的密码时**UseSSO**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="625ff-407">Specify the password to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span>

<span data-ttu-id="625ff-408">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-408">Type: String</span></span>  
<span data-ttu-id="625ff-409">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-409">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-410">适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-410">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>  

#### <a name="propagatefaultmessage"></a><span data-ttu-id="625ff-411">PropagateFaultMessage</span><span class="sxs-lookup"><span data-stu-id="625ff-411">PropagateFaultMessage</span></span>
<span data-ttu-id="625ff-412">指定是路由还是挂起在出站处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-412">Specify whether to route or suspend messages that fail in outbound processing.</span></span> <span data-ttu-id="625ff-413">此属性是仅对要求响应端口有效。</span><span class="sxs-lookup"><span data-stu-id="625ff-413">This property is valid only for solicit-response ports.</span></span> 

<span data-ttu-id="625ff-414">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-414">**Note**</span></span>  
<span data-ttu-id="625ff-415">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-415">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="625ff-416">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-416">Type: Boolean</span></span>  
<span data-ttu-id="625ff-417">默认值：**True**</span><span class="sxs-lookup"><span data-stu-id="625ff-417">Default value: **True**</span></span>  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

<span data-ttu-id="625ff-418">适用范围：所有 WCF 都发送适配器*除*Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-418">Applies to: All WCF send adapters *except* the WCF-NetMsmq adapter</span></span>
  
#### <a name="proxyaddress"></a><span data-ttu-id="625ff-419">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="625ff-419">ProxyAddress</span></span>
<span data-ttu-id="625ff-420">指定代理服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="625ff-420">Specify the address of the proxy server.</span></span> <span data-ttu-id="625ff-421">使用**https**或**http**具体取决于安全配置的方案。</span><span class="sxs-lookup"><span data-stu-id="625ff-421">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="625ff-422">此地址可以跟一个冒号和端口号。</span><span class="sxs-lookup"><span data-stu-id="625ff-422">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="625ff-423">该属性是必需的如果**ProxyToUse**属性设置为**UserSpecified** （例如， http://127.0.0.1:8080)</span><span class="sxs-lookup"><span data-stu-id="625ff-423">The property is required if the **ProxyToUse** property is set to **UserSpecified** (For example, http://127.0.0.1:8080)</span></span>

<span data-ttu-id="625ff-424">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-424">Type: String</span></span>  
<span data-ttu-id="625ff-425">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-425">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-426">适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-426">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxypassword"></a><span data-ttu-id="625ff-427">ProxyPassword</span><span class="sxs-lookup"><span data-stu-id="625ff-427">ProxyPassword</span></span>
<span data-ttu-id="625ff-428">指定要用于在指定的代理服务器的密码**ProxyAddress**属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-428">Specify the password to use for the proxy server specified in the **ProxyAddress** property.</span></span>

<span data-ttu-id="625ff-429">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-429">Type: String</span></span>  
<span data-ttu-id="625ff-430">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-430">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-431">适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-431">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="proxytouse"></a><span data-ttu-id="625ff-432">ProxyToUse</span><span class="sxs-lookup"><span data-stu-id="625ff-432">ProxyToUse</span></span>
<span data-ttu-id="625ff-433">指定要用于传出 HTTP 通信的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="625ff-433">Specify which proxy server to use for outgoing HTTP traffic.</span></span>

<span data-ttu-id="625ff-434">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-434">Type: String</span></span>  
<span data-ttu-id="625ff-435">默认值：**无**</span><span class="sxs-lookup"><span data-stu-id="625ff-435">Default value: **None**</span></span>  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

<span data-ttu-id="625ff-436">适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-436">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxyusername"></a><span data-ttu-id="625ff-437">ProxyUserName</span><span class="sxs-lookup"><span data-stu-id="625ff-437">ProxyUserName</span></span>
<span data-ttu-id="625ff-438">指定要用于在指定的代理服务器的用户名**ProxyAddress**属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-438">Specify the user name to use for the proxy server specified in the **ProxyAddress** property.</span></span> <span data-ttu-id="625ff-439">该属性是必需的如果**ProxyToUse**属性设置为**UserSpecified**。</span><span class="sxs-lookup"><span data-stu-id="625ff-439">The property is required if the **ProxyToUse** property is set to **UserSpecified**.</span></span>

<span data-ttu-id="625ff-440">有关此属性的详细信息，请参阅[如何配置 Wcf-wshttp 发送端口](../core/how-to-configure-a-wcf-wshttp-send-port.md)并[如何配置 Wcf-basichttp 发送端口](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)。</span><span class="sxs-lookup"><span data-stu-id="625ff-440">For more information about this property, see [How to Configure a WCF-WSHttp Send Port](../core/how-to-configure-a-wcf-wshttp-send-port.md) and [How to Configure a WCF-BasicHttp Send Port](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f).</span></span>

<span data-ttu-id="625ff-441">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-441">Type: String</span></span>  
<span data-ttu-id="625ff-442">适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-442">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="replytoaddress"></a><span data-ttu-id="625ff-443">ReplyToAddress</span><span class="sxs-lookup"><span data-stu-id="625ff-443">ReplyToAddress</span></span>
<span data-ttu-id="625ff-444">指示答复终结点地址与通过请求-响应接收的传入消息相对应的传出 WCF 消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="625ff-444">Indicate the reply endpoint address for the outgoing WCF messages corresponding to incoming messages received through the request-response receive locations.</span></span> <span data-ttu-id="625ff-445">从传入消息，则会自动升级该属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-445">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="625ff-446">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-446">Type: String</span></span>  
<span data-ttu-id="625ff-447">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-447">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-448">适用范围：所有 WCF 适配器*除*Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-448">Applies to: All WCF adapters *except* the WCF-NetMsmq adapter</span></span>

#### <a name="securitymode"></a><span data-ttu-id="625ff-449">SecurityMode</span><span class="sxs-lookup"><span data-stu-id="625ff-449">SecurityMode</span></span>
<span data-ttu-id="625ff-450">指定使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="625ff-450">Specify the type of security that is used.</span></span> <span data-ttu-id="625ff-451">每个 WCF 适配器不同的值。</span><span class="sxs-lookup"><span data-stu-id="625ff-451">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="625ff-452">有关详细信息**SecurityMode**属性，每个 WCF 适配器中，请参阅操作指南主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-452">For more information about the **SecurityMode** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span> 

<span data-ttu-id="625ff-453">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-453">**Note**</span></span>  
<span data-ttu-id="625ff-454">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-454">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="625ff-455">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-455">Type: String</span></span>  
<span data-ttu-id="625ff-456">适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-456">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="sendtimeout"></a><span data-ttu-id="625ff-457">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="625ff-457">SendTimeout</span></span>
<span data-ttu-id="625ff-458">指定一个时间跨度值来表示为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="625ff-458">Specify a time span value that indicates the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="625ff-459">此值指定完成，整个交互的时间跨度，即使响应方返回发送大消息。</span><span class="sxs-lookup"><span data-stu-id="625ff-459">This value specifies a time span for the whole interaction to complete, even if the correspondent sends a large message.</span></span>

<span data-ttu-id="625ff-460">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-460">Type: String</span></span>  
<span data-ttu-id="625ff-461">默认值：00:01:00</span><span class="sxs-lookup"><span data-stu-id="625ff-461">Default value: 00:01:00</span></span>  
<span data-ttu-id="625ff-462">适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-462">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="servicebehaviorconfiguration"></a><span data-ttu-id="625ff-463">ServiceBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="625ff-463">ServiceBehaviorConfiguration</span></span>
<span data-ttu-id="625ff-464">指定 XML 字符串与 **\<行为\>** 元素 **\<serviceBehaviors\>** 元素来配置 WCF 行为设置服务。</span><span class="sxs-lookup"><span data-stu-id="625ff-464">Specify an XML string with the **\<behavior\>** element of the **\<serviceBehaviors\>** element to configure the behavior settings of a WCF service.</span></span> <span data-ttu-id="625ff-465">有关详细信息 **\<serviceBehaviors\>** 元素，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="625ff-465">For more information about the **\<serviceBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="625ff-466">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-466">Example:</span></span>

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

<span data-ttu-id="625ff-467">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-467">Type: String</span></span>  
<span data-ttu-id="625ff-468">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-468">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-469">适用范围：WCF 自定义接收适配器，Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-469">Applies to: WCF-Custom receive adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="servicecertificate"></a><span data-ttu-id="625ff-470">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="625ff-470">ServiceCertificate</span></span>
<span data-ttu-id="625ff-471">如果此属性用于接收位置，指定接收位置的客户端使用服务进行身份验证的 X.509 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="625ff-471">If this property is used for receive locations, specify the thumbprint of the X.509 certificate for the receive locations that clients use to authenticate the service.</span></span> <span data-ttu-id="625ff-472">要用于此属性的证书必须安装到**我**将存储在**当前用户**位置。</span><span class="sxs-lookup"><span data-stu-id="625ff-472">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="625ff-473">如果此属性用于发送端口，指定用于对此发送端口将消息发送到该服务进行身份验证的 X.509 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="625ff-473">If this property is used for send ports, specify the thumbprint of the X.509 certificate for authenticating the service to which this send port sends messages.</span></span> <span data-ttu-id="625ff-474">要用于此属性的证书必须安装到**其他人**将存储在**本地计算机**位置。</span><span class="sxs-lookup"><span data-stu-id="625ff-474">The certificate to be used for this property must be installed into the **Other People** store in the **Local Machine** location.</span></span>

<span data-ttu-id="625ff-475">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-475">Type: String</span></span>  
<span data-ttu-id="625ff-476">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-476">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-477">适用范围：</span><span class="sxs-lookup"><span data-stu-id="625ff-477">Applies to:</span></span> 
- <span data-ttu-id="625ff-478">Wcf-basichttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-478">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="625ff-479">Wcf-netmsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-479">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="625ff-480">Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-480">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="625ff-481">Wcf-nettcp 接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-481">WCF-NetTcp receive adapter</span></span>

#### <a name="suspendmessageonfailure"></a><span data-ttu-id="625ff-482">SuspendMessageOnFailure</span><span class="sxs-lookup"><span data-stu-id="625ff-482">SuspendMessageOnFailure</span></span>
<span data-ttu-id="625ff-483">指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。</span><span class="sxs-lookup"><span data-stu-id="625ff-483">Specify whether to suspend the request message that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span>

<span data-ttu-id="625ff-484">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-484">Type: Boolean</span></span>  
<span data-ttu-id="625ff-485">默认值：True</span><span class="sxs-lookup"><span data-stu-id="625ff-485">Default value: True</span></span>  
<span data-ttu-id="625ff-486">适用范围：所有 WCF 都接收适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-486">Applies to: All WCF receive adapters</span></span>  

#### <a name="textencoding"></a><span data-ttu-id="625ff-487">TextEncoding</span><span class="sxs-lookup"><span data-stu-id="625ff-487">TextEncoding</span></span>
<span data-ttu-id="625ff-488">指定要使用该绑定上发出消息编码的字符集时**MessageEncoding**属性设置为**文本**。</span><span class="sxs-lookup"><span data-stu-id="625ff-488">Specify the character set encoding to be used for emitting messages on the binding when the **MessageEncoding** property is set to **Text**.</span></span> 

<span data-ttu-id="625ff-489">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-489">**Note**</span></span>  
<span data-ttu-id="625ff-490">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-490">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="625ff-491">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-491">Type: String</span></span>  
<span data-ttu-id="625ff-492">默认值： utf-8</span><span class="sxs-lookup"><span data-stu-id="625ff-492">Default value: utf-8</span></span>  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

<span data-ttu-id="625ff-493">适用范围：Wcf-basichttp 适配器，Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-493">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>
  
#### <a name="timetolive"></a><span data-ttu-id="625ff-494">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="625ff-494">TimeToLive</span></span>
<span data-ttu-id="625ff-495">指定在将过期并放入死信队列之前消息多长时间是有效的时间跨度。</span><span class="sxs-lookup"><span data-stu-id="625ff-495">Specify a time span for how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="625ff-496">若要确保具有时效性的消息执行操作不会过时，通过发送端口进行处理之前，设置此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-496">This property is set to ensure that time-sensitive messages do not become stale before they are processed by a send port.</span></span> <span data-ttu-id="625ff-497">不使用时此发送端口指定的时间间隔内队列中的消息被认为已过期。</span><span class="sxs-lookup"><span data-stu-id="625ff-497">A message in a queue that is not consumed by this send port within the time interval specified is said to be expired.</span></span> <span data-ttu-id="625ff-498">已过期的消息发送到称为死信队列的特殊队列。</span><span class="sxs-lookup"><span data-stu-id="625ff-498">Expired messages are sent to special queue called the dead-letter queue.</span></span> <span data-ttu-id="625ff-499">死信队列的位置设置与**DeadLetterQueue**属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-499">The location of the dead-letter queue is set with the **DeadLetterQueue** property.</span></span>

<span data-ttu-id="625ff-500">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-500">Type: String</span></span>  
<span data-ttu-id="625ff-501">默认值：1.00:00:00</span><span class="sxs-lookup"><span data-stu-id="625ff-501">Default value: 1.00:00:00</span></span>  
<span data-ttu-id="625ff-502">适用范围：Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-502">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="to"></a><span data-ttu-id="625ff-503">若要</span><span class="sxs-lookup"><span data-stu-id="625ff-503">To</span></span>
<span data-ttu-id="625ff-504">指定 WCF 发送端口发送的传出 WCF 消息的目标终结点地址。</span><span class="sxs-lookup"><span data-stu-id="625ff-504">Specify the destination endpoint address for outgoing WCF messages that the WCF send ports send.</span></span>

<span data-ttu-id="625ff-505">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-505">Type: String</span></span>  
<span data-ttu-id="625ff-506">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-506">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-507">适用范围：所有 WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-507">Applies to: All WCF send adapters</span></span>  

#### <a name="transactionprotocol"></a><span data-ttu-id="625ff-508">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="625ff-508">TransactionProtocol</span></span>
<span data-ttu-id="625ff-509">指定要与此绑定一起使用的事务协议。</span><span class="sxs-lookup"><span data-stu-id="625ff-509">Specify the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="625ff-510">此属性是必需的如果**EnableTransaction**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="625ff-510">This property is required if the **EnableTransaction** property is set to **True**.</span></span>

<span data-ttu-id="625ff-511">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-511">Type: String</span></span>  
<span data-ttu-id="625ff-512">默认值：OleTransaction</span><span class="sxs-lookup"><span data-stu-id="625ff-512">Default value: OleTransaction</span></span>  

    Applicable values are: OleTransaction, WS-AtomicTransaction

<span data-ttu-id="625ff-513">适用范围：Wcf-netnamedpipe 适配器，Wcf-nettcp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-513">Applies to: WCF-NetNamedPipe adapter,  WCF-NetTcp adapter</span></span>  

#### <a name="transportclientcredentialtype"></a><span data-ttu-id="625ff-514">TransportClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="625ff-514">TransportClientCredentialType</span></span>
<span data-ttu-id="625ff-515">指定要执行发送端口验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="625ff-515">Specify the type of credential to be used when performing the send port authentication.</span></span> <span data-ttu-id="625ff-516">每个 WCF 适配器不同的值。</span><span class="sxs-lookup"><span data-stu-id="625ff-516">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="625ff-517">有关详细信息**TransportClientCredentialType**属性，每个 WCF 适配器中，请参阅操作指南主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="625ff-517">For more information about the **TransportClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="625ff-518">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-518">Type: String</span></span>  
<span data-ttu-id="625ff-519">适用范围：Wcf-basic 适配器、 WCF NetTcp 适配器、 Wcf-wshttp 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-519">Applies to: WCF-Basic adapter, WCF-NetTcp adapter, WCF-WSHttp adapter</span></span>  

#### <a name="transportprotectionlevel"></a><span data-ttu-id="625ff-520">TransportProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="625ff-520">TransportProtectionLevel</span></span>
<span data-ttu-id="625ff-521">指定 TCP 传输级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="625ff-521">Specify security at the level of the TCP transport.</span></span> <span data-ttu-id="625ff-522">消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="625ff-522">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="625ff-523">加密为传输过程提供了数据级保密功能。</span><span class="sxs-lookup"><span data-stu-id="625ff-523">Encryption provides data-level privacy during transport.</span></span>

<span data-ttu-id="625ff-524">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-524">Type: String</span></span>  
<span data-ttu-id="625ff-525">默认值：**EncryptAndSign**</span><span class="sxs-lookup"><span data-stu-id="625ff-525">Default value: **EncryptAndSign**</span></span>  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

<span data-ttu-id="625ff-526">适用范围：Wcf-nettcp 适配器，Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-526">Applies to: WCF-NetTcp adapter, WCF-NetNamedPipe adapter</span></span>  

#### <a name="username"></a><span data-ttu-id="625ff-527">UserName</span><span class="sxs-lookup"><span data-stu-id="625ff-527">UserName</span></span>
<span data-ttu-id="625ff-528">指定要用于目标服务器的身份验证的用户名时**UseSSO**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="625ff-528">Specify the user name to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span> <span data-ttu-id="625ff-529">无需使用此属性的域 \ 用户格式。</span><span class="sxs-lookup"><span data-stu-id="625ff-529">You do not have to use the domain\user format for this property.</span></span>

<span data-ttu-id="625ff-530">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-530">Type: String</span></span>  
<span data-ttu-id="625ff-531">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-531">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-532">适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-532">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="usesourcejournal"></a><span data-ttu-id="625ff-533">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="625ff-533">UseSourceJournal</span></span>
<span data-ttu-id="625ff-534">指定此发送端口处理的消息副本是否应存储在源日记队列。</span><span class="sxs-lookup"><span data-stu-id="625ff-534">Specify whether copies of messages processed by this send port should be stored in the source journal queue.</span></span>

<span data-ttu-id="625ff-535">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-535">Type: Boolean</span></span>  
<span data-ttu-id="625ff-536">默认值：False</span><span class="sxs-lookup"><span data-stu-id="625ff-536">Default value: False</span></span>  
<span data-ttu-id="625ff-537">适用范围：Wcf-netmsmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-537">Applies to: WCF-NetMsmq send adapter</span></span>  

#### <a name="usesso"></a><span data-ttu-id="625ff-538">UseSSO</span><span class="sxs-lookup"><span data-stu-id="625ff-538">UseSSO</span></span>
<span data-ttu-id="625ff-539">指定是否使用单一登录检索客户端凭据的目标服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="625ff-539">Specify whether to use Single Sign-On to retrieve client credentials for authentication with the destination server.</span></span> 

<span data-ttu-id="625ff-540">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-540">**Note**</span></span>  
<span data-ttu-id="625ff-541">使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-541">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="625ff-542">键入：Boolean</span><span class="sxs-lookup"><span data-stu-id="625ff-542">Type: Boolean</span></span>  
<span data-ttu-id="625ff-543">默认值：False</span><span class="sxs-lookup"><span data-stu-id="625ff-543">Default value: False</span></span>  
<span data-ttu-id="625ff-544">适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-544">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="referencedbindings"></a><span data-ttu-id="625ff-545">ReferencedBindings</span><span class="sxs-lookup"><span data-stu-id="625ff-545">ReferencedBindings</span></span>
<span data-ttu-id="625ff-546">指定引用的绑定配置 **bindingConfiguration** 的属性 **\<颁发者\>** 元素 **wsFederationHttpBinding** 并**customBinding**， 表示安全令牌服务 (STS) 颁发安全令牌。</span><span class="sxs-lookup"><span data-stu-id="625ff-546">Specify the binding configurations referenced by the **bindingConfiguration** attribute of the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding**, which indicates the Security Token Service (STS) that issues security tokens.</span></span> <span data-ttu-id="625ff-547">有关详细信息 **\<颁发者\>** 元素中，请参阅本主题中，"\<颁发者\>"在[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)。</span><span class="sxs-lookup"><span data-stu-id="625ff-547">For more information about the **\<issuer\>** element, see the topic, "\<issuer\>" at [http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476).</span></span>

<span data-ttu-id="625ff-548">绑定信息，包括 **\<颁发者\>** 元素 **wsFederationHttpBinding**并**customBinding**可以是通过配置**BindingConfiguration** Wcf-custom 和 Wcf-customisolated 适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-548">The binding information including the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding** can be configured through the **BindingConfiguration** property of the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="625ff-549">此属性的引用的绑定配置的所有必须置于的窗体[\<绑定\>](http://go.microsoft.com/fwlink/?LinkID=80878)元素。</span><span class="sxs-lookup"><span data-stu-id="625ff-549">All of the referenced binding configurations for this property must be placed in the form of the [\<bindings\>](http://go.microsoft.com/fwlink/?LinkID=80878) element.</span></span> 

<span data-ttu-id="625ff-550">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-550">**Note**</span></span>  
<span data-ttu-id="625ff-551">**BindingConfiguration**的属性 **\<颁发者\>** 元素必须引用此属性中的有效绑定名称。</span><span class="sxs-lookup"><span data-stu-id="625ff-551">The **bindingConfiguration** attribute of the **\<issuer\>** element must refer to a valid binding name in this property.</span></span> 

<span data-ttu-id="625ff-552">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-552">**Note**</span></span>  
<span data-ttu-id="625ff-553">**\<颁发者\>** 中引用的绑定配置元素还可以对此属性中的其他绑定配置引用如果此引用链不会使循环依赖项。</span><span class="sxs-lookup"><span data-stu-id="625ff-553">The **\<issuer\>** element in the referenced binding configurations can also refer to a different binding configuration in this property if this reference chain does not make a circular dependency.</span></span> 

<span data-ttu-id="625ff-554">例如：</span><span class="sxs-lookup"><span data-stu-id="625ff-554">Example:</span></span> 

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

<span data-ttu-id="625ff-555">**注意**</span><span class="sxs-lookup"><span data-stu-id="625ff-555">**Note**</span></span>  
<span data-ttu-id="625ff-556">**ReferencedBinding**属性不能包含中使用的绑定配置**BindingConfiguration**属性。</span><span class="sxs-lookup"><span data-stu-id="625ff-556">**ReferencedBinding** property must not contain the binding configuration used in the **BindingConfiguration** property.</span></span>

<span data-ttu-id="625ff-557">键入：String</span><span class="sxs-lookup"><span data-stu-id="625ff-557">Type: String</span></span>  
<span data-ttu-id="625ff-558">默认值：空字符串</span><span class="sxs-lookup"><span data-stu-id="625ff-558">Default value: An empty string</span></span>  
<span data-ttu-id="625ff-559">适用范围：Wcf-custom 适配器，Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="625ff-559">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>
  
## <a name="see-also"></a><span data-ttu-id="625ff-560">请参阅</span><span class="sxs-lookup"><span data-stu-id="625ff-560">See Also</span></span>  
 <span data-ttu-id="625ff-561">[WCF 适配器](../core/wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="625ff-561">[WCF Adapters](../core/wcf-adapters.md) </span></span>  
 <span data-ttu-id="625ff-562">[\<行为\>的\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span><span class="sxs-lookup"><span data-stu-id="625ff-562">[\<behavior\> of \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span></span>  
 <span data-ttu-id="625ff-563">[\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span><span class="sxs-lookup"><span data-stu-id="625ff-563">[\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span></span>  
 <span data-ttu-id="625ff-564">[\<行为\>的\<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span><span class="sxs-lookup"><span data-stu-id="625ff-564">[\<behavior\> of \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span></span>  
 <span data-ttu-id="625ff-565">[按序送达消息](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="625ff-565">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="625ff-566">负载平衡</span><span class="sxs-lookup"><span data-stu-id="625ff-566">Load Balancing</span></span>](http://go.microsoft.com/fwlink/?LinkId=81089)
