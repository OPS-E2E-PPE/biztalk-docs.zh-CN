---
title: 调用函数使用 WCF 通道模型的 Oracle 数据库中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- channel programming, executing a function
- WCF channel model, invoking a function
- how to, execute a function using a channel
- executing a function, using a channel
ms.assetid: 6c15c352-3086-44f6-b265-4c7a7aee47ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 115e7e2421ed31ed20db9cbec5abdaa26a3639e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961747"
---
# <a name="invoke-a-function-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="51419-102">调用中使用 WCF 通道模型的 Oracle 数据库的函数</span><span class="sxs-lookup"><span data-stu-id="51419-102">Invoke a Function in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="51419-103">本部分演示如何使用中创建的通道 Oracle 数据库中执行的函数[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="51419-103">This section demonstrates how to execute a function in an Oracle database using the channel created in [Create a Channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).</span></span>  
  
## <a name="executing-a-function-using-the-channel"></a><span data-ttu-id="51419-104">执行使用通道函数</span><span class="sxs-lookup"><span data-stu-id="51419-104">Executing a Function Using the Channel</span></span>  
 <span data-ttu-id="51419-105">你可以在 Oracle 数据库上执行的函数，通过将传递到一条 XML 消息[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51419-105">You can execute a function on an Oracle database by passing an XML message to [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span> <span data-ttu-id="51419-106">输入 XML 如下所示：</span><span class="sxs-lookup"><span data-stu-id="51419-106">The input XML resembles the following:</span></span>  
  
```  
<CREATE_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG" xmlns:ns0="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">  
  <REC xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
    <ns0:ID>1</ns0:ID>  
    <ns0:NAME>Scott</ns0:NAME>  
    <ns0:BANKNAME>CitiBank</ns0:BANKNAME>  
    <ns0:BRANCH>NY</ns0:BRANCH>  
    <ns0:ENABLED>Y</ns0:ENABLED>  
  </REC>  
</CREATE_ACCOUNT>  
```  
  
 <span data-ttu-id="51419-107">下面的代码摘录演示如何使用通道 Oracle 数据库中执行的函数。</span><span class="sxs-lookup"><span data-stu-id="51419-107">The following code excerpt demonstrates how to execute a function in an Oracle database using a channel.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51419-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51419-108">See Also</span></span>  
 <span data-ttu-id="51419-109">[通过使用 WCF 通道模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="51419-109">[Develop Oracle Database Applications by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span></span>  
 <span data-ttu-id="51419-110">[使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="51419-110">[Run an Insert Operation in Oracle Database Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md) </span></span>  
 [<span data-ttu-id="51419-111">使用 WCF 通道模型运行 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="51419-111">Run a SQLEXECUTE Operation by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)