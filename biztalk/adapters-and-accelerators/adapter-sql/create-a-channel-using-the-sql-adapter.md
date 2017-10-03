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
ms.openlocfilehash: f79fa2e40bd80bb3a4fd8b976aa31a34e4d3c0bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-channel-using-the-sql-adapter"></a>创建一个通道，使用 SQL 适配器
在 WCF 通道模型中，调用 SQL Server 数据库上的操作并通过交换使用 SOAP 消息接收结果[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]通过 WCF 通道。  
  
-   通过使用调用出站操作**IRequestChannel**或**IOutputChannel**将消息发送到适配器。  
  
-   通过接收消息接收入站操作的消息**IInputChannel**为**轮询**， **TypedPolling**，或**通知**操作。  
  
 本主题中的过程提供有关如何创建和配置用于入站和出站操作的通道形状的信息。  
  
## <a name="creating-outbound-client-channels"></a>创建出站 （客户端） 通道  
 你可以使用**IRequestChannel**或**IOutputChannel**来调用 SQL Server 数据库上的操作。 在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。 然后可以使用工厂来创建通道。 创建通道后可用于调用在适配器上的操作。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>若要创建并打开一个出站通道  
  
1.  创建和初始化的实例**ChannelFactory**使用终结点和绑定所需的通道形状。 终结点指定的 SQL Server 连接 URI 和绑定是的一个实例**sqlBinding**。  
  
2.  通过使用中提供的通道工厂的 SQL Server 凭据**凭据**属性。  
  
3.  打开通道工厂。  
  
4.  获取通道的实例通过调用**CreateChannel**的通道工厂的方法。  
  
5.  打开通道。  
  
 在代码中或从配置，你可以指定的绑定和终结点地址。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。 若要创建的代码**IOutputChannel**具有相同，只不过你必须指定**IOutputChannel**接口**ChannelFactory**并通道类型。  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>在配置中指定的绑定和终结点地址  
 下面的代码示例演示如何从配置中指定的客户端终结点创建通道工厂。  
  
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
  
#### <a name="the-configuration-settings"></a>配置设置  
 下面的代码演示使用前面示例的配置设置。 客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IOutputChannel"根据你想要创建的通道形状的种类。  
  
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
  
## <a name="creating-inbound-service-channels"></a>创建入站 （服务） 通道  
 你配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]轮询通过设置绑定属性的实例上的 SQL Server 数据库表和视图**sqlBinding**。 然后使用此绑定来生成通道侦听器，从中可以获取**IInputChannel**通道接收**轮询**， **TypedPolling**，或**通知**适配器中的操作。  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a>若要创建并打开 IInputChannel 接收入站的操作  
  
1.  创建的实例**SQLBinding**。  
  
2.  设置入站操作所需的绑定属性。 例如，对于**轮询**操作，必须设置至少**InboundOperationType**， **PolledDataAvailableStatement**，和**PollingStatement**绑定属性来配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]轮询 SQL Server 数据库。  
  
3.  创建通道侦听器，通过调用**BuildChannelListener\<IInputChannel >**方法**SQLBinding**。 作为此方法的参数之一指定 SQL Server 连接 URI。  
  
4.  打开侦听器。  
  
5.  获取**IInputChannel**通道通过调用**AcceptChannel**侦听程序的方法。  
  
6.  打开通道。  
  
 下面的代码演示如何创建一个通道侦听器，并获取**IInputChannel**从适配器接收数据更改消息。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]仅支持单向接收。 因此，你必须使用**IInputChannel**从 SQL Server 接收入站操作的消息。  
  
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
  
## <a name="see-also"></a>另请参阅  
[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)