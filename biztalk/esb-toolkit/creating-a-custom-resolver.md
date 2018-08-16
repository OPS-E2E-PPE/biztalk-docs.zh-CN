---
title: 创建自定义冲突解决程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2775460-8e04-40be-9557-8278336b031c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3752348a5cc9273ad203b78b77b58bde33bd141
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981710"
---
# <a name="creating-a-custom-resolver"></a><span data-ttu-id="bae2f-102">创建自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="bae2f-102">Creating a Custom Resolver</span></span>
<span data-ttu-id="bae2f-103">中的冲突解决程序和适配器提供程序框架实现[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用名为调度程序的管道组件和名为 ItineraryReceive 和 ItinerarySend 的管道。</span><span class="sxs-lookup"><span data-stu-id="bae2f-103">The Resolver and Adapter Provider Framework implementation in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses a pipeline component named Dispatcher and pipelines named ItineraryReceive and ItinerarySend.</span></span>  
  
 <span data-ttu-id="bae2f-104">调度程序管道组件有四个属性：**验证、 已启用、 终结点，** 并**MapName**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-104">The Dispatcher pipeline component has four properties: **Validate, Enabled, EndPoint,** and **MapName**.</span></span> <span data-ttu-id="bae2f-105">**终结点**属性可以包含冲突解决程序连接字符串值如下所示，其中**UDDI:\\ \\** 表示要使用 （根的解析类型名字对象）。</span><span class="sxs-lookup"><span data-stu-id="bae2f-105">The **EndPoint** property can contain resolver connection strings with values such as the following, where **UDDI:\\\\** represents the resolution type to use (the root moniker).</span></span>  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="bae2f-106">其他受支持的名字对象包括**XPATH:\\\\静态：\\\\，** 并**BRE:\\\\**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-106">Other supported monikers include **XPATH:\\\\, STATIC:\\\\,** and **BRE:\\\\**.</span></span> <span data-ttu-id="bae2f-107">每个名字对象类型使用特定的类实现**IResolveProvider**接口。</span><span class="sxs-lookup"><span data-stu-id="bae2f-107">Each moniker type uses a specific class that implements the **IResolveProvider** interface.</span></span> <span data-ttu-id="bae2f-108">您可以创建自己为其他名字对象类型的自定义解析程序并注册它们以供使用的动态解析系统。</span><span class="sxs-lookup"><span data-stu-id="bae2f-108">You can create your own custom resolvers for other moniker types and register them for use by the dynamic resolution system.</span></span>  
  
 <span data-ttu-id="bae2f-109">名字对象等同于冲突解决程序连接字符串。</span><span class="sxs-lookup"><span data-stu-id="bae2f-109">The moniker equates to a resolver connection string.</span></span> <span data-ttu-id="bae2f-110">单个架构定义的参数和其根名字对象。</span><span class="sxs-lookup"><span data-stu-id="bae2f-110">Individual schemas define the parameters and their root moniker.</span></span> <span data-ttu-id="bae2f-111">冲突解决程序需要冲突解决程序连接字符串中，验证它，并使用的结果来查询和填充**字典**对象，它可用于路由、 转换、 路线选择或特定于某些其他目的在服务。</span><span class="sxs-lookup"><span data-stu-id="bae2f-111">A resolver takes the resolver connection string, validates it, and uses the result to query and populate a **Dictionary** object that can be used for routing, transformation, itinerary selection, or some other purpose specific to your service.</span></span>  
  
## <a name="resolver-configuration"></a><span data-ttu-id="bae2f-112">解析程序配置</span><span class="sxs-lookup"><span data-stu-id="bae2f-112">Resolver Configuration</span></span>  
 <span data-ttu-id="bae2f-113">必须在 Esb.config 配置文件中注册所有冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="bae2f-113">You must register all resolvers in the Esb.config configuration file.</span></span> <span data-ttu-id="bae2f-114">以下 XML 显示了配置文件内容的示例。</span><span class="sxs-lookup"><span data-stu-id="bae2f-114">The following XML shows an example of the configuration file content.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
     <configSections>  
          <section name="esb" type="Microsoft.Practices.ESB.Configuration.ESBConfigurationSection, Microsoft.Practices.ESB.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
          <!-- Other Section Definitions Here -->  
     </configSections>  
  
     <esb>  
          <resolvers cacheManager= "Resolver Providers Cache Manager"  absoluteExpiration="3600">  
               <resolver name="UDDI" type="Microsoft.Practices.ESB.Resolver.UDDI.ResolveProvider, Microsoft.Practices.ESB.Resolver.UDDI, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
                    <resolverConfig>  
                         <add name="cacheTimeoutValue" value="120" />  
                         <add name="cacheName" value="UDDI Cache Manager" />  
                    </resolverConfig>  
               </resolver>  
               <resolver name="XPATH" type="Microsoft.Practices.ESB.Resolver.XPATH.ResolveProvider, Microsoft.Practices.ESB.Resolver.XPATH, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
               <!-- Other Resolver Definitions Here -->  
          </resolvers>  
          <!-- Other ESB Configuration Settings Here -->  
     </esb>  
     <!-- Other Configuration Sections Here -->  
</configuration>  
```  
  
 <span data-ttu-id="bae2f-115">**ResolverConfig**部分中的每个冲突解决程序节点下，可配置您的解析程序可能需要的特定环境中运行的其他属性。</span><span class="sxs-lookup"><span data-stu-id="bae2f-115">The **resolverConfig** section under each resolver node allows you to configure additional properties that your resolver may require to operate in a specific environment.</span></span> <span data-ttu-id="bae2f-116">若要访问的配置，您的解析程序必须公开采用的类型参数的构造函数**Microsoft.Practices.ESB.Configuration.Resolver**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-116">To have access to the configuration, your resolver must expose a constructor that takes in a parameter of type **Microsoft.Practices.ESB.Configuration.Resolver**.</span></span> <span data-ttu-id="bae2f-117">在解析程序实现中，配置属性可以访问使用**ReadResolverConfigByKey**方法**ResolverConfigHelper**类; 若要执行此操作，将传递的参数中最初传递给构造函数中，然后传入名称值有问题。</span><span class="sxs-lookup"><span data-stu-id="bae2f-117">In your resolver implementation, configuration properties can then be accessed using the **ReadResolverConfigByKey** method of the **ResolverConfigHelper** class; to do this, pass in the parameter originally passed to the constructor, and then pass in the name of the value in question.</span></span> <span data-ttu-id="bae2f-118">如果没有名称-值对中指定**resolverConfig**节点，将使用默认的无参数构造函数来实例化您的解析程序。</span><span class="sxs-lookup"><span data-stu-id="bae2f-118">If no name-value pairs are specified in the **resolverConfig** node, the default parameterless constructor will be used to instantiate your resolver.</span></span>  
  
 <span data-ttu-id="bae2f-119">两个通用描述、 发现和集成 (UDDI) 3 已在配置中定义冲突解决程序： UDDI 3 和 UDDI 3 SOASOFTWARE。</span><span class="sxs-lookup"><span data-stu-id="bae2f-119">Two Universal Description, Discovery, and Integration (UDDI) 3 resolvers have been defined in the configuration: UDDI 3 and UDDI 3-SOASOFTWARE.</span></span> <span data-ttu-id="bae2f-120">这些冲突解决程序都使用相同的基础程序集，但它们提供不同的配置，以支持不同的 UDDI 3.0 兼容注册表使用不同的统一资源标识符 (URI) 格式和安全要求。</span><span class="sxs-lookup"><span data-stu-id="bae2f-120">Both of these resolvers use the same underlying assembly, but they provide different configurations for supporting different UDDI 3.0–compliant registries with different Uniform Resource Identifier (URI) formats and security requirements.</span></span> <span data-ttu-id="bae2f-121">如果你需要配置 UDDI 3.0 兼容的注册表，除了那些已支持为其他名字对象，可以使用以下配置属性：</span><span class="sxs-lookup"><span data-stu-id="bae2f-121">If you need to configure an additional moniker for a UDDI 3.0–compliant registry besides those already supported, the following configuration properties can be used:</span></span>  
  
- <span data-ttu-id="bae2f-122">**cacheTimeoutValue**</span><span class="sxs-lookup"><span data-stu-id="bae2f-122">**cacheTimeoutValue**</span></span>  
  
- <span data-ttu-id="bae2f-123">**cacheName**</span><span class="sxs-lookup"><span data-stu-id="bae2f-123">**cacheName**</span></span>  
  
- <span data-ttu-id="bae2f-124">**publisherKey**</span><span class="sxs-lookup"><span data-stu-id="bae2f-124">**publisherKey**</span></span>  
  
- <span data-ttu-id="bae2f-125">**useUddiAuth**</span><span class="sxs-lookup"><span data-stu-id="bae2f-125">**useUddiAuth**</span></span>  
  
- <span data-ttu-id="bae2f-126">**baseUri**</span><span class="sxs-lookup"><span data-stu-id="bae2f-126">**baseUri**</span></span>  
  
- <span data-ttu-id="bae2f-127">**inquireUriSuffix**</span><span class="sxs-lookup"><span data-stu-id="bae2f-127">**inquireUriSuffix**</span></span>  
  
- <span data-ttu-id="bae2f-128">**securityUriSuffix**</span><span class="sxs-lookup"><span data-stu-id="bae2f-128">**securityUriSuffix**</span></span>  
  
- <span data-ttu-id="bae2f-129">**securityMode**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-129">**securityMode**.</span></span> <span data-ttu-id="bae2f-130">有效的值，请参阅枚举[System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409))。</span><span class="sxs-lookup"><span data-stu-id="bae2f-130">For valid values, see the enumeration [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409)).</span></span> <span data-ttu-id="bae2f-131">默认值是**TransportCredentialOnly**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-131">The default value is **TransportCredentialOnly**.</span></span>  
  
- <span data-ttu-id="bae2f-132">**credentialType**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-132">**credentialType**.</span></span> <span data-ttu-id="bae2f-133">有效的值，请参阅枚举[System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285))。</span><span class="sxs-lookup"><span data-stu-id="bae2f-133">For valid values, see the enumeration [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285)).</span></span> <span data-ttu-id="bae2f-134">默认值是**Windows**。</span><span class="sxs-lookup"><span data-stu-id="bae2f-134">The default value is **Windows**.</span></span>  
  
- <span data-ttu-id="bae2f-135">**username**</span><span class="sxs-lookup"><span data-stu-id="bae2f-135">**username**</span></span>  
  
- <span data-ttu-id="bae2f-136">**password**</span><span class="sxs-lookup"><span data-stu-id="bae2f-136">**password**</span></span>  
  
  <span data-ttu-id="bae2f-137">如果你想要创建的解析程序依赖于 Unity 应用程序块的依赖关系注入功能，则需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="bae2f-137">If you want to create a resolver that relies on the dependency injection capabilities of the Unity Application Block, additional configuration is required.</span></span> <span data-ttu-id="bae2f-138">有关详细信息，请参阅[使用 Unity 容器创建自定义冲突解决程序](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)。</span><span class="sxs-lookup"><span data-stu-id="bae2f-138">For more information, see [Creating a Custom Resolver with a Unity Container](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md).</span></span>  
  
## <a name="the-iresolveprovider-interface"></a><span data-ttu-id="bae2f-139">IResolveProvider 接口</span><span class="sxs-lookup"><span data-stu-id="bae2f-139">The IResolveProvider Interface</span></span>  
 <span data-ttu-id="bae2f-140">所有冲突解决程序必须实现**IResolveProvider**接口。</span><span class="sxs-lookup"><span data-stu-id="bae2f-140">All resolvers must implement the **IResolveProvider** interface.</span></span> <span data-ttu-id="bae2f-141">**IResolveProvider**接口，位于 Microsoft.Practices.ESB.Resolver 项目包含的三个重载**解决**返回的实例方法**字典**类，该类包含提供的具体的解析程序类的实例解析事实。</span><span class="sxs-lookup"><span data-stu-id="bae2f-141">The **IResolveProvider** interface, located in the Microsoft.Practices.ESB.Resolver project, consists of three overloads of the **Resolve** method that return an instance of the **Dictionary** class, which contains resolution facts provided by the instance of concrete resolver class.</span></span> <span data-ttu-id="bae2f-142">下面的代码示例演示了这些方法重载的签名。</span><span class="sxs-lookup"><span data-stu-id="bae2f-142">The following code example shows the signature of these method overloads.</span></span>  
  
```csharp  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from a Microsoft BizTalk   
// Server pipeline component.  
// </summary>  
// <param name="config">Configuration string entered into   
// pipeline component as argument</param>  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">IBaseMessage passed from pipeline</param>.  
// <param name="pipelineContext">IPipelineContext passed from   
// pipeline</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(string config, string resolver,  
              IBaseMessage message, IPipelineContext pipelineContext);  
  
// <summary>  
// This is the main interface that is called from the ResolverMgr   
// class.  
// This interface supports being called from a Web service interface.  
// </summary>  
// <param name="config">Configuration string entered into Web   
// service as argument</param>.  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">XML document passed from Web   
// service</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string,string> Resolve(string config, string resolver, System.Xml.XmlDocument message);  
  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from an orchestration.  
// </summary>  
// <param name="resolverInfo">Configuration string containing   
// configuration and resolver</param>.  
// <param name="message">XLANGMessage passed from   
// orchestration</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(ResolverInfo resolverInfo, XLANGs.BaseTypes.XLANGMessage message);  
```  
  
 <span data-ttu-id="bae2f-143">**解析**结构，位于 Microsoft.Practices.ESB.Resolver 项目还定义中存储的名称/值对**字典**实例。</span><span class="sxs-lookup"><span data-stu-id="bae2f-143">The **Resolution** structure, located in Microsoft.Practices.ESB.Resolver project, also defines the name/value pairs stored in the **Dictionary** instance.</span></span> <span data-ttu-id="bae2f-144">**解析**结构揭示了多个属性; 下表列出了最相关的这些。</span><span class="sxs-lookup"><span data-stu-id="bae2f-144">The **Resolution** structure exposes several properties; the following table lists the most relevant of these.</span></span> <span data-ttu-id="bae2f-145">**CreateResolverDictionary**方法**ResolutionHelper**类可用于生成一个冲突解决程序字典，其中包含最常用的关键字，使用空字符串值。</span><span class="sxs-lookup"><span data-stu-id="bae2f-145">The **CreateResolverDictionary** method of the **ResolutionHelper** class can be used to generate a resolver dictionary that contains the most used keys, with empty string values.</span></span> <span data-ttu-id="bae2f-146">**字典**实例支持的自定义冲突解决程序名称/值对的具体实现通过添加**冲突解决程序**类。</span><span class="sxs-lookup"><span data-stu-id="bae2f-146">The **Dictionary** instance supports the addition of custom resolver name/value pairs through a concrete implementation of the **Resolver** class.</span></span>  
  
|<span data-ttu-id="bae2f-147">“属性”</span><span class="sxs-lookup"><span data-stu-id="bae2f-147">Property</span></span>|<span data-ttu-id="bae2f-148">数据类型</span><span class="sxs-lookup"><span data-stu-id="bae2f-148">Data type</span></span>|<span data-ttu-id="bae2f-149">数据类型</span><span class="sxs-lookup"><span data-stu-id="bae2f-149">Data type</span></span>|<span data-ttu-id="bae2f-150">数据类型</span><span class="sxs-lookup"><span data-stu-id="bae2f-150">Data type</span></span>|  
|--------------|---------------|---------------|---------------|  
|<span data-ttu-id="bae2f-151">**TransformType**</span><span class="sxs-lookup"><span data-stu-id="bae2f-151">**TransformType**</span></span>|<span data-ttu-id="bae2f-152">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-152">String</span></span>|<span data-ttu-id="bae2f-153">**ActionField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-153">**ActionField**</span></span>|<span data-ttu-id="bae2f-154">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-154">String</span></span>|  
|<span data-ttu-id="bae2f-155">**成功**</span><span class="sxs-lookup"><span data-stu-id="bae2f-155">**Success**</span></span>|<span data-ttu-id="bae2f-156">Boolean</span><span class="sxs-lookup"><span data-stu-id="bae2f-156">Boolean</span></span>|<span data-ttu-id="bae2f-157">**EpmRRCorrelationTokenField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-157">**EpmRRCorrelationTokenField**</span></span>|<span data-ttu-id="bae2f-158">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-158">String</span></span>|  
|<span data-ttu-id="bae2f-159">**TransportNamespace**</span><span class="sxs-lookup"><span data-stu-id="bae2f-159">**TransportNamespace**</span></span>|<span data-ttu-id="bae2f-160">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-160">String</span></span>|<span data-ttu-id="bae2f-161">**InboundTransportLocationField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-161">**InboundTransportLocationField**</span></span>|<span data-ttu-id="bae2f-162">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-162">String</span></span>|  
|<span data-ttu-id="bae2f-163">**TransportType**</span><span class="sxs-lookup"><span data-stu-id="bae2f-163">**TransportType**</span></span>|<span data-ttu-id="bae2f-164">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-164">String</span></span>|<span data-ttu-id="bae2f-165">**InterchangeIDField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-165">**InterchangeIDField**</span></span>|<span data-ttu-id="bae2f-166">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-166">String</span></span>|  
|<span data-ttu-id="bae2f-167">**TransportLocation**</span><span class="sxs-lookup"><span data-stu-id="bae2f-167">**TransportLocation**</span></span>|<span data-ttu-id="bae2f-168">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-168">String</span></span>|<span data-ttu-id="bae2f-169">**ReceiveLocationNameField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-169">**ReceiveLocationNameField**</span></span>|<span data-ttu-id="bae2f-170">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-170">String</span></span>|  
|<span data-ttu-id="bae2f-171">**操作**</span><span class="sxs-lookup"><span data-stu-id="bae2f-171">**Action**</span></span>|<span data-ttu-id="bae2f-172">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-172">String</span></span>|<span data-ttu-id="bae2f-173">**ReceivePortNameField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-173">**ReceivePortNameField**</span></span>|<span data-ttu-id="bae2f-174">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-174">String</span></span>|  
|<span data-ttu-id="bae2f-175">**MessageExchangePattern**</span><span class="sxs-lookup"><span data-stu-id="bae2f-175">**MessageExchangePattern**</span></span>|<span data-ttu-id="bae2f-176">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-176">String</span></span>|<span data-ttu-id="bae2f-177">**InboundTransportTypeField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-177">**InboundTransportTypeField**</span></span>|<span data-ttu-id="bae2f-178">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-178">String</span></span>|  
|<span data-ttu-id="bae2f-179">**EndpointConfig**</span><span class="sxs-lookup"><span data-stu-id="bae2f-179">**EndpointConfig**</span></span>|<span data-ttu-id="bae2f-180">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-180">String</span></span>|<span data-ttu-id="bae2f-181">**IsRequestResponseField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-181">**IsRequestResponseField**</span></span>|<span data-ttu-id="bae2f-182">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-182">String</span></span>|  
|<span data-ttu-id="bae2f-183">**TargetNamespace**</span><span class="sxs-lookup"><span data-stu-id="bae2f-183">**TargetNamespace**</span></span>|<span data-ttu-id="bae2f-184">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-184">String</span></span>|<span data-ttu-id="bae2f-185">**DocumentSpecStrongNameField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-185">**DocumentSpecStrongNameField**</span></span>|<span data-ttu-id="bae2f-186">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-186">String</span></span>|  
|<span data-ttu-id="bae2f-187">**FixJaxRPC**</span><span class="sxs-lookup"><span data-stu-id="bae2f-187">**FixJaxRPC**</span></span>|<span data-ttu-id="bae2f-188">Boolean</span><span class="sxs-lookup"><span data-stu-id="bae2f-188">Boolean</span></span>|<span data-ttu-id="bae2f-189">**DocumentSpecNameField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-189">**DocumentSpecNameField**</span></span>|<span data-ttu-id="bae2f-190">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-190">String</span></span>|  
|<span data-ttu-id="bae2f-191">**WindowUserField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-191">**WindowUserField**</span></span>|<span data-ttu-id="bae2f-192">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-192">String</span></span>|<span data-ttu-id="bae2f-193">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="bae2f-193">**MessageType**</span></span>|<span data-ttu-id="bae2f-194">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-194">String</span></span>|  
|<span data-ttu-id="bae2f-195">**CacheTimeout**</span><span class="sxs-lookup"><span data-stu-id="bae2f-195">**CacheTimeout**</span></span>|<span data-ttu-id="bae2f-196">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-196">String</span></span>|<span data-ttu-id="bae2f-197">**OutboundTransportCLSID**</span><span class="sxs-lookup"><span data-stu-id="bae2f-197">**OutboundTransportCLSID**</span></span>|<span data-ttu-id="bae2f-198">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-198">String</span></span>|  
|<span data-ttu-id="bae2f-199">**MethodNameField**</span><span class="sxs-lookup"><span data-stu-id="bae2f-199">**MethodNameField**</span></span>|<span data-ttu-id="bae2f-200">String</span><span class="sxs-lookup"><span data-stu-id="bae2f-200">String</span></span>|||  
  
## <a name="creating-a-custom-resolver"></a><span data-ttu-id="bae2f-201">创建自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="bae2f-201">Creating a Custom Resolver</span></span>  
 <span data-ttu-id="bae2f-202">在运行时，管道检索冲突解决程序连接字符串，并将调用冲突解决程序管理器 (的实例**ResolverMgr**类)。</span><span class="sxs-lookup"><span data-stu-id="bae2f-202">At run time, a pipeline retrieves the resolver connection string and calls the resolver manager (an instance of the **ResolverMgr** class).</span></span> <span data-ttu-id="bae2f-203">冲突解决程序管理器将分析、 填充并验证冲突解决程序连接字符串。</span><span class="sxs-lookup"><span data-stu-id="bae2f-203">The resolver manager parses, populates, and validates the resolver connection string.</span></span> <span data-ttu-id="bae2f-204">这是通过执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bae2f-204">It does this by doing the following:</span></span>  
  
- <span data-ttu-id="bae2f-205">它将解析连接字符串以确定哪个**冲突解决程序**要加载类型。</span><span class="sxs-lookup"><span data-stu-id="bae2f-205">It parses the connection string to determine which **Resolver** type to load.</span></span>  
  
- <span data-ttu-id="bae2f-206">它可匹配此名字对象 （该密钥是根名字对象，如 UDDI） 配置文件中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="bae2f-206">It matches this type to a moniker defined in the configuration file (the key is the root moniker, such as UDDI).</span></span>  
  
- <span data-ttu-id="bae2f-207">它将读取此名字对象的冲突解决程序的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="bae2f-207">It reads the assembly name of the resolver for this moniker.</span></span>  
  
- <span data-ttu-id="bae2f-208">它将加载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="bae2f-208">It loads the specified assembly.</span></span>  
  
  <span data-ttu-id="bae2f-209">动态解析机制缓存的所有已加载的实现**IResolveProvider**接口以避免重复的读取配置信息和程序集加载时多个传入消息使用相同的冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="bae2f-209">The dynamic resolution mechanism caches all loaded implementations of the **IResolveProvider** interface to avoid repeated reading of configuration information and assembly loading when several incoming messages use the same resolver.</span></span>  
  
  <span data-ttu-id="bae2f-210">最后，冲突解决程序管理器执行**解决**方法的具体**IResolveProvider**实现，并返回填充**字典**实例。</span><span class="sxs-lookup"><span data-stu-id="bae2f-210">Finally, the resolver manager executes the **Resolve** method of the concrete **IResolveProvider** implementation and returns the populated **Dictionary** instance.</span></span>  
  
  <span data-ttu-id="bae2f-211">**若要创建自定义冲突解决程序**</span><span class="sxs-lookup"><span data-stu-id="bae2f-211">**To create a custom resolver**</span></span>  
  
1.  <span data-ttu-id="bae2f-212">创建实现的类的程序集**IResolveProvider**接口并包含**解决**方法，它返回的实例作为冲突解决程序事实**字典**类。</span><span class="sxs-lookup"><span data-stu-id="bae2f-212">Create an assembly with a class that implements the **IResolveProvider** interface and contains a **Resolve** method that returns resolver facts as an instance of the **Dictionary** class.</span></span>  
  
2.  <span data-ttu-id="bae2f-213">通过将其添加到 Esb.config 配置文件使用注册冲突解决程序**\<冲突解决程序\>** 元素，其中包含作为根名字对象**名称**属性和完全限定的程序集同名**类型**属性。</span><span class="sxs-lookup"><span data-stu-id="bae2f-213">Register the resolver by adding it to the Esb.config configuration file using a **\<resolver\>** element that contains the root moniker as the **name** attribute and the fully qualified assembly name as the **type** attribute.</span></span>  
  
3.  <span data-ttu-id="bae2f-214">（可选）创建架构定义的根名字对象和查询参数，并将其保存在 ESB。Schemas.Resolvers 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bae2f-214">(Optional) Create a schema that defines the root moniker and the query parameters, and then save it in the ESB.Schemas.Resolvers folder.</span></span> <span data-ttu-id="bae2f-215">该名称应采用现有 ESB 命名约定;这意味着它应使用的名称后追加"_Resolution.xsd"的根名字对象。</span><span class="sxs-lookup"><span data-stu-id="bae2f-215">The name should follow existing ESB naming conventions; this means it should use the name of the root moniker appended with "_Resolution.xsd".</span></span>  
  
4.  <span data-ttu-id="bae2f-216">（可选）从新的架构生成类，并将其保存在自定义冲突解决程序程序集。</span><span class="sxs-lookup"><span data-stu-id="bae2f-216">(Optional) Generate a class from the new schema and save it in the custom resolver assembly.</span></span> <span data-ttu-id="bae2f-217">这会公开自定义冲突解决程序中的类型化的参数。</span><span class="sxs-lookup"><span data-stu-id="bae2f-217">This exposes typed parameters in the custom resolver.</span></span>  
  
5.  <span data-ttu-id="bae2f-218">在全局程序集缓存中注册新的程序集。</span><span class="sxs-lookup"><span data-stu-id="bae2f-218">Register the new assembly in the global assembly cache.</span></span>