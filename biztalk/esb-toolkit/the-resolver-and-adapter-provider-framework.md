---
title: ESB 冲突解决程序和适配器提供程序框架 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a350ac19ac1fa95ffb8eb6782380bda78a457b75
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="666bc-102">冲突解决程序和适配器提供程序框架</span><span class="sxs-lookup"><span data-stu-id="666bc-102">The Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="666bc-103">冲突解决程序和适配器提供程序框架支持路线、 转换和终结点解析和路由。</span><span class="sxs-lookup"><span data-stu-id="666bc-103">The Resolver and Adapter Provider Framework supports itinerary, transformation, and endpoint resolution and routing.</span></span> <span data-ttu-id="666bc-104">框架可以动态解析终结点，并设置出站适配器属性。</span><span class="sxs-lookup"><span data-stu-id="666bc-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="666bc-105">后一个冲突解决程序组件解析终结点 （例如，使用通用、 描述、 发现和集成 [UDDI] 看起来出站 Web 服务终结点），适配器提供程序组件设置的已注册 BizTalk Server 特定属性适配器。</span><span class="sxs-lookup"><span data-stu-id="666bc-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound Web service endpoint), an adapter provider component sets specific properties of registered BizTalk Server adapters.</span></span> <span data-ttu-id="666bc-106">例如，WCF BasicHttp 适配器提供程序负责设置 BizTalk 特定消息终结点将使用特定的 BizTalk adapter; 的 URI 的上下文属性FTP 适配器提供程序负责属性特定于设置 FTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="666bc-106">For example, the WCF-BasicHttp adapter provider is responsible for setting the BizTalk-specific message context properties for the endpoint URI that will use the specific BizTalk adapter; the FTP adapter provider is responsible for setting the properties specific to the FTP adapter.</span></span>  
  
 <span data-ttu-id="666bc-107">冲突解决程序和适配器提供程序框架的目标之一是支持解析和路由在任一消息级别，而无需使用 BizTalk 业务流程或业务流程级别。</span><span class="sxs-lookup"><span data-stu-id="666bc-107">One goal of the Resolver and Adapter Provider Framework is to support resolution and routing at either the messaging level, without requiring the use of BizTalk orchestrations, or at the orchestration level.</span></span> <span data-ttu-id="666bc-108">在这两种情况下，可插入 framework 会提供更轻松的开发、 部署和新解析程序和适配器提供程序的注册。</span><span class="sxs-lookup"><span data-stu-id="666bc-108">In both cases, the pluggable framework provides easy development, deployment, and registration of new resolvers and adapter providers.</span></span> <span data-ttu-id="666bc-109">所有冲突解决程序和适配器提供程序实现定义完善的接口，且需加载在运行时通过在配置文件中的注册。</span><span class="sxs-lookup"><span data-stu-id="666bc-109">All resolvers and adapter providers implement well-defined interfaces and are demand-loaded at run time through registration in the configuration files.</span></span>  
  
 <span data-ttu-id="666bc-110">ESB 调度程序和 ESB 调度程序反汇编管道组件使用的解析程序和适配器提供程序框架从路线 SOAP 标头或管道配置到的冲突解决程序管理器传递连接字符串。</span><span class="sxs-lookup"><span data-stu-id="666bc-110">Both the ESB Dispatcher and ESB Dispatcher Disassemble pipeline components use the Resolver and Adapter Provider Framework by passing the connection string from either the itinerary SOAP header or the pipeline configuration to the Resolver Manager.</span></span>  
  
 <span data-ttu-id="666bc-111">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]配置包含所有已注册的解析程序和适配器提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="666bc-111">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration contains details of all registered resolvers and adapter providers.</span></span> <span data-ttu-id="666bc-112">在运行的时，冲突解决程序管理器和适配器管理器从配置文件中读取的已注册的解析程序和适配器提供程序的详细信息，加载相应的程序集，并将它们存储在 BizTalk 主机级缓存。</span><span class="sxs-lookup"><span data-stu-id="666bc-112">At run time, the resolver managers and adapter managers read details of the registered resolvers and adapter providers from the configuration files, load the appropriate assemblies, and store them in a BizTalk host–level cache.</span></span> <span data-ttu-id="666bc-113">此缓存的方法中删除重复的配置文件的读取和加载的程序集的每个已提交的邮件的要求。</span><span class="sxs-lookup"><span data-stu-id="666bc-113">This caching technique removes the requirement for repeated reading of configuration files and loading of assemblies for every submitted message.</span></span>  
  
 <span data-ttu-id="666bc-114">有关详细信息冲突解决程序和适配器提供程序框架的工作原理以及如何通过创建自定义解析程序和适配器提供程序，扩展它的请参阅有关[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="666bc-114">For more information about how the Resolver and Adapter Provider Framework works and how you can extend it by creating custom resolvers and adapter providers, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>  
  
## <a name="supported-resolution-mechanisms-resolvers"></a><span data-ttu-id="666bc-115">支持的解析机制 （解析程序）</span><span class="sxs-lookup"><span data-stu-id="666bc-115">Supported Resolution Mechanisms (Resolvers)</span></span>  
 <span data-ttu-id="666bc-116">BizTalk ESB 工具包包括以下冲突解决程序：**静态、 UDDI、 UDDI3、 XPATH、 BRE、 BRI、 路线，路线静态**和**LDAP**。</span><span class="sxs-lookup"><span data-stu-id="666bc-116">The BizTalk ESB Toolkit includes the following resolvers: **STATIC, UDDI, UDDI3, XPATH, BRE, BRI, ITINERARY, ITINERARY-STATIC** and **LDAP**.</span></span>  
  
 <span data-ttu-id="666bc-117">冲突解决程序的连接字符串始终组成**标记**(如**BRE**) 后跟":\\\\"和连接或处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="666bc-117">A resolver's connection string always consists of a **moniker** (such as **BRE**) followed by ":\\\\" and the connection or processing details.</span></span> <span data-ttu-id="666bc-118">标记与配置文件中关联的冲突解决程序的定义相匹配。</span><span class="sxs-lookup"><span data-stu-id="666bc-118">The moniker matches the definition of the associated resolver in the configuration file.</span></span> <span data-ttu-id="666bc-119">与每个连接字符串关联的属性是唯一的而不是所有属性都是必需。</span><span class="sxs-lookup"><span data-stu-id="666bc-119">The properties associated with each connection string are unique, and not all properties are required.</span></span> <span data-ttu-id="666bc-120">ESB 中找不到解析程序的每个架构。Resolvers.Schemas 项目。</span><span class="sxs-lookup"><span data-stu-id="666bc-120">The schema for each of the resolvers can be found in the ESB.Resolvers.Schemas project.</span></span>  
  
 <span data-ttu-id="666bc-121">连接字符串的示例如下：</span><span class="sxs-lookup"><span data-stu-id="666bc-121">The following are examples of connection strings:</span></span>  
  
-   <span data-ttu-id="666bc-122">**静态**</span><span class="sxs-lookup"><span data-stu-id="666bc-122">**STATIC**</span></span>  
  
     <span data-ttu-id="666bc-123">STATIC:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="666bc-123">STATIC:\\\TransportType=;</span></span>  
  
     <span data-ttu-id="666bc-124">TransportLocation =http://localhost/ESB.CanadianServices/SubmitPOService.asmx;</span><span class="sxs-lookup"><span data-stu-id="666bc-124">TransportLocation=http://localhost/ESB.CanadianServices/SubmitPOService.asmx;</span></span>  
  
     <span data-ttu-id="666bc-125">Action=;</span><span class="sxs-lookup"><span data-stu-id="666bc-125">Action=;</span></span>  
  
     <span data-ttu-id="666bc-126">EndPointConfig=;</span><span class="sxs-lookup"><span data-stu-id="666bc-126">EndPointConfig=;</span></span>  
  
     <span data-ttu-id="666bc-127">JaxRpcResponse=false;</span><span class="sxs-lookup"><span data-stu-id="666bc-127">JaxRpcResponse=false;</span></span>  
  
     <span data-ttu-id="666bc-128">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="666bc-128">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="666bc-129">TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;</span><span class="sxs-lookup"><span data-stu-id="666bc-129">TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;</span></span>  
  
     <span data-ttu-id="666bc-130">TransformType=;</span><span class="sxs-lookup"><span data-stu-id="666bc-130">TransformType=;</span></span>  
  
-   <span data-ttu-id="666bc-131">**UDDI**</span><span class="sxs-lookup"><span data-stu-id="666bc-131">**UDDI**</span></span>  
  
     <span data-ttu-id="666bc-132">UDDI:\\\serverUrl=http://localhost:9901/rmengine;</span><span class="sxs-lookup"><span data-stu-id="666bc-132">UDDI:\\\serverUrl=http://localhost:9901/rmengine;</span></span>  
  
     <span data-ttu-id="666bc-133">serviceName=OrderPurchaseWebService;</span><span class="sxs-lookup"><span data-stu-id="666bc-133">serviceName=OrderPurchaseWebService;</span></span>  
  
     <span data-ttu-id="666bc-134">serviceProvider=Microsoft Practices ESB</span><span class="sxs-lookup"><span data-stu-id="666bc-134">serviceProvider=Microsoft Practices ESB</span></span>  
  
-   <span data-ttu-id="666bc-135">**XPATH**</span><span class="sxs-lookup"><span data-stu-id="666bc-135">**XPATH**</span></span>  
  
     <span data-ttu-id="666bc-136">XPATH:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="666bc-136">XPATH:\\\TransportType=;</span></span>  
  
     `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
     <span data-ttu-id="666bc-137">Action=;</span><span class="sxs-lookup"><span data-stu-id="666bc-137">Action=;</span></span>  
  
     <span data-ttu-id="666bc-138">EndPointConfig=;</span><span class="sxs-lookup"><span data-stu-id="666bc-138">EndPointConfig=;</span></span>  
  
     <span data-ttu-id="666bc-139">JaxRpcResponse=;</span><span class="sxs-lookup"><span data-stu-id="666bc-139">JaxRpcResponse=;</span></span>  
  
     <span data-ttu-id="666bc-140">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="666bc-140">MessageExchangePattern=;</span></span>  
  
     `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
     <span data-ttu-id="666bc-141">TransformType=;</span><span class="sxs-lookup"><span data-stu-id="666bc-141">TransformType=;</span></span>  

-   <span data-ttu-id="666bc-142">**BRE**</span><span class="sxs-lookup"><span data-stu-id="666bc-142">**BRE**</span></span>  
  
     <span data-ttu-id="666bc-143">BRE:\\\policy=GetCanadaEndPoint;</span><span class="sxs-lookup"><span data-stu-id="666bc-143">BRE:\\\policy=GetCanadaEndPoint;</span></span>  
  
     <span data-ttu-id="666bc-144">version=;</span><span class="sxs-lookup"><span data-stu-id="666bc-144">version=;</span></span>  
  
     <span data-ttu-id="666bc-145">useMsg=;</span><span class="sxs-lookup"><span data-stu-id="666bc-145">useMsg=;</span></span>  
  
-   <span data-ttu-id="666bc-146">**BRI**</span><span class="sxs-lookup"><span data-stu-id="666bc-146">**BRI**</span></span>  
  
     <span data-ttu-id="666bc-147">BRI:\\\policy=ResolveItinerary;</span><span class="sxs-lookup"><span data-stu-id="666bc-147">BRI:\\\policy=ResolveItinerary;</span></span>  
  
     <span data-ttu-id="666bc-148">version=;</span><span class="sxs-lookup"><span data-stu-id="666bc-148">version=;</span></span>  
  
     <span data-ttu-id="666bc-149">useMsg=;</span><span class="sxs-lookup"><span data-stu-id="666bc-149">useMsg=;</span></span>  
  
-   <span data-ttu-id="666bc-150">**路线**</span><span class="sxs-lookup"><span data-stu-id="666bc-150">**ITINERARY**</span></span>  
  
     <span data-ttu-id="666bc-151">ITINERARY:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="666bc-151">ITINERARY:\\\name=TwoWayTestItinerary;</span></span>  
  
     <span data-ttu-id="666bc-152">version=;</span><span class="sxs-lookup"><span data-stu-id="666bc-152">version=;</span></span>  
  
-   <span data-ttu-id="666bc-153">**路线静态**</span><span class="sxs-lookup"><span data-stu-id="666bc-153">**ITINERARY-STATIC**</span></span>  
  
     <span data-ttu-id="666bc-154">路线静态：\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="666bc-154">ITINERARY-STATIC:\\\name=TwoWayTestItinerary;</span></span>  
  
     <span data-ttu-id="666bc-155">version=;</span><span class="sxs-lookup"><span data-stu-id="666bc-155">version=;</span></span>  
  
-   <span data-ttu-id="666bc-156">**LDAP**</span><span class="sxs-lookup"><span data-stu-id="666bc-156">**LDAP**</span></span>  
  
     <span data-ttu-id="666bc-157">LDAP:\\\TransportType=SMTP;</span><span class="sxs-lookup"><span data-stu-id="666bc-157">LDAP:\\\TransportType=SMTP;</span></span>  
  
     <span data-ttu-id="666bc-158">TransportLocation={mail}</span><span class="sxs-lookup"><span data-stu-id="666bc-158">TransportLocation={mail}</span></span>  
  
     <span data-ttu-id="666bc-159">筛选器 = (&(objectClass=User) (| (userPrincipalName =yourname@domain.com)));</span><span class="sxs-lookup"><span data-stu-id="666bc-159">Filter=(&(objectClass=User)(|(userPrincipalName=yourname@domain.com)));</span></span>  
  
     <span data-ttu-id="666bc-160">SearchRoot=;</span><span class="sxs-lookup"><span data-stu-id="666bc-160">SearchRoot=;</span></span>  
  
     <span data-ttu-id="666bc-161">SearchScope=Subtree;</span><span class="sxs-lookup"><span data-stu-id="666bc-161">SearchScope=Subtree;</span></span>  
  
     <span data-ttu-id="666bc-162">EndpointConfig = Subject = {邮件} 到路线测试消息 （& a)</span><span class="sxs-lookup"><span data-stu-id="666bc-162">EndpointConfig=Subject=Itinerary Test Message to {mail}&</span></span> 
  
     <span data-ttu-id="666bc-163">SMTPAuthenticate = 0 （& a)</span><span class="sxs-lookup"><span data-stu-id="666bc-163">SMTPAuthenticate=0&</span></span>
  
     <span data-ttu-id="666bc-164">SMTPHost = 127.0.0.1 （& a)</span><span class="sxs-lookup"><span data-stu-id="666bc-164">SMTPHost=127.0.0.1&</span></span>
  
     <span data-ttu-id="666bc-165">从 =test@globalbank.com（& a)</span><span class="sxs-lookup"><span data-stu-id="666bc-165">From=test@globalbank.com&</span></span>
  
     <span data-ttu-id="666bc-166">DeliveryReceipt = false （& a)</span><span class="sxs-lookup"><span data-stu-id="666bc-166">DeliveryReceipt=false&</span></span>
  
     <span data-ttu-id="666bc-167">MessagePartsAttachments = 0 （& a)</span><span class="sxs-lookup"><span data-stu-id="666bc-167">MessagePartsAttachments=0&</span></span>
  
     <span data-ttu-id="666bc-168">ReadReceipt=false;</span><span class="sxs-lookup"><span data-stu-id="666bc-168">ReadReceipt=false;</span></span>  
  
     <span data-ttu-id="666bc-169">ThrowErrorIfNotFound=false;</span><span class="sxs-lookup"><span data-stu-id="666bc-169">ThrowErrorIfNotFound=false;</span></span>  
  
     <span data-ttu-id="666bc-170">Action=;</span><span class="sxs-lookup"><span data-stu-id="666bc-170">Action=;</span></span>  
  
     <span data-ttu-id="666bc-171">JaxRpcResponse=false;</span><span class="sxs-lookup"><span data-stu-id="666bc-171">JaxRpcResponse=false;</span></span>  
  
     <span data-ttu-id="666bc-172">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="666bc-172">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="666bc-173">TargetNamespace=;</span><span class="sxs-lookup"><span data-stu-id="666bc-173">TargetNamespace=;</span></span>  
  
     <span data-ttu-id="666bc-174">TransformType=;</span><span class="sxs-lookup"><span data-stu-id="666bc-174">TransformType=;</span></span>  
  
 <span data-ttu-id="666bc-175">并非所有连接字符串中的属性都是必需的。</span><span class="sxs-lookup"><span data-stu-id="666bc-175">Not all attributes in the connection string are mandatory.</span></span> <span data-ttu-id="666bc-176">此外， **EndPointConfig**是一个特殊属性，任何冲突解决程序可以填充并返回。</span><span class="sxs-lookup"><span data-stu-id="666bc-176">In addition, **EndPointConfig** is a special attribute that any resolver can populate and return.</span></span> <span data-ttu-id="666bc-177">（可选） 冲突解决程序可以存储特定的 BizTalk 适配器上下文属性，它可以反过来，写入 BizTalk 消息的上下文所对应的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="666bc-177">Optionally, the resolver can store the name/value pairs that correspond to specific BizTalk Adapter Context properties, which it can, in turn, write to the context of the BizTalk message.</span></span>  
  
 <span data-ttu-id="666bc-178">在这种情况下， **ResolverDictionary**实例，其中包含所有已解决的属性返回的解析进程然后传递到适配器管理器。</span><span class="sxs-lookup"><span data-stu-id="666bc-178">In this case, the **ResolverDictionary** instance that contains all the resolved properties returned from the resolution process then passes to the adapter manager.</span></span> <span data-ttu-id="666bc-179">适配器管理器将传递到的特定的适配器提供程序将设置所有适配器特定和特定终结点的 BizTalk 上下文消息属性的字典。</span><span class="sxs-lookup"><span data-stu-id="666bc-179">The adapter manager passes the dictionary to the specific adapter provider that will set all the adapter-specific and endpoint-specific BizTalk Context properties for the message.</span></span> <span data-ttu-id="666bc-180">冲突解决程序查找**EndPointConfig**属性，对应于它们各自的适配器的属性的名称/值对中提取，然后在消息上设置这些值。</span><span class="sxs-lookup"><span data-stu-id="666bc-180">The resolvers look for the **EndPointConfig** property, extract the name/value pairs that correspond to their respective adapter properties, and then set these values on the message.</span></span>  
  
## <a name="supported-adapter-providers"></a><span data-ttu-id="666bc-181">受支持的适配器提供程序</span><span class="sxs-lookup"><span data-stu-id="666bc-181">Supported Adapter Providers</span></span>  
 <span data-ttu-id="666bc-182">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下内置适配器提供程序：**文件、 FTP、 SMTP、 MQSeries、 WCF BasicHttp、 WCF WSHttp，**和**WCF 自定义**。</span><span class="sxs-lookup"><span data-stu-id="666bc-182">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following built-in adapter providers: **FILE, FTP, SMTP,MQSeries, WCF-BasicHttp, WCF-WSHttp,** and **WCF-Custom**.</span></span> <span data-ttu-id="666bc-183">每个适配器提供程序的名称等同于 BizTalk Server 中关联的适配器 （传输类型） 的名称。</span><span class="sxs-lookup"><span data-stu-id="666bc-183">The name of each adapter provider is identical to the name of the associated adapter (transport type) in BizTalk Server.</span></span>  
  
 <span data-ttu-id="666bc-184">冲突解决程序和适配器提供程序框架的主要优点是，你可以通过创建并注册你自己的自定义解析程序来解析终结点信息和自定义适配器提供商能够设置的已注册 BizTalk 适配器的特定属性来扩展它。</span><span class="sxs-lookup"><span data-stu-id="666bc-184">A major advantage of the Resolver and Adapter Provider Framework is that you can extend it by creating and registering your own custom resolvers to resolve endpoint information and custom adapter providers to set specific properties of registered BizTalk adapters.</span></span> <span data-ttu-id="666bc-185">有关详细信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="666bc-185">For more information, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>
