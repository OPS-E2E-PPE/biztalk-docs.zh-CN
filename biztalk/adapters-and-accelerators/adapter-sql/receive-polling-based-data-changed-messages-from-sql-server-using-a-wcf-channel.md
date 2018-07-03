---
title: 使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0f4af71-fb0c-433d-ba74-48ee6487eb1a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6b87cdb7d36b5f143a833547e4b5522a40e0eb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987351"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-by-using-the-wcf-channel-model"></a>使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收定期的数据更改消息的 SQL Server 表或视图。 可以指定适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。  

 适配器如何支持轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  

> [!IMPORTANT]
>  如果想要在单个应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。 指定的入站的 ID 添加到要使其成为唯一的操作命名空间。  

## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收数据更改消息，请创建.NET 应用程序来**轮询**操作。 对于本主题中，指定**PolledDataAvailableStatement**作为：  

```  
SELECT COUNT(*) FROM Employee  
```  

 **PolledDataAvailableStatement**必须返回的结果集包含正值的第一个单元格。 如果第一个单元格不包含正值，适配器将不会执行轮询语句。  

 轮询语句的一部分，请执行以下操作：  

1. 从 Employee 表选择所有行。  

2. 执行存储的过程 (MOVE_EMP_DATA) 将所有记录从 Employee 表移动到 EmployeeHistory 表。  

3. 执行存储的过程 (ADD_EMP_DETAILS) 若要将新记录添加到 Employee 表。 此过程将雇员姓名、 designation 和薪金作为参数。  

   若要执行这些操作，必须指定以下**PollingStatement**绑定属性：  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 执行轮询语句后，选择从 Employee 表的所有记录，并接收到来自 SQL Server 的消息。 一旦 MOVE_EMP_DATA 存储过程执行适配器，所有记录都移动到 EmployeeHistory 表。 然后，执行 ADD_EMP_DETAILS 存储过程以将新记录添加到 Employee 表。 下一次轮询执行将仅返回一条记录。 此循环将一直继续，直到您关闭通道侦听器。  

## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>使用 SQL 适配器的绑定属性中配置轮询查询  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 轮询的.NET 应用程序的一部分，必须指定这些绑定属性。  


|         绑定属性         |                                                                                                                                                                                                                                         Description                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                             指定是否想要执行**轮询**， **TypedPolling**，或**通知**的入站操作。 默认值是**轮询**。                                                                                                                                                                              |
| **PolledDataAvailableStatement** |                                                                                       指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 SQL 语句必须返回的结果集由行和列组成。 仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行属性绑定。                                                                                       |
|   **PollingIntervalInSeconds**   |                         指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 30 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将等待间隔中的剩余时间。                          |
|       **PollingStatement**       | 指定要轮询 SQL Server 数据库表的 SQL 语句。 您可以指定简单的 SELECT 语句或存储的过程轮询语句。 默认值为 null。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。 可以指定任意数量的以分号分隔的 SQL 语句。 |
|      **PollWhileDataFound**      |                            指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略的轮询间隔，并持续执行 SQL 语句为指定**PolledDataAvailableStatement**绑定属性，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。                             |

 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请参阅此主题的其余部分。  

## <a name="consuming-the-polling-request-message"></a>使用轮询请求消息  
 适配器调用**轮询**代码来轮询 SQL Server 数据库上的操作。 也就是说，适配器通过 IInputChannel 通道形状发送您收到的轮询请求消息。 轮询请求消息包含 PollingStatement 绑定属性所指定的查询的结果集。 可以使用两种方式之一中的轮询消息：  

-   若要使用此消息使用节点值流式传输，必须调用**WriteBodyContents**方法在响应消息，并将其传递**XmlDictionaryWriter**实现节点值流式处理。  

-   若要使用可调用使用节点流式处理的消息**GetReaderAtBodyContents**若要获取在响应消息**XmlReader**。  

## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例轮询 Employee 表。 此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。 这些示例提供了一个脚本来生成这些项目。 有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。 示例中， **Polling_ChannelModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  

## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a>轮询操作使用 WCF 通道模型接收入站的消息  
 本部分说明了如何编写.NET 应用程序 （通道模型） 接收使用入站的轮询消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a>若要从 SQL 适配器接收轮询消息  

1. Microsoft Visual C# 中创建项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 有关本主题中，创建一个控制台应用程序。  

2. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。  

3. 打开 Program.cs 文件并添加以下命名空间：  

   -   `Microsoft.Adapters.Sql`  

   -   `System.ServiceModel`  

   -   `System.ServiceModel.Description`  

   -   `System.ServiceModel.Channels`  

   -   `System.Xml`  

4. 指定连接 URI。 有关适配器的连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

   ```  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
   ```  

5. 创建的实例**SqlAdapterBinding**并设置配置轮询所需的绑定属性。 至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**，并**PollingStatement**绑定属性。 有关绑定属性用于配置轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

6. 创建绑定参数集合并设置凭据。  

   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  

   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  

7. 创建通道侦听器，并将其打开。 通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**SqlAdapterBinding**。  

   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  

8. 获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。  

   ```  
   IInputChannel channel = listener.AcceptChannel();  
   channel.Open();  
   ```  

9. 调用**接收**从适配器获取下一步的 POLLINGSTMT 消息在通道上。  

    ```  
    Message message = channel.Receive();  
    ```  

10. 使用由 POLLINGSTMT 操作返回的结果集。 可以使用使用的消息**XmlReader**或**XmlDictionaryWriter**。  

    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  

11. 已完成处理请求时，请关闭通道。  

    ```  
    channel.Close()  
    ```  

    > [!IMPORTANT]
    >  处理 POLLINGSTMT 操作完成后，您必须关闭通道。 未能关闭通道可能会影响你的代码的行为。  

12. 在完成接收数据更改消息时，请关闭侦听器。  

    ```  
    listener.Close()  
    ```  

    > [!IMPORTANT]
    >  关闭侦听器不会关闭创建使用侦听器通道。 您必须显式关闭使用侦听器创建的每个通道。  

### <a name="example"></a>示例  
 下面的示例演示执行 Employee 表的轮询查询。 轮询语句将执行以下任务：  

- 从 Employee 表中选择的所有记录。  

- 执行上述 MOVE_EMP_DATA 存储过程以将所有记录从 Employee 表都移动到 EmployeeHistory 表。  

- 执行上述 ADD_EMP_DETAILS 存储过程以将一条记录添加到 Employee 表。  

  轮询消息保存在`C:\PollingOutput.xml`。  

```  
using System;  
using Microsoft.Adapters.Sql;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  

using System.Xml;  

namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  

            IInputChannel channel = null;  

            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  

                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  

                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  

                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  

                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  

                channel = listener.AcceptChannel();  
                channel.Open();  

                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
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

                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  

                    // return the cursor  
                    Console.WriteLine();  

                    // close the reader  
                    reader.Close();  

                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
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

## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)