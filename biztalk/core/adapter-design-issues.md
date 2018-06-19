---
title: 适配器设计问题 |Microsoft 文档
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
ms.openlocfilehash: 79c6228db8342f3d1ad2628d4e4caf418efd9b29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226557"
---
# <a name="adapter-design-issues"></a>适配器设计问题
在用户在设计时对配置进行更改后，适配器配置存储于单一登录 (SSO) 数据库中。 在运行时，消息引擎检索适配器的配置并将配置传送到适配器。 四种类型的配置信息将传送到适配器：  
  
-   接收处理程序配置  
  
-   接收位置（终结点）配置  
  
-   发送处理程序配置  
  
-   发送位置（终结点）配置  
  
## <a name="receive-and-send-handler-configuration"></a>接收和发送处理程序配置  
 适配器的处理程序配置传递到其实现的可选上的适配器**IPersistPropertyBag**。**负载**接口。 处理程序配置只传送一次，因此，如果在 BizTalk 服务已启动后更改适配器处理程序配置，则不更新适配器。 常见的模型是使适配器将处理程序配置视作默认配置，终结点配置将基于各终结点重写该处理程序配置。  
  
 以下代码段说明了对配置的解析。 正在传入到中的属性的适配器的配置**负载**字符串属性中调用**AdapterConfig**。 该属性值包含表示适配器的配置的 XML 文档。 适配器需要将此配置加载到文档对象模型 (DOM) 或 XML 阅读器中，并且使用 XPath 来检索单独的属性。  
  
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
  
## <a name="receive-location-configuration"></a>接收位置配置  
 接收位置配置信息传递到其实现上的适配器**IBTTransportConfig**。 此接口包含三个方法**AddReceiveEndpoint**， **UpdateEndpointConfig**，和**RemoveReceiveEndpoint**。 消息引擎通知适配器它需要侦听哪些终结点以接收消息。 在更改某一单独终结点的配置时，将通知适配器对该终结点进行了更改。 与之相反的是，不通知适配器对处理程序配置的更改。 同样，适配器并不需要处理服务时段，因为 BizTalk Server 将在服务时段变得活动或不活动时添加或删除终结点。  
  
### <a name="addreceiveendpoint"></a>AddReceiveEndpoint  
 当适配器需要以开始侦听终结点，则引擎将调用上**IBTTransportConfig.AddReceiveEndpoint**接收位置的 URI，其中包含该终结点的适配器的配置属性包中传递和第二个的属性包，其中包含为该终结点的特定于 BizTalk Server 的配置。 适配器需要作为 BizTalk 服务器系统属性的消息上下文中写入 URI **InboundTransportLocation**。  
  
 从适配器的属性包读取接收位置属性的过程与上面详细介绍的读取处理程序配置的过程相同。 传递到该适配器的 BizTalk Server 配置包含单个属性， **TwoWayReceivePort**，指示端口是单向或双向。 下面的代码段演示了如何从 BizTalk Server 属性包计算接收端口是单向的还是双向的：  
  
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
  
### <a name="updateendpointconfig"></a>UpdateEndpointConfig  
 当活动的配置接收更改位置，则引擎会使用**UpdateEndpointConfig** API 来通知该适配器，它需要使用不同的配置。 所有配置都传送到适配器，包括特定于 BizTalk Server 的配置。  
  
### <a name="removereceiveendpoint"></a>RemoveReceiveEndpoint  
 当接收位置不再处于活动状态时，该适配器将通知通过**RemoveReceiveEndpoint**。 从适配器返回后**RemoveReceiveEndpoint**不再允许使用该 URI 引擎提交消息。  
  
## <a name="send-port-configuration"></a>发送端口配置  
 消息引擎在将消息传送到适配器之前，将发送端口的配置写入适配器的命名空间的消息上下文中。 由适配器负责读取和验证该配置，并在以后使用该配置控制消息的传输。 对于支持成批发送的发送适配器，发往不同发送端口的消息可能位于同一批中，因此，适配器需要处理这些“混合”批。  
  
 下面的代码段演示如何读取**OutboundTransportLocation**发送端口的 URI。 它还演示了如何读取包含适配器的配置的 XML blob，然后读取单独的属性。  
  
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
  
 **实现提示：** 适配器通常应使用**OutboundTransportLocation**消息上下文属性来确定要将消息发送到的地址。 这样做之后，适配器可以一致地处理对静态和动态发送的传输， 并且还可以简化对生产绑定文件中地址的修改。  
  
## <a name="xsd"></a>XSD  
 SDK 文件适配器示例中包括的四个 XSD 文件主要句柄适配器配置： ReceiveHandler.xsd、 ReceiveLocation.xsd、 TransmitLocation.xsd 和 TransmitHandler.xsd。  
  
 下面的主题介绍上述各个文件以及如何对它们进行修改。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [正在验证适配器配置](../core/validating-the-adapter-configuration.md)  
  
-   [注册的适配器](../core/registering-an-adapter.md)  
  
-   [适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [受支持的适配器 XSD 元素类型](../core/supported-adapter-xsd-element-types.md)  
  
-   [适配器 XSD 元素属性构造](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [适配器 XSD 数据类型方面构造](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [适配器的高级的配置组件](../core/advanced-configuration-components-for-adapters.md)