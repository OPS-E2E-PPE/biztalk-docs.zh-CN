---
title: "适配器设计问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5568be-a046-40ff-a94a-eda086457564
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c6228db8342f3d1ad2628d4e4caf418efd9b29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-design-issues"></a><span data-ttu-id="82e39-102">适配器设计问题</span><span class="sxs-lookup"><span data-stu-id="82e39-102">Adapter Design Issues</span></span>
<span data-ttu-id="82e39-103">在用户在设计时对配置进行更改后，适配器配置存储于单一登录 (SSO) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="82e39-103">Adapter configuration is stored in the Single Sign-On (SSO) database when the user makes configuration changes during design time.</span></span> <span data-ttu-id="82e39-104">在运行时，消息引擎检索适配器的配置并将配置传送到适配器。</span><span class="sxs-lookup"><span data-stu-id="82e39-104">At run time the Messaging Engine retrieves the adapter's configuration and delivers it to the adapter.</span></span> <span data-ttu-id="82e39-105">四种类型的配置信息将传送到适配器：</span><span class="sxs-lookup"><span data-stu-id="82e39-105">Four types of configuration information are delivered to adapters:</span></span>  
  
-   <span data-ttu-id="82e39-106">接收处理程序配置</span><span class="sxs-lookup"><span data-stu-id="82e39-106">Receive handler configuration</span></span>  
  
-   <span data-ttu-id="82e39-107">接收位置（终结点）配置</span><span class="sxs-lookup"><span data-stu-id="82e39-107">Receive location (endpoint) configuration</span></span>  
  
-   <span data-ttu-id="82e39-108">发送处理程序配置</span><span class="sxs-lookup"><span data-stu-id="82e39-108">Send handler configuration</span></span>  
  
-   <span data-ttu-id="82e39-109">发送位置（终结点）配置</span><span class="sxs-lookup"><span data-stu-id="82e39-109">Send location (endpoint) configuration</span></span>  
  
## <a name="receive-and-send-handler-configuration"></a><span data-ttu-id="82e39-110">接收和发送处理程序配置</span><span class="sxs-lookup"><span data-stu-id="82e39-110">Receive and Send Handler Configuration</span></span>  
 <span data-ttu-id="82e39-111">适配器的处理程序配置传递到其实现的可选上的适配器**IPersistPropertyBag**。**负载**接口。</span><span class="sxs-lookup"><span data-stu-id="82e39-111">An adapter's handler configuration is delivered to the adapter on its implementation of the optional **IPersistPropertyBag**.**Load** interface.</span></span> <span data-ttu-id="82e39-112">处理程序配置只传送一次，因此，如果在 BizTalk 服务已启动后更改适配器处理程序配置，则不更新适配器。</span><span class="sxs-lookup"><span data-stu-id="82e39-112">The handler configuration is delivered only once, so if the adapter handler configuration is changed after the BizTalk service has started the adapter is not updated.</span></span> <span data-ttu-id="82e39-113">常见的模型是使适配器将处理程序配置视作默认配置，终结点配置将基于各终结点重写该处理程序配置。</span><span class="sxs-lookup"><span data-stu-id="82e39-113">The common model is for the adapter to treat the handler configuration as the default configuration; endpoint configuration overrides the handler configuration on a per-endpoint basis.</span></span>  
  
 <span data-ttu-id="82e39-114">以下代码段说明了对配置的解析。</span><span class="sxs-lookup"><span data-stu-id="82e39-114">The following code fragment demonstrates parsing the configuration.</span></span> <span data-ttu-id="82e39-115">正在传入到中的属性的适配器的配置**负载**字符串属性中调用**AdapterConfig**。</span><span class="sxs-lookup"><span data-stu-id="82e39-115">The adapter's configuration is in the property passed in to the **Load** call in the string property **AdapterConfig**.</span></span> <span data-ttu-id="82e39-116">该属性值包含表示适配器的配置的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="82e39-116">This property value contains an XML document representing the adapter's configuration.</span></span> <span data-ttu-id="82e39-117">适配器需要将此配置加载到文档对象模型 (DOM) 或 XML 阅读器中，并且使用 XPath 来检索单独的属性。</span><span class="sxs-lookup"><span data-stu-id="82e39-117">The adapter needs to load this configuration into a document object model (DOM) or an XML reader and use XPath to retrieve the individual properties.</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,  
 IPersistPropertyBag,   
 IBaseComponent  
{  
...  
// Handler configuration properties...  
private int defaultBatchSize = 0;  
private string defaultHeader;  
  
// IPersistPropertyBag.Load() implementation...  
public void Load(IPropertyBag pb, int pErrorLog)  
{  
// The adapter configuration is in the property  
 // “AdapterConfig” in the form of an Xml blob...  
object obj = null;  
pb.Read("AdapterConfig", out obj, 0);  
  
// Create a DOM and load the Xml blob...  
XmlDocument dom = new XmlDocument();  
string adapterConfig = (string)obj;  
dom.LoadXml(adapterConfig);  
  
// XPath the individual properties...  
XmlNode node =   
 document.SelectSingleNode(“/Config/batchSize”);  
defaultBatchSize = int.Parse(node.InnerText);  
  
node = document.SelectSingleNode(“/Config/header”);  
defaultHeader = node.InnerText;  
}  
}  
```  
  
## <a name="receive-location-configuration"></a><span data-ttu-id="82e39-118">接收位置配置</span><span class="sxs-lookup"><span data-stu-id="82e39-118">Receive Location Configuration</span></span>  
 <span data-ttu-id="82e39-119">接收位置配置信息传递到其实现上的适配器**IBTTransportConfig**。</span><span class="sxs-lookup"><span data-stu-id="82e39-119">Receive location configuration information is delivered to an adapter on its implementation of **IBTTransportConfig**.</span></span> <span data-ttu-id="82e39-120">此接口包含三个方法**AddReceiveEndpoint**， **UpdateEndpointConfig**，和**RemoveReceiveEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="82e39-120">This interface contains the three methods **AddReceiveEndpoint**, **UpdateEndpointConfig**, and **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="82e39-121">消息引擎通知适配器它需要侦听哪些终结点以接收消息。</span><span class="sxs-lookup"><span data-stu-id="82e39-121">The Messaging Engine notifies the adapter of which endpoints it needs to listen on to receive messages.</span></span> <span data-ttu-id="82e39-122">在更改某一单独终结点的配置时，将通知适配器对该终结点进行了更改。</span><span class="sxs-lookup"><span data-stu-id="82e39-122">When the configuration for an individual endpoint is changed the adapter is notified of the change for that endpoint.</span></span> <span data-ttu-id="82e39-123">与之相反的是，不通知适配器对处理程序配置的更改。</span><span class="sxs-lookup"><span data-stu-id="82e39-123">This is in contrast to the fact that when handler configuration changes the adapter is not notified.</span></span> <span data-ttu-id="82e39-124">同样，适配器并不需要处理服务时段，因为 BizTalk Server 将在服务时段变得活动或不活动时添加或删除终结点。</span><span class="sxs-lookup"><span data-stu-id="82e39-124">Similarly, the adapter does not need to handle service windows because BizTalk Server adds or removes endpoints as service windows become active or inactive.</span></span>  
  
### <a name="addreceiveendpoint"></a><span data-ttu-id="82e39-125">AddReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="82e39-125">AddReceiveEndpoint</span></span>  
 <span data-ttu-id="82e39-126">当适配器需要以开始侦听终结点，则引擎将调用上**IBTTransportConfig.AddReceiveEndpoint**接收位置的 URI，其中包含该终结点的适配器的配置属性包中传递和第二个的属性包，其中包含为该终结点的特定于 BizTalk Server 的配置。</span><span class="sxs-lookup"><span data-stu-id="82e39-126">When an adapter needs to begin listening on an endpoint, the engine calls **IBTTransportConfig.AddReceiveEndpoint** passing in the receive location's URI, a property bag containing the adapter's configuration for that endpoint, and a second property bag containing BizTalk Server-specific configuration for that endpoint.</span></span> <span data-ttu-id="82e39-127">适配器需要作为 BizTalk 服务器系统属性的消息上下文中写入 URI **InboundTransportLocation**。</span><span class="sxs-lookup"><span data-stu-id="82e39-127">The adapter needs to write the URI to the message context as the BizTalk Server system property **InboundTransportLocation**.</span></span>  
  
 <span data-ttu-id="82e39-128">从适配器的属性包读取接收位置属性的过程与上面详细介绍的读取处理程序配置的过程相同。</span><span class="sxs-lookup"><span data-stu-id="82e39-128">Reading the receive location properties from the adapter's property bag is the same as reading the handler configuration as detailed above.</span></span> <span data-ttu-id="82e39-129">传递到该适配器的 BizTalk Server 配置包含单个属性， **TwoWayReceivePort**，指示端口是单向或双向。</span><span class="sxs-lookup"><span data-stu-id="82e39-129">The BizTalk Server configuration passed into the adapter contains a single property, **TwoWayReceivePort**, which indicates whether the port is one-way or two-way.</span></span> <span data-ttu-id="82e39-130">下面的代码段演示了如何从 BizTalk Server 属性包计算接收端口是单向的还是双向的：</span><span class="sxs-lookup"><span data-stu-id="82e39-130">The following code fragment illustrates how to evaluate if the receive port is one-way or two-way from the BizTalk Server property bag:</span></span>  
  
```  
public void AddReceiveEndpoint(  
 string  url,   
 IPropertyBag adapterConfig,   
 IPropertyBag bizTalkConfig )  
{  
...  
  
// The property "TwoWayReceivePort" in the BizTalk Config  
// property bag indicates whether the port is one or two  
 // way...  
  
 // Add receive location to config cache (not shown here)  
  
object obj = null;  
bizTalkConfig.Read("TwoWayReceivePort", out obj, 0);  
  
if ( null != obj )  
this.twoWay = (bool)obj;  
}  
```  
  
### <a name="updateendpointconfig"></a><span data-ttu-id="82e39-131">UpdateEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="82e39-131">UpdateEndpointConfig</span></span>  
 <span data-ttu-id="82e39-132">当活动的配置接收更改位置，则引擎会使用**UpdateEndpointConfig** API 来通知该适配器，它需要使用不同的配置。</span><span class="sxs-lookup"><span data-stu-id="82e39-132">When the configuration of an active receive location is changed, the engine uses the **UpdateEndpointConfig** API to notify the adapter that it needs to use a different configuration.</span></span> <span data-ttu-id="82e39-133">所有配置都传送到适配器，包括特定于 BizTalk Server 的配置。</span><span class="sxs-lookup"><span data-stu-id="82e39-133">All of the configuration is delivered to the adapter, including the BizTalk Server-specific configuration.</span></span>  
  
### <a name="removereceiveendpoint"></a><span data-ttu-id="82e39-134">RemoveReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="82e39-134">RemoveReceiveEndpoint</span></span>  
 <span data-ttu-id="82e39-135">当接收位置不再处于活动状态时，该适配器将通知通过**RemoveReceiveEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="82e39-135">When a receive location is no longer active, the adapter is notified through **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="82e39-136">从适配器返回后**RemoveReceiveEndpoint**不再允许使用该 URI 引擎提交消息。</span><span class="sxs-lookup"><span data-stu-id="82e39-136">After the adapter returns from **RemoveReceiveEndpoint** it is no longer allowed to use that URI to submit messages into the engine.</span></span>  
  
## <a name="send-port-configuration"></a><span data-ttu-id="82e39-137">发送端口配置</span><span class="sxs-lookup"><span data-stu-id="82e39-137">Send Port Configuration</span></span>  
 <span data-ttu-id="82e39-138">消息引擎在将消息传送到适配器之前，将发送端口的配置写入适配器的命名空间的消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="82e39-138">The Messaging Engine writes the configuration for the send port to the message context in the adapter’s namespace before delivering the message to the adapter.</span></span> <span data-ttu-id="82e39-139">由适配器负责读取和验证该配置，并在以后使用该配置控制消息的传输。</span><span class="sxs-lookup"><span data-stu-id="82e39-139">It is the adapters’ responsibility to read and validate the configuration, which it subsequently uses to control the transmission of the message.</span></span> <span data-ttu-id="82e39-140">对于支持成批发送的发送适配器，发往不同发送端口的消息可能位于同一批中，因此，适配器需要处理这些“混合”批。</span><span class="sxs-lookup"><span data-stu-id="82e39-140">For send adapters that support batched sends, messages destined for different send ports may be in the same batch, so the adapter needs to handle these "mixed" batches.</span></span>  
  
 <span data-ttu-id="82e39-141">下面的代码段演示如何读取**OutboundTransportLocation**发送端口的 URI。</span><span class="sxs-lookup"><span data-stu-id="82e39-141">The following code fragment illustrates how to read the **OutboundTransportLocation** that is the URI for the send port.</span></span> <span data-ttu-id="82e39-142">它还演示了如何读取包含适配器的配置的 XML blob，然后读取单独的属性。</span><span class="sxs-lookup"><span data-stu-id="82e39-142">It also shows how to read the XML blob containing the adapter's configuration and then read the individual properties.</span></span>  
  
```  
...  
 private static readonly PropertyBase UriProperty =   
 new BTS.OutboundTransportLocation();  
  
 private string propertyNamespace =   
  "http://schemas.mySchemas.com/MyAdapter/myadapter-properties";  
private string uri;  
private string headers;  
private int timeOut = 1000;  
  
private void ReadSendPortConfig(IBaseMessage msg)  
{  
// Read the OutboundTransportLocation,   
 // i.e. the send port uri....  
uri = (string)msg.Context.Read(  
 UriProperty.Name.Name, UriProperty.Name.Namespace);  
  
// Read the adapters configuration Xml blob from   
 // the message...  
XmlDocument locationConfigDom = null;  
object obj = msg.Context.Read(  
 "AdapterConfig", this.propertyNamespace);  
  
// If this is a dynamic send there will not be   
 // any configuration...  
if ( null != obj )  
{  
locationConfigDom = new XmlDocument();  
locationConfigDom.LoadXml((string)obj);  
  
this.headers = Extract(  
 locationConfigDom, "/Config/headers", true);  
  
 this.timeOut = ExtractInt32(  
 locationConfigDom, "/Config/timeOut", true);  
}  
}  
  
 // Helper method to XPath string properties...  
private static string Extract(  
 XmlDocument document, string path, bool required)  
{  
XmlNode node = document.SelectSingleNode(path);  
if (!required && null == node)  
return String.Empty;  
if (null == node)  
throw new ApplicationException(string.Format(  
 "No property was found at {0}", path));  
return node.InnerText;  
}  
  
  // Helper method to XPath int32 properties...  
private static int ExtractInt32(  
 XmlDocument document, string path, bool required)  
{  
string s = Extract(document, path, required);  
return int.Parse(s);  
}   
```  
  
 <span data-ttu-id="82e39-143">**实现提示：**适配器通常应使用**OutboundTransportLocation**消息上下文属性来确定要将消息发送到的地址。</span><span class="sxs-lookup"><span data-stu-id="82e39-143">**Implementation Tip:** Adapters should in general use the **OutboundTransportLocation** message context property to determine the address to send the message to.</span></span> <span data-ttu-id="82e39-144">这样做之后，适配器可以一致地处理对静态和动态发送的传输，</span><span class="sxs-lookup"><span data-stu-id="82e39-144">By doing this the adapter can handle transmissions to both static and dynamic sends consistently.</span></span> <span data-ttu-id="82e39-145">并且还可以简化对生产绑定文件中地址的修改。</span><span class="sxs-lookup"><span data-stu-id="82e39-145">This also simplifies the modification of addresses in production binding files.</span></span>  
  
## <a name="xsd"></a><span data-ttu-id="82e39-146">XSD</span><span class="sxs-lookup"><span data-stu-id="82e39-146">XSD</span></span>  
 <span data-ttu-id="82e39-147">SDK 文件适配器示例中包括的四个 XSD 文件主要句柄适配器配置： ReceiveHandler.xsd、 ReceiveLocation.xsd、 TransmitLocation.xsd 和 TransmitHandler.xsd。</span><span class="sxs-lookup"><span data-stu-id="82e39-147">Four XSD files included in the SDK File Adapter sample primarily handle adapter configuration: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd, and TransmitHandler.xsd.</span></span>  
  
 <span data-ttu-id="82e39-148">下面的主题介绍上述各个文件以及如何对它们进行修改。</span><span class="sxs-lookup"><span data-stu-id="82e39-148">The following topics discuss each of these files and describe how you can modify them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82e39-149">本节内容</span><span class="sxs-lookup"><span data-stu-id="82e39-149">In This Section</span></span>  
  
-   [<span data-ttu-id="82e39-150">正在验证适配器配置</span><span class="sxs-lookup"><span data-stu-id="82e39-150">Validating the Adapter Configuration</span></span>](../core/validating-the-adapter-configuration.md)  
  
-   [<span data-ttu-id="82e39-151">注册的适配器</span><span class="sxs-lookup"><span data-stu-id="82e39-151">Registering an Adapter</span></span>](../core/registering-an-adapter.md)  
  
-   [<span data-ttu-id="82e39-152">适配器 Framework 配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="82e39-152">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [<span data-ttu-id="82e39-153">受支持的适配器 XSD 元素类型</span><span class="sxs-lookup"><span data-stu-id="82e39-153">Supported Adapter XSD Element Types</span></span>](../core/supported-adapter-xsd-element-types.md)  
  
-   [<span data-ttu-id="82e39-154">适配器 XSD 元素属性构造</span><span class="sxs-lookup"><span data-stu-id="82e39-154">Adapter XSD Element-Attribute Constructs</span></span>](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [<span data-ttu-id="82e39-155">适配器 XSD 数据类型方面构造</span><span class="sxs-lookup"><span data-stu-id="82e39-155">Adapter XSD Data Type-Facet Constructs</span></span>](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [<span data-ttu-id="82e39-156">适配器的高级的配置组件</span><span class="sxs-lookup"><span data-stu-id="82e39-156">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)