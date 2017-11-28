---
title: "创建一个通道，使用 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d18b7c2f-a43e-4499-ba94-4955dd5fe641
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4273ab2dad26cee8f600ff3e502d88933d243e70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-channel-using-oracle-e-business-suite"></a><span data-ttu-id="cf261-102">创建一个通道，使用 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="cf261-102">Create a channel using Oracle E-Business Suite</span></span>
<span data-ttu-id="cf261-103">在 WCF 通道模型中，调用对 Oracle E-business Suite 操作并通过交换使用 SOAP 消息接收结果[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]通过 WCF 通道。</span><span class="sxs-lookup"><span data-stu-id="cf261-103">In the WCF channel model, you invoke operations on the Oracle E-Business Suite and receive the results by exchanging SOAP messages with the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="cf261-104">通过使用调用操作 （出站操作） **IRequestChannel**或**IOutputChannel**将消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="cf261-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
-   <span data-ttu-id="cf261-105">通过接收入站操作的消息**IInputChannel**。</span><span class="sxs-lookup"><span data-stu-id="cf261-105">You receive messages for inbound operations over an **IInputChannel**.</span></span>  
  
 <span data-ttu-id="cf261-106">此部分中的主题提供有关如何创建和配置用于入站和出站操作的通道形状的信息。</span><span class="sxs-lookup"><span data-stu-id="cf261-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="cf261-107">创建出站 （客户端） 通道</span><span class="sxs-lookup"><span data-stu-id="cf261-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="cf261-108">你可以使用**IRequestChannel**或**IOutputChannel**来调用上 Oracle E-business Suite 操作。</span><span class="sxs-lookup"><span data-stu-id="cf261-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="cf261-109">在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。</span><span class="sxs-lookup"><span data-stu-id="cf261-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="cf261-110">然后可以使用工厂来创建通道。</span><span class="sxs-lookup"><span data-stu-id="cf261-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="cf261-111">创建通道后可用于调用在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="cf261-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="cf261-112">若要创建并打开一个出站通道</span><span class="sxs-lookup"><span data-stu-id="cf261-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="cf261-113">创建和初始化的实例**ChannelFactory**使用终结点和绑定所需的通道形状。</span><span class="sxs-lookup"><span data-stu-id="cf261-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="cf261-114">终结点指定 Oracle E-business Suite 连接 URI 和绑定是的一个实例**OracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="cf261-114">The endpoint specifies an Oracle E-Business Suite connection URI and the binding is an instance of **OracleEBSBinding**.</span></span>  
  
2.  <span data-ttu-id="cf261-115">通过使用中提供的通道工厂的 Oracle E-business Suite 凭据**凭据**属性。</span><span class="sxs-lookup"><span data-stu-id="cf261-115">Provide Oracle E-Business Suite credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3.  <span data-ttu-id="cf261-116">打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="cf261-116">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="cf261-117">获取通道的实例通过调用**CreateChannel**的通道工厂的方法。</span><span class="sxs-lookup"><span data-stu-id="cf261-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="cf261-118">打开通道。</span><span class="sxs-lookup"><span data-stu-id="cf261-118">Open the channel.</span></span>  
  
 <span data-ttu-id="cf261-119">在代码中或从配置，你可以指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="cf261-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="cf261-120">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="cf261-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="cf261-121">下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="cf261-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="cf261-122">若要创建的代码**IOutputChannel**具有相同，只不过你必须指定**IOutputChannel**接口**ChannelFactory**并通道类型。</span><span class="sxs-lookup"><span data-stu-id="cf261-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleEBSBinding binding = new OracleEBSBinding();  
  
// Create address  
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(binding, address);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="cf261-123">在配置中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="cf261-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="cf261-124">下面的代码示例演示如何从配置中指定的客户端终结点创建通道工厂。</span><span class="sxs-lookup"><span data-stu-id="cf261-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
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
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="cf261-125">配置设置</span><span class="sxs-lookup"><span data-stu-id="cf261-125">The Configuration Settings</span></span>  
 <span data-ttu-id="cf261-126">下面的代码演示使用前面示例的配置设置。</span><span class="sxs-lookup"><span data-stu-id="cf261-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="cf261-127">客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IOutputChannel"根据你想要创建的通道形状的种类。</span><span class="sxs-lookup"><span data-stu-id="cf261-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true" enablePerformanceCounters="false">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://oracle_ebs_instance/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="cf261-128">创建入站 （服务） 通道</span><span class="sxs-lookup"><span data-stu-id="cf261-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="cf261-129">你配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]轮询通过设置绑定属性的实例上的 Oracle 数据库表和视图**OracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="cf261-129">You configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database tables and views by setting binding properties on an instance of **OracleEBSBinding**.</span></span> <span data-ttu-id="cf261-130">然后使用此绑定来生成通道侦听器，从中可以获取**IInputChannel**通道从适配器接收入站的操作。</span><span class="sxs-lookup"><span data-stu-id="cf261-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive inbound operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a><span data-ttu-id="cf261-131">若要创建并打开 IInputChannel 接收入站操作的消息</span><span class="sxs-lookup"><span data-stu-id="cf261-131">To create and open an IInputChannel to receive messages for inbound operations</span></span>  
  
1.  <span data-ttu-id="cf261-132">创建的实例**OracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="cf261-132">Create an instance of **OracleEBSBinding**.</span></span>  
  
2.  <span data-ttu-id="cf261-133">设置入站操作所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cf261-133">Set the binding properties required for the inbound operation.</span></span> <span data-ttu-id="cf261-134">例如，对于轮询操作，至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**， **PollingAction**，和**PollingInput**绑定属性来配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]轮询 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="cf261-134">For example, for a polling operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingAction**, and the **PollingInput** binding properties to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database.</span></span>  
  
3.  <span data-ttu-id="cf261-135">创建一个绑定参数集合使用**BindingParameterCollection**类，然后设置凭据。</span><span class="sxs-lookup"><span data-stu-id="cf261-135">Create a binding parameter collection using the **BindingParameterCollection** class and set the credentials.</span></span>  
  
4.  <span data-ttu-id="cf261-136">创建通道侦听器，通过调用**BuildChannelListener\<IInputChannel >**方法**OracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="cf261-136">Create a channel listener by invoking **BuildChannelListener\<IInputChannel>** method on the **OracleEBSBinding**.</span></span> <span data-ttu-id="cf261-137">作为此方法的参数之一指定 Oracle 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="cf261-137">You specify the Oracle connection URI as one of the parameters to this method.</span></span>  
  
5.  <span data-ttu-id="cf261-138">打开侦听器。</span><span class="sxs-lookup"><span data-stu-id="cf261-138">Open the listener.</span></span>  
  
6.  <span data-ttu-id="cf261-139">获取**IInputChannel**通道通过调用**AcceptChannel**侦听程序的方法。</span><span class="sxs-lookup"><span data-stu-id="cf261-139">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="cf261-140">打开通道。</span><span class="sxs-lookup"><span data-stu-id="cf261-140">Open the channel.</span></span>  
  
 <span data-ttu-id="cf261-141">下面的代码演示如何创建一个通道侦听器，并获取**IInputChannel**从适配器接收入站操作的消息。</span><span class="sxs-lookup"><span data-stu-id="cf261-141">The following code shows how to create a channel listener and get an **IInputChannel** to receive messages for inbound operations from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf261-142">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]仅支持单向接收。</span><span class="sxs-lookup"><span data-stu-id="cf261-142">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="cf261-143">因此，你必须使用**IInputChannel**接收来自 Oracle E-business Suite 的入站操作的消息。</span><span class="sxs-lookup"><span data-stu-id="cf261-143">So, you must use **IInputChannel** to receive messages for inbound operations from Oracle E-Business Suite.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, the PollingAction, and   
// the PollingInput binding properties.  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleebs://oracle_ebs_instance/");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf261-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf261-144">See Also</span></span>  
 [<span data-ttu-id="cf261-145">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="cf261-145">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)