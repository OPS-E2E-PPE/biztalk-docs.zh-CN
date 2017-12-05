---
title: "步骤 3d： 启用 BizTalk 服务器发送和接收来自 Salesforce 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470c4a72-1e97-4493-8958-33a13f793ffd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8489c484bdb88a292b998d31e7c6de90e0937c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce"></a><span data-ttu-id="3f7ed-102">步骤 3d： 启用 BizTalk 服务器发送和接收来自 Salesforce 的消息</span><span class="sxs-lookup"><span data-stu-id="3f7ed-102">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>
<span data-ttu-id="3f7ed-103">使用 REST 接口发送消息时，我们必须向 Salesforce 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-103">We must authenticate with Salesforce while sending messages using the REST interface.</span></span> <span data-ttu-id="3f7ed-104">Salesforce 支持的 REST 调用的身份验证方法并不是 WCF-WebHttp 适配器现成提供的，我们将使用该适配器来调用 Salesforce 的 REST 接口。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-104">The authentication methods for REST calls supported by Salesforce are not available out of the box with the WCF-WebHttp adapter, which we’ll use to invoke Salesforce’s REST interface.</span></span> <span data-ttu-id="3f7ed-105">因此，我们将创建自定义 WCF 终结点行为，然后将其附加到我们配置用于调用 Salesforce REST 接口的 WCF-WebHttp 发送适配器。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-105">So, we’ll create a custom WCF endpoint behavior and then attach it to WCF-WebHttp send adapter that we’ll configure to invoke the Salesforce REST interface.</span></span>  
  
 <span data-ttu-id="3f7ed-106">同样，从 Salesforce 收到的 XML 响应将不包含任何命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-106">Similarly, the XML response received from Salesforce will not contain any namespace.</span></span> <span data-ttu-id="3f7ed-107">要使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 根据响应架构处理响应消息，响应消息必须包含目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-107">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process the response message against the response schema, the response message must include the target namespace.</span></span> <span data-ttu-id="3f7ed-108">因此，我们将使用 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]创建一个自定义管道，以将命名空间添加到响应消息。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-108">So, we’ll create a custom pipeline using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] to add a namespace to the response message.</span></span> <span data-ttu-id="3f7ed-109">然后，我们将使用此自定义管道作为请求-响应 WCF-WebHttp 发送端口的接收管道。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-109">We’ll then use this custom pipeline as the receive pipeline for request-response WCF-WebHttp send port.</span></span>  
  
## <a name="add-a-custom-wcf-behavior-for-salesforce-authentication"></a><span data-ttu-id="3f7ed-110">为 Salesforce 身份验证添加自定义 WCF 行为</span><span class="sxs-lookup"><span data-stu-id="3f7ed-110">Add a Custom WCF Behavior for Salesforce Authentication</span></span>  
 <span data-ttu-id="3f7ed-111">Salesforce 向客户端应用程序提供了不同选项来向 Salesforce 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-111">Salesforce provides different options for client applications to authenticate with Salesforce.</span></span> <span data-ttu-id="3f7ed-112">我们将使用作为哪些 Salesforce 条款[用户名密码](http://go.microsoft.com/fwlink/?LinkId=287082)流。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-112">We’ll use what Salesforce terms as the [Username-password](http://go.microsoft.com/fwlink/?LinkId=287082) flow.</span></span> <span data-ttu-id="3f7ed-113">在客户端中，WCF 使您能够创建[消息检查器](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx)以更改发送之前或之后接收的消息。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-113">On the client side, WCF enables you to create [Message Inspectors](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx) to alter messages before they are sent or after they are received.</span></span> <span data-ttu-id="3f7ed-114">消息检查器是客户端运行时的扩展，已配置为一种行为。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-114">A message inspector is an extension to the client runtime and is configured as a behavior.</span></span> <span data-ttu-id="3f7ed-115">行为进而会添加到行为扩展元素。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-115">A behavior, in turn, is added to a behavior extension element.</span></span> <span data-ttu-id="3f7ed-116">此行为扩展元素在 machine.config 中使用元素名称注册，这使它可以在 WCF 端口上配置为一种自定义行为。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-116">This behavior extension element is registered in the machine.config with an element name, which makes it available to be configured as a custom behavior on a WCF port.</span></span> <span data-ttu-id="3f7ed-117">有关详细信息，请参阅[的自定义行为扩展 WCF](http://msdn.microsoft.com/magazine/cc163302.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-117">For more information, see [Extending WCF with Custom Behaviors](http://msdn.microsoft.com/magazine/cc163302.aspx).</span></span> <span data-ttu-id="3f7ed-118">我们将会使用此方法整合用于向 Salesforce 进行身份验证的用户名身份验证流程。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-118">We are going to use this approach to incorporate the username-authentication flow for authenticating with Salesforce.</span></span> <span data-ttu-id="3f7ed-119">我们将执行的广泛步骤如下：</span><span class="sxs-lookup"><span data-stu-id="3f7ed-119">The broad steps that we’ll follow are:</span></span>  
  
-   <span data-ttu-id="3f7ed-120">创建一个对 Salesforce 身份验证终结点进行 HTTP POST 调用并接收访问令牌的消息检查器。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-120">Create a message inspector that makes an HTTP POST call to the Salesforce authentication endpoint and receives an access token.</span></span> <span data-ttu-id="3f7ed-121">然后，该消息检查器会将身份验证令牌添加为要发送到 Salesforce 的查询消息的 Authorization 标头值。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-121">The message inspector then adds the authentication token as the value of the Authorization header of the query message being sent to Salesforce.</span></span> <span data-ttu-id="3f7ed-122">该消息检查器还会将 Accept 标头添加到请求消息，以使收到的响应采用 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-122">The message inspector also adds the Accept header to the request message so that the response received is in an XML format.</span></span> <span data-ttu-id="3f7ed-123">否则，Salesforce 将以默认的 JSON 格式发送消息。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-123">Otherwise, Salesforce sends the message in the default JSON format.</span></span>  
  
-   <span data-ttu-id="3f7ed-124">创建终结点行为，以将该消息检查器应用于客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-124">Create an endpoint behavior to apply the message inspector to the client endpoint.</span></span>  
  
-   <span data-ttu-id="3f7ed-125">创建行为扩展元素，以启用终结点行为配置。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-125">Create a behavior extension element to enable configuration of the endpoint behavior.</span></span>  
  
#### <a name="to-create-a-message-inspector"></a><span data-ttu-id="3f7ed-126">创建消息检查器</span><span class="sxs-lookup"><span data-stu-id="3f7ed-126">To create a message inspector</span></span>  
  
1.  <span data-ttu-id="3f7ed-127">作为的一部分**BtsSalesforceIntegration**解决方案在 Visual Studio 中，创建一个 C# 类库。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-127">As part of the **BtsSalesforceIntegration** solution in Visual Studio, create a C# Class Library.</span></span> <span data-ttu-id="3f7ed-128">将其命名为`Microsoft.BizTalk.Adapter.Behaviors`并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="3f7ed-128">Name it `Microsoft.BizTalk.Adapter.Behaviors` and add the following namespaces:</span></span>  
  
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
  
2.  <span data-ttu-id="3f7ed-129">在解决方案资源管理器中，添加对 `System.ServiceModel`、`System.Web.Extensions` 和 `System.Configuration` 的引用。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-129">From the Solution Explorer, add references to `System.ServiceModel`, `System.Web.Extensions`, and `System.Configuration`.</span></span>  
  
3.  <span data-ttu-id="3f7ed-130">添加具有以下属性的类 `SalesforceOAuthToken`。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-130">Add a class `SalesforceOAuthToken` with the following properties.</span></span> <span data-ttu-id="3f7ed-131">此类表示从 Salesforce 收到的授权令牌。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-131">This class represents the authorization token that is received from Salesforce.</span></span>  
  
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
  
4.  <span data-ttu-id="3f7ed-132">添加一个实现了 `SalesforceRESTSecurityBehavior` 和 `IClientMessageInspector` 的类 `IEndpointBehavior`。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-132">Add a class `SalesforceRESTSecurityBehavior` that implements the `IClientMessageInspector` and the `IEndpointBehavior`.</span></span> <span data-ttu-id="3f7ed-133">此类包含对 Salesforce 身份验证终结点进行 HTTP POST 调用以检索授权令牌的 `HttpPost()` 和 `FetchOAuthToken()` 方法。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-133">This class includes the `HttpPost()` and `FetchOAuthToken()` methods that make an HTTP POST call to the Salesforce authentication endpoint to retrieve the authorization token.</span></span>  
  
     <span data-ttu-id="3f7ed-134">由于 `SalesforceRESTSecurityBehavior` 类实现了 `IClientMessageInspector` 接口，它必须实现两个方法：`AfterReceiveReply()` 和 `BeforeSendRequest()`。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-134">Because the `SalesforceRESTSecurityBehavior` class implements the `IClientMessageInspector` interface, it must implement the two methods, `AfterReceiveReply()` and `BeforeSendRequest()`.</span></span> <span data-ttu-id="3f7ed-135">在此方案中，我们不需要在 `AfterReceiverReply()` 方法中执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-135">For this scenario we do not need to do anything as part of the `AfterReceiverReply()` method.</span></span> <span data-ttu-id="3f7ed-136">但是，`BeforeSendRequest()` 方法将调用 `FetchOAuthToken()` 方法，后者又调用 `HttpPost()` 方法。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-136">However, the `BeforeSendRequest()` method invokes the `FetchOAuthToken()` method, which in turn calls the `HttpPost()` method.</span></span> <span data-ttu-id="3f7ed-137">然后，`BeforeSendRequest()` 方法将添加授权令牌作为消息标头的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-137">The `BeforeSendRequest()` method then adds the authorization token as part of the message header.</span></span> <span data-ttu-id="3f7ed-138">它还添加了**接受**标头，以确保从 Salesforce 收到的响应所采用 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-138">It also adds the **Accept** header to ensure that that the response received from Salesforce is in an XML format.</span></span>  
  
     <span data-ttu-id="3f7ed-139">`IEndpointBehavior` 实现只是将消息检查器类添加到客户端终结点行为。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-139">The `IEndpointBehavior` implementation simply adds the message inspector class to the client endpoint behavior.</span></span>  
  
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
  
5.  <span data-ttu-id="3f7ed-140">在上一步中，我们创建了一个将消息检查器应用于客户端终结点的行为类。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-140">In the previous step we created a behavior class that applies the message inspector to the client endpoint.</span></span> <span data-ttu-id="3f7ed-141">我们现在需要使此行为可用于向 Salesforce 发送请求消息的 WCF-WebHttp 适配器的配置体验。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-141">We now need to make this behavior available to the configuration experience for the WCF-WebHttp adapter that will send the request message to Salesforce.</span></span> <span data-ttu-id="3f7ed-142">若要使此行为可用于配置，我们需要执行两项操作：</span><span class="sxs-lookup"><span data-stu-id="3f7ed-142">To make this behavior available for configuration we need to do two things:</span></span>  
  
    -   <span data-ttu-id="3f7ed-143">创建一个从 `BehaviorExtensionElement` 派生的类</span><span class="sxs-lookup"><span data-stu-id="3f7ed-143">Create a class that derives from the `BehaviorExtensionElement`</span></span>  
  
    -   <span data-ttu-id="3f7ed-144">注册在你 BehavaiorExtensionElement\<扩展\>\\< behaviorExtensions\>使用的是元素名称 machine.config 中的元素。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-144">Register your BehavaiorExtensionElement in the \<extensions\>\\<behaviorExtensions\> element in the machine.config using an element name.</span></span>  
  
     <span data-ttu-id="3f7ed-145">我们还会向此类添加配置属性，以便可以从 WCF-WebHttp 适配器配置 UI 获取这些属性。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-145">We’ll also add configuration properties to this class so that they are available from the WCF-WebHttp adapter configuration UI.</span></span>  
  
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
  
6.  <span data-ttu-id="3f7ed-146">向项目添加强名称密钥文件并生成项目。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-146">Add a strong name key file to the project and build the project.</span></span> <span data-ttu-id="3f7ed-147">成功生成项目后，将程序集 `Microsoft.BizTalk.Adapter.Behaviors` 添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-147">Once the project builds successfully, add the assembly `Microsoft.BizTalk.Adapter.Behaviors` to the GAC.</span></span>  
  
7.  <span data-ttu-id="3f7ed-148">在 machine.config 中，将以下条目添加到 System.ServiceModel\Extensions\BehaviorExtensions 之下。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-148">Add the following entry in the machine.config under System.ServiceModel\Extensions\BehaviorExtensions.</span></span>  
  
    ```  
    <add name="Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce" type="Microsoft.BizTalk.Adapter.Behaviors.SalesforceRESTBehaviorElement, Microsoft.BizTalk.Adapter.Behaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=45bd7fe67ef032db"/>  
    ```  
  
     <span data-ttu-id="3f7ed-149">你可以从 GAC 中检索程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-149">You can retrieve the public key token for the assembly from the GAC.</span></span> <span data-ttu-id="3f7ed-150">此外，如果你要在 64 位计算机上创建此应用程序，还必须将此条目添加到 32 位和 64 位版本的 machine.config。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-150">Also, if you are creating this application on a 64-bit computer, you must add this entry to both 32-bit and 64-bit versions of the machine.config.</span></span>  
  
## <a name="add-a-custom-pipeline-to-add-namespace-to-the-salesforce-response"></a><span data-ttu-id="3f7ed-151">添加自定义管道以向 Salesforce 响应添加命名空间</span><span class="sxs-lookup"><span data-stu-id="3f7ed-151">Add a Custom Pipeline to Add Namespace to the Salesforce Response</span></span>  
 <span data-ttu-id="3f7ed-152">从 Salesforce 收到的响应不包括命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-152">The response received from Salesforce does not include a namespace.</span></span> <span data-ttu-id="3f7ed-153">但是，若要根据响应架构 (QueryResult.xsd) 处理响应消息，必须在 Salesforce 响应中包括命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-153">However, to process the response message against the response schema (QueryResult.xsd) we must include the namespace in the Salesforce response.</span></span> <span data-ttu-id="3f7ed-154">在本部分中，我们将创建自定义管道，并使用 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]附带的自定义管道组件将命名空间添加到响应消息中。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-154">In this section, we create a custom pipeline and use a custom pipeline component shipped with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] to add a namespace to the response message.</span></span> <span data-ttu-id="3f7ed-155">此自定义管道使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序进行部署，并将在配置 WCF-WebHttp 适配器时用作接收管道。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-155">This custom pipeline is deployed with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application and will be used as the receive pipeline while configuring the WCF-WebHttp adapter.</span></span>  
  
 <span data-ttu-id="3f7ed-156">执行此过程中的步骤之前，请确保 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]已在要创建此应用程序的计算机上安装并配置好。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-156">Before performing the steps in this procedure, ensure that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is installed and configured on the computer where you are creating this application.</span></span>  
  
#### <a name="to-add-a-custom-pipeline"></a><span data-ttu-id="3f7ed-157">添加自定义管道</span><span class="sxs-lookup"><span data-stu-id="3f7ed-157">To add a custom pipeline</span></span>  
  
1.  <span data-ttu-id="3f7ed-158">在**BtsSalesforceIntegration**解决方案中，创建一个新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-158">Within the **BtsSalesforceIntegration** solution, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="3f7ed-159">将项目`CustomPipeline`。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-159">Name the project `CustomPipeline`.</span></span>  
  
2.  <span data-ttu-id="3f7ed-160">在**CustomPipeline**项目中，添加新的接收管道。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-160">Within the **CustomPipeline** project, add a new receive pipeline.</span></span> <span data-ttu-id="3f7ed-161">命名管道作为`AddNamespace.btp`。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-161">Name the pipeline as `AddNamespace.btp`.</span></span>  
  
3.  <span data-ttu-id="3f7ed-162">在**解码**管道，从工具箱的阶段拖放**ESB 添加 Namespace**管道组件。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-162">Within the **Decode** stage of the pipeline, from the toolbox, drag and drop the **ESB Add Namespace** pipeline component.</span></span> <span data-ttu-id="3f7ed-163">在**拆卸**暂存、 拖动和删除**XML 反汇编程序**管道组件。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-163">Within the **Disassemble** stage, drag and drop the **XML disassembler** pipeline component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f7ed-164">如果**ESB 添加 Namespace**管道组件未列出工具箱中，你可以添加它。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-164">If the **ESB Add Namespace** pipeline component is not listed in the toolbox, you can add it.</span></span> <span data-ttu-id="3f7ed-165">右键单击**BizTalk 管道组件**选项卡上，并依次**选择项**。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-165">Right-click the **BizTalk Pipeline Components** tab, and then click **Choose Items**.</span></span> <span data-ttu-id="3f7ed-166">在**选择工具箱项**对话框中，单击**BizTalk 管道组件**选项卡上，选中的复选框**ESB 添加 Namespace**组件，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-166">In the **Choose Toolbox Items** dialog box, click the **BizTalk Pipeline Components** tab, select the check box for **ESB Add Namespace** component, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="3f7ed-167">向项目添加强名称密钥文件，并保存项目。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-167">Add a strong name key file to the project and save the project.</span></span>  
  
5.  <span data-ttu-id="3f7ed-168">右键单击**CustomPipeline**项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-168">Right-click the **CustomPipeline** project and select **Properties**.</span></span> <span data-ttu-id="3f7ed-169">在**部署**选项卡上，为**应用程序名称**，输入`SalesforceIntegration`。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-169">In the **Deployment** tab, for **Application Name**, enter `SalesforceIntegration`.</span></span>  
  
6.  <span data-ttu-id="3f7ed-170">保存对项目所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-170">Save changes to the project.</span></span>  
  
 <span data-ttu-id="3f7ed-171">在本主题中，添加了自定义行为以向 Salesforce 进行身份验证，并添加了自定义管道以向 Salesforce 响应添加命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-171">In this topic, added a custom behavior to authenticate with Salesforce and a custom pipeline to add a namespace to the Salesforce response.</span></span> <span data-ttu-id="3f7ed-172">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置物理端口时，我们将使用这些自定义组件。</span><span class="sxs-lookup"><span data-stu-id="3f7ed-172">We’ll use these custom components while configuring the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f7ed-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f7ed-173">See Also</span></span>  
 [<span data-ttu-id="3f7ed-174">步骤 3：在 Visual Studio 中创建 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="3f7ed-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)