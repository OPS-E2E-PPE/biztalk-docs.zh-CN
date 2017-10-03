---
title: "调用函数使用 WCF 通道模型的 Oracle 数据库中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- channel programming, executing a function
- WCF channel model, invoking a function
- how to, execute a function using a channel
- executing a function, using a channel
ms.assetid: 6c15c352-3086-44f6-b265-4c7a7aee47ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc38e0ce4dc1f6ae184b51ee157fb4461364a85e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-a-function-in-oracle-database-using-the-wcf-channel-model"></a>调用中使用 WCF 通道模型的 Oracle 数据库的函数
本部分演示如何使用中创建的通道 Oracle 数据库中执行的函数[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)。  
  
## <a name="executing-a-function-using-the-channel"></a>执行使用通道函数  
 你可以在 Oracle 数据库上执行的函数，通过将传递到一条 XML 消息[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。 输入 XML 如下所示：  
  
```  
\<CREATE_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG" xmlns:ns0="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">  
  <REC xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
    \<ns0:ID>1\</ns0:ID>  
    \<ns0:NAME>Scott\</ns0:NAME>  
    \<ns0:BANKNAME>CitiBank\</ns0:BANKNAME>  
    \<ns0:BRANCH>NY\</ns0:BRANCH>  
    \<ns0:ENABLED>Y\</ns0:ENABLED>  
  </REC>  
</CREATE_ACCOUNT>  
```  
  
 下面的代码摘录演示如何使用通道 Oracle 数据库中执行的函数。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Xml;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
using Microsoft.ServiceModel.Adapters;  
using Microsoft.Adapters.OracleDB;  
  
namespace OraclePackageChannel  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create Endpoint  
            EndpointAddress address = new EndpointAddress("oracledb:// ADAPTER");  
  
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
            System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("Create_Account.xml");  
  
            Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT", readerIn);  
            Message messageOut = channel.Request(messageIn);  
  
            // Get Response XML  
            XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
            // Get Employee ID  
            XmlDocument doc = new XmlDocument();  
            doc.Load(readerOut);  
            doc.Save("d:\\out.xml");  
  
            messageOut.Close();  
            channel.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 通道模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)   
 [使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)   
 [使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)