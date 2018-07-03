---
title: 创建一个通道，使用 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d18b7c2f-a43e-4499-ba94-4955dd5fe641
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947dc1a0a2b602d1dbcce032f721998b9fc84a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984638"
---
# <a name="create-a-channel-using-oracle-e-business-suite"></a>创建一个通道，使用 Oracle E-business Suite
在 WCF 通道模型中，调用对 Oracle E-business Suite 操作并通过交换 SOAP 消息接收结果[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]通过 WCF 通道。  
  
- 通过使用调用操作 （出站操作） **IRequestChannel**或**IOutputChannel**将消息发送到适配器。  
  
- 通过接收消息的入站操作**IInputChannel**。  
  
  在本部分中的主题提供有关如何创建和配置用于入站和出站操作的通道形状的信息。  
  
## <a name="creating-outbound-client-channels"></a>创建出站 （客户端） 通道  
 你可以使用**IRequestChannel**或**IOutputChannel**调用 Oracle E-business Suite 操作。 在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。 然后使用工厂来创建通道。 创建通道后可用于调用在适配器上的操作。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>若要创建并打开出站通道  
  
1. 创建和初始化的实例**ChannelFactory**为通过使用一个终结点和绑定所需的通道形状。 终结点指定 Oracle E-business Suite 连接 URI 和绑定是的一个实例**OracleEBSBinding**。  
  
2. 使用通道工厂提供 Oracle E-business Suite 凭据**凭据**属性。  
  
3. 打开通道工厂。  
  
4. 通过调用获取通道的实例**CreateChannel**方法对的通道工厂。  
  
5. 打开通道。  
  
   在代码中或从配置，可以指定的绑定和终结点地址。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。 若要创建的代码**IOutputChannel**是相同，只不过必须指定**IOutputChannel**接口**ChannelFactory**和通道类型。  
  
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
 下面的代码演示上述示例使用的配置设置。 客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IOutputChannel"取决于你想要创建的通道形状的类型。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
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
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a>创建入站 （服务） 通道  
 在配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]轮询 Oracle 数据库表和视图的实例上设置绑定属性**OracleEBSBinding**。 然后使用此绑定来生成通道侦听器可以获取**IInputChannel**频道从适配器接收的入站的操作。  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a>若要创建并打开 IInputChannel 接收消息的入站操作  
  
1. 创建的实例**OracleEBSBinding**。  
  
2. 设置所需的入站操作的绑定属性。 例如，对于轮询操作，至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**， **PollingAction**，以及**PollingInput**绑定属性来配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]轮询 Oracle 数据库。  
  
3. 创建一个绑定参数集合使用**BindingParameterCollection**类，并设置凭据。  
  
4. 通过调用创建的通道侦听器**BuildChannelListener\<IInputChannel\>** 方法**OracleEBSBinding**。 作为此方法的参数之一指定 Oracle 连接 URI。  
  
5. 打开侦听器。  
  
6. 获取**IInputChannel**通道通过调用**AcceptChannel**在侦听器上的方法。  
  
7. 打开通道。  
  
   下面的代码演示如何创建通道侦听器，并获取**IInputChannel**从适配器接收消息的入站操作。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]仅支持单向接收。 因此，必须使用**IInputChannel**以接收来自 Oracle E-business Suite 的入站操作消息。  
  
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
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)