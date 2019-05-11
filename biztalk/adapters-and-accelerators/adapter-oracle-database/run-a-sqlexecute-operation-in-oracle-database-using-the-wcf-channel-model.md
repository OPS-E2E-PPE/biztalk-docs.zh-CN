---
title: 在 Oracle 数据库中使用 WCF 通道模型运行 SQLEXECUTE 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- running a SQLEXECUTE statement, using a channel
- how to, run a SQLEXECUTE statement by using a channel
- WCF channel model, running a SQLEXECUTE statement
ms.assetid: e1af11ef-3f44-4726-99ca-d6961d79e651
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef49976eb15f5022871549f5240b22a97b908312
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528943"
---
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a>在 Oracle 数据库中使用 WCF 通道模型运行 SQLEXECUTE 操作
本部分演示如何通过通道执行 SQLEXECUTE 操作的 Oracle 数据库。 必须对 SOAP 消息中指定的消息和消息操作。 SQLEXECUTE 操作的详细信息，请参阅[在 Oracle 数据库中使用 WCF 服务模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)。  
  
## <a name="the-sqlexecute-message"></a>SQLEXECUTE 消息  
 下面的 XML 演示 SQLEXECUTE 消息，它返回一个 Oracle 序列的下一个值。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 SQLEXECUTE 可以指定的参数架构元素和一个参数块以包含多个参数数据集。 所显示的消息是指定的 SQL 语句的单个调用，因此消息正文中省略了指定的参数架构和参数块元素。 SQLEXECUTE 操作的消息架构有关的信息，请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。  
  
## <a name="specifying-the-sqlexecute-action"></a>指定 SQLEXECUTE 操作  
 必须指定消息的操作。 以下代码摘录显示了如何指定 SQLEXECUTE 消息的操作。  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a>发送 SQLEXECUTE 消息  
 以下代码段演示如何通过对通道调用 SQLEXECUTE 操作的 Oracle 数据库。  
  
```  
// Create Endpoint  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
  
// Create Binding  
OracleDBBinding binding = new OracleDBBinding();  
  
// Create Channel Factory  
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
// Create Request Channel  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
  
// Send Request  
System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("SQLExecute.xml");  
  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
Message messageOut = channel.Request(messageIn);  
  
// Get Response XML  
XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
// Get tid_seq SEQUENCE  
string id = null;  
XmlDocument doc = new XmlDocument();  
doc.Load(readerOut);  
XmlNodeList list = doc.GetElementsByTagName("ColumnValue");  
if (list.Count > 0) id = list[0].InnerXml;  
```  
  
> [!NOTE]
>  SQLEXECUTE 操作始终返回弱类型化结果集。  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)