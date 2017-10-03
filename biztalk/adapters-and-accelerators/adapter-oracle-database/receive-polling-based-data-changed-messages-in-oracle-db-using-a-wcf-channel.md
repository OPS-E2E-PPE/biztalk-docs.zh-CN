---
title: "使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, receiving polling-based messages
- how to, receive polling-based messages by using the WCF channel model
ms.assetid: 13f501e4-cff7-497c-a9da-fdd6382c779f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e1596c0b0676db916068ff9a33a8be9d6a9fa3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-channel-model"></a>使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息
你可以配置[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]轮询的 Oracle 数据库表或视图的任何数据更改。 若要执行此类轮询操作，该适配器定期执行对 Oracle 表或视图后, 跟一个可选的 PL/SQL 代码块的 SQL 查询。 然后返回 SQL 查询的结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到你的代码作为强类型的结果集在入站 POLLINGSTMT 操作中。 有关用于配置和对 Oracle 执行轮询机制的详细信息数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。 强烈建议你阅读然后再继续本主题。  
  
 你配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到轮询和 Oracle 数据库表或视图中的实例上设置绑定属性**OracleDBBinding**。 在 WCF 通道模型中，您然后使用此绑定来生成通道侦听器，从中可以获取**IInputChannel**通道从适配器接收 POLLINGSTMT 操作。  
  
 有关如何接收操作使用的概述**IInputChannel**在 WCF 中，请参阅[服务通道级编程](https://msdn.microsoft.com/library/ms789029.aspx)。 
  
 此主题中的部分提供信息来帮助你对 Oracle 数据库表执行轮询和视图使用的是 WCF 通道模型。  
  
## <a name="consuming-the-pollingstmt-request-message"></a>使用 POLLINGSTMT 请求消息  
 适配器调用 POLLINGSTMT 操作于你的代码来轮询 Oracle 数据库。 适配器将通过接收 POLLINGSTMT 请求消息发送的即**IInputChannel**通道形状。 POLLINGSTMT 请求消息包含由指定的查询的结果集**PollingStatement**绑定属性。 你可以使用两种方式之一中的 POLLINGSTMT 消息：  
  
-   若要使用使用流式处理你的节点的值的消息必须调用**WriteBodyContents**方法则会在响应消息并将其传递**XmlDictionaryWriter**实现节点值流式处理。  
  
-   若要使用的消息使用节点流可以调用**GetReaderAtBodyContents**若要获取的响应消息**XmlReader**。  
  
 你通常使用流式处理以使用包含 Oracle LOB 数据列的结果集的节点的值。  
  
 有关 POLLINGSTMT 操作的消息结构的详细信息，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)。  
  
 有关详细信息，如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持流式处理 LOB 数据，请参阅[流式处理 Oracle 数据库适配器中的大型对象数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。  
  
 有关实现节点值在你的代码以支持端到端流式处理的 LOB 数据的流式处理的详细信息，请参阅[流式处理 Oracle 数据库 LOB 数据类型使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例使用 SCOTT。ACCOUNTACTIVITY 表和 SCOTT。ACCOUNT_PKG。PROCESS_ACTIVITY 函数。 在示例提供了一个脚本以生成这些项目。 该示例执行以下操作：  
  
-   作为轮询语句的一部分，从该 ACCOUNTACTIVITY 表并在控制台上的显示选择的所有记录。  
  
-   作为 post 轮询语句的一部分，该示例调用移动到 ACTIVITYHISTORY 表中从 ACCOUNTACTIVITY 表的所有记录的 PROCESS_ACTIVITY 函数。  
  
-   后续轮询 ACCOUNTACTIVITY 表上的不会返回任何记录。 但是，如果你想要作为轮询操作的一部分返回更多记录的示例，你必须在 ACCOUNTACTIVITY 表中插入一些记录。 你可以通过运行这些示例使用提供的 more_activity_data.sql 脚本来实现。  
  
 有关这些示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="how-do-i-poll-an-oracle-database-using-an-iinputchannel"></a>如何轮询使用 IInputChannel Oracle 数据库？  
 若要轮询的 Oracle 数据库表或视图，以接收数据更改消息使用 WCF 通道模型，请执行以下步骤。  
  
#### <a name="to-receive-data-changed-messages-using-an-iinputchannel"></a>接收数据更改消息使用 IInputChannel  
  
1.  创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 有关本主题中，创建一个控制台应用程序。  
  
2.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleDB`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。  
  
3.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.OracleDB`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
    -   `System.Runtime.Serialization`  
  
    -   `System.IO`  
  
    -   `Microsoft.ServiceModel.Channels.Common`  
  
4.  创建的实例**OracleDBBinding**并设置配置轮询所需的绑定属性。 至少必须设置**InboundOperationType**， **PollingStatement**，和**PollingInterval**绑定属性。 对于此示例中，你还设置**PostPollStatement**绑定属性。 有关绑定属性用于配置轮询的详细信息，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。  
  
    ```  
    OracleDBBinding binding = new OracleDBBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PollingInterval = 30;  
    binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;"  
    ```  
  
5.  创建一个绑定参数集合，并设置凭据。  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "SCOTT";  
    credentials.UserName.Password = "TIGER";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
6.  创建一个通道侦听器，并将其打开。 通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**OracleDBBinding**。 你可以通过在连接 URI 设置 PollingId 属性修改 POLLINGSTMT 操作的目标命名空间。 有关 URI 的适配器连接的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
7.  获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
8.  调用**接收**从适配器获取下一步的 POLLINGSTMT 消息在通道上。  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
9. 使用 POLLINGSTMT 操作返回的结果集。 你可以使用使用消息**XmlReader**或**XmlDictionaryWriter**。  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
10. 已完成处理请求时，请关闭通道。  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  处理 POLLINGSTMT 操作之后，您必须关闭通道。 未能关闭通道可能会影响你代码的行为。  
  
11. 在完成接收数据更改消息时，请关闭该侦听器。  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  关闭侦听器不会关闭使用侦听器创建的通道。 您必须显式关闭使用侦听器创建每个通道。  
  
### <a name="example"></a>示例  
 下面的示例演示如何配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]轮询 Oracle 数据库表和视图和接收 POLLLINGSTMT 操作使用的是 WCF 通道模型。 POLLINGSTMT 操作中返回的结果集通过向控制台写入**XmlReader**。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Add this namespace for channel model  
using System.ServiceModel.Channels;  
  
using System.Xml;  
using System.Runtime.Serialization;  
using System.IO;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace OraclePollingCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Uri connectionUri = new Uri("oracleDB://ADAPTER/");  
  
            IChannelListener<IInputChannel> listener = null;  
            IInputChannel channel = null;  
  
            // set timeout to receive POLLINGSTMT message  
            TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
            Console.WriteLine("Sample Started");  
  
            try  
            {  
                // Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the           
                // PollingStatement,and the PostPollStatement.  
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
  
                Console.WriteLine("Opening listener");  
                // get a listener  from the binding  
                listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
                listener.Open();  
  
                Console.WriteLine("Opening channel");  
                // get a channel from the listener  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel opened -- waiting for polled data");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  
  
                    // Write the TID, ACCOUNT, AMOUNT, and TRANSDATE for each record to the Console  
                    Console.WriteLine("\nPolling data received for request number {0}", i+1);  
                    Console.WriteLine("Tx ID\tACCOUNT\tAMOUNT\tTx DATE");  
  
                    while (reader.Read())  
                    {  
                        if (reader.IsStartElement())  
                        {  
                            switch (reader.Name)  
                            {  
                                case "POLLINGSTMTRECORD":  
                                    Console.Write("\n");  
                                    break;  
  
                                case "TID":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "ACCOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
                                case "AMOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "TRANSDATE":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                default:  
                                    break;  
                            }  
                        }  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    //            To save the polling data to a file you can REPLACE the code above with the following  
                    //  
                    //            XmlDocument doc = new XmlDocument();  
                    //            doc.Load(reader);  
                    //            using (XmlWriter writer = XmlWriter.Create("PollingOutput.xml"))  
                    //            {  
                    //                doc.WriteTo(writer);  
                    //            }  
                    message.Close();  
                }  
  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop polling  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)