---
title: 使用 WCF LOB 适配器 SDK 开发最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 469464edec3ca22a63ee5185a4371cb77c962cb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363654"
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 开发最佳做法
使用本主题中的最佳实践，以提高应用程序和适配器。  

## <a name="call-abort-before-close-on-channel-exception"></a>调用中止前关闭通道异常  
 在编写使用 WCF 通道模型的应用程序时，应调用`IRequestChannel.Abort`之前调用`ChannelFactory.Close`。 如果没有，`ChannelFactory.Close`将引发异常。  

 在以下示例中，通道操作尝试在 try/catch 块内。 如果发生异常，通道处于中止状态。  

```csharp  
ChannelFactory<IRequestChannel> cf = new  ChannelFactory<IRequestChannel>();  
IRequestChannel channel = null;  
try  
{  
  cf.Open();  
  channel = cf.CreateChannel();  
  channel.Open();  
  channel.Request();// This causes the channel to go into a faulted state.  
  channel.Close();  
}  
catch (Exception e)  
{  
  // Abort the channel if we have one  
  if(channel != null)  
    channel.Abort();  
}  
finally  
{  
  if (cf.State == CommunicationState.Opened)  
  {  
    cf.Close(); // It throws an exception that the channel is in a faulted state.  
  }  
}  
```  

## <a name="implement-both-asynchronous-and-synchronous-handlers"></a>实现异步和同步处理程序  
 如果可能，请在您的适配器中实现异步和同步处理程序。 如果您的适配器只实现同步调用，可能会处理大量的消息或在多线程环境中使用该适配器时遇到的障碍。  

## <a name="use-connection-pooling"></a>使用连接池  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]支持连接池默认情况下。 但是，它是由适配器开发人员确定哪些连接池将公开为绑定属性的属性。 可用的连接池设置中定义`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`。  

 中没有选项[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]轻松公开这些属性作为适配器的连接属性。 在适配器实现，适配器开发人员必须手动定义的属性。  

```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  

## <a name="ensure-that-the-adapter-supports-two-way-operations"></a>请确保该适配器支持双向操作  
 如果从 BizTalk Server 调用您的适配器，则它必须支持双向操作，即使返回值为 void。 这是因为 BizTalk Server 需要从任何传出的请求，返回的响应，如果您的适配器仅实现单向操作，将引发异常。  

 下面是返回 void 的请求-响应协定的示例。  

```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  

## <a name="implement-tracing"></a>实现跟踪  
 在开发周期中，这不看起来可能必须将跟踪添加到您的适配器，因为可以单步执行代码并调试任何问题。 但是，在生产环境中安装适配器后，您可能不能以使用运行时调试来隔离问题。 如果在您的适配器已启用跟踪，它可以用于隔离故障的发生位置。  

 请参阅[跟踪使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md)的更多详细信息。  

## <a name="use-uri-properties-for-frequently-changed-settings"></a>使用 URI 属性的频繁更改的设置  
 在决定是否要将自定义属性公开为绑定或 URI 属性，建议使用 URI 属性，如果经常更改值。 绑定属性应该很少更改的值为保留。  

 示例绑定属性将为所有连接都使用的数据库服务器名称。 示例 URI 属性是特定的表或存储的过程，供该特定连接。  

## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a>不在 URI 中传递的用户名或密码值  
 如果您的适配器需要调用方的凭据，则建议使用**ClientCredentials**类检索凭据值而不是作为 URI 的一部分传递客户端凭据。 **ClientCredentials**类是用于将凭据信息从客户端传递到该服务，以更安全的方式的 WCF 的标准功能。 作为 URI 字符串的一部分传递的用户信息可能会使在传输过程中的用户信息。  

 下表中显示的传递凭据的建议的方法。  


|      方法       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    设计时    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                当使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，可以指定的适配器支持的客户端凭据类型。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     运行的时      | 使用时生成的.NET CLR 代理，你可以以编程方式设置客户端凭据。<br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> 或者，如果你需要直接与通道进行交互，您可以使用 WCF 通道模型来创建通道工厂时指定的客户端凭据。<br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();` |
| WCF 配置 |                                                                                                                                                                                                                                               在客户端配置文件中添加\<endpointBehaviors\>包含的元素\<clientCredentials\>。<br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`                                                                                                                                                                                                                                               |
|   使用 BizTalk   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 在使用 WCF 适配器以使用您的适配器，你可以添加**clientCredentials**上的行为扩展**行为**选项卡。这添加后，你可以设置所需的客户端凭据中的终结点行为。                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a>不会返回同时 StrongDataSetType 和 WeakDataSetType  
 如果您的适配器返回`DataSet`，可以使用两种`Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A`或`Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`，但不要同时在同一时间使用。 根节点名称和命名空间生成这两种类型的相同，并且不能同时存在于 WSDL。  

 虽然`WeakDataSetType`并`StrongDataSetType`二者都表示`System.Data.DataSet`，`StrongDataSetType`更轻松地在.NET 应用程序中使用，因为生成的代理显示为`System.Data.Dataset`。 生成的代理`WeakDataSetType`是`XmlElement[]`，这是在.NET 应用程序中使用的难度。  BizTalk Server 不能使用从返回的架构`StrongDataSet`，但无法使用`WeakDataSetType`。  

> [!NOTE]
>  `StrongDataSetType` 和`WeakDataSetType`仅控制客户端应用程序如何解释适配器传递的 XML 消息。 XML 消息是相同的而不考虑该指定类型。  

> [!NOTE]
>  返回时`StrongDataSetType`，则必须设置`Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A`到`false`。 如果设置为`true`，默认情况下，`XmlSchemaSet::Compile`调用中以确保在 WSDL 中没有任何错误的适配器，但是架构生成`StrongDataSetType`生成中的异常`XmlSchemaSet`。  
>   
>  设置`CompileWsdl`到`false`将绕过代理生成期间出现 WSDL 架构验证中的适配器和验证。  可以生成两个代理，则 svcutil.exe 之类的实用工具`StrongDataSetType`和`WeakDataSetType`。  

 若要使用 BizTalk 和.NET 环境，请考虑实施允许由环境所规定的两个返回类型之间进行切换的绑定属性。  

```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  

## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a>BizTalk Server 中创建有意义的 XSD 架构名称  
 使用时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]设计时工具在您的 BizTalk 项目中生成的 XSD 架构的名称创建使用`DefaultXsdFileNamePrefix`属性， `fileNameHint` WSDL 中的批注，如果需要，唯一的整数值。  

 例如，如果`DefaultXsdFileNamePrefix`设置为"MyAdapter"和`fileNameHint`批注设置为"Stream"中，创建的 XSD 架构命名为 MyAdapterStream.xsd。  

```  
<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
<xs:annotation>  
<xs:appinfo>  
<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
</xs:appinfo>  
</xs:annotation>  
<xs:simpleType name='StreamBody'>  
<xs:restriction base='xs:base64Binary' />  
</xs:simpleType>  
</xs:schema>  

```  

> [!NOTE]
>  默认值`DefaultXsdFileNamePrefix`是绑定的名称。 若要指定不同的值，请重写`DefaultXsdFileNamePrefix`适配器的类中派生自`Microsoft.ServiceModel.Channels.Common.AdapterBinding`。  

 有两个可能的方法来添加`fileNameHint`到架构的批注： 重写导出...架构上 OperationMetadata\TypeMetadata 或重写适配器的 IWsdlRetrieval 实现的方法。 对于任一方法，可以调用基实现，并将批注添加到架构集合中的架构。  

> [!NOTE]
>  重写导出时...架构方法可能有多个操作/类型定义中相同的架构;适配器应确保多次出现`fileNameHints`中相同的架构的批注不会发生冲突。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]使用的第一个匹配项`fileNameHint`如果它在架构中出现多次。  

 在以下示例中，IWsdlRetrieval 用于添加`fileNameHint`到 WSDL 批注。  

```csharp  
sealed class MyAdapterWsdlRetrieval : IWsdlRetrieval  
{  
   IWsdlRetrieval mBaseWsdlRetrieval;  
   public MyAdapterWsdlRetrieval(IWsdlRetrieval baseWsdlRetrieval)  
   {  
      mBaseWsdlRetrieval = baseWsdlRetrieval;  
   }  

   ServiceDescription IWsdlRetrieval.GetWsdl(Microsoft.ServiceModel.Channels.MetadataRetrievalNode[] nodes, Uri uri, TimeSpan timeout)  
   {  
      ServiceDescription baseDesc = mBaseWsdlRetrieval.GetWsdl(nodes, uri, timeout);  
      foreach (XmlSchema schema in baseDesc.Types.Schemas)  
      {  
         CreateFileNameHint(schema);  
      }  
      return baseDesc;  
   }  

   void CreateFileNameHint(XmlSchema schema)  
   {  
      string targetNamespace = schema.TargetNamespace;  
      if (string.IsNullOrEmpty(targetNamespace))  
         return;  
      string fileNameHint = null;  
      //determine the filename based on namespace  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadaptpter/HelloWorld"))  
      {  
         fileNameHint = "HelloWorld";  
      }  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadapter/Hello"))  
      {  
         fileNameHint = "Hello";  
      }  
      //create the annotation and populate it with fileNameHint  
      XmlSchemaAnnotation annotation = new XmlSchemaAnnotation();  
      XmlSchemaAppInfo appInfo = new XmlSchemaAppInfo();  
      XmlDocument doc = new XmlDocument();  
      XmlNode[] fileNameHintNodes = new XmlNode[1];  
      fileNameHintNodes[0] = doc.CreateElement(null, "fileNameHint", "http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd");  
      fileNameHintNodes[0].AppendChild(doc.CreateTextNode(fileNameHint));  
      appInfo.Markup = fileNameHintNodes;  
      annotation.Items.Add(appInfo);  
      schema.Items.Insert(0, annotation);  
   }  
```  

## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a>在处理期间不修改 AdapterEnvironmentSettings  
 应仅设置适配器**AdapterEnvironmentSettings**， **ConnectionPoolManager**， **ConnectionPool**，和**CommonCacheSize**适配器初始化期间，应尝试进行修改的正在运行的实例的值。  

 如果当前正在运行的适配器实例上修改这些设置，这可能会导致覆盖配置设置为当前正在执行的连接的新连接。  

## <a name="see-also"></a>请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)