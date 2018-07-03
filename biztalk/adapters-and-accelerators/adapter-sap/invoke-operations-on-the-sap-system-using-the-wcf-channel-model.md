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
ms.openlocfilehash: 408d2ce053a30a4692b6e17a73087b13c648ab2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997334"
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a><span data-ttu-id="ecf29-102">调用上使用 WCF 通道模型的 SAP 系统的操作</span><span class="sxs-lookup"><span data-stu-id="ecf29-102">Invoke Operations on the SAP System Using the WCF Channel Model</span></span>
<span data-ttu-id="ecf29-103">在调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过使用**IRequestChannel**或**IOutputChannel**通道形状将消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="ecf29-103">You invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** channel shape to send messages to the adapter.</span></span> <span data-ttu-id="ecf29-104">基本模式是通过使用绑定创建通道工厂为所需的通道形状 (**SAPBinding**) 并创建从一个连接 URI 的终结点。</span><span class="sxs-lookup"><span data-stu-id="ecf29-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**SAPBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="ecf29-105">然后，创建**消息**为目标操作的消息架构表示符合的 SOAP 消息的实例。</span><span class="sxs-lookup"><span data-stu-id="ecf29-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="ecf29-106">然后可以将发送这**消息**到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用从通道工厂创建的通道。</span><span class="sxs-lookup"><span data-stu-id="ecf29-106">You can then send this **Message** to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="ecf29-107">如果使用的**IRequestChannel**，你收到的响应。</span><span class="sxs-lookup"><span data-stu-id="ecf29-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="ecf29-108">如果执行对 SAP 系统的操作问题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将引发**Microsoft.ServiceModel.Channels.Common.TargetSystemException**。</span><span class="sxs-lookup"><span data-stu-id="ecf29-108">If there is a problem executing the operation on the SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="ecf29-109">有关如何发送操作使用的概述**IRequestChannel**在 WCF 中，请参阅[客户端通道级编程](https://msdn.microsoft.com/library/ms788970.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ecf29-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see [Client Channel-Level Programming](https://msdn.microsoft.com/library/ms788970.aspx).</span></span>  
  
 <span data-ttu-id="ecf29-110">本主题中的部分提供信息以帮助您在调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="ecf29-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a><span data-ttu-id="ecf29-111">在 WCF 通道模型中支持 BAPI 事务</span><span class="sxs-lookup"><span data-stu-id="ecf29-111">Supporting BAPI Transactions in the WCF Channel Model</span></span>  
 <span data-ttu-id="ecf29-112">使用相同的 SAP 连接调用的所有 Bapi 都属于同一个逻辑单元的工作 (LUW)-或事务-SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="ecf29-112">All BAPIs that are invoked using the same SAP connection are part of the same Logical Unit of Work (LUW) -- or transaction -- on the SAP system.</span></span> <span data-ttu-id="ecf29-113">每个 WCF 通道表示的唯一连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="ecf29-113">Each WCF channel represents a unique connection to the SAP system.</span></span> <span data-ttu-id="ecf29-114">若要支持 BAPI 事务使用 WCF 通道模型：</span><span class="sxs-lookup"><span data-stu-id="ecf29-114">To support BAPI transactions using the WCF channel model:</span></span>  
  
- <span data-ttu-id="ecf29-115">确保将通过同一通道发送 LUW （事务） 中的每个 BAPI。</span><span class="sxs-lookup"><span data-stu-id="ecf29-115">Ensure that every BAPI in an LUW (transaction) is sent over the same channel.</span></span> <span data-ttu-id="ecf29-116">这包括 BAPI_TRANSACTION 提交或 BAPI_TRANSACTION_ROLLBACK 操作。</span><span class="sxs-lookup"><span data-stu-id="ecf29-116">This includes the BAPI_TRANSACTION COMMIT or the BAPI_TRANSACTION_ROLLBACK operations.</span></span>  
  
- <span data-ttu-id="ecf29-117">请确保关闭之前调用的通道上的下一步 BAPI bapi 收到任何响应消息。</span><span class="sxs-lookup"><span data-stu-id="ecf29-117">Ensure that you close any response message received for a BAPI before you invoke the next BAPI on the channel.</span></span> <span data-ttu-id="ecf29-118">（你应执行此操作对于每个操作; 但对于 Bapi 尤为重要。）</span><span class="sxs-lookup"><span data-stu-id="ecf29-118">(You should do this for every operation; but it is especially important for BAPIs.)</span></span>  
  
  <span data-ttu-id="ecf29-119">有关 BAPI 事务的详细信息，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf29-119">For more information about BAPI transactions, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a><span data-ttu-id="ecf29-120">为 SAP 适配器的流式处理平面文件 Idoc</span><span class="sxs-lookup"><span data-stu-id="ecf29-120">Streaming Flat File IDOCs to the SAP Adapter</span></span>  
 <span data-ttu-id="ecf29-121">SendIdoc 操作用于发送平面文件 （字符串） IDOC 到适配器。</span><span class="sxs-lookup"><span data-stu-id="ecf29-121">You use the SendIdoc operation to send a flat file (string) IDOC to the adapter.</span></span> <span data-ttu-id="ecf29-122">IDOC 数据表示为此操作中的单个节点下的字符串。</span><span class="sxs-lookup"><span data-stu-id="ecf29-122">The IDOC data is represented as a string under a single node in this operation.</span></span> <span data-ttu-id="ecf29-123">出于此原因，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持节点值流处理的请求消息。</span><span class="sxs-lookup"><span data-stu-id="ecf29-123">For this reason, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports node-value streaming on the request message.</span></span> <span data-ttu-id="ecf29-124">若要执行节点值传送视频流，必须创建 SendIdoc 操作的请求消息使用**System.ServiceModel.Channels.BodyWriter** ，它能够流式传输 IDOC 的数据。</span><span class="sxs-lookup"><span data-stu-id="ecf29-124">To perform node-value streaming, you must create the request message for the SendIdoc operation by using a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the IDOC data.</span></span> <span data-ttu-id="ecf29-125">有关如何执行此操作的信息，请参阅[流式处理中使用 WCF 通道模型的 SAP 的平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf29-125">For information about how to do this, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="ecf29-126">如何通过使用对通道调用的操作？</span><span class="sxs-lookup"><span data-stu-id="ecf29-126">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="ecf29-127">若要通过使用调用的操作**IRequestChannel**，执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ecf29-127">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="ecf29-128">如何通过使用 IRequestChannel 的实例调用的操作</span><span class="sxs-lookup"><span data-stu-id="ecf29-128">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1. <span data-ttu-id="ecf29-129">生成通道工厂 (**ChannelFactory\<IRequestChannel\>**)。</span><span class="sxs-lookup"><span data-stu-id="ecf29-129">Build a channel factory (**ChannelFactory\<IRequestChannel\>**).</span></span> <span data-ttu-id="ecf29-130">若要执行此操作，必须指定一个绑定 (**SAPBinding**) 和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="ecf29-130">To do this, you must specify a binding (**SAPBinding**) and an endpoint address.</span></span> <span data-ttu-id="ecf29-131">您可以在代码中以强制方式或在配置中以声明方式指定绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="ecf29-131">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="ecf29-132">应设置任何属性的操作所需，您将会发送之前打开工厂的绑定。</span><span class="sxs-lookup"><span data-stu-id="ecf29-132">You should set any binding properties required for the operations that you will send before you open the factory.</span></span> <span data-ttu-id="ecf29-133">有关如何在配置中指定的绑定和终结点地址的详细信息，请参阅[创建一个通道，使用 SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf29-133">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md).</span></span>  
  
   ```  
   // Create a binding  
   SAPBinding binding = new SAPBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. <span data-ttu-id="ecf29-134">通过设置用户名称密码凭据的通道工厂**ClientCredentials**属性。</span><span class="sxs-lookup"><span data-stu-id="ecf29-134">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
   ```  
   factory.Credentials.UserName.UserName = "YourUserName";  
   factory.Credentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="ecf29-135">打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="ecf29-135">Open the channel factory.</span></span>  
  
   ```  
   factory.Open();  
   ```  
  
4. <span data-ttu-id="ecf29-136">从工厂获取通道并将其打开。</span><span class="sxs-lookup"><span data-stu-id="ecf29-136">Get a channel from the factory and open it.</span></span>  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. <span data-ttu-id="ecf29-137">创建**消息**目标操作的实例。</span><span class="sxs-lookup"><span data-stu-id="ecf29-137">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="ecf29-138">请确保指定目标操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="ecf29-138">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="ecf29-139">在此示例中，消息正文传递通过创建**XmlReader**通过一个字符串。</span><span class="sxs-lookup"><span data-stu-id="ecf29-139">In this example, the message body is passed by creating an **XmlReader** over a string.</span></span> <span data-ttu-id="ecf29-140">目标操作调用 SD_RFC_CUSTOMER_GET RFC，SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="ecf29-140">The target operation invokes the SD_RFC_CUSTOMER_GET RFC on an SAP system.</span></span>  
  
   ```  
   string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
   //create an XML reader from the input XML  
   XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
   //create a WCF message from our XML reader  
   Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
   ```  
  
6. <span data-ttu-id="ecf29-141">调用**请求**方法将消息发送到在通道上的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并接收回复。</span><span class="sxs-lookup"><span data-stu-id="ecf29-141">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="ecf29-142">如果 SAP 系统遇到的异常，则适配器将引发**TargetSystemException**。</span><span class="sxs-lookup"><span data-stu-id="ecf29-142">If the SAP system encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="ecf29-143">（其他异常是可能的非 SAP 异常。）可以获取从 SAP 错误的说明**InnerException.Message**的属性**TargetSystemException**。</span><span class="sxs-lookup"><span data-stu-id="ecf29-143">(Other exceptions are possible for non SAP exceptions.) You can get a description of the SAP error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
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
  
7. <span data-ttu-id="ecf29-144">处理响应。</span><span class="sxs-lookup"><span data-stu-id="ecf29-144">Process the response.</span></span> <span data-ttu-id="ecf29-145">在此示例中， **GetReaderAtBodyContents**调用以获取消息正文的响应消息。</span><span class="sxs-lookup"><span data-stu-id="ecf29-145">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. <span data-ttu-id="ecf29-146">完成处理响应消息时，关闭读取器和消息。</span><span class="sxs-lookup"><span data-stu-id="ecf29-146">When you are done processing the response message, close the reader and the message.</span></span>  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. <span data-ttu-id="ecf29-147">完成后使用通道和通道工厂，将其关闭。</span><span class="sxs-lookup"><span data-stu-id="ecf29-147">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="ecf29-148">关闭工厂将关闭所有使用它创建的通道。</span><span class="sxs-lookup"><span data-stu-id="ecf29-148">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
    ```  
  
10. 
  
    <span data-ttu-id="ecf29-149">请按照相同的步骤来发送邮件时使用**IOutputChannel**形状除外：</span><span class="sxs-lookup"><span data-stu-id="ecf29-149">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="ecf29-150">您创建**ChannelFactory\<IOutputChannel\>** 步骤 1 中。</span><span class="sxs-lookup"><span data-stu-id="ecf29-150">You create a **ChannelFactory\<IOutputChannel\>** in step 1.</span></span>  
  
-   <span data-ttu-id="ecf29-151">在调用**发送**步骤 6 中的通道上的方法。</span><span class="sxs-lookup"><span data-stu-id="ecf29-151">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="ecf29-152">`channel.Send(messageIn);`的用户。</span><span class="sxs-lookup"><span data-stu-id="ecf29-152">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="ecf29-153">不没有返回任何响应消息**IOutputChannel**。</span><span class="sxs-lookup"><span data-stu-id="ecf29-153">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ecf29-154">示例</span><span class="sxs-lookup"><span data-stu-id="ecf29-154">Example</span></span>  
 <span data-ttu-id="ecf29-155">下面的示例演示如何使用调用 RFC **IRequestChannel**通道。</span><span class="sxs-lookup"><span data-stu-id="ecf29-155">The following example shows how to invoke an RFC by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="ecf29-156">此示例调用 SD_RFC_CUSTOMER_GET RFC，若要获取其名称以"AB"开头的客户列表。</span><span class="sxs-lookup"><span data-stu-id="ecf29-156">This example invokes the SD_RFC_CUSTOMER_GET RFC to get a list of customers whose names start with "AB".</span></span> <span data-ttu-id="ecf29-157">响应消息将通过使用消费**XmlReader**和的客户数和返回每个客户的名称写入控制台。</span><span class="sxs-lookup"><span data-stu-id="ecf29-157">The response message is consumed by using an **XmlReader** and the customer number and name of each customer returned is written to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ecf29-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecf29-158">See Also</span></span>  
[<span data-ttu-id="ecf29-159">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="ecf29-159">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)