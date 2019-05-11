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
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="88728-102">在 Oracle 数据库中使用 WCF 通道模型运行 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="88728-102">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="88728-103">本部分演示如何通过通道执行 SQLEXECUTE 操作的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="88728-103">This section shows how to perform a SQLEXECUTE operation on an Oracle database over a channel.</span></span> <span data-ttu-id="88728-104">必须对 SOAP 消息中指定的消息和消息操作。</span><span class="sxs-lookup"><span data-stu-id="88728-104">You must specify both a message and a message action on the SOAP message.</span></span> <span data-ttu-id="88728-105">SQLEXECUTE 操作的详细信息，请参阅[在 Oracle 数据库中使用 WCF 服务模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="88728-105">For more information about the SQLEXECUTE operation, see [Run SQLEXECUTE operation in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="the-sqlexecute-message"></a><span data-ttu-id="88728-106">SQLEXECUTE 消息</span><span class="sxs-lookup"><span data-stu-id="88728-106">The SQLEXECUTE Message</span></span>  
 <span data-ttu-id="88728-107">下面的 XML 演示 SQLEXECUTE 消息，它返回一个 Oracle 序列的下一个值。</span><span class="sxs-lookup"><span data-stu-id="88728-107">The following XML shows a SQLEXECUTE message that returns the next value of an Oracle SEQUENCE.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="88728-108">SQLEXECUTE 可以指定的参数架构元素和一个参数块以包含多个参数数据集。</span><span class="sxs-lookup"><span data-stu-id="88728-108">The SQLEXECUTE can specify a parameter schema element and a parameter block that contains multiple sets of parameter data.</span></span> <span data-ttu-id="88728-109">所显示的消息是指定的 SQL 语句的单个调用，因此消息正文中省略了指定的参数架构和参数块元素。</span><span class="sxs-lookup"><span data-stu-id="88728-109">The message shown is for a single invocation of the specified SQL statement so the elements that specify the parameter schema and parameter block are omitted from the message body.</span></span> <span data-ttu-id="88728-110">SQLEXECUTE 操作的消息架构有关的信息，请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="88728-110">For information about the message schema for the SQLEXECUTE operation, see [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span></span>  
  
## <a name="specifying-the-sqlexecute-action"></a><span data-ttu-id="88728-111">指定 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="88728-111">Specifying the SQLEXECUTE Action</span></span>  
 <span data-ttu-id="88728-112">必须指定消息的操作。</span><span class="sxs-lookup"><span data-stu-id="88728-112">You must specify an action for the message.</span></span> <span data-ttu-id="88728-113">以下代码摘录显示了如何指定 SQLEXECUTE 消息的操作。</span><span class="sxs-lookup"><span data-stu-id="88728-113">The following code excerpt shows how to specify the action for the SQLEXECUTE message.</span></span>  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a><span data-ttu-id="88728-114">发送 SQLEXECUTE 消息</span><span class="sxs-lookup"><span data-stu-id="88728-114">Sending the SQLEXECUTE Message</span></span>  
 <span data-ttu-id="88728-115">以下代码段演示如何通过对通道调用 SQLEXECUTE 操作的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="88728-115">The following code excerpt demonstrates how to invoke a SQLEXECUTE operation on an Oracle database over a channel.</span></span>  
  
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
>  <span data-ttu-id="88728-116">SQLEXECUTE 操作始终返回弱类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="88728-116">The SQLEXECUTE operation always returns a weakly-typed result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88728-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="88728-117">See Also</span></span>  
 [<span data-ttu-id="88728-118">开发 Oracle 数据库应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="88728-118">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [<span data-ttu-id="88728-119">创建一个通道，使用 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="88728-119">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)