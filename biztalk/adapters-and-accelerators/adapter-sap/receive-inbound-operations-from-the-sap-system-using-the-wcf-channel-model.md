---
title: 使用 WCF 通道模型的 SAP 系统从接收入站的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming inbound flat-file IDOCs
- WCF channel model, receiving inbound operations from the SAP system
- WCF channel model, raising an exception
ms.assetid: d71d0537-fda4-44ab-85dc-6e27aad23caf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b76ae42cf0ffc26b818e35d83f59e64158b923a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966195"
---
# <a name="receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model"></a>使用 WCF 通道模型的 SAP 系统从接收入站的操作
若要用作 RFC 服务器和接收操作 （如发送 IDOC 或调用 RFC） SAP 系统调用，必须创建可以通过侦听来自 SAP 程序 ID 的消息的通道侦听器**System.ServiceModel.Channels.IReplyChannel**通道形状。  
  
 通道侦听器 (**System.ServiceModel.Channels.IChannelListener**) 是可以用于从特定的 WCF 终结点接收消息的 WCF 通信对象。 通道侦听器都充当通过它可以创建对其可以通过你的服务接收调用客户端 （SAP 系统） 的消息的通道的工厂。 创建通道侦听器，通过从**Microsoft.Adapters.SAP.SAPBinding**对象通过调用**BuildChannelListener**方法。 提供的 SAP 连接指定从中入站的操作将接收到此方法的 SAP 程序 ID URI。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持**IReplyChannel**通道形状。 **IReplyChannel**通道支持入站的请求-响应消息交换模式。 也就是说，在其中一个外部程序发送的请求消息通过通道并且你的程序的模式返回的响应。  
  
 有关如何接收操作使用的概述**IReplyChannel**在 WCF 中，请参阅[服务通道级编程](https://msdn.microsoft.com/library/ms789029.aspx)。
  
 本部分介绍的是特定于 SAP 系统从接收操作的以下主题：  
  
-   如何针对特定操作使用的通道侦听器的筛选器。  
  
-   如何在引发异常 SAP 系统。  
  
-   从 SAP 适配器的流式处理入站的平面文件 Idoc。  
  
-   如何从 SAP 系统接收操作。  
  
## <a name="how-do-i-filter-operations-using-the-channel-listener"></a>如何筛选使用通道侦听器操作？  
  
### <a name="using-an-inboundactioncollection-to-filter-operations"></a>使用 InboundActionCollection 来筛选操作  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供**Microsoft.ServiceModel.Channels.InboundActionCollection**类，以使你能够筛选由通道侦听器接收和传递给应用程序代码的操作。 若要筛选特定操作，请通过使用侦听器终结点 URI 创建此类的实例。 然后将每个目标操作 （请求） 消息操作添加到集合。 最后，你将添加到的入站的操作集合**System.ServiceModel.Channels.BindingParameterCollection**对象，然后将此绑定参数集合传递到用于创建通道侦听器的调用。  
  
 如果 SAP 系统调用不是入站的操作集合中的操作：  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]返回给调用方具有以下消息的 SAP 系统上的异常异常:"未处理 Rfc 服务器上的传入 RFC 调用 [RFC_NAME]"。 此消息中，[RFC_NAME] 是 RFC (例如，IDOC_INBOUND_ASYNCHRONOUS) 的名称。  
  
-   适配器引发**Microsoft.ServiceModel.Channels.Common.AdapterException**与一条消息，指示已接收到的操作。 有关如何使用此异常的示例，请参阅本主题末尾的示例。  
  
 下面的代码示例演示如何使用**InboundActionCollection**创建为单个 RFC，Z_RFC_MKD_DIV 筛选器的通道侦听器。  
  
```  
// The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
// and credentials.  
Uri listeneraddress =  
    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
// Create a binding and set AcceptCredentialsInUri to true  
SAPBinding binding = new SAPBinding();  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying the binding parameter collection (to filter for the Z_RFC_MKD_DIV action)  
listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
```  
  
### <a name="manually-filtering-operations"></a>手动筛选操作  
 如果你未指定的入站的操作集合的通道侦听器，则将向你的代码传递 SAP 系统调用的所有操作。 通过检查入站请求的消息操作，可以手动筛选此类操作。  
  
 也可能是你要在其中筛选基于其内容的操作的方案。 例如，如果你收到的 Idoc 中：  
  
-   字符串格式 ( **ReceiveIDocFormat**绑定属性是**字符串**); 所有使用 ReceiveIdoc 操作接收到的 Idoc。  
  
-   Rfc 格式 ( **ReceiveIDocFormat**绑定属性是**Rfc**); 所有使用 IDOC_INBOUND_ASYNCHRONOUS RFC 或 INBOUND_IDOC_PROCESS RFC 接收到的 Idoc。  
  
 在这种情况下，你可能想要实现筛选基于在代码中特定 IDOC 参数 （如 IDOC 类型中）。  
  
 手动筛选操作时，你可以返回到错误[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不处理的操作。 这将引发的异常异常向调用方 SAP 系统上。 如果您不想要提升 SAP 出现异常，你还可以返回了空响应。  
  
 下面的代码演示如何手动筛选 Z_RFC_MKD_DIV 操作。  
  
```  
// Get the message from the channel  
RequestContext rc = channel.ReceiveRequest();  
Message reqMessage = rc.RequestMessage;  
  
// Filter based on the message action.  
if (reqMessage.Headers.Action == "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV")  
{  
  
    // Process message and return response.  
    ...  
  
}  
else  
{  
    // If this isn't the correct message return an empty response or a fault message.  
    // This example returns an empty response.  
    rc.Reply(Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response"));  
}  
```  
  
## <a name="how-do-i-raise-an-exception-on-the-sap-system"></a>如何引发异常，SAP 系统？  
 以指示到 SAP 系统上调用方错误来答复请求消息并出现 SOAP 错误。 当您返回到 SOAP 错误[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器返回给调用方 SAP 系统上的异常异常。 异常消息创建从 SOAP 错误的元素。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]创建根据以下优先顺序 SAP 异常消息：  
  
1.  如果 SOAP 错误包含详细信息对象，该适配器序列化到字符串的详细信息和异常消息将设置为此字符串。  
  
2.  如果 SOAP 错误中包含的原因，异常消息为其值设置。  
  
3.  否则，该适配器的序列化**MessageFault**为字符串，并异常消息对象本身设置为此字符串。  
  
> [!NOTE]
>  适配器仅使用错误消息来创建针对 SAP 系统，则为引发的异常中返回的异常消息因此，为这些实体设置的值可完全是由您决定。  
  
 WCF 提供了**System.ServiceModel.Channels.MessageFault**类来封装内存中表示 SOAP 错误。 你可以使用任何静态、 重载**MessageFault.CreateFault**方法来创建新的 SOAP 错误，从中你可以然后创建错误消息通过调用适当**Message.CreateMessage**重载。 WCF 还提供了重载**CreateMessage** ，而无需使用创建的错误消息**MessageFault**对象。  
  
 你使用**System.ServiceModel.Channels.RequestContext.Reply**方法以返回到适配器的错误消息。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]忽略错误消息的消息操作，因此你可以为任何值设置的消息操作。  
  
 下面的示例演示如何返回到的错误消息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 此示例中省略创建的通道侦听器和通道的步骤。  
  
```  
RequestContext rc = channel.ReceiveRequest();  
…  
// Start processing the inbound message  
…  
// If an error is encountered return a fault to the SAP system  
// This example uses CreateMessage overload to create a fault message.  
// The overload takes a SOAP version, fault code, reason, and message action  
// The SAP adapter ignores the message action for a fault so you can set it to any value you want.   
Message faultMessage = Message.CreateMessage(MessageVersion.Default, new FaultCode("SAP Example Fault"), "Testing SAP Faults", rc.RequestMessage.Headers.Action + "/fault");  
  
rc.Reply(faultMessage);  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-sap-adapter"></a>从 SAP 适配器的流式处理入站的平面文件 Idoc  
 接收平面文件 （字符串） Idoc 从入站 ReceiveIdoc 操作中的适配器。 IDOC 数据表示为此操作中的单个节点下的字符串。 为此，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持流式处理请求消息的节点的值。 若要执行节点值流式处理，必须使用 ReceiveIdoc 操作的请求消息通过调用**Message.WriteBodyContents**方法替换**System.Xml.XmlDictionaryWriter** ，就能够流式处理 IDOC 数据。 有关如何执行此操作的信息，请参阅[SAP 使用 WCF 通道模型中流式处理平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。  
  
## <a name="how-do-i-receive-operations-from-a-sap-system-using-an-ireplychannel"></a>如何从使用 IReplyChannel SAP 系统接收操作？  
 若要通过使用 WCF 通道模型从 SAP 系统接收操作，执行以下步骤。  
  
#### <a name="to-receive-operations-from-the-sap-system-using-an-ireplychannel"></a>若要从使用 IReplyChannel 的 SAP 系统接收操作  
  
1.  创建的实例**SAPBinding**并设置你想要接收的操作所需的绑定属性。 至少必须设置**AcceptCredentialsInUri**绑定属性为 true。 若要配置为 tRFC 服务器，必须设置**TidDatabaseConnectionString**绑定属性。 有关绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    ```  
    SAPBinding binding = new SAPBinding();  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
2.  创建**BindingParameterCollection**并添加**InboundActionCollection** ，其中包含你想要接收的操作的操作。 到 SAP 系统的所有其他操作，该适配器将返回一个异常。 此步骤为可选步骤。 有关详细信息，请参阅[接收从使用 WCF 通道模型的 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。  
  
    ```  
    InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
    actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
    BindingParameterCollection bpcol = new BindingParameterCollection();  
    bpcol.Add(actions);  
    ```  
  
3.  创建通道侦听器，通过调用**BuildChannelListener < IReplyChannel\>** 方法**SAPBinding**并将其打开。 作为此方法的参数之一指定 SAP 连接 URI。 连接 URI 必须包含 SAP 系统上 RFC 目标的参数。 有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。 如果你创建**BindingParameterCollection**在步骤 3 中，还这可以指定当创建通道侦听器。  
  
    ```  
    Uri listeneraddress =  
        new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
    IChannelListener<IReplyChannel> listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, bpcol);  
    listener.Open();  
    ```  
  
4.  获取**IReplyChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。  
  
    ```  
    IReplyChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
5.  调用**ReceiveRequest**上从适配器获取下一个操作的请求消息的通道。  
  
    ```  
    RequestContext rc = channel.ReceiveRequest();  
    ```  
  
6.  使用适配器发送的请求消息。 获取从请求消息**RequestMessage**属性**requestcontext 已**。 你可以使用使用消息**XmlReader**或**XmlDictionaryWriter**。  
  
    ```  
    XmlReader reader = (XmlReader)rc.RequestMessage.GetReaderAtBodyContents();  
    ```  
  
7.  通过返回到 SAP 系统的响应或错误来完成该操作：  
  
    1.  处理该消息，通过将响应消息返回到适配器返回对 SAP 系统的响应。 此示例返回一条空消息。  
  
        ```  
        respMessage = Message.CreateMessage(MessageVersion.Default, rc.RequestMessage.Headers.Action + "/response");  
        rc.Reply(respMessage);  
        ```  
  
    2.  通过到适配器中返回的错误消息返回到 SAP 系统的一个异常。 消息操作、 错误代码和原因，可以使用任何值。  
  
        ```  
        MessageFault fault = MessageFault.CreateFault(new FaultCode("ProcFault"), "Processing Error");  
        Message respMessage = Message.CreateMessage(MessageVersion.Default, fault, String.Empty);  
        rc.Reply(respMessage);  
        ```  
  
8.  在发送消息之后，请关闭的请求上下文。  
  
    ```  
    rc.Close();  
    ```  
  
9. 已完成处理请求时，请关闭通道。  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  在处理该操作完成，您必须关闭通道。 未能关闭通道可能会影响你代码的行为。  
  
10. 在完成接收操作从 SAP 系统时，请关闭该侦听器。  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  完成后，必须显式关闭该侦听器使用它;否则，程序可能不能正常工作。 关闭侦听器不会关闭使用侦听器创建的通道。 您还可以显式必须关闭使用侦听器创建每个通道。  
  
### <a name="example"></a>示例  
 下面的示例接收 RFC，Z_RFC_MKD_DIV 从 SAP 系统。 此 RFC 将两个数相除。 在此示例实现使用**InboundActionCollection**来接收消息时筛选 Z_RFC_MKD_DIV 操作和以下措施：  
  
-   如果除数为非零，它将写入控制台的除法的结果，并将其返回给 SAP 系统。  
  
-   如果除数为零，它将生成的异常消息写入控制台，并返回到 SAP 系统的错误。  
  
-   如果任何其他操作发送的 SAP 系统，它会将消息写入控制台。 在这种情况下，适配器本身到 SAP 系统返回一个错误。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Runtime.Serialization;  
using System.Xml;  
using System.IO;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Add this namespace to use Channel Model   
using System.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This sample demonstrates using the adapter as an rfc server over a channel.  
// The sample implements an RFC, Z_RFC_MKD_DIV that divides two numbers and returns the result  
// 1)  A SAPBinding instance is created and configured (AcceptCredentialsInUri is set true)  
// 2)  A binding parameter collection is created with an InboundAction collection that specifies  
//     target RFC (Z_RFC_MKD_DIV) so that only messages with this action will be received by the  
//     listener (and channel).  
// 3)  An <IReplyChannel> listener is created from the binding and binding parameter collection  
// 4)  A channel is created and opened to receive a request  
// 6)  When Z_RFC_MKD_DIV is received the two parameters are divided and the parameters and result  
//     are written to the console, then the result is returned to the adapter by using a template  
//     message.  
// 7)  If a divide by 0 occurs the exception message is written to the console and a  
//     fault is returned to the SAP system  
// 8)  If any other operation is received an error message is written to the console and the adapter  
///    returns a fault to the SAP system  
// 9)  IMPORTANT you must close the channel and listener to deregister them from the SAP Program ID.  
namespace SapRfcServerCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Variables to hold the listener and channel  
            IChannelListener<IReplyChannel> listener = null;  
            IReplyChannel channel = null;  
  
            Console.WriteLine("Sample started");  
            Console.WriteLine("Initializing and creating channel listener -- please wait");  
            try  
            {  
  
                // The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
                // and also credentials.  
                Uri listeneraddress =  
                    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
                // Create a binding -- set AcceptCredentialsInUri true  
                SAPBinding binding = new SAPBinding();  
                binding.AcceptCredentialsInUri = true;  
  
                // Create a binding parameter collection with a list of SOAP actions to listen on  
                // in this case: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
                // This ensures that only these actions are received on the channel.  
                InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
                actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
                BindingParameterCollection bpcol = new BindingParameterCollection();  
                bpcol.Add(actions);  
  
                // Pass the Uri and the binding parameter collection (to specify the Z_RFC_MKD_DIV action)  
                listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
  
                Console.WriteLine("Opening listener");  
                // Open the listener  
                listener.Open();  
  
                // Get an IReplyChannel  
                channel = listener.AcceptChannel();  
  
                Console.WriteLine("Opening channel");  
                // Open the channel  
                channel.Open();  
  
                Console.WriteLine("\nReady to receive Z_RFC_MKD_DIV RFC");  
  
                try  
                {  
                    // Get the message from the channel  
                    RequestContext rc = channel.ReceiveRequest();  
  
                    // Get the request message sent by SAP  
                    Message reqMessage = rc.RequestMessage;  
  
                    // get the message body  
                    XmlReader reader = reqMessage.GetReaderAtBodyContents();  
  
                    reader.ReadStartElement("Z_RFC_MKD_DIV");  
                    reader.ReadElementString("DEST");  
                    int x_in = int.Parse(reader.ReadElementString("X"));  
                    int y_in = int.Parse(reader.ReadElementString("Y"));  
                    reader.ReadEndElement();  
  
                    Console.WriteLine("\nRfc Received");  
                    Console.WriteLine("X =\t\t" + x_in);  
                    Console.WriteLine("Y =\t\t" + y_in);  
  
                    Message messageOut = null;  
  
                    try   
                    {  
                        int result_out = x_in/y_in;  
  
                        Console.WriteLine("RESULT =\t" + result_out.ToString());  
  
                        string out_xml = "<Z_RFC_MKD_DIVResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"><RESULT>" + result_out + "</RESULT></Z_RFC_MKD_DIVResponse>";  
                        StringReader sr = new StringReader(out_xml);  
                        reader = XmlReader.Create(sr);  
  
                        // create a response message  
                        // be sure to specify the response action  
                        messageOut = Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response", reader);  
  
                    }  
                    catch (DivideByZeroException ex)  
                    {  
                        Console.WriteLine();  
                        Console.WriteLine(ex.Message + " Returning fault to SAP");  
  
                        // Create a message that contains a fault  
                        // The fault code and message action can be any value  
  
                        messageOut = Message.CreateMessage(MessageVersion.Default, new FaultCode("Fault"), ex.Message, string.Empty);  
                    }  
  
                    // Send the reply  
                    rc.Reply(messageOut);  
  
                    // Close the request context  
                    rc.Close();  
  
                }  
                catch (AdapterException aex)  
                {  
                    // Will get here if the message received was not in the InboundActionCollection  
                    Console.WriteLine();  
                    Console.WriteLine(aex.Message);  
                }  
  
                // Wait for a key to exit  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
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
                // IMPORTANT: close the channel and listener to stop listening on the Program ID  
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
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)