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
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="36fb7-102">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="36fb7-102">Development best practices using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="36fb7-103">使用本主题中的最佳实践，以提高应用程序和适配器。</span><span class="sxs-lookup"><span data-stu-id="36fb7-103">You can use the best practices in this topic to improve your applications and adapters.</span></span>  

## <a name="call-abort-before-close-on-channel-exception"></a><span data-ttu-id="36fb7-104">调用中止前关闭通道异常</span><span class="sxs-lookup"><span data-stu-id="36fb7-104">Call Abort Before Close on Channel Exception</span></span>  
 <span data-ttu-id="36fb7-105">在编写使用 WCF 通道模型的应用程序时，应调用`IRequestChannel.Abort`之前调用`ChannelFactory.Close`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-105">When you write an application that uses the WCF channel model, you should call `IRequestChannel.Abort` before calling `ChannelFactory.Close`.</span></span> <span data-ttu-id="36fb7-106">如果没有，`ChannelFactory.Close`将引发异常。</span><span class="sxs-lookup"><span data-stu-id="36fb7-106">If you do not, `ChannelFactory.Close` throws an exception.</span></span>  

 <span data-ttu-id="36fb7-107">在以下示例中，通道操作尝试在 try/catch 块内。</span><span class="sxs-lookup"><span data-stu-id="36fb7-107">In the following example, channel operations are attempted within a try/catch block.</span></span> <span data-ttu-id="36fb7-108">如果发生异常，通道处于中止状态。</span><span class="sxs-lookup"><span data-stu-id="36fb7-108">If an exception occurs, the channel is aborted.</span></span>  

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

## <a name="implement-both-asynchronous-and-synchronous-handlers"></a><span data-ttu-id="36fb7-109">实现异步和同步处理程序</span><span class="sxs-lookup"><span data-stu-id="36fb7-109">Implement Both Asynchronous and Synchronous Handlers</span></span>  
 <span data-ttu-id="36fb7-110">如果可能，请在您的适配器中实现异步和同步处理程序。</span><span class="sxs-lookup"><span data-stu-id="36fb7-110">If possible, implement both asynchronous and synchronous handlers in your adapter.</span></span> <span data-ttu-id="36fb7-111">如果您的适配器只实现同步调用，可能会处理大量的消息或在多线程环境中使用该适配器时遇到的障碍。</span><span class="sxs-lookup"><span data-stu-id="36fb7-111">If your adapter only implements synchronous calls, you may run into blocking issues when processing a large volume of messages or when the adapter is used in a multithreaded environment.</span></span>  

## <a name="use-connection-pooling"></a><span data-ttu-id="36fb7-112">使用连接池</span><span class="sxs-lookup"><span data-stu-id="36fb7-112">Use Connection Pooling</span></span>  
 <span data-ttu-id="36fb7-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]支持连接池默认情况下。</span><span class="sxs-lookup"><span data-stu-id="36fb7-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports connection pooling by default.</span></span> <span data-ttu-id="36fb7-114">但是，它是由适配器开发人员确定哪些连接池将公开为绑定属性的属性。</span><span class="sxs-lookup"><span data-stu-id="36fb7-114">However, it is up to the adapter developer to determine which connection pooling properties to expose as binding properties.</span></span> <span data-ttu-id="36fb7-115">可用的连接池设置中定义`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-115">The available Connection Pool settings are defined within `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`.</span></span>  

 <span data-ttu-id="36fb7-116">中没有选项[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]轻松公开这些属性作为适配器的连接属性。</span><span class="sxs-lookup"><span data-stu-id="36fb7-116">There are no options within the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to easily expose these properties as adapter connection properties.</span></span> <span data-ttu-id="36fb7-117">在适配器实现，适配器开发人员必须手动定义的属性。</span><span class="sxs-lookup"><span data-stu-id="36fb7-117">The adapter developer must manually define the properties in the adapter implementation.</span></span>  

```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  

## <a name="ensure-that-the-adapter-supports-two-way-operations"></a><span data-ttu-id="36fb7-118">请确保该适配器支持双向操作</span><span class="sxs-lookup"><span data-stu-id="36fb7-118">Ensure That the Adapter Supports Two-Way Operations</span></span>  
 <span data-ttu-id="36fb7-119">如果从 BizTalk Server 调用您的适配器，则它必须支持双向操作，即使返回值为 void。</span><span class="sxs-lookup"><span data-stu-id="36fb7-119">If your adapter is called from BizTalk Server, it must support two-way operations, even if the return value is void.</span></span> <span data-ttu-id="36fb7-120">这是因为 BizTalk Server 需要从任何传出的请求，返回的响应，如果您的适配器仅实现单向操作，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="36fb7-120">This is because BizTalk Server expects a response returned from any outgoing request, and throws an exception if your adapter only implements one-way operations.</span></span>  

 <span data-ttu-id="36fb7-121">下面是返回 void 的请求-响应协定的示例。</span><span class="sxs-lookup"><span data-stu-id="36fb7-121">Here is an example of a request-response contract that returns void.</span></span>  

```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  

## <a name="implement-tracing"></a><span data-ttu-id="36fb7-122">实现跟踪</span><span class="sxs-lookup"><span data-stu-id="36fb7-122">Implement Tracing</span></span>  
 <span data-ttu-id="36fb7-123">在开发周期中，这不看起来可能必须将跟踪添加到您的适配器，因为可以单步执行代码并调试任何问题。</span><span class="sxs-lookup"><span data-stu-id="36fb7-123">During the development cycle, it might not seem important to add tracing to your adapter, since you can step through the code and debug any problems.</span></span> <span data-ttu-id="36fb7-124">但是，在生产环境中安装适配器后，您可能不能以使用运行时调试来隔离问题。</span><span class="sxs-lookup"><span data-stu-id="36fb7-124">However, once the adapter is installed in a production environment, you might not be able to use run-time debugging to isolate problems.</span></span> <span data-ttu-id="36fb7-125">如果在您的适配器已启用跟踪，它可以用于隔离故障的发生位置。</span><span class="sxs-lookup"><span data-stu-id="36fb7-125">If you have enabled tracing throughout your adapter, it can be used to isolate where failures are occurring.</span></span>  

 <span data-ttu-id="36fb7-126">请参阅[跟踪使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="36fb7-126">See [Trace an adapter with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md) for further details.</span></span>  

## <a name="use-uri-properties-for-frequently-changed-settings"></a><span data-ttu-id="36fb7-127">使用 URI 属性的频繁更改的设置</span><span class="sxs-lookup"><span data-stu-id="36fb7-127">Use URI Properties for Frequently Changed Settings</span></span>  
 <span data-ttu-id="36fb7-128">在决定是否要将自定义属性公开为绑定或 URI 属性，建议使用 URI 属性，如果经常更改值。</span><span class="sxs-lookup"><span data-stu-id="36fb7-128">When deciding whether to expose a custom property as a binding or URI property, it is recommended to use a URI property if the value changes often.</span></span> <span data-ttu-id="36fb7-129">绑定属性应该很少更改的值为保留。</span><span class="sxs-lookup"><span data-stu-id="36fb7-129">Binding properties should be reserved for values that rarely change.</span></span>  

 <span data-ttu-id="36fb7-130">示例绑定属性将为所有连接都使用的数据库服务器名称。</span><span class="sxs-lookup"><span data-stu-id="36fb7-130">An example binding property would be a database server name that is used by all connections.</span></span> <span data-ttu-id="36fb7-131">示例 URI 属性是特定的表或存储的过程，供该特定连接。</span><span class="sxs-lookup"><span data-stu-id="36fb7-131">An example URI property would be a specific table or stored procedure to be used by that specific connection.</span></span>  

## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a><span data-ttu-id="36fb7-132">不在 URI 中传递的用户名或密码值</span><span class="sxs-lookup"><span data-stu-id="36fb7-132">Do Not Pass User Name or Password Values in the URI</span></span>  
 <span data-ttu-id="36fb7-133">如果您的适配器需要调用方的凭据，则建议使用**ClientCredentials**类检索凭据值而不是作为 URI 的一部分传递客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="36fb7-133">If your adapter requires the caller’s credentials, it is recommended to use the **ClientCredentials** class to retrieve credential values instead of passing client credentials as part of the URI.</span></span> <span data-ttu-id="36fb7-134">**ClientCredentials**类是用于将凭据信息从客户端传递到该服务，以更安全的方式的 WCF 的标准功能。</span><span class="sxs-lookup"><span data-stu-id="36fb7-134">The **ClientCredentials** class is a standard feature of WCF that is intended for passing credential information from the client to the service in a more secure manner.</span></span> <span data-ttu-id="36fb7-135">作为 URI 字符串的一部分传递的用户信息可能会使在传输过程中的用户信息。</span><span class="sxs-lookup"><span data-stu-id="36fb7-135">Passing the user information as part of the URI string may expose the user information while in transit.</span></span>  

 <span data-ttu-id="36fb7-136">下表中显示的传递凭据的建议的方法。</span><span class="sxs-lookup"><span data-stu-id="36fb7-136">The recommended methods of passing credentials are shown in the following table.</span></span>  


|      <span data-ttu-id="36fb7-137">方法</span><span class="sxs-lookup"><span data-stu-id="36fb7-137">Method</span></span>       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              <span data-ttu-id="36fb7-138">Description</span><span class="sxs-lookup"><span data-stu-id="36fb7-138">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="36fb7-139">设计时</span><span class="sxs-lookup"><span data-stu-id="36fb7-139">Design time</span></span>    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                <span data-ttu-id="36fb7-140">当使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，可以指定的适配器支持的客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="36fb7-140">When using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you can specify the client credential types that the adapter supports.</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     <span data-ttu-id="36fb7-141">运行的时</span><span class="sxs-lookup"><span data-stu-id="36fb7-141">Run time</span></span>      | <span data-ttu-id="36fb7-142">使用时生成的.NET CLR 代理，你可以以编程方式设置客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="36fb7-142">When using a generated .NET CLR proxy, you can programmatically set the client credentials.</span></span><br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> <span data-ttu-id="36fb7-143">或者，如果你需要直接与通道进行交互，您可以使用 WCF 通道模型来创建通道工厂时指定的客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="36fb7-143">Alternatively, if you need to interact with the channel directly, you can use the WCF channel model to specify the client credentials when creating a channel factory.</span></span><br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();` |
| <span data-ttu-id="36fb7-144">WCF 配置</span><span class="sxs-lookup"><span data-stu-id="36fb7-144">WCF configuration</span></span> |                                                                                                                                                                                                                                               <span data-ttu-id="36fb7-145">在客户端配置文件中添加\<endpointBehaviors\>包含的元素\<clientCredentials\>。</span><span class="sxs-lookup"><span data-stu-id="36fb7-145">In the client configuration file, add an \<endpointBehaviors\> element that includes \<clientCredentials\>.</span></span><br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`                                                                                                                                                                                                                                               |
|   <span data-ttu-id="36fb7-146">使用 BizTalk</span><span class="sxs-lookup"><span data-stu-id="36fb7-146">Using BizTalk</span></span>   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 <span data-ttu-id="36fb7-147">在使用 WCF 适配器以使用您的适配器，你可以添加**clientCredentials**上的行为扩展**行为**选项卡。这添加后，你可以设置所需的客户端凭据中的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="36fb7-147">When using the WCF adapter to consume your adapter, you can add the **clientCredentials** behavior extension on the **Behavior** tab. Once this has been added, you can set the desired client credentials in the endpoint behavior.</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a><span data-ttu-id="36fb7-148">不会返回同时 StrongDataSetType 和 WeakDataSetType</span><span class="sxs-lookup"><span data-stu-id="36fb7-148">Do Not Return Both StrongDataSetType and WeakDataSetType</span></span>  
 <span data-ttu-id="36fb7-149">如果您的适配器返回`DataSet`，可以使用两种`Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A`或`Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`，但不要同时在同一时间使用。</span><span class="sxs-lookup"><span data-stu-id="36fb7-149">If your adapter returns a `DataSet`, use either `Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A` or `Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`, but do not use both at the same time.</span></span> <span data-ttu-id="36fb7-150">根节点名称和命名空间生成这两种类型的相同，并且不能同时存在于 WSDL。</span><span class="sxs-lookup"><span data-stu-id="36fb7-150">The root node name and namespace produced by both types are identical, and cannot exist simultaneously in a WSDL.</span></span>  

 <span data-ttu-id="36fb7-151">虽然`WeakDataSetType`并`StrongDataSetType`二者都表示`System.Data.DataSet`，`StrongDataSetType`更轻松地在.NET 应用程序中使用，因为生成的代理显示为`System.Data.Dataset`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-151">While `WeakDataSetType` and `StrongDataSetType` both represent a `System.Data.DataSet`, `StrongDataSetType` is easier to use in .NET applications, since the proxy generated appears as `System.Data.Dataset`.</span></span> <span data-ttu-id="36fb7-152">生成的代理`WeakDataSetType`是`XmlElement[]`，这是在.NET 应用程序中使用的难度。</span><span class="sxs-lookup"><span data-stu-id="36fb7-152">The proxy generated by `WeakDataSetType` is `XmlElement[]`, which is more difficult to use in a .NET application.</span></span>  <span data-ttu-id="36fb7-153">BizTalk Server 不能使用从返回的架构`StrongDataSet`，但无法使用`WeakDataSetType`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-153">BizTalk Server cannot consume the schema returned from `StrongDataSet`, but is able to consume `WeakDataSetType`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="36fb7-154">`StrongDataSetType` 和`WeakDataSetType`仅控制客户端应用程序如何解释适配器传递的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="36fb7-154">`StrongDataSetType` and `WeakDataSetType` only control how the client application interprets the XML messages passed by the adapter.</span></span> <span data-ttu-id="36fb7-155">XML 消息是相同的而不考虑该指定类型。</span><span class="sxs-lookup"><span data-stu-id="36fb7-155">The XML message is the same regardless of which type is specified.</span></span>  

> [!NOTE]
>  <span data-ttu-id="36fb7-156">返回时`StrongDataSetType`，则必须设置`Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A`到`false`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-156">When returning `StrongDataSetType`, you must set `Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A` to `false`.</span></span> <span data-ttu-id="36fb7-157">如果设置为`true`，默认情况下，`XmlSchemaSet::Compile`调用中以确保在 WSDL 中没有任何错误的适配器，但是架构生成`StrongDataSetType`生成中的异常`XmlSchemaSet`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-157">When set to `true`, the default, `XmlSchemaSet::Compile` is called within the adapter to ensure there are no errors in the WSDL, however the schema produced by `StrongDataSetType` generates an exception in `XmlSchemaSet`.</span></span>  
>   
>  <span data-ttu-id="36fb7-158">设置`CompileWsdl`到`false`将绕过代理生成期间出现 WSDL 架构验证中的适配器和验证。</span><span class="sxs-lookup"><span data-stu-id="36fb7-158">Setting `CompileWsdl` to `false` bypasses WSDL schema validation within the adapter and validation occurs during proxy generation.</span></span>  <span data-ttu-id="36fb7-159">可以生成两个代理，则 svcutil.exe 之类的实用工具`StrongDataSetType`和`WeakDataSetType`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-159">Utilities such as svcutil.exe are able to generate a proxy for both `StrongDataSetType` and `WeakDataSetType`.</span></span>  

 <span data-ttu-id="36fb7-160">若要使用 BizTalk 和.NET 环境，请考虑实施允许由环境所规定的两个返回类型之间进行切换的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36fb7-160">To work with both BizTalk and .NET environments, consider implementing a binding property that allows switching between the two return types as dictated by the environment.</span></span>  

```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  

## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a><span data-ttu-id="36fb7-161">BizTalk Server 中创建有意义的 XSD 架构名称</span><span class="sxs-lookup"><span data-stu-id="36fb7-161">Create Meaningful XSD Schema Names in BizTalk Server</span></span>  
 <span data-ttu-id="36fb7-162">使用时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]设计时工具在您的 BizTalk 项目中生成的 XSD 架构的名称创建使用`DefaultXsdFileNamePrefix`属性， `fileNameHint` WSDL 中的批注，如果需要，唯一的整数值。</span><span class="sxs-lookup"><span data-stu-id="36fb7-162">When using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] design-time tool, the name of the XSD schema generated in your BizTalk project is created using the `DefaultXsdFileNamePrefix` property, the `fileNameHint` annotation in the WSDL and, if required, a unique integer value.</span></span>  

 <span data-ttu-id="36fb7-163">例如，如果`DefaultXsdFileNamePrefix`设置为"MyAdapter"和`fileNameHint`批注设置为"Stream"中，创建的 XSD 架构命名为 MyAdapterStream.xsd。</span><span class="sxs-lookup"><span data-stu-id="36fb7-163">For example, if `DefaultXsdFileNamePrefix` is set to “MyAdapter” and the `fileNameHint` annotation is set to “Stream”, the XSD schema created is named MyAdapterStream.xsd.</span></span>  

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
>  <span data-ttu-id="36fb7-164">默认值`DefaultXsdFileNamePrefix`是绑定的名称。</span><span class="sxs-lookup"><span data-stu-id="36fb7-164">The default value of `DefaultXsdFileNamePrefix` is the name of your binding.</span></span> <span data-ttu-id="36fb7-165">若要指定不同的值，请重写`DefaultXsdFileNamePrefix`适配器的类中派生自`Microsoft.ServiceModel.Channels.Common.AdapterBinding`。</span><span class="sxs-lookup"><span data-stu-id="36fb7-165">To specify a different value, override `DefaultXsdFileNamePrefix` in your Adapter class that is derived from `Microsoft.ServiceModel.Channels.Common.AdapterBinding`.</span></span>  

 <span data-ttu-id="36fb7-166">有两个可能的方法来添加`fileNameHint`到架构的批注： 重写导出...架构上 OperationMetadata\TypeMetadata 或重写适配器的 IWsdlRetrieval 实现的方法。</span><span class="sxs-lookup"><span data-stu-id="36fb7-166">There are two possible methods to add the `fileNameHint` annotation to the schema: override the Export…Schema methods on OperationMetadata\TypeMetadata or override the IWsdlRetrieval implementation of the adapter.</span></span> <span data-ttu-id="36fb7-167">对于任一方法，可以调用基实现，并将批注添加到架构集合中的架构。</span><span class="sxs-lookup"><span data-stu-id="36fb7-167">For either method, you can call the base implementation and then add the annotation to the schemas in the schema collection.</span></span>  

> [!NOTE]
>  <span data-ttu-id="36fb7-168">重写导出时...架构方法可能有多个操作/类型定义中相同的架构;适配器应确保多次出现`fileNameHints`中相同的架构的批注不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="36fb7-168">When overriding the Export…Schema methods, there may be multiple operation/type definitions in the same schema; the adapter should make sure that multiple occurrences of the `fileNameHints` annotation in the same schema do not conflict.</span></span> <span data-ttu-id="36fb7-169">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]使用的第一个匹配项`fileNameHint`如果它在架构中出现多次。</span><span class="sxs-lookup"><span data-stu-id="36fb7-169">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] uses the first occurrence of `fileNameHint` if it occurs multiple times within a schema.</span></span>  

 <span data-ttu-id="36fb7-170">在以下示例中，IWsdlRetrieval 用于添加`fileNameHint`到 WSDL 批注。</span><span class="sxs-lookup"><span data-stu-id="36fb7-170">In the following example, IWsdlRetrieval is used to add the `fileNameHint` annotation to the WSDL.</span></span>  

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

## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a><span data-ttu-id="36fb7-171">在处理期间不修改 AdapterEnvironmentSettings</span><span class="sxs-lookup"><span data-stu-id="36fb7-171">Do Not Modify AdapterEnvironmentSettings During Processing</span></span>  
 <span data-ttu-id="36fb7-172">应仅设置适配器**AdapterEnvironmentSettings**， **ConnectionPoolManager**， **ConnectionPool**，和**CommonCacheSize**适配器初始化期间，应尝试进行修改的正在运行的实例的值。</span><span class="sxs-lookup"><span data-stu-id="36fb7-172">The adapter should only set the **AdapterEnvironmentSettings**, **ConnectionPoolManager**, **ConnectionPool**, and **CommonCacheSize** during adapter initialization and should not attempt to modify the values for a running instance.</span></span>  

 <span data-ttu-id="36fb7-173">如果当前正在运行的适配器实例上修改这些设置，这可能会导致覆盖配置设置为当前正在执行的连接的新连接。</span><span class="sxs-lookup"><span data-stu-id="36fb7-173">If these settings are modified on a currently running adapter instance, this may result in new connections overwriting configuration settings for currently executing connections.</span></span>  

## <a name="see-also"></a><span data-ttu-id="36fb7-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="36fb7-174">See Also</span></span>  
 [<span data-ttu-id="36fb7-175">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="36fb7-175">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)