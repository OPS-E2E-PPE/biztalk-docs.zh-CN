---
title: "使用 WCF 通道模型使用 SELECT 语句的轮询 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f689b035f926e0fd5bbdaa159e1450fbad92b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a>轮询 Oracle E-business Suite SELECT 语句中使用 WCF 通道模型
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要通过使用 SELECT 语句持续轮询接口表接收定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。 你可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。 你还可以指定后轮询 PL/SQL 代码块适配器执行执行轮询语句后。  
  
 若要启用轮询，必须指定某些绑定属性，如本主题中所述。 有关如何适配器支持轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>使用 Oracle E-business Suite 适配器绑定属性中配置的轮询操作  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]更改消息的绑定属性，用于配置适配器，以接收数据。 在运行轮询应用程序时，必须指定这些绑定属性。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定是否想要执行**轮询**或**通知**入站操作。 默认值是**轮询**。|  
|**PolledDataAvailableStatement**|指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。 仅当一条记录时，SELECT 语句你为指定**PollingInput**将执行绑定属性。|  
|**PollingInterval**|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 30 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器休眠的剩余时间的时间间隔内。|  
|**PollingInput**|指定的轮询语句。 若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。 默认值为 null。<br /><br /> 必须指定的值**PollingInput**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。|  
|**PollingAction**|指定轮询操作的操作。 你可以确定此轮询操作的生成操作使用的服务接口[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。|  
|**PostPollStatement**|指定在指定的语句之后执行的语句块**PollingInput**绑定属性执行。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略轮询间隔和连续执行轮询语句中，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。|  
  
 有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询的 Oracle 数据库，请阅读此主题的其余部分。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 在此主题中，以演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收数据的支持更改使用 SELECT 语句的消息，轮询**MS_SAMPLE_EMPLOYEE**接口中的表**应用程序对象库**应用程序。 运行示例后，在 Oracle E-business Suite 中创建这些对象提供的 create_apps_artifacts.sql 脚本时创建此表。  
  
 为了演示轮询操作，我们执行以下操作：  
  
-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性以确定其中接口表轮询 (MS_SAMPLE_EMPLOYEE) 有任何数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     这可确保仅当 MS_SAMPLE_EMPLOYEE 接口表具有某些记录时，适配器都将执行轮询语句。  
  
-   指定 SELECT 语句，以**PollingInput**绑定属性。 此语句将检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[从 Oracle E-business Suite 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)。  
  
-   指定作为的一部分的 DELETE 语句**PostPollStatement**绑定属性。 此语句将从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     发生这种情况后下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。  
  
-   直到更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，因此必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新记录将不会获取任何轮询消息。 你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。 运行此脚本后下, 一个轮询操作将获取新记录插入到表。  
  
## <a name="consuming-the-polling-request-message"></a>使用轮询请求消息  
 适配器调用于你的代码来轮询 Oracle E-business Suite 轮询操作。 也就是说，该适配器通过 IInputChannel 通道形状发送轮询请求消息，你将收到。 轮询请求消息包含由指定的查询的结果集**PollingInput**绑定属性。 你可以使用两种方式之一中的轮询消息：  
  
-   若要使用使用节点值流式处理的消息，必须调用**WriteBodyContents**方法则会在响应消息并将其传递**XmlDictionaryWriter**实现节点值流式处理。  
  
-   若要使用使用节点流式处理的消息，你可以调用**GetReaderAtBodyContents**若要获取的响应消息**XmlReader**。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例轮询 MS_SAMPLE_EMPLOYEE 接口表。 在示例提供了一个脚本以生成表。 有关这些示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **SelectPolling_ChannelModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a>使用 WCF 通道模型的轮询操作接收入站的消息  
 此部分提供有关如何编写一个.NET 应用程序 （通道模型） 来接收使用的入站的轮询消息说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
#### <a name="to-receive-polling-messages-from-the-adapter"></a>从适配器接收轮询消息  
  
1.  创建一个在 Microsoft Visual C#® 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 有关本主题中，创建一个控制台应用程序。  
  
2.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。  
  
3.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  指定连接 URI。 有关 URI 的适配器连接的详细信息，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。  
  
    ```  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    ```  
  
5.  创建的实例**OracleEBSBinding**并设置配置轮询所需的绑定属性。 至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**， **PollingInput**，和**PollingAction**绑定的属性。 有关绑定属性用于配置轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
    binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
    binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
    binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
    ```  
  
6.  因为轮询接口表，你还必须设置应用程序上下文。 有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
    ```  
    binding.OracleUserName = "<Enter user name here>";  
    binding.OraclePassword = "<Enter password here>";  
    binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
    ```  
  
7.  创建一个绑定参数集合，并设置凭据。  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
8.  创建一个通道侦听器，并将其打开。 通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**OracleEBSBinding**。  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
9. 获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
10. 调用**接收**从适配器获取下一步的入站的消息在通道上。  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
11. 使用入站操作返回的结果集。 你可以使用使用消息**XmlReader**或**XmlDictionaryWriter**。  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
12. 已完成处理请求时，请关闭通道。  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  在完成处理入站的操作后，您必须关闭通道。 未能关闭通道可能会影响你代码的行为。  
  
13. 在完成接收数据更改消息时，请关闭该侦听器。  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  关闭侦听器不会关闭使用侦听器创建的通道。 您必须显式关闭使用侦听器创建每个通道。  
  
### <a name="example"></a>示例  
 下面的示例演示的轮询应用程序轮询 MS_SAMPLE_EMPLOYEE 接口表。 **PollingInput**属性包含从 MS_SAMPLE_EMPLOYEE 表中读取所有数据的 select 语句和 post 轮询语句从同一个表中删除所有数据。 轮询消息写入到`C:\PollingOutput.xml`。  
  
 更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表之前，后续的轮询消息将不包含任何记录。 你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。 运行此脚本后下, 一个轮询操作将获取新记录插入到表。 适配器将继续轮询，直到按关闭服务主机\<返回 >。  
  
```  
using System;  
using Microsoft.Adapters.OracleEBS;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Xml;  
  
namespace SelectPolling_ChannelModel  
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
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "<Enter user name here>";  
                binding.OraclePassword = "<Enter password here>";  
                binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
  
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
                Console.ReadLine();  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                    Console.ReadLine();  
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
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)