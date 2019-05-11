---
title: 适配器设计问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e5568be-a046-40ff-a94a-eda086457564
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c6b99ff1416ace11c11d07dc9b137b5e33a231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361575"
---
# <a name="adapter-design-issues"></a><span data-ttu-id="2d659-102">适配器设计问题</span><span class="sxs-lookup"><span data-stu-id="2d659-102">Adapter Design Issues</span></span>
<span data-ttu-id="2d659-103">当用户在设计时进行配置更改时，将单一登录 (SSO) 数据库中存储适配器配置。</span><span class="sxs-lookup"><span data-stu-id="2d659-103">Adapter configuration is stored in the Single Sign-On (SSO) database when the user makes configuration changes during design time.</span></span> <span data-ttu-id="2d659-104">在运行时，消息引擎检索适配器的配置，并将其传送到适配器。</span><span class="sxs-lookup"><span data-stu-id="2d659-104">At run time the Messaging Engine retrieves the adapter's configuration and delivers it to the adapter.</span></span> <span data-ttu-id="2d659-105">四种类型的配置信息将传送到适配器：</span><span class="sxs-lookup"><span data-stu-id="2d659-105">Four types of configuration information are delivered to adapters:</span></span>  
  
-   <span data-ttu-id="2d659-106">接收处理程序配置</span><span class="sxs-lookup"><span data-stu-id="2d659-106">Receive handler configuration</span></span>  
  
-   <span data-ttu-id="2d659-107">接收位置 （终结点） 配置</span><span class="sxs-lookup"><span data-stu-id="2d659-107">Receive location (endpoint) configuration</span></span>  
  
-   <span data-ttu-id="2d659-108">发送处理程序配置</span><span class="sxs-lookup"><span data-stu-id="2d659-108">Send handler configuration</span></span>  
  
-   <span data-ttu-id="2d659-109">发送位置 （终结点） 配置</span><span class="sxs-lookup"><span data-stu-id="2d659-109">Send location (endpoint) configuration</span></span>  
  
## <a name="receive-and-send-handler-configuration"></a><span data-ttu-id="2d659-110">接收和发送处理程序配置</span><span class="sxs-lookup"><span data-stu-id="2d659-110">Receive and Send Handler Configuration</span></span>  
 <span data-ttu-id="2d659-111">适配器处理程序配置传递到适配器在其实现的可选**IPersistPropertyBag**。**负载**接口。</span><span class="sxs-lookup"><span data-stu-id="2d659-111">An adapter's handler configuration is delivered to the adapter on its implementation of the optional **IPersistPropertyBag**.**Load** interface.</span></span> <span data-ttu-id="2d659-112">处理程序配置为仅发送一次，因此如果已启动 BizTalk 服务后更改适配器处理程序配置该适配器不会更新。</span><span class="sxs-lookup"><span data-stu-id="2d659-112">The handler configuration is delivered only once, so if the adapter handler configuration is changed after the BizTalk service has started the adapter is not updated.</span></span> <span data-ttu-id="2d659-113">常见的模型是使适配器将处理程序配置为默认配置中;终结点配置将覆盖在每个终结点的基础上的处理程序配置。</span><span class="sxs-lookup"><span data-stu-id="2d659-113">The common model is for the adapter to treat the handler configuration as the default configuration; endpoint configuration overrides the handler configuration on a per-endpoint basis.</span></span>  
  
 <span data-ttu-id="2d659-114">下面的代码段演示了对配置的解析。</span><span class="sxs-lookup"><span data-stu-id="2d659-114">The following code fragment demonstrates parsing the configuration.</span></span> <span data-ttu-id="2d659-115">适配器的配置是在属性中传递给**负载**字符串属性中调用**AdapterConfig**。</span><span class="sxs-lookup"><span data-stu-id="2d659-115">The adapter's configuration is in the property passed in to the **Load** call in the string property **AdapterConfig**.</span></span> <span data-ttu-id="2d659-116">此属性的值包含 XML 文档，表示适配器的配置。</span><span class="sxs-lookup"><span data-stu-id="2d659-116">This property value contains an XML document representing the adapter's configuration.</span></span> <span data-ttu-id="2d659-117">适配器需要将此配置加载到文档对象模型 (DOM) 或 XML 读取器和使用 XPath 来检索各个属性。</span><span class="sxs-lookup"><span data-stu-id="2d659-117">The adapter needs to load this configuration into a document object model (DOM) or an XML reader and use XPath to retrieve the individual properties.</span></span>  
  
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
  
## <a name="receive-location-configuration"></a><span data-ttu-id="2d659-118">接收位置配置</span><span class="sxs-lookup"><span data-stu-id="2d659-118">Receive Location Configuration</span></span>  
 <span data-ttu-id="2d659-119">接收位置配置信息传递到其实现上的适配器**IBTTransportConfig**。</span><span class="sxs-lookup"><span data-stu-id="2d659-119">Receive location configuration information is delivered to an adapter on its implementation of **IBTTransportConfig**.</span></span> <span data-ttu-id="2d659-120">此接口包含三个方法**AddReceiveEndpoint**， **UpdateEndpointConfig**，并**RemoveReceiveEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="2d659-120">This interface contains the three methods **AddReceiveEndpoint**, **UpdateEndpointConfig**, and **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="2d659-121">消息引擎通知的适配器它需要哪些终结点侦听接收消息。</span><span class="sxs-lookup"><span data-stu-id="2d659-121">The Messaging Engine notifies the adapter of which endpoints it needs to listen on to receive messages.</span></span> <span data-ttu-id="2d659-122">更改的单个终结点的配置时该终结点的更改通知适配器。</span><span class="sxs-lookup"><span data-stu-id="2d659-122">When the configuration for an individual endpoint is changed the adapter is notified of the change for that endpoint.</span></span> <span data-ttu-id="2d659-123">这是与之相反的处理程序配置发生更改时将不通知适配器。</span><span class="sxs-lookup"><span data-stu-id="2d659-123">This is in contrast to the fact that when handler configuration changes the adapter is not notified.</span></span> <span data-ttu-id="2d659-124">同样，适配器不需要处理服务时段，因为 BizTalk Server 将添加或删除服务时段变得活动或非活动终结点。</span><span class="sxs-lookup"><span data-stu-id="2d659-124">Similarly, the adapter does not need to handle service windows because BizTalk Server adds or removes endpoints as service windows become active or inactive.</span></span>  
  
### <a name="addreceiveendpoint"></a><span data-ttu-id="2d659-125">AddReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="2d659-125">AddReceiveEndpoint</span></span>  
 <span data-ttu-id="2d659-126">适配器需要开始侦听的终结点，则引擎将调用**IBTTransportConfig.AddReceiveEndpoint**传入接收位置的 URI，包含该终结点的适配器的配置的属性包和包含该终结点的特定于 BizTalk Server 的配置的第二个属性包。</span><span class="sxs-lookup"><span data-stu-id="2d659-126">When an adapter needs to begin listening on an endpoint, the engine calls **IBTTransportConfig.AddReceiveEndpoint** passing in the receive location's URI, a property bag containing the adapter's configuration for that endpoint, and a second property bag containing BizTalk Server-specific configuration for that endpoint.</span></span> <span data-ttu-id="2d659-127">适配器需要将此 URI 写入消息上下文为 BizTalk Server 系统属性**InboundTransportLocation**。</span><span class="sxs-lookup"><span data-stu-id="2d659-127">The adapter needs to write the URI to the message context as the BizTalk Server system property **InboundTransportLocation**.</span></span>  
  
 <span data-ttu-id="2d659-128">从适配器的属性包读取接收位置属性等同于读取处理程序配置与上面详细介绍。</span><span class="sxs-lookup"><span data-stu-id="2d659-128">Reading the receive location properties from the adapter's property bag is the same as reading the handler configuration as detailed above.</span></span> <span data-ttu-id="2d659-129">传递到适配器的 BizTalk Server 配置包含一个属性， **TwoWayReceivePort**，指示此端口是单向还是双向。</span><span class="sxs-lookup"><span data-stu-id="2d659-129">The BizTalk Server configuration passed into the adapter contains a single property, **TwoWayReceivePort**, which indicates whether the port is one-way or two-way.</span></span> <span data-ttu-id="2d659-130">下面的代码段演示了如何评估是否接收端口从 BizTalk Server 属性包是单向还是双向：</span><span class="sxs-lookup"><span data-stu-id="2d659-130">The following code fragment illustrates how to evaluate if the receive port is one-way or two-way from the BizTalk Server property bag:</span></span>  
  
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
  
### <a name="updateendpointconfig"></a><span data-ttu-id="2d659-131">UpdateEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="2d659-131">UpdateEndpointConfig</span></span>  
 <span data-ttu-id="2d659-132">接收活动配置时，可以更改位置，该引擎使用**UpdateEndpointConfig** API 来通知适配器它需要使用不同的配置。</span><span class="sxs-lookup"><span data-stu-id="2d659-132">When the configuration of an active receive location is changed, the engine uses the **UpdateEndpointConfig** API to notify the adapter that it needs to use a different configuration.</span></span> <span data-ttu-id="2d659-133">所有配置传送到适配器，包括特定于 BizTalk Server 的配置。</span><span class="sxs-lookup"><span data-stu-id="2d659-133">All of the configuration is delivered to the adapter, including the BizTalk Server-specific configuration.</span></span>  
  
### <a name="removereceiveendpoint"></a><span data-ttu-id="2d659-134">RemoveReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="2d659-134">RemoveReceiveEndpoint</span></span>  
 <span data-ttu-id="2d659-135">当接收位置不再处于活动状态时，通过通知适配器**RemoveReceiveEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="2d659-135">When a receive location is no longer active, the adapter is notified through **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="2d659-136">从适配器返回后**RemoveReceiveEndpoint**不再允许使用该 URI 将消息提交到引擎中。</span><span class="sxs-lookup"><span data-stu-id="2d659-136">After the adapter returns from **RemoveReceiveEndpoint** it is no longer allowed to use that URI to submit messages into the engine.</span></span>  
  
## <a name="send-port-configuration"></a><span data-ttu-id="2d659-137">发送端口配置</span><span class="sxs-lookup"><span data-stu-id="2d659-137">Send Port Configuration</span></span>  
 <span data-ttu-id="2d659-138">消息引擎将消息传递到适配器前将发送端口的配置写入到的消息上下文中适配器的命名空间。</span><span class="sxs-lookup"><span data-stu-id="2d659-138">The Messaging Engine writes the configuration for the send port to the message context in the adapter’s namespace before delivering the message to the adapter.</span></span> <span data-ttu-id="2d659-139">它是由适配器负责读取和验证配置，并在以后使用控制消息的传输。</span><span class="sxs-lookup"><span data-stu-id="2d659-139">It is the adapters’ responsibility to read and validate the configuration, which it subsequently uses to control the transmission of the message.</span></span> <span data-ttu-id="2d659-140">为发送支持批处理的适配器，将消息发送发往不同发送端口可能是在同一个批处理，因此适配器需要处理这些"混合"批。</span><span class="sxs-lookup"><span data-stu-id="2d659-140">For send adapters that support batched sends, messages destined for different send ports may be in the same batch, so the adapter needs to handle these "mixed" batches.</span></span>  
  
 <span data-ttu-id="2d659-141">下面的代码段演示了如何读取**OutboundTransportLocation**发送端口的 URI。</span><span class="sxs-lookup"><span data-stu-id="2d659-141">The following code fragment illustrates how to read the **OutboundTransportLocation** that is the URI for the send port.</span></span> <span data-ttu-id="2d659-142">它还演示如何读取包含适配器的配置的 XML blob，然后读取单独的属性。</span><span class="sxs-lookup"><span data-stu-id="2d659-142">It also shows how to read the XML blob containing the adapter's configuration and then read the individual properties.</span></span>  
  
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
  
 <span data-ttu-id="2d659-143">**实现提示：** 适配器通常应使用**OutboundTransportLocation**消息上下文属性来确定将消息发送到的地址。</span><span class="sxs-lookup"><span data-stu-id="2d659-143">**Implementation Tip:** Adapters should in general use the **OutboundTransportLocation** message context property to determine the address to send the message to.</span></span> <span data-ttu-id="2d659-144">通过执行此操作，适配器可以句柄传输到这两个静态和动态发送的一致。</span><span class="sxs-lookup"><span data-stu-id="2d659-144">By doing this the adapter can handle transmissions to both static and dynamic sends consistently.</span></span> <span data-ttu-id="2d659-145">这还简化了生产绑定文件中的地址的修改。</span><span class="sxs-lookup"><span data-stu-id="2d659-145">This also simplifies the modification of addresses in production binding files.</span></span>  
  
## <a name="xsd"></a><span data-ttu-id="2d659-146">XSD</span><span class="sxs-lookup"><span data-stu-id="2d659-146">XSD</span></span>  
 <span data-ttu-id="2d659-147">SDK 文件适配器示例中包含的四个 XSD 文件主要用于处理适配器配置：ReceiveHandler.xsd、 ReceiveLocation.xsd、 TransmitLocation.xsd 和 TransmitHandler.xsd。</span><span class="sxs-lookup"><span data-stu-id="2d659-147">Four XSD files included in the SDK File Adapter sample primarily handle adapter configuration: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd, and TransmitHandler.xsd.</span></span>  
  
 <span data-ttu-id="2d659-148">下列主题讨论每个文件，并描述如何修改它们。</span><span class="sxs-lookup"><span data-stu-id="2d659-148">The following topics discuss each of these files and describe how you can modify them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d659-149">本节内容</span><span class="sxs-lookup"><span data-stu-id="2d659-149">In This Section</span></span>  
  
-   [<span data-ttu-id="2d659-150">验证适配器配置</span><span class="sxs-lookup"><span data-stu-id="2d659-150">Validating the Adapter Configuration</span></span>](../core/validating-the-adapter-configuration.md)  
  
-   [<span data-ttu-id="2d659-151">注册适配器</span><span class="sxs-lookup"><span data-stu-id="2d659-151">Registering an Adapter</span></span>](../core/registering-an-adapter.md)  
  
-   [<span data-ttu-id="2d659-152">适配器框架配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="2d659-152">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [<span data-ttu-id="2d659-153">支持的适配器 XSD 元素类型</span><span class="sxs-lookup"><span data-stu-id="2d659-153">Supported Adapter XSD Element Types</span></span>](../core/supported-adapter-xsd-element-types.md)  
  
-   [<span data-ttu-id="2d659-154">适配器 XSD 元素-属性构造</span><span class="sxs-lookup"><span data-stu-id="2d659-154">Adapter XSD Element-Attribute Constructs</span></span>](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [<span data-ttu-id="2d659-155">适配器 XSD 数据类型-Facet 构造</span><span class="sxs-lookup"><span data-stu-id="2d659-155">Adapter XSD Data Type-Facet Constructs</span></span>](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [<span data-ttu-id="2d659-156">适配器的高级配置组件</span><span class="sxs-lookup"><span data-stu-id="2d659-156">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)