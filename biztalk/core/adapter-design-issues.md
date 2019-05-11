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
# <a name="adapter-design-issues"></a>适配器设计问题
当用户在设计时进行配置更改时，将单一登录 (SSO) 数据库中存储适配器配置。 在运行时，消息引擎检索适配器的配置，并将其传送到适配器。 四种类型的配置信息将传送到适配器：  
  
-   接收处理程序配置  
  
-   接收位置 （终结点） 配置  
  
-   发送处理程序配置  
  
-   发送位置 （终结点） 配置  
  
## <a name="receive-and-send-handler-configuration"></a>接收和发送处理程序配置  
 适配器处理程序配置传递到适配器在其实现的可选**IPersistPropertyBag**。**负载**接口。 处理程序配置为仅发送一次，因此如果已启动 BizTalk 服务后更改适配器处理程序配置该适配器不会更新。 常见的模型是使适配器将处理程序配置为默认配置中;终结点配置将覆盖在每个终结点的基础上的处理程序配置。  
  
 下面的代码段演示了对配置的解析。 适配器的配置是在属性中传递给**负载**字符串属性中调用**AdapterConfig**。 此属性的值包含 XML 文档，表示适配器的配置。 适配器需要将此配置加载到文档对象模型 (DOM) 或 XML 读取器和使用 XPath 来检索各个属性。  
  
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
 接收位置配置信息传递到其实现上的适配器**IBTTransportConfig**。 此接口包含三个方法**AddReceiveEndpoint**， **UpdateEndpointConfig**，并**RemoveReceiveEndpoint**。 消息引擎通知的适配器它需要哪些终结点侦听接收消息。 更改的单个终结点的配置时该终结点的更改通知适配器。 这是与之相反的处理程序配置发生更改时将不通知适配器。 同样，适配器不需要处理服务时段，因为 BizTalk Server 将添加或删除服务时段变得活动或非活动终结点。  
  
### <a name="addreceiveendpoint"></a>AddReceiveEndpoint  
 适配器需要开始侦听的终结点，则引擎将调用**IBTTransportConfig.AddReceiveEndpoint**传入接收位置的 URI，包含该终结点的适配器的配置的属性包和包含该终结点的特定于 BizTalk Server 的配置的第二个属性包。 适配器需要将此 URI 写入消息上下文为 BizTalk Server 系统属性**InboundTransportLocation**。  
  
 从适配器的属性包读取接收位置属性等同于读取处理程序配置与上面详细介绍。 传递到适配器的 BizTalk Server 配置包含一个属性， **TwoWayReceivePort**，指示此端口是单向还是双向。 下面的代码段演示了如何评估是否接收端口从 BizTalk Server 属性包是单向还是双向：  
  
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
 接收活动配置时，可以更改位置，该引擎使用**UpdateEndpointConfig** API 来通知适配器它需要使用不同的配置。 所有配置传送到适配器，包括特定于 BizTalk Server 的配置。  
  
### <a name="removereceiveendpoint"></a>RemoveReceiveEndpoint  
 当接收位置不再处于活动状态时，通过通知适配器**RemoveReceiveEndpoint**。 从适配器返回后**RemoveReceiveEndpoint**不再允许使用该 URI 将消息提交到引擎中。  
  
## <a name="send-port-configuration"></a>发送端口配置  
 消息引擎将消息传递到适配器前将发送端口的配置写入到的消息上下文中适配器的命名空间。 它是由适配器负责读取和验证配置，并在以后使用控制消息的传输。 为发送支持批处理的适配器，将消息发送发往不同发送端口可能是在同一个批处理，因此适配器需要处理这些"混合"批。  
  
 下面的代码段演示了如何读取**OutboundTransportLocation**发送端口的 URI。 它还演示如何读取包含适配器的配置的 XML blob，然后读取单独的属性。  
  
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
  
 **实现提示：** 适配器通常应使用**OutboundTransportLocation**消息上下文属性来确定将消息发送到的地址。 通过执行此操作，适配器可以句柄传输到这两个静态和动态发送的一致。 这还简化了生产绑定文件中的地址的修改。  
  
## <a name="xsd"></a>XSD  
 SDK 文件适配器示例中包含的四个 XSD 文件主要用于处理适配器配置：ReceiveHandler.xsd、 ReceiveLocation.xsd、 TransmitLocation.xsd 和 TransmitHandler.xsd。  
  
 下列主题讨论每个文件，并描述如何修改它们。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [验证适配器配置](../core/validating-the-adapter-configuration.md)  
  
-   [注册适配器](../core/registering-an-adapter.md)  
  
-   [适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [支持的适配器 XSD 元素类型](../core/supported-adapter-xsd-element-types.md)  
  
-   [适配器 XSD 元素-属性构造](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [适配器 XSD 数据类型-Facet 构造](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)