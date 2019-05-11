---
title: 调用上使用 WCF 通道模型的 SAP 系统的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, supporting BAPI transactions
- WCF channel model, invoking operations on the SAP system
ms.assetid: 80ed85ff-360d-4b7f-a119-cd2a99c21cf4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eeaa671bbcc1ad45ab06074d6cef6e362e66c41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373386"
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a>调用上使用 WCF 通道模型的 SAP 系统的操作
在调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过使用**IRequestChannel**或**IOutputChannel**通道形状将消息发送到适配器。 基本模式是通过使用绑定创建通道工厂为所需的通道形状 (**SAPBinding**) 并创建从一个连接 URI 的终结点。 然后，创建**消息**为目标操作的消息架构表示符合的 SOAP 消息的实例。 然后可以将发送这**消息**到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用从通道工厂创建的通道。 如果使用的**IRequestChannel**，你收到的响应。 如果执行对 SAP 系统的操作问题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将引发**Microsoft.ServiceModel.Channels.Common.TargetSystemException**。  
  
 有关如何发送操作使用的概述**IRequestChannel**在 WCF 中，请参阅[客户端通道级编程](https://msdn.microsoft.com/library/ms788970.aspx)。  
  
 本主题中的部分提供信息以帮助您在调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 WCF 通道模型。  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a>在 WCF 通道模型中支持 BAPI 事务  
 使用相同的 SAP 连接调用的所有 Bapi 都属于同一个逻辑单元的工作 (LUW)-或事务-SAP 系统上。 每个 WCF 通道表示的唯一连接到 SAP 系统。 若要支持 BAPI 事务使用 WCF 通道模型：  
  
- 确保将通过同一通道发送 LUW （事务） 中的每个 BAPI。 这包括 BAPI_TRANSACTION 提交或 BAPI_TRANSACTION_ROLLBACK 操作。  
  
- 请确保关闭之前调用的通道上的下一步 BAPI bapi 收到任何响应消息。 （你应执行此操作对于每个操作; 但对于 Bapi 尤为重要。）  
  
  有关 BAPI 事务的详细信息，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a>为 SAP 适配器的流式处理平面文件 Idoc  
 SendIdoc 操作用于发送平面文件 （字符串） IDOC 到适配器。 IDOC 数据表示为此操作中的单个节点下的字符串。 出于此原因，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持节点值流处理的请求消息。 若要执行节点值传送视频流，必须创建 SendIdoc 操作的请求消息使用**System.ServiceModel.Channels.BodyWriter** ，它能够流式传输 IDOC 的数据。 有关如何执行此操作的信息，请参阅[流式处理中使用 WCF 通道模型的 SAP 的平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>如何通过使用对通道调用的操作？  
 若要通过使用调用的操作**IRequestChannel**，执行以下步骤。  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>如何通过使用 IRequestChannel 的实例调用的操作  
  
1. 生成通道工厂 (**ChannelFactory\<IRequestChannel\>**)。 若要执行此操作，必须指定一个绑定 (**SAPBinding**) 和终结点地址。 您可以在代码中以强制方式或在配置中以声明方式指定绑定和终结点地址。 应设置任何属性的操作所需，您将会发送之前打开工厂的绑定。 有关如何在配置中指定的绑定和终结点地址的详细信息，请参阅[创建一个通道，使用 SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)。  
  
   ```  
   // Create a binding  
   SAPBinding binding = new SAPBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. 通过设置用户名称密码凭据的通道工厂**ClientCredentials**属性。  
  
   ```  
   factory.Credentials.UserName.UserName = "YourUserName";  
   factory.Credentials.UserName.Password = "YourPassword";  
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
  
5. 创建**消息**目标操作的实例。 请确保指定目标操作的消息操作。 在此示例中，消息正文传递通过创建**XmlReader**通过一个字符串。 目标操作调用 SD_RFC_CUSTOMER_GET RFC，SAP 系统上。  
  
   ```  
   string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
   //create an XML reader from the input XML  
   XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
   //create a WCF message from our XML reader  
   Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
   ```  
  
6. 调用**请求**方法将消息发送到在通道上的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并接收回复。 如果 SAP 系统遇到的异常，则适配器将引发**TargetSystemException**。 （其他异常是可能的非 SAP 异常。）可以获取从 SAP 错误的说明**InnerException.Message**的属性**TargetSystemException**。  
  
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
  
10. 
  
    请按照相同的步骤来发送邮件时使用**IOutputChannel**形状除外：  
  
-   您创建**ChannelFactory\<IOutputChannel\>** 步骤 1 中。  
  
-   在调用**发送**步骤 6 中的通道上的方法。 `channel.Send(messageIn);` 的用户。  
  
-   不没有返回任何响应消息**IOutputChannel**。  
  
### <a name="example"></a>示例  
 下面的示例演示如何使用调用 RFC **IRequestChannel**通道。 此示例调用 SD_RFC_CUSTOMER_GET RFC，若要获取其名称以"AB"开头的客户列表。 响应消息将通过使用消费**XmlReader**和的客户数和返回每个客户的名称写入控制台。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Xml;  
using System.IO;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel.Channels;  
  
namespace SapRfcClientCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //set up an endpoint address.  
            EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
            //create a channel factory, capable of sending a request to SAP and receiving a reply (IRequestChannel)  
            ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress);  
  
            // add credentials  
            factory.Credentials.UserName.UserName = "YourUserName";  
            factory.Credentials.UserName.Password = "YourPassword";  
  
            //open the factory  
            factory.Open();  
  
            //obtain a channel from the factory by specifying the address you want to connect to  
            IRequestChannel channel = factory.CreateChannel();  
  
            //open the channel  
            channel.Open();  
  
            //create an XML message to send to the SAP system  
            //We are invoking the SD_RFC_CUSTOMER_GET RFC.  
            //The XML below specifies that we want to search for customers with names starting with "AB"  
            string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
            //create an XML reader from the input XML  
            XmlReader readerOut = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
            //create a WCF message from the XML reader  
            Message messageOut = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", readerOut);  
  
            //send the message to SAP and obtain a reply  
            Message messageIn = channel.Request(messageOut);  
  
            // Write the KUNNR and NAME1 fields for each returned record to the Console  
            Console.WriteLine("Results of SD_RFC_CUSTOMER_GET");  
            Console.WriteLine("KUNNR\t\tNAME1");  
  
            XmlReader readerIn = messageIn.GetReaderAtBodyContents();  
  
            while (readerIn.Read())  
            {  
                if (readerIn.IsStartElement())  
                {  
                    switch (readerIn.Name)  
                    {  
                        case "RFCCUST":  
                            Console.Write("\n");  
                            break;  
  
                        case "KUNNR":  
                            readerIn.Read();  
                            Console.Write(readerIn.ReadString() + "\t");  
                            break;  
  
                        case "NAME1":  
                            readerIn.Read();  
                            Console.Write(readerIn.ReadString() + "\t");  
                            break;  
  
                        default:  
                            break;  
                    }  
                }  
            }  
  
            // return the cursor  
            Console.WriteLine();  
  
            // Close the input reader  
            readerIn.Close();  
  
            // Close the input message. You should do this for every message you   
            // send on the channel  
            messageIn.Close();  
  
            // close the channel when you are done using it.  
            channel.Close();  
  
            //close the factory  
            //note: closing the factory will close all of its channels.  
            factory.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)