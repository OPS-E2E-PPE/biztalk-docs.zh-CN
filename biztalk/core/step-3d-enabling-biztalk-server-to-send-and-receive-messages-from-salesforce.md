---
title: 步骤 3d： 使 BizTalk Server 发送和接收来自 Salesforce 的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470c4a72-1e97-4493-8958-33a13f793ffd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35e34692c0ae64385c4f7d81dc92e82aee6ae88a
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753005"
---
# <a name="step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce"></a>步骤 3d： 使 BizTalk Server 发送和接收来自 Salesforce 的消息
使用 REST 接口发送消息时，我们必须向 Salesforce 进行身份验证。 Salesforce 支持的 REST 调用的身份验证方法并不是 WCF-WebHttp 适配器现成提供的，我们将使用该适配器来调用 Salesforce 的 REST 接口。 因此，我们将创建自定义 WCF 终结点行为，然后将其附加到我们配置用于调用 Salesforce REST 接口的 WCF-WebHttp 发送适配器。  
  
 同样，从 Salesforce 收到的 XML 响应将不包含任何命名空间。 要使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 根据响应架构处理响应消息，响应消息必须包含目标命名空间。 因此，我们将使用 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]创建一个自定义管道，以将命名空间添加到响应消息。 然后，我们将使用此自定义管道作为请求-响应 WCF-WebHttp 发送端口的接收管道。  
  
## <a name="add-a-custom-wcf-behavior-for-salesforce-authentication"></a>为 Salesforce 身份验证添加自定义 WCF 行为  
 Salesforce 向客户端应用程序提供了不同选项来向 Salesforce 进行身份验证。 我们将使用 Salesforce 称之为[用户名和密码](http://go.microsoft.com/fwlink/?LinkId=287082)流。 在客户端，WCF 允许你创建[消息检查器](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx)更改消息发送前或后它们被接收。 消息检查器是客户端运行时的扩展，已配置为一种行为。 行为进而会添加到行为扩展元素。 此行为扩展元素在 machine.config 中使用元素名称注册，这使它可以在 WCF 端口上配置为一种自定义行为。 有关详细信息，请参阅[的自定义行为扩展 WCF](http://msdn.microsoft.com/magazine/cc163302.aspx)。 我们将会使用此方法整合用于向 Salesforce 进行身份验证的用户名身份验证流程。 我们将执行的广泛步骤如下：  
  
-   创建一个对 Salesforce 身份验证终结点进行 HTTP POST 调用并接收访问令牌的消息检查器。 然后，该消息检查器会将身份验证令牌添加为要发送到 Salesforce 的查询消息的 Authorization 标头值。 该消息检查器还会将 Accept 标头添加到请求消息，以使收到的响应采用 XML 格式。 否则，Salesforce 将以默认的 JSON 格式发送消息。  
  
-   创建终结点行为，以将该消息检查器应用于客户端终结点。  
  
-   创建行为扩展元素，以启用终结点行为配置。  
  
#### <a name="to-create-a-message-inspector"></a>创建消息检查器  
  
1. 作为的一部分**BtsSalesforceIntegration**解决方案在 Visual Studio 中，创建一个 C# 类库。 其命名为`Microsoft.BizTalk.Adapter.Behaviors`并添加以下命名空间：  
  
   ```  
   using System.ServiceModel.Description;  
   using System.ServiceModel.Dispatcher;  
   using System.ServiceModel.Channels;  
   using System.Xml;  
   using System.Net;  
   using System.IO;  
   using System.ServiceModel.Configuration;  
   using System.Configuration;  
   using System.Web.Script.Serialization;  
   ```  
  
2. 在解决方案资源管理器中，添加对 `System.ServiceModel`、`System.Web.Extensions` 和 `System.Configuration` 的引用。  
  
3. 添加具有以下属性的类 `SalesforceOAuthToken`。 此类表示从 Salesforce 收到的授权令牌。  
  
   ```  
   public class SalesforceOAuthToken  
   {  
       public string id { get; set; }  
       public string issued_at { get; set; }  
       public string refresh_token { get; set; }  
       public string instance_url { get; set; }  
       public string signature { get; set; }  
       public string access_token { get; set; }  
   }  
   ```  
  
4. 添加一个实现了 `SalesforceRESTSecurityBehavior` 和 `IClientMessageInspector` 的类 `IEndpointBehavior`。 此类包含对 Salesforce 身份验证终结点进行 HTTP POST 调用以检索授权令牌的 `HttpPost()` 和 `FetchOAuthToken()` 方法。  
  
    由于 `SalesforceRESTSecurityBehavior` 类实现了 `IClientMessageInspector` 接口，它必须实现两个方法：`AfterReceiveReply()` 和 `BeforeSendRequest()`。 在此方案中，我们不需要在 `AfterReceiverReply()` 方法中执行任何操作。 但是，`BeforeSendRequest()` 方法将调用 `FetchOAuthToken()` 方法，后者又调用 `HttpPost()` 方法。 然后，`BeforeSendRequest()` 方法将添加授权令牌作为消息标头的一部分。 它还添加了**接受**标头，以确保从 Salesforce 收到的响应采用 XML 格式。  
  
    `IEndpointBehavior` 实现只是将消息检查器类添加到客户端终结点行为。  
  
   ```  
   public class SalesforceRESTSecurityBehavior : IClientMessageInspector, IEndpointBehavior  
   {  
       // Some constants  
       private static string SalesforceAuthEndpoint = "https://login.salesforce.com/services/oauth2/token";  
  
       // Configuration Properties  
       private string username_;  
       private string password_;  
       private string consumerKey_;  
       private string consumerSecret_;  
       private int sessionTimeout_;  
  
       // Private Properties  
       private SalesforceOAuthToken token_;  
       private DateTime tokenExpiryTime_;  
  
       public SalesforceRESTSecurityBehavior(  
           string username,  
           string password,  
           string consumerKey,  
           string consumerSecret,  
           int sessionTimeout)  
       {  
           this.username_ = username;  
           this.password_ = password;  
           this.consumerKey_ = consumerKey;  
           this.consumerSecret_ = consumerSecret;  
           this.sessionTimeout_ = sessionTimeout;  
       }  
  
       private void FetchOAuthToken()  
       {  
           if ((tokenExpiryTime_ == null) || (tokenExpiryTime_.CompareTo(DateTime.Now) <= 0))  
           {  
               StringBuilder body = new StringBuilder();  
               body.Append("grant_type=password&")  
                   .Append("client_id=" + consumerKey_ + "&")  
                   .Append("client_secret=" + consumerSecret_ + "&")  
                   .Append("username=" + username_ + "&")  
                   .Append("password=" + password_);  
  
               string result;  
  
               try  
               {  
                   result = HttpPost(SalesforceAuthEndpoint, body.ToString());  
               }  
               catch (WebException)  
               {  
                   // do something  
                   return;  
               }  
  
               // Convert the JSON response into a token object  
               JavaScriptSerializer ser = new JavaScriptSerializer();  
               this.token_ = ser.Deserialize<SalesforceOAuthToken>(result);  
               this.tokenExpiryTime_ = DateTime.Now.AddSeconds(this.sessionTimeout_);  
           }  
       }  
  
       public string HttpPost(string URI, string Parameters)  
       {  
           WebRequest req = WebRequest.Create(URI);  
           req.ContentType = "application/x-www-form-urlencoded";  
           req.Method = "POST";  
  
           // Add parameters to post  
           byte[] data = Encoding.ASCII.GetBytes(Parameters);  
           req.ContentLength = data.Length;  
           System.IO.Stream os = req.GetRequestStream();  
           os.Write(data, 0, data.Length);  
           os.Close();  
  
           // Do the post and get the response.  
           System.Net.WebResponse resp = null;  
           resp = req.GetResponse();  
  
           StreamReader sr = new StreamReader(resp.GetResponseStream());  
           return sr.ReadToEnd().Trim();  
       }  
       #region IClientMessageInspector  
  
       public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
       {  
           // do nothing  
       }  
       public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
       {  
           // We are going to send a request to Salesforce  
           // Overview:  
           // This behavior will do the following:  
           // (1) Fetch Token from Salesforce, if required  
           // (2) Add the token to the message  
           // (3) Insert an Http Accept header so we get XML data in response, instead of JSON, which is default  
           // Reference: http://www.salesforce.com/us/developer/docs/api_rest/index.htm  
           //  
           // (1) Authentication with Salesforce  
           // (2) The token is added to the HTTP Authorization Header   
           // (3) Add the Accept Header  
           //  
  
           HttpRequestMessageProperty httpRequest = null;  
  
           if (request.Properties.ContainsKey(HttpRequestMessageProperty.Name))  
           {  
               httpRequest = request.Properties[HttpRequestMessageProperty.Name] as HttpRequestMessageProperty;  
           }  
  
           if (httpRequest == null)  
           {  
               // NOTE: Ideally, we shouldn’t get here for WebHttp  
               httpRequest = new HttpRequestMessageProperty()  
               {  
                   Method = "GET",  
                   SuppressEntityBody = true  
               };  
               request.Properties.Add(HttpRequestMessageProperty.Name, httpRequest);  
           }  
  
           WebHeaderCollection headers = httpRequest.Headers;  
           FetchOAuthToken();  
  
           headers.Add(HttpRequestHeader.Authorization, "OAuth " + this.token_.access_token);  
           headers.Add(HttpRequestHeader.Accept, "application/xml");  
  
           return null;  
       }  
  
       #endregion IClientMessageInspector  
  
       #region IEndpointBehavior  
  
       public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
       {  
           // do nothing  
       }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
       {  
           clientRuntime.MessageInspectors.Add(this);  
       }  
  
       public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
       {  
           // do nothing  
       }  
  
       public void Validate(ServiceEndpoint endpoint)  
       {  
           // do nothing  
       }  
  
       #endregion IEndpointBehavior  
   }  
   ```  
  
5. 在上一步中，我们创建了一个将消息检查器应用于客户端终结点的行为类。 我们现在需要使此行为可用于向 Salesforce 发送请求消息的 WCF-WebHttp 适配器的配置体验。 若要使此行为可用于配置，我们需要执行两项操作：  
  
   - 创建一个从 `BehaviorExtensionElement` 派生的类  
  
   - 注册在 <extensions>\<behaviorextensions>\<扩展\>\\< behaviorExtensions\>使用元素名称在 machine.config 中的元素。  
  
     我们还会向此类添加配置属性，以便可以从 WCF-WebHttp 适配器配置 UI 获取这些属性。  
  
   ```  
   public class SalesforceRESTBehaviorElement : BehaviorExtensionElement  
   {  
       public override Type BehaviorType  
       {  
           get { return typeof(SalesforceRESTSecurityBehavior); }  
       }  
  
       protected override object CreateBehavior()  
       {  
           return new SalesforceRESTSecurityBehavior(Username, Password, ConsumerKey, ConsumerSecret, SessionTimeout);  
       }  
  
       [ConfigurationProperty("username", IsRequired = true)]  
       public string Username  
       {  
           get { return (string)this["username"]; }  
           set { this["username"] = value; }  
       }  
  
       [ConfigurationProperty("password", IsRequired = true)]  
       public string Password  
       {  
           get { return (string)this["password"]; }  
           set { this["password"] = value; }  
       }  
  
       [ConfigurationProperty("consumerKey", IsRequired = true)]  
       public string ConsumerKey  
       {  
           get { return (string)this["consumerKey"]; }  
           set { this["consumerKey"] = value; }  
       }  
  
       [ConfigurationProperty("consumerSecret", IsRequired = true)]  
       public string ConsumerSecret  
       {  
           get { return (string)this["consumerSecret"]; }  
           set { this["consumerSecret"] = value; }  
       }  
  
       [ConfigurationProperty("sessionTimeout", IsRequired = false, DefaultValue = 300)]  
       public int SessionTimeout  
       {  
           get { return (int)this["sessionTimeout"]; }  
           set { this["sessionTimeout"] = value; }  
       }  
   }  
   ```  
  
6. 向项目添加强名称密钥文件并生成项目。 成功生成项目后，将程序集 `Microsoft.BizTalk.Adapter.Behaviors` 添加到 GAC。  
  
7. 在 machine.config 中，将以下条目添加到 System.ServiceModel\Extensions\BehaviorExtensions 之下。  
  
   ```  
   <add name="Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce" type="Microsoft.BizTalk.Adapter.Behaviors.SalesforceRESTBehaviorElement, Microsoft.BizTalk.Adapter.Behaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=45bd7fe67ef032db"/>  
   ```  
  
    你可以从 GAC 中检索程序集的公钥标记。 此外，如果你要在 64 位计算机上创建此应用程序，还必须将此条目添加到 32 位和 64 位版本的 machine.config。  
  
## <a name="add-a-custom-pipeline-to-add-namespace-to-the-salesforce-response"></a>添加自定义管道以向 Salesforce 响应添加命名空间  
 从 Salesforce 收到的响应不包括命名空间。 但是，若要根据响应架构 (QueryResult.xsd) 处理响应消息，必须在 Salesforce 响应中包括命名空间。 在本部分中，我们将创建自定义管道，并使用 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]附带的自定义管道组件将命名空间添加到响应消息中。 此自定义管道使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序进行部署，并将在配置 WCF-WebHttp 适配器时用作接收管道。  
  
 执行此过程中的步骤之前，请确保 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]已在要创建此应用程序的计算机上安装并配置好。  
  
#### <a name="to-add-a-custom-pipeline"></a>添加自定义管道  
  
1. 内**BtsSalesforceIntegration**解决方案，创建一个新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。 将项目命名`CustomPipeline`。  
  
2. 内**CustomPipeline**项目中，添加新的接收管道。 命名管道作为`AddNamespace.btp`。  
  
3. 内**解码**阶段的管道，从工具箱拖放到**ESB 添加 Namespace**管道组件。 内**拆装**暂存，拖放**XML 拆装器**管道组件。  
  
   > [!NOTE]
   >  如果**ESB 添加 Namespace**管道组件未列在工具箱中，你可以添加它。 右键单击**BizTalk 管道组件**选项卡，然后依次**选择项**。 在中**选择工具箱项**对话框中，单击**BizTalk 管道组件**选项卡上，选中的复选框**ESB 添加 Namespace**组件，然后单击**确定**。  
  
4. 向项目添加强名称密钥文件，并保存项目。  
  
5. 右键单击**CustomPipeline**项目，然后选择**属性**。 在中**部署**选项卡上，对于**应用程序名称**，输入`SalesforceIntegration`。  
  
6. 保存对项目所做的更改。  
  
   在本主题中，添加了自定义行为以向 Salesforce 进行身份验证，并添加了自定义管道以向 Salesforce 响应添加命名空间。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置物理端口时，我们将使用这些自定义组件。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：在 Visual Studio 中创建 BizTalk Server 解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)