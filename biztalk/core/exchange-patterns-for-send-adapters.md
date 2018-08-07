---
title: 发送适配器的交换模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4cef519e4648814e1636daac7b60a42addf5111
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978366"
---
# <a name="exchange-patterns-for-send-adapters"></a>发送适配器的交换模式
发送适配器传送消息从 BizTalk 消息引擎，以通过网络传输。 所使用的单向或双向消息交换模式，可能会发送这些消息。 处理此双向消息交换模式的适配器称为要求-响应适配器。  

## <a name="blocking-vs-non-blocking-transmissions"></a>阻止 vs。非阻塞传输  
 消息引擎将消息传送到发送适配器，通过使用**IBTTransmitter.TransmitMessage**方法或**IBTTransmitterBatch.TransmitMessage**方法，具体取决于可识别批的适配器。 这两个版本的方法有一个布尔返回值，该值指示适配器如何传输该消息。 如果适配器返回 `true`，则在返回前它已发送完消息。 在这种情况下，消息引擎从 MessageBox 数据库代表适配器删除消息。 如果适配器返回 `false`，则适配器已开始传送消息，但是在传送未完成之前就返回了。 在这种情况下，适配器负责不仅用于删除从其应用程序队列发送消息，但还用于处理需要要传输的重试或挂起的消息传输失败。  

 适配器返回`false`是非阻塞调用，这表示**TransmitMessage**实现代码不会阻止消息引擎调用线程。 适配器只需将消息添加到准备要传输的内存中队列，然后返回。 适配器应具有自己的线程池的服务的内存中队列、 传输消息，并随后通知传输结果的引擎。  

 消息引擎线程是通常更多的 CPU 绑定用于通过网络发送数据的线程。 混合使用这两种类型的线程对性能有负面影响。 非阻塞发送启用分离这两种类型的线程，并阻止调用产生显著的性能改善。  

 下图显示了适配器的线程池，其中可以往往会受 I/O 操作。 BizTalk Server 消息引擎的线程池是多个由 CPU 处理绑定。 通过使两个不同的线程池并不混合使用相同类型的线程系统可以更有效地运行。  

 ![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")  

 **性能提示：** 为了获得最佳性能，发送适配器应该非阻止性并且能够识别批。 BizTalk 文件适配器从阻塞和非批处理识别已更改时为非阻止性和批处理注意，已实现了三倍的性能提升。  

 **故障排除提示：** 阻塞传输可能会导致整个主机实例的性能下降。 如果适配器造成过多阻塞**TransmitMessage**将阻止引擎线程将消息传递到其他适配器。  

## <a name="non-batched-sends"></a>非批处理发送  
 不能识别批的适配器应该实现**IBTTransmitter**中所述[异步发送适配器的接口](../core/interfaces-for-an-asynchronous-send-adapter.md)。 为每条消息，适配器需要传送消息引擎调用**IBTTransmitter.TransmitMessage**。 下面的对象交互图详细说明了典型的方法以传输消息，其中包括以下步骤：  

1. 该引擎的消息传递到适配器。  

2. 适配器将准备要传输的内存中队列消息中。  

3. 从适配器的线程池线程取消排队的消息从队列中读取消息，配置，并通过网络传输消息。  

4. 适配器从引擎中获取新批。  

5. 适配器调用**DeleteMessage** batch，传入刚刚传输的消息上。  

6. 适配器调用**完成**对批。  

7. 引擎处理该批，并从应用程序队列中删除消息。  

8. 引擎回调适配器，以通知它的结果**DeleteMessage**操作。  

   ![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")  

   前面的对象交互图显示了从应用程序队列中删除一条消息的适配器。 理想情况下提高而不是上一条消息一次操作消息操作适配器批。  

## <a name="batched-sends"></a>成批的发送  
 可识别批的适配器应该实现**IBTBatchTransmitter**并**IBTTransmitterBatch**中所述[发送适配器的接口](../core/interfaces-for-send-adapters.md)。 当引擎具有适配器传输的消息时，引擎通过调用从适配器获取新批**IBTBatchTransmitter.GetBatch**。 适配器返回一个新的 batch 对象实现**IBTTransmitterBatch**。 然后，引擎通过调用启动批处理**IBTTransmitterBatch.BeginBatch**。 此 API 具有输出参数，使适配器对批中指定它将接收的消息最大数目。 该适配器可能会选择性地返回 DTC 事务。 引擎随后会调用**IBTTransmitterBatch.TransmitMessage**每条传出消息添加到批的一次。 这称为次数大于零，但小于或等于由适配器批的最大大小。 当所有消息都已都添加到批时，适配器调用**IBTTransmitterBatch.Done**。 现在适配器通常排入队列中批处理层到其内存中队列的所有消息。 适配器传输来自非可识别批的适配器一样其自身线程池中的线程或线程的消息。 适配器然后通知传输结果的引擎。  

 以下对象交互图说明了两个消息的成批的发送适配器的传输。  

 ![](../core/media/batchedsends.gif "BatchedSends")  

## <a name="handling-transmission-failures"></a>处理传输失败  
 在下图说明了传输失败所建议的语义。 这些仅仅是建议，不会强制执行由消息引擎。 你可以开发偏离这些准则，如果有理由需要执行此操作，但你应小心这种情况下的适配器。 例如，一般情况下适配器应始终将消息移到备份传输后已用完所有重试。  

 更常见的传输可能需要使用比配置的多个重试。 虽然这是略有不同帐户被视为可接受，因为要增加传输层的恢复能力。 一般情况下，消息引擎通过公开的 Api 旨在使适配器最大控制，在可能的情况。 此控件，提供了更高级别的责任。  

 ![](../core/media/handlingerrors.gif "HandlingErrors")  

 适配器可以通过检查系统上下文属性来确定可用于消息的重试次数**RetryCount**。 适配器调用**重新提交**API 一次为每个重试尝试，并传入要重新提交的消息。 与消息一起传递，该值指示当引擎应将消息传递回适配器时的时间戳。 此值通常应为当前时间加上的值**RetryInterval**。 **RetryInterval**是系统上下文属性，单位是分钟。 这两个**RetryCount**并**RetryInterval**在消息上下文是在发送端口配置的值。 请考虑在向外扩展部署中使用的相同的多台计算机上部署的 BizTalk 主机实例。 如果重试时间间隔到期后，传递消息，消息可能会被传送到任何它们已配置为运行的计算机上的主机实例的任何一个。 为此适配器不应阻止与要使用重试上一条消息关联的任何状态尝试由于并不保证同一适配器的实例将负责在更高版本时传输。  

 适配器应仅尝试将消息移到备份传输后重试计数小于或等于零。 如果没有为端口配置备份传输，尝试将消息移到备份传输将失败。 在这种情况下应挂起该消息。  

 下面的代码段演示了如何确定重试计数和从消息上下文和后续重新提交间隔或移动到备份传输。  

```  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
 …  
// RetryCount and RetyInterval are system context properties...  
private static readonly PropertyBase RetryCountProperty =   
 new BTS.RetryCount();  
private static readonly PropertyBase RetryIntervalProperty =   
 new BTS.RetryInterval();  

public void HandleRetry(IBaseMessage msg, IBTTransportBatch batch)  
{  
int retryCount = 0;  
int retryInterval = 0;  

// Get the RetryCount and RetryInterval off the msg ctx...  
 GetMessageRetryState(msg, out retryCount, out retryInterval);  

// If we have retries available resubmit, else move to   
 // backup transport...  
 if ( retryCount > 0 )  
batch.Resubmit(  
 msg, DateTime.Now.AddMinutes(retryInterval));  
else  
batch.MoveToNextTransport(msg);  
}  

public void GetMessageRetryState(  
 IBaseMessage msg,   
 out int retryCount,   
 out int retryInterval )  
{  
retryCount = 0;  
retryInterval = 0;  

object obj =  msg.Context.Read(  
RetryCountProperty.Name.Name,    
RetryCountProperty.Name.Namespace);   

if ( null != obj )  
retryCount = (int)obj;  

obj =  msg.Context.Read(  
RetryIntervalProperty.Name.Name,    
RetryIntervalProperty.Name.Namespace);   

if ( null != obj )  
retryInterval = (int)obj;  
}  
```  

## <a name="throwing-an-exception-from-transmitmessage"></a>从 TransmitMessage 引发异常  
 如果适配器在任何 Api 时引发异常**IBTTransmitter.TransmitMessage**， **IBTTransmitterBatch.TransmitMessage**， **IBTTransmitterBatch.Done**、引擎处理所涉及的消息传输看作失败传输，并采取相应的措施的消息，如中所述[如何处理适配器故障](../core/how-to-handle-adapter-failures.md)。  

 可识别批的发送适配器引发异常的 TransmitMessage API 会导致整个要清除的批处理和默认传输失败操作正在执行该批处理中的所有消息。  

## <a name="solicit-response"></a>要求-响应  
 双向发送适配器通常支持单向和双向传输。 发送适配器可以确定是否应将消息作为单向或双向发送传输通过检查**IsSolicitResponse**系统上下文属性在消息上下文。  

 以下代码段演示了这一操作：  

```  
private bool portIsTwoWay = false;  
private static readonly PropertyBase IsSolicitResponseProperty= new BTS.IsSolicitResponse();  

...  

 // Port is one way or two way...  
 object obj =  this.message.Context.Read(  
 IsSolicitResponseProperty.Name.Name,    
 IsSolicitResponseProperty.Name.Namespace);   

if ( null != obj )  
 this.portIsTwoWay = (bool)obj;  
```  

 在要求-响应传输过程适配器传输要求消息。 之后此工作完成后它将提交相关联的响应和通知消息引擎从 MessageBox 数据库中删除原始的要求消息。 在应用程序队列删除消息的操作应执行与响应消息提交相同的传输代理批。 这可确保删除操作的原子性和提交的响应。 对于完整原子性适配器应使用 DTC 事务，由此识别事务的资源，提交响应消息，要求消息的传输和删除要求消息都在同一 DTC 的上下文事务。 与往常一样，我们建议使用非阻塞发送传输请求消息。  

 下面的代码段演示了双向发送的主要方面。 当引擎调用**IBTTransmitter.TransmitMessage**适配器排入队列传输到内存中队列的消息。 适配器返回 `false`，指示它在执行非阻塞发送。 适配器的线程池 (**WorkerThreadThunk**) 为内存中队列提供服务并将消息以将其提交给帮助器方法。 此方法负责发送要求消息和接收响应消息。 （此帮助器方法的实现。 本主题的讨论范围内）响应消息提交到引擎，并从应用程序队列中删除要求消息。  

```  
using System.Collections;  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  

     static private Queue _transmitQueue = new Queue();  
  static private IBTTransportProxy _transportProxy = null;   
// IBTTransmitter...  
 public bool TransmitMessage(IBaseMessage msg)  
{  
// Add message to the transmit queue...  
lock(_transmitQueue.SyncRoot)  
 {  
_transmitQueue.Enqueue(msg);  
 }  

 return false;  
}  

 // Threadpool worker thread...   
private void WorkerThreadThunk()  
{  
try  
{  
 IBaseMessage solicitMsg = null;  

 lock(_transmitQueue.SyncRoot)  
 {  
 solicitMsg =   
 (IBaseMessage)_transmitQueue.Dequeue();  
}  

 IBaseMessage responseMsg = SendSolicitResponse(   
 solicitMsg );  
Callback cb = new Callback();  

IBTTransportBatch batch = _transportProxy.GetBatch(  
 cb, null);  
batch.SubmitResponseMessage( solicitMsg, responseMsg );  
batch.DeleteMessage( solicitMsg );  
batch.Done(null);  
}  
catch(Exception)  
{  
// Handle failure....  
}  
}  

static private IBaseMessage SendSolicitResponse(  
 IBaseMessage solicitMsg )  
{  
// Helper method to send solicit message and receive   
 // response message...  
IBaseMessage responseMsg = null;  
return responseMsg;  
}  
```  

## <a name="dynamic-sends"></a>动态发送  
 动态发送端口不具有与其关联的适配器配置。 而是他们使用处理程序配置的任何默认属性，适配器需要传送动态端口上的消息。 例如，HTTP 适配器可能需要使用代理服务器并需要提供凭据。 用户名、 密码和端口无法指定处理程序配置中适配器缓存在运行时。  

 要确定动态消息是，通过发送传输的引擎**OutboundTransportLocation**与适配器的别名作为前缀。 在安装时，适配器可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中注册一个或多个别名。 该引擎将分析**OutboundTransportLocation**在运行时查找匹配项。 适配器负责处理**OutboundTransportLocation**无论其前面的别名。 下表显示了已注册的开箱 BizTalk 适配器的别名的一些示例。  


| 适配器别名 | 适配器 |   OutboundTransportLocation 示例    |
|---------------|---------|----------------------------------------|
|    HTTP://    |  HTTP   |     http://www 的用户。 MyCompany.com/bar      |
|   HTTPS://    |  HTTP   |     https://www 的用户。 MyCompany.com/bar     |
|    mailto:    |  SMTP   |      mailto:A.User@MyCompany.com       |
|    FILE://    |  FILE   | FILE://C:\MyCompany \\%MessageID%.xml |

