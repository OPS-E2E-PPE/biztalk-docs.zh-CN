---
title: "使用 Siebel 适配器使用 WCF 通道模型运行业务组件上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, perform operations using the channel
- performing operations, using the channel
ms.assetid: bae74013-38fa-413c-ba91-4e4ba096339e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0aa0287eb13f522324080ce97fe357540947cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-the-siebel-adapter-using-the-wcf-channel-model"></a>使用 Siebel 适配器使用 WCF 通道模型运行业务组件上的操作
本部分演示如何在使用中创建的通道的 Siebel 上执行操作[创建一个通道，使用 Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md)。  
  
```  
// create binding  
SiebelBinding binding = new SiebelBinding();  
  
//set up an endpoint address  
EndpointAddress address = new EndpointAddress("siebel://Username=myuser;Password=mypass@mysiebelserver:1234?SiebelObjectManager=SSEObjMgr&SiebelEnterpriseServer=ent771&Language=enu");  
  
//create request channel factory  
IChannelFactory<IRequestChannel> factory = binding.BuildChannelFactory<IRequestChannel>(new BindingParameterCollection());  
  
//open factory  
factory.Open();  
  
//create request channel using endpoint  
IRequestChannel channel = factory.CreateChannel(address);  
  
//open the channel  
channel.Open();  
  
// send request message and receive reply  
System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create(inputXml);  
System.ServiceModel.Channels.Message messageIn = System.ServiceModel.Channels.Message.CreateMessage(MessageVersion.Default,action,readerIn);  
System.ServiceModel.Channels.Message messageOut = channel.Request(messageIn);  
  
// get response XML from SOAP message  
System.Xml.XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
// save output file  
XmlDocument doc = new XmlDocument();  
doc.Load(readerOut);  
doc.Save(outputXml);  
Console.WriteLine("XML written out to {0}", outputXml);  
  
// close the channel and the factory  
channel.Close();  
factory.Close();  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发 Siebel 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)   
 [使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)