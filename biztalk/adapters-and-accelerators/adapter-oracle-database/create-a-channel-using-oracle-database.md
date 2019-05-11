---
title: 创建一个通道，使用 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating a channel
- WCF channel model, creating a channel
- how to, create a channel
- channel programming, creating a channel
ms.assetid: a30156a0-5a5a-4418-be17-2e23c3716fc1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abce809fb62966fc311f59c8706c8d6823a16d13
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529411"
---
# <a name="create-a-channel-using-oracle-database"></a>创建一个通道，使用 Oracle 数据库
在 WCF 通道模型中，调用对 Oracle 数据库的操作和接收的交换的 SOAP 消息具有轮询查询的结果[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]通过 WCF 通道。  
  
- 通过使用调用操作 （出站操作） **IRequestChannel**或**IOutputChannel**将消息发送到适配器。  
  
- 通过接收 POLLINGSTMT 消息接收基于轮询的数据更改消息**IInputChannel**。  
  
  在本部分中的主题提供有关如何创建和配置用于入站和出站操作的通道形状的信息。  
  
## <a name="creating-outbound-client-channels"></a>创建出站 （客户端） 通道  
 你可以使用**IRequestChannel**或**IOutputChannel**调用对 Oracle 数据库的操作。 在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。 然后使用工厂来创建通道。 创建通道后可用于调用在适配器上的操作。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>若要创建并打开出站通道  
  
1. 创建和初始化的实例**ChannelFactory**为通过使用一个终结点和绑定所需的通道形状。 终结点指定 URI 的 Oracle 连接并绑定是的一个实例**OracleDBBinding**。  
  
2. 通过使用通道工厂提供的 Oracle 凭据**凭据**属性。  
  
3. 打开通道工厂。  
  
4. 通过调用获取通道的实例**CreateChannel**方法对的通道工厂。  
  
5. 打开通道。  
  
   在代码中或从配置，可以指定的绑定和终结点地址。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。 若要创建的代码**IOutputChannel**是相同，只不过必须指定**IOutputChannel**接口**ChannelFactory**和通道类型。  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
// Create address.  
EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>在配置中指定的绑定和终结点地址  
 下面的代码示例演示如何从配置中指定的客户端终结点创建通道工厂。  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a>配置设置  
 下面的代码演示上述示例使用的配置设置。 客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IRequestChannel"取决于你想要创建的通道形状的类型。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" metadataPooling="true"  
                    statementCachePurge="false" statementCacheSize="10" pollingInterval="500"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" polledDataAvailableStatement="SELECT 1 FROM DUAL"  
                    pollWhileDataFound="false" notifyOnListenerStart="true" notificationPort="-1"  
                    inboundOperationType="Polling" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="1" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="false" enablePerformanceCounters="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a>创建入站 （服务） 通道  
 在配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]轮询 Oracle 数据库表和视图的实例上设置绑定属性**OracleDBBinding**。 然后使用此绑定来生成通道侦听器可以获取**IInputChannel**通道用于接收来自适配器的入站操作消息。  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a>若要创建并打开 IInputChannel 接收消息的入站操作  
  
1. 创建的实例**OracleDBBinding**。  
  
2. 设置所需的入站操作的绑定属性。 例如，对于 POLLINGSTMT 操作中，至少必须设置**InboundOperationType**， **PollingStatement**，并**PollingInterval**绑定到的属性配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]轮询 Oracle 数据库。  
  
3. 创建一个绑定参数集合使用**BindingParameterCollection**类，并设置凭据。  
  
4. 通过调用创建的通道侦听器**BuildChannelListener\<IInputChannel\>** 方法**OracleDBBinding**。 作为此方法的参数之一指定 Oracle 连接 URI。 有关 Oracle 连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
5. 打开侦听器。  
  
6. 获取**IInputChannel**通道通过调用**AcceptChannel**在侦听器上的方法。  
  
7. 打开通道。  
  
   下面的代码演示如何创建通道侦听器，并获取**IInputChannel**到入站消息从适配器使用 POLLINGSTMT 操作。  
  
> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]仅支持单向接收。 因此，必须使用 IInputChannel 从 Oracle 数据库接收消息的入站操作。  
  
```  
// Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the PollingStatement, and  
// the PostPollStatement.  
OracleDBBinding binding = new OracleDBBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PollingInterval = 30;  
binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "SCOTT";  
credentials.UserName.Password = "TIGER";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleDB://ADAPTER");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)