---
title: "创建一个通道，使用 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e86398f6-c835-46f8-814f-31e43b18970e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c31146310b8c8b559fcd93d19362679b060cb42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="create-a-channel-using-the-sql-adapter"></a><span data-ttu-id="52b5b-102">创建一个通道，使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="52b5b-102">Create a channel using the SQL adapter</span></span>
<span data-ttu-id="52b5b-103">在 WCF 通道模型中，调用 SQL Server 数据库上的操作并通过交换使用 SOAP 消息接收结果[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]通过 WCF 通道。</span><span class="sxs-lookup"><span data-stu-id="52b5b-103">In the WCF channel model, you invoke operations on the SQL Server database and receive the results by exchanging SOAP messages with the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="52b5b-104">通过使用调用出站操作**IRequestChannel**或**IOutputChannel**将消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="52b5b-104">You invoke outbound operations by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
-   <span data-ttu-id="52b5b-105">通过接收消息接收入站操作的消息**IInputChannel**为**轮询**， **TypedPolling**，或**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="52b5b-105">You receive messages for inbound operations by receiving messages over an **IInputChannel** for **Polling**, **TypedPolling**, or **Notification** operations.</span></span>  
  
 <span data-ttu-id="52b5b-106">本主题中的过程提供有关如何创建和配置用于入站和出站操作的通道形状的信息。</span><span class="sxs-lookup"><span data-stu-id="52b5b-106">The procedures in this topic provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="52b5b-107">创建出站 （客户端） 通道</span><span class="sxs-lookup"><span data-stu-id="52b5b-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="52b5b-108">你可以使用**IRequestChannel**或**IOutputChannel**来调用 SQL Server 数据库上的操作。</span><span class="sxs-lookup"><span data-stu-id="52b5b-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the SQL Server database.</span></span> <span data-ttu-id="52b5b-109">在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。</span><span class="sxs-lookup"><span data-stu-id="52b5b-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="52b5b-110">然后可以使用工厂来创建通道。</span><span class="sxs-lookup"><span data-stu-id="52b5b-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="52b5b-111">创建通道后可用于调用在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="52b5b-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="52b5b-112">若要创建并打开一个出站通道</span><span class="sxs-lookup"><span data-stu-id="52b5b-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="52b5b-113">创建和初始化的实例**ChannelFactory**使用终结点和绑定所需的通道形状。</span><span class="sxs-lookup"><span data-stu-id="52b5b-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="52b5b-114">终结点指定的 SQL Server 连接 URI 和绑定是的一个实例**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="52b5b-114">The endpoint specifies a SQL Server connection URI and the binding is an instance of **sqlBinding**.</span></span>  
  
2.  <span data-ttu-id="52b5b-115">通过使用中提供的通道工厂的 SQL Server 凭据**凭据**属性。</span><span class="sxs-lookup"><span data-stu-id="52b5b-115">Provide SQL Server credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3.  <span data-ttu-id="52b5b-116">打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="52b5b-116">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="52b5b-117">获取通道的实例通过调用**CreateChannel**的通道工厂的方法。</span><span class="sxs-lookup"><span data-stu-id="52b5b-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="52b5b-118">打开通道。</span><span class="sxs-lookup"><span data-stu-id="52b5b-118">Open the channel.</span></span>  
  
 <span data-ttu-id="52b5b-119">在代码中或从配置，你可以指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="52b5b-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="52b5b-120">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="52b5b-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="52b5b-121">下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="52b5b-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="52b5b-122">若要创建的代码**IOutputChannel**具有相同，只不过你必须指定**IOutputChannel**接口**ChannelFactory**并通道类型。</span><span class="sxs-lookup"><span data-stu-id="52b5b-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
SqlAdapterBinding sdbBinding = new SqlAdapterBinding();  
  
// Create address.  
EndpointAddress sdbAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sdbBinding, sdbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="52b5b-123">在配置中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="52b5b-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="52b5b-124">下面的代码示例演示如何从配置中指定的客户端终结点创建通道工厂。</span><span class="sxs-lookup"><span data-stu-id="52b5b-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="52b5b-125">配置设置</span><span class="sxs-lookup"><span data-stu-id="52b5b-125">The Configuration Settings</span></span>  
 <span data-ttu-id="52b5b-126">下面的代码演示使用前面示例的配置设置。</span><span class="sxs-lookup"><span data-stu-id="52b5b-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="52b5b-127">客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IOutputChannel"根据你想要创建的通道形状的种类。</span><span class="sxs-lookup"><span data-stu-id="52b5b-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sqlBinding>  
                <binding name="SqlAdapterBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" maxConnectionPoolSize="100"  
                    encrypt="false" useAmbientTransaction="true" batchSize="20"  
                    polledDataAvailableStatement="" pollingStatement="" pollingIntervalInSeconds="30"  
                    pollWhileDataFound="false" notificationStatement="" notifyOnListenerStart="true"  
                    enableBizTalkCompatibilityMode="true" chunkSize="4194304"  
                    inboundOperationType="Polling" useDatabaseNameInXsdNamespace="false"  
                    allowIdentityInsert="false" enablePerformanceCounters="false"  
                    xmlStoredProcedureRootNodeName="" xmlStoredProcedureRootNodeNamespace="" />  
            </sqlBinding>  
        </bindings>  
        <client>  
            <endpoint address="mssql://mysqlserver//mydatabase?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="creating-inbound-service-channels"></a><span data-ttu-id="52b5b-128">创建入站 （服务） 通道</span><span class="sxs-lookup"><span data-stu-id="52b5b-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="52b5b-129">你配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]轮询通过设置绑定属性的实例上的 SQL Server 数据库表和视图**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="52b5b-129">You configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll the SQL Server database tables and views by setting binding properties on an instance of **sqlBinding**.</span></span> <span data-ttu-id="52b5b-130">然后使用此绑定来生成通道侦听器，从中可以获取**IInputChannel**通道接收**轮询**， **TypedPolling**，或**通知**适配器中的操作。</span><span class="sxs-lookup"><span data-stu-id="52b5b-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive the **Polling**, **TypedPolling**, or **Notification** operation from the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a><span data-ttu-id="52b5b-131">若要创建并打开 IInputChannel 接收入站的操作</span><span class="sxs-lookup"><span data-stu-id="52b5b-131">To create and open an IInputChannel to receive inbound operations</span></span>  
  
1.  <span data-ttu-id="52b5b-132">创建的实例**SQLBinding**。</span><span class="sxs-lookup"><span data-stu-id="52b5b-132">Create an instance of **SQLBinding**.</span></span>  
  
2.  <span data-ttu-id="52b5b-133">设置入站操作所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="52b5b-133">Set the binding properties required for inbound operation.</span></span> <span data-ttu-id="52b5b-134">例如，对于**轮询**操作，必须设置至少**InboundOperationType**， **PolledDataAvailableStatement**，和**PollingStatement**绑定属性来配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]轮询 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="52b5b-134">For example, for a **Polling** operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement** binding properties to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="52b5b-135">创建通道侦听器，通过调用**BuildChannelListener\<IInputChannel\>** 方法**SQLBinding**。</span><span class="sxs-lookup"><span data-stu-id="52b5b-135">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **SQLBinding**.</span></span> <span data-ttu-id="52b5b-136">作为此方法的参数之一指定 SQL Server 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="52b5b-136">You specify the SQL Server connection URI as one of the parameters to this method.</span></span>  
  
4.  <span data-ttu-id="52b5b-137">打开侦听器。</span><span class="sxs-lookup"><span data-stu-id="52b5b-137">Open the listener.</span></span>  
  
5.  <span data-ttu-id="52b5b-138">获取**IInputChannel**通道通过调用**AcceptChannel**侦听程序的方法。</span><span class="sxs-lookup"><span data-stu-id="52b5b-138">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
6.  <span data-ttu-id="52b5b-139">打开通道。</span><span class="sxs-lookup"><span data-stu-id="52b5b-139">Open the channel.</span></span>  
  
 <span data-ttu-id="52b5b-140">下面的代码演示如何创建一个通道侦听器，并获取**IInputChannel**从适配器接收数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="52b5b-140">The following code shows how to create a channel listener and get an **IInputChannel** to receive data-changed messages from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52b5b-141">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]仅支持单向接收。</span><span class="sxs-lookup"><span data-stu-id="52b5b-141">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="52b5b-142">因此，你必须使用**IInputChannel**从 SQL Server 接收入站操作的消息。</span><span class="sxs-lookup"><span data-stu-id="52b5b-142">So, you must use **IInputChannel** to receive messages for inbound operations from SQL Server.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, and   
// the PollingStatement binding properties.  
SqlAdapterBinding binding = new SqlAdapterBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="52b5b-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52b5b-143">See Also</span></span>  
[<span data-ttu-id="52b5b-144">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="52b5b-144">Develop applications using the WCF Channel model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)