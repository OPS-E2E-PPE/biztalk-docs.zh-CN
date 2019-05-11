---
title: 调用上使用 WCF 通道模型，在 Oracle 数据库的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking operations, using the WCF channel model
- WCF channel model, invoking operations
- invoking operations
- operations, invoking
ms.assetid: 6dd95c18-8f78-46d0-8845-b74890614c33
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95220f03bb427d2a849b23e278763d3beb0d3632
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376500"
---
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a>调用上使用 WCF 通道模型，在 Oracle 数据库的操作
可在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过使用**IRequestChannel**或**IOutputChannel**形状将消息发送到适配器。 基本模式是通过使用绑定创建通道工厂为所需的通道形状 (**OracleDBBinding**) 并创建从一个连接 URI 的终结点。 然后，创建**消息**为目标操作的消息架构表示符合的 SOAP 消息的实例。 然后可以将发送这**消息**到[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用从通道工厂创建的通道。 如果使用的**IRequestChannel**，你收到的响应。 如果执行对 Oracle 数据库的操作问题[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将引发**Microsoft.ServiceModel.Channels.Common.TargetSystemException**。  
  
 有关如何发送操作使用的概述**IRequestChannel**在 WCF 中，查看"客户端通道级编程 》 [ http://go.microsoft.com/fwlink/?LinkId=106081 ](http://go.microsoft.com/fwlink/?LinkId=106081)。  
  
 本主题中的部分提供信息以帮助您在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型。  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a>创建和使用的消息的出站操作  
 若要在调用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，发送请求消息的目标操作使用**IRequestChannel**或**IOutputChannel**。 如果您使用**IRequestChannel**适配器返回的响应消息中的操作的结果。  
  
 详细了解请求和响应消息架构和每个操作的消息操作的详细信息，请参阅[消息和消息架构的 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。  
  
 创建请求消息和使用响应消息的方式确定是否在适配器执行节点流式处理或流式处理的节点的值。 这反过来确定是否为受支持的操作执行端到端的 LOB 数据的流式处理。  
  
### <a name="creating-the-request-message"></a>创建请求消息  
 可以通过两种方式之一创建请求消息：  
  
- 若要创建一条消息，可用于节点值流式传输，必须将传递的消息正文**XmlBodyWriter**实现节点值流式处理。  
  
- 若要创建一条消息，可用于节点流式传输，可传递的消息正文**XmlReader**。  
  
  通常使用的流式处理以支持端到端流式处理的请求消息中的 Oracle LOB 数据的节点的值。 支持此功能的唯一操作是 UpdateLOB。  
  
### <a name="consuming-the-response-message"></a>使用响应消息  
 可使用响应消息的两种方式之一：  
  
- 若要使用此消息使用节点值流式传输，必须调用**WriteBodyContents**方法在响应消息，并将其传递**XmlDictionaryWriter**实现节点值流式处理。  
  
- 若要使用可调用使用节点流式处理的消息**GetReaderAtBodyContents**若要获取在响应消息**XmlReader**。  
  
  通常使用节点值的流式处理以支持端到端流式处理的 Oracle LOB 的响应消息中的数据。 有一些支持此功能的许多操作。  
  
### <a name="lob-data-and-message-streaming-support"></a>LOB 数据和消息流式处理支持  
 详细了解如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持流式处理 LOB 数据，请参阅[流式处理大型对象数据类型在 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。  
  
 有关实现节点值在您的代码以支持端到端流式处理的 LOB 数据的流式处理的详细信息，请参阅[流式处理 Oracle 数据库 LOB 数据类型使用的 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a>对 WCF 通道模型中的出站操作的事务支持。  
 适配器将执行对 Oracle 数据库专用事务内调用每个操作。 可以通过设置控制这些事务的隔离级别**TransactionIsolationLevel**属性绑定。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例使用了 SCOTT。ACCOUNTACTIVITY 表。 使用 SDK 示例提供了一个脚本来生成这些项目。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>如何通过使用对通道调用的操作？  
 若要通过使用调用的操作**IRequestChannel**，执行以下步骤。  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>如何通过使用 IRequestChannel 的实例调用的操作  
  
1. 生成通道工厂 (**ChannelFactory\<IRequestChannel\>**)。 若要执行此操作，必须指定一个绑定 (**OracleDBBinding**) 和终结点地址。 您可以在代码中以强制方式或在配置中以声明方式指定绑定和终结点地址。 有关如何在配置中指定的绑定和终结点地址的详细信息，请参阅[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)。  
  
   ```  
   // Create a binding  
   OracleDBBinding binding = new OracleDBBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. 通过设置用户名称密码凭据的通道工厂**ClientCredentials**属性。  
  
   ```  
   factory.Credentials.UserName.UserName = "SCOTT";  
   factory.Credentials.UserName.Password = "TIGER";  
   ```  
  
3. 打开通道工厂。  
  
   ```  
   factory.Open();  
   ```  
  
4. 从工厂获取通道并将其打开。  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. 创建**消息**目标操作的实例。 请确保指定目标操作的消息操作。 在此示例中，消息正文传递通过创建**XmlReader**放在某个文件。 目标操作是 SCOTT/EMP 表上的选择操作。  
  
   ```  
   XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
   Message messageIn = Message.CreateMessage(MessageVersion.Default,  
       "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
       readerIn);  
   ```  
  
6. 调用**请求**方法将消息发送到在通道上的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]并接收回复。 如果 Oracle 数据库时遇到异常，适配器将引发**TargetSystemException**。 （其他异常是可能的非 Oracle 异常。）可以获取从 Oracle 错误的说明**InnerException.Message**的属性**TargetSystemException**。  
  
   ```  
   try  
   {  
       Message messageOut = channel.Request(messageIn);  
   }  
   catch (Exception ex)  
   {  
       // handle exception  
   }  
   ```  
  
7. 处理响应。 在此示例中， **GetReaderAtBodyContents**调用以获取消息正文的响应消息。  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. 完成处理响应消息时，关闭读取器和消息。  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. 完成后使用通道和通道工厂，将其关闭。 关闭工厂将关闭所有使用它创建的通道。  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
   请按照相同的步骤来发送邮件时使用**IOutputChannel**形状除外：  
  
-   您创建**ChannelFactory\<IOutputChannel\>** 步骤 1 中。  
  
-   在调用**发送**步骤 6 中的通道上的方法。 `channel.Send(messageIn);` 的用户。  
  
-   不没有返回任何响应消息**IOutputChannel**。  
  
### <a name="example"></a>示例  
 下面的示例演示如何使用调用 Select 操作**IRequestChannel**通道。 选择响应消息将通过使用消费**XmlReader**和返回的记录数写入到控制台。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
using System.Xml;  
using System.IO;  
using System.Runtime.Serialization;  
  
namespace RequestChanneSample  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The Select operation request message  
            const string selectRequestString =  
                "\<Select xmlns=\"http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY\"\>" +  
                    "<COLUMN_NAMES>*</COLUMN_NAMES>" +  
                    "<FILTER>ACCOUNT = 100002</FILTER>" +  
                "</Select>";  
            try  
            {  
                // Create binding -- specify binding properties before you open the factory.  
                OracleDBBinding odbBinding = new OracleDBBinding();  
  
                // Create address.  
                EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
                // Create channel factory from binding and address.  
                ChannelFactory<IRequestChannel> factory =   
                    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
                // Specify credentials   
                factory.Credentials.UserName.UserName = "SCOTT";  
                factory.Credentials.UserName.Password = "TIGER";  
  
                // Open the factory.  
                factory.Open();  
  
                // Get a channel.  
                IRequestChannel channel = factory.CreateChannel();  
  
                // Open the channel.  
                channel.Open();  
  
                // Create the request message from the string  
                StringReader strReader = new StringReader(selectRequestString);  
                XmlReader readerIn = XmlReader.Create(strReader);  
  
                Message requestMessage = Message.CreateMessage(MessageVersion.Default,  
                    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
                    readerIn);  
  
                Send the message and get a respone  
                Message responseMessage = channel.Request(requestMessage);  
  
                // Get an XmlReader from the message  
                XmlReader readerOut = (XmlReader) responseMessage.GetReaderAtBodyContents();  
  
                // Count the number of records returned and write to the console.  
                readerOut.MoveToContent();  
                int numberOfRecordsReturned = 0;  
                while (readerOut.Read())  
                {  
                    if (readerOut.NodeType == XmlNodeType.Element && readerOut.Name == "ACCOUNTACTIVITYRECORDSELECT")  
                        numberOfRecordsReturned++;  
                }  
  
                Console.WriteLine("{0} records returned.", numberOfRecordsReturned);  
  
                // Close the output reader and message  
                readerOut.Close();  
                responseMessage.Close();  
  
                //Close channel  
                channel.Close();  
  
                //Close the factory  
                factory.Close();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)