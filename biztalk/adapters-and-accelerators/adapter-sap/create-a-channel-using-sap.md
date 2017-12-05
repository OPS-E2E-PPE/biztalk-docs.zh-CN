---
title: "创建一个通道，使用 SAP |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- channel programming, creating a channel
- how to, create a channel
- creating a channel
- WCF channel model, creating a channel
ms.assetid: 24af1465-bb60-41d7-98bd-e501a981f82a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22a0d6e48d1a33e4d7c0aec8a1231346a671c1ef
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="create-a-channel-using-sap"></a><span data-ttu-id="7789f-102">创建一个通道，使用 SAP</span><span class="sxs-lookup"><span data-stu-id="7789f-102">Create a channel using SAP</span></span>
<span data-ttu-id="7789f-103">在 WCF 通道模型中，调用 SAP 系统上的操作或从 SAP 系统接收消息，通过交换使用 SOAP 消息[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过 WCF 通道。</span><span class="sxs-lookup"><span data-stu-id="7789f-103">In the WCF channel model, you invoke operations on the SAP system or receive messages from the SAP system by exchanging SOAP messages with the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="7789f-104">通过使用调用操作 （出站操作） **IRequestChannel**或**IOutputChannel**将消息发送到适配器</span><span class="sxs-lookup"><span data-stu-id="7789f-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter</span></span>  
  
-   <span data-ttu-id="7789f-105">接收消息 （触发从 SAP 系统） 通过**IReplyChannel**。</span><span class="sxs-lookup"><span data-stu-id="7789f-105">You receive messages (triggered from the SAP system) over an **IReplyChannel**.</span></span>  
  
 <span data-ttu-id="7789f-106">此部分中的主题提供有关如何创建和配置用于入站和出站操作的通道形状的信息。</span><span class="sxs-lookup"><span data-stu-id="7789f-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="7789f-107">创建出站 （客户端） 通道</span><span class="sxs-lookup"><span data-stu-id="7789f-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="7789f-108">你可以使用**IRequestChannel**或**IOutputChannel**来调用 SAP 系统上的操作。</span><span class="sxs-lookup"><span data-stu-id="7789f-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the SAP system.</span></span> <span data-ttu-id="7789f-109">在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。</span><span class="sxs-lookup"><span data-stu-id="7789f-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="7789f-110">然后可以使用工厂来创建通道。</span><span class="sxs-lookup"><span data-stu-id="7789f-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="7789f-111">创建通道后可用于调用在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="7789f-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="7789f-112">若要创建并打开一个出站通道</span><span class="sxs-lookup"><span data-stu-id="7789f-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="7789f-113">创建和初始化的实例**ChannelFactory**使用终结点和绑定所需的通道形状。</span><span class="sxs-lookup"><span data-stu-id="7789f-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="7789f-114">终结点指定 SAP 连接 URI 和绑定是的一个实例**SAPDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="7789f-114">The endpoint specifies an SAP connection URI and the binding is an instance of **SAPDBBinding**.</span></span> <span data-ttu-id="7789f-115">（设置之前打开通道工厂所需的任何绑定属性。）</span><span class="sxs-lookup"><span data-stu-id="7789f-115">(Set any binding properties required before you open the channel factory.)</span></span>  
  
2.  <span data-ttu-id="7789f-116">通过使用中提供的通道工厂的 SAP 凭据**ClientCredentials**属性。</span><span class="sxs-lookup"><span data-stu-id="7789f-116">Provide SAP credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
3.  <span data-ttu-id="7789f-117">打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="7789f-117">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="7789f-118">获取通道的实例通过调用**CreateChannel**的通道工厂的方法。</span><span class="sxs-lookup"><span data-stu-id="7789f-118">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="7789f-119">打开通道。</span><span class="sxs-lookup"><span data-stu-id="7789f-119">Open the channel.</span></span>  
  
 <span data-ttu-id="7789f-120">在代码中或从配置，你可以指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="7789f-120">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="7789f-121">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="7789f-121">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="7789f-122">下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="7789f-122">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="7789f-123">若要创建的代码**IOutputChannel**具有相同，只不过你必须指定**IOutputChannel**接口**ChannelFactory**并通道类型。</span><span class="sxs-lookup"><span data-stu-id="7789f-123">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
SAPBinding sapBinding = new SAPBinding();  
  
// Create address.  
EndpointAddress sapAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sapBinding, sapAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="7789f-124">在配置中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="7789f-124">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="7789f-125">下面的代码示例演示如何从配置中指定的客户端终结点创建通道工厂。</span><span class="sxs-lookup"><span data-stu-id="7789f-125">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="7789f-126">配置设置</span><span class="sxs-lookup"><span data-stu-id="7789f-126">The Configuration Settings</span></span>  
 <span data-ttu-id="7789f-127">下面的代码演示使用前面示例的配置设置。</span><span class="sxs-lookup"><span data-stu-id="7789f-127">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="7789f-128">客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IRequestChannel"根据你想要创建的通道形状的种类。</span><span class="sxs-lookup"><span data-stu-id="7789f-128">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IRequestChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    receiveIdocFormat="Typed" enableSafeTyping="false" generateFlatFileCompatibleIdocSchema="true"  
                    maxConnectionsPerSystem="50" enableConnectionPooling="true"  
                    idleConnectionTimeout="00:15:00" flatFileSegmentIndicator="SegmentDefinition"  
                    enablePerformanceCounters="false" autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false"  
                    padReceivedIdocWithSpaces="false" sncLibrary="" sncPartnerName="" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/ADAPSAP47/00?RfcSdkTrace=False&AbapDebug=False"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="7789f-129">创建入站 （服务） 通道</span><span class="sxs-lookup"><span data-stu-id="7789f-129">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="7789f-130">配置以设置绑定属性的实例上将入站的消息接收某个 SAP 系统的适配器**SAPBinding**。</span><span class="sxs-lookup"><span data-stu-id="7789f-130">You configure the adapter to receive inbound messages from an SAP system by setting binding properties on an instance of **SAPBinding**.</span></span> <span data-ttu-id="7789f-131">然后使用此绑定来生成通道侦听器，从中可以获取**IReplyChannel**通道从适配器接收操作。</span><span class="sxs-lookup"><span data-stu-id="7789f-131">You then use this binding to build a channel listener from which you can get an **IReplyChannel** channel to receive operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-ireplychannel-to-receive-data-changed-notifications"></a><span data-ttu-id="7789f-132">若要创建并打开 IReplyChannel 接收数据更改通知</span><span class="sxs-lookup"><span data-stu-id="7789f-132">To create and open an IReplyChannel to Receive Data-changed Notifications</span></span>  
  
1.  <span data-ttu-id="7789f-133">创建的实例**SAPBinding**。</span><span class="sxs-lookup"><span data-stu-id="7789f-133">Create an instance of **SAPBinding**.</span></span>  
  
2.  <span data-ttu-id="7789f-134">设置你想要接收的操作所需的任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7789f-134">Set any binding properties required for the operations you want to receive.</span></span> <span data-ttu-id="7789f-135">请务必设置**AcceptCredentialsInUri**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7789f-135">Be sure to set the **AcceptCredentialsInUri** binding property.</span></span>  
  
3.  <span data-ttu-id="7789f-136">创建**BindingParameterCollection**并添加**InboundActionCollection** ，其中包含你想要接收的操作的操作。</span><span class="sxs-lookup"><span data-stu-id="7789f-136">Create a **BindingParameterCollection** and add an **InboundActionCollection** that contains the actions of the operations that you want to receive.</span></span> <span data-ttu-id="7789f-137">到 SAP 系统的所有其他操作，该适配器将返回一个异常。</span><span class="sxs-lookup"><span data-stu-id="7789f-137">The adapter will return an exception to the SAP system for all other operations.</span></span> <span data-ttu-id="7789f-138">此步骤为可选步骤。</span><span class="sxs-lookup"><span data-stu-id="7789f-138">This step is optional.</span></span> <span data-ttu-id="7789f-139">有关详细信息，请参阅[接收从使用 WCF 通道模型 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="7789f-139">For more information, see [Receiving Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
4.  <span data-ttu-id="7789f-140">创建通道侦听器，通过调用**BuildChannelListener\<IReplyChannel\>** 方法**SAPBinding**。</span><span class="sxs-lookup"><span data-stu-id="7789f-140">Create a channel listener by invoking **BuildChannelListener\<IReplyChannel\>** method on the **SAPBinding**.</span></span> <span data-ttu-id="7789f-141">作为此方法的参数之一指定 SAP 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="7789f-141">You specify the SAP connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="7789f-142">连接 URI 必须包含 SAP 系统上 RFC 目标的参数。</span><span class="sxs-lookup"><span data-stu-id="7789f-142">The connection URI must contain parameters for an RFC Destination on the SAP system.</span></span> <span data-ttu-id="7789f-143">有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="7789f-143">For more information about the SAP connection URI, see The [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span> <span data-ttu-id="7789f-144">如果你创建**BindingParameterCollection**在步骤 3 中，还这可以指定当创建通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="7789f-144">If you created a **BindingParameterCollection** in step 3, you also specify this when you create the channel listener.</span></span>  
  
5.  <span data-ttu-id="7789f-145">打开侦听器。</span><span class="sxs-lookup"><span data-stu-id="7789f-145">Open the listener.</span></span>  
  
6.  <span data-ttu-id="7789f-146">获取**IReplyChannel**通道通过调用**AcceptChannel**侦听程序的方法。</span><span class="sxs-lookup"><span data-stu-id="7789f-146">Get an **IReplyChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="7789f-147">打开通道。</span><span class="sxs-lookup"><span data-stu-id="7789f-147">Open the channel.</span></span>  
  
 <span data-ttu-id="7789f-148">下面的代码演示如何创建一个通道侦听器，并获取**IReplyChannel**从适配器接收操作。</span><span class="sxs-lookup"><span data-stu-id="7789f-148">The following code shows how to create a channel listener and get an **IReplyChannel** to receive operations from the adapter.</span></span>  
  
```  
// Create a binding and specify any binding properties required  
// for the opreations you want to receive  
SAPBinding binding = new SAPBinding();  
  
// Set AcceptCredentialsInUri because the URI must contain credentials.  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying  
// the binding parameter collection (to filter for the Z_RFC_MKD_ADD action) and   
// a connection URI that contains listener parameters.  
Uri listeneraddress =  
new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, new BindingParameterCollection());  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="7789f-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7789f-149">See Also</span></span>  
[<span data-ttu-id="7789f-150">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="7789f-150">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)