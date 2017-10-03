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
ms.openlocfilehash: 1f69fbeb86cf63485591f048ef75cdcfd3d5056d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-channel-using-sap"></a>创建一个通道，使用 SAP
在 WCF 通道模型中，调用 SAP 系统上的操作或从 SAP 系统接收消息，通过交换使用 SOAP 消息[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过 WCF 通道。  
  
-   通过使用调用操作 （出站操作） **IRequestChannel**或**IOutputChannel**将消息发送到适配器  
  
-   接收消息 （触发从 SAP 系统） 通过**IReplyChannel**。  
  
 此部分中的主题提供有关如何创建和配置用于入站和出站操作的通道形状的信息。  
  
## <a name="creating-outbound-client-channels"></a>创建出站 （客户端） 通道  
 你可以使用**IRequestChannel**或**IOutputChannel**来调用 SAP 系统上的操作。 在任一情况下，你首先创建**System.ServiceModel.ChannelFactory**使用适当的接口。 然后可以使用工厂来创建通道。 创建通道后可用于调用在适配器上的操作。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>若要创建并打开一个出站通道  
  
1.  创建和初始化的实例**ChannelFactory**使用终结点和绑定所需的通道形状。 终结点指定 SAP 连接 URI 和绑定是的一个实例**SAPDBBinding**。 （设置之前打开通道工厂所需的任何绑定属性。）  
  
2.  通过使用中提供的通道工厂的 SAP 凭据**ClientCredentials**属性。  
  
3.  打开通道工厂。  
  
4.  获取通道的实例通过调用**CreateChannel**的通道工厂的方法。  
  
5.  打开通道。  
  
 在代码中或从配置，你可以指定的绑定和终结点地址。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码示例演示如何创建**IRequestChannel**通过在代码中指定的绑定和终结点地址。 若要创建的代码**IOutputChannel**具有相同，只不过你必须指定**IOutputChannel**接口**ChannelFactory**并通道类型。  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>在配置中指定的绑定和终结点地址  
 下面的代码示例演示如何从配置中指定的客户端终结点创建通道工厂。  
  
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
  
#### <a name="the-configuration-settings"></a>配置设置  
 下面的代码演示使用前面示例的配置设置。 客户端终结点的协定必须是"System.ServiceModel.Channels.IRequestChannel"或"System.ServiceModel.Channels.IRequestChannel"根据你想要创建的通道形状的种类。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
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
    \</system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a>创建入站 （服务） 通道  
 配置以设置绑定属性的实例上将入站的消息接收某个 SAP 系统的适配器**SAPBinding**。 然后使用此绑定来生成通道侦听器，从中可以获取**IReplyChannel**通道从适配器接收操作。  
  
##### <a name="to-create-and-open-an-ireplychannel-to-receive-data-changed-notifications"></a>若要创建并打开 IReplyChannel 接收数据更改通知  
  
1.  创建的实例**SAPBinding**。  
  
2.  设置你想要接收的操作所需的任何绑定属性。 请务必设置**AcceptCredentialsInUri**绑定属性。  
  
3.  创建**BindingParameterCollection**并添加**InboundActionCollection** ，其中包含你想要接收的操作的操作。 到 SAP 系统的所有其他操作，该适配器将返回一个异常。 此步骤为可选步骤。 有关详细信息，请参阅[接收从使用 WCF 通道模型 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。  
  
4.  创建通道侦听器，通过调用**BuildChannelListener\<IReplyChannel >**方法**SAPBinding**。 作为此方法的参数之一指定 SAP 连接 URI。 连接 URI 必须包含 SAP 系统上 RFC 目标的参数。 有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。 如果你创建**BindingParameterCollection**在步骤 3 中，还这可以指定当创建通道侦听器。  
  
5.  打开侦听器。  
  
6.  获取**IReplyChannel**通道通过调用**AcceptChannel**侦听程序的方法。  
  
7.  打开通道。  
  
 下面的代码演示如何创建一个通道侦听器，并获取**IReplyChannel**从适配器接收操作。  
  
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
  
## <a name="see-also"></a>另请参阅  
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)