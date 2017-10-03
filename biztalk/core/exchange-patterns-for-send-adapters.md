---
title: "为发送适配器交换模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 997aaa9a92f90f30bdaaeb59cc9cecb0c454496f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exchange-patterns-for-send-adapters"></a>发送适配器的交换模式
发送适配器从 BizTalk 消息引擎通过网络传输来传送消息。 这些消息可能会发送使用的单向或双向消息交换模式。 处理此双向消息交换模式的适配器调用请求-响应适配器。  
  
## <a name="blocking-vs-non-blocking-transmissions"></a>阻止 vs。非阻塞传输  
 The Messaging Engine 将消息传送到发送适配器，通过使用**IBTTransmitter.TransmitMessage**方法或**IBTTransmitterBatch.TransmitMessage**方法，具体取决于是否适配器是批处理感知。 这两个版本的方法具有返回值，该值指示适配器传输消息的方式一个布尔值。 如果适配器返回 `true`，则在返回前它已发送完消息。 在这种情况下消息引擎从 MessageBox 数据库代表适配器中删除消息。 如果适配器返回 `false`，则适配器已开始传送消息，但是在传送未完成之前就返回了。 在这种情况下，不仅对删除来自其应用程序队列的消息也用于处理需要传输重试或挂起的消息的传输失败，则适配器负责。  
  
 返回的适配器`false`非阻止调用，这意味着， **TransmitMessage**实现代码不会阻止调用线程的消息传送引擎。 适配器只需将消息添加到准备要传输的内存中队列，然后返回。 适配器应具有其自己的线程池，为内存中队列提供服务、 传输消息，然后通知传输的结果的引擎。  
  
 消息传送引擎的线程是通常更多的 CPU 绑定用于通过网络发送数据的线程。 混合使用这两种类型的线程对性能有负面影响。 非阻塞发送启用分离线程这两种类型和通过阻止调用产生显著的性能改善。  
  
 下图显示适配器的线程池，其中往往会受 I/O 操作。 BizTalk Server 消息传送引擎的线程池是多个受 CPU 处理。 通过使两个不同的线程池并不混用相同的线程类型系统可以更有效地运行。  
  
 ![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")  
  
 **性能提示：**以实现最佳性能，将发送适配器都应锁定和感知的批处理。 当 BizTalk 文件适配器已从阻止和非批处理感知更改为非阻止和批处理感知，实现了三倍的性能提升了。  
  
 **故障排除提示：**阻止传输可能会导致性能降低的整个主机实例。 如果适配器执行过多阻塞**TransmitMessage**将阻止引擎线程将消息传送到其他适配器。  
  
## <a name="non-batched-sends"></a>非成批发送  
 不感知的批处理的适配器应实现**IBTTransmitter**详见[异步发送适配器的接口](../core/interfaces-for-an-asynchronous-send-adapter.md)。 为每条消息，该适配器需要传输 the Messaging Engine 调用**IBTTransmitter.TransmitMessage**。 以下对象交互示意图详细说明的典型方法以传输消息，其中包括以下步骤：  
  
1.  引擎将该消息传送到适配器。  
  
2.  适配器将排到内存中队列准备要传输的消息。  
  
3.  适配器的线程池中的线程中取消排队的消息从队列中读取消息，配置，并通过网络传输消息。  
  
4.  适配器从引擎中获取新批。  
  
5.  适配器调用**DeleteMessage**批次，它只是已传输的消息中传递。  
  
6.  适配器调用**完成**批次。  
  
7.  引擎处理批处理，并从应用程序队列中删除消息。  
  
8.  引擎回调通知它的结果的适配器**DeleteMessage**操作。  
  
 ![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")  
  
 前面的对象交互图显示从应用程序队列中删除一条消息的适配器。 理想情况下适配器的批次而不是一次运行上一条消息的消息操作。  
  
## <a name="batched-sends"></a>成批的发送  
 批处理感知适配器应实现**IBTBatchTransmitter**和**IBTTransmitterBatch**详见[发送适配器的接口](../core/interfaces-for-send-adapters.md)。 当引擎具有的适配器以传输消息时，引擎将获取一批新的适配器通过调用**IBTBatchTransmitter.GetBatch**。 适配器返回一个新的 batch 对象实现**IBTTransmitterBatch**。 引擎然后通过调用启动批处理**IBTTransmitterBatch.BeginBatch**。 此 API 具有输出参数，它将接受的消息的最大数指定批次的适配器。 适配器 （可选） 可能会返回一个 DTC 事务。 则引擎会调用**IBTTransmitterBatch.TransmitMessage**一次针对每个传出消息添加到批处理。 这称为次数是大于零，但小于或等于到适配器所述的批处理的最大大小。 在所有消息都添加到批处理后，调用该适配器**IBTTransmitterBatch.Done**。 此时的适配器通常将排到内存中队列批处理中的所有消息。 适配器传输的消息从一个线程或在非批处理感知适配器如同其自己线程池中的线程。 适配器然后通知传输的结果的引擎。  
  
 以下对象交互图说明了两条消息由成批的发送适配器传输。  
  
 ![](../core/media/batchedsends.gif "BatchedSends")  
  
## <a name="handling-transmission-failures"></a>处理传输故障  
 在下图说明了传输失败的建议的语义。 这些是仅为建议，不会强制执行消息传送引擎。 你可以开发偏离这些准则，如果有这样的有效原因，但你应注意这种情况下的适配器。 例如，一般情况下适配器应始终将消息移到备份传输耗尽所有重试后。  
  
 更常见传输可能需要使用比配置的多个重试。 虽然这是略有不同帐户被视为可接受，因为已增加的传输层的灵活性。 一般情况下由 the Messaging Engine 公开的 Api 旨在尽可能让适配器能够最大控制。 伴随此控件的更大程度的责任。  
  
 ![](../core/media/handlingerrors.gif "HandlingErrors")  
  
 适配器通过检查系统上下文属性确定可在上找到一条消息的重试次数**RetryCount**。 适配器调用**重新提交**API 一次每个重试尝试，并传入要重新提交的消息。 与消息一起传递用于指示当引擎应将消息传递回适配器时的时间戳。 此值通常应当前时间加上的值**RetryInterval**。 **RetryInterval**是系统的上下文属性的单位为分钟。 这两个**RetryCount**和**RetryInterval**消息上下文中是在发送端口配置的值。 请考虑具有的相同的多台计算机上部署 BizTalk 主机实例的向外扩展的部署。 如果消息传送后重试间隔已过期，则可能对任何其中它们配置为运行的计算机上的主机实例的任一传递消息。 为此适配器应保持与消息重试后使用关联的任何状态尝试由于并不保证同一实例的适配器将负责在更高版本时传输。  
  
 适配器应仅尝试将消息移到备份传输后重试计数小于或等于零。 如果没有备份传输的端口配置，以便将消息移到备份传输尝试将失败。 在这种情况下应挂起消息。  
  
 下面的代码段演示如何确定重试计数和从消息上下文中和后续的重新提交间隔或将移动到备份传输。  
  
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
 在适配器上的任何 Api 引发的异常**IBTTransmitter.TransmitMessage**， **IBTTransmitterBatch.TransmitMessage**， **IBTTransmitterBatch.Done**，引擎将涉及的消息传输视为传输失败，并执行适当的操作对于消息，如所述[如何处理适配器故障影响](../core/how-to-handle-adapter-failures.md)。  
  
 批处理感知发送适配器引发 TransmitMessage api 异常会导致整个批处理正在清除和默认传输失败操作正在执行该批处理中的所有消息。  
  
## <a name="solicit-response"></a>要求-响应  
 双向发送适配器通常支持单向和双向传输。 发送适配器确定是否应通过检查传输为单向或双向发送消息**IsSolicitResponse**消息上下文中的系统上下文属性。  
  
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
  
 在请求-响应传输过程中适配器传输请求消息。 此完成之后它提交了关联的响应，告知要从 MessageBox 数据库中删除原始请求消息的消息传送引擎。 应为响应消息的提交相同的传输代理批处理中执行的应用程序队列中删除消息的操作。 这可确保原子性的删除和提交的响应。 对于完整的原子性适配器应使用一个 DTC 事务，由此识别事务的资源，响应消息中，提交该请求消息的传输和删除请求消息都在同一个 DTC 的上下文事务。 与往常一样，我们建议使用非阻止发送传输请求消息。  
  
 下面的代码段演示了双向发送的主要方面。 在引擎调用**IBTTransmitter.TransmitMessage**适配器将排要将传输到内存中队列的消息。 适配器返回 `false`，指示它在执行非阻塞发送。 适配器的线程池 (**WorkerThreadThunk**) 为内存中队列提供服务和一条消息，将其提交给一个帮助器方法中取消排队。 此方法负责发送请求消息和接收响应消息。 （此帮助器方法的实现不在本主题的范围。）响应消息提交到引擎，并从应用程序队列中删除请求消息。  
  
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
 动态发送端口没有与之关联的适配器配置。 它们改用处理程序配置任何适配器需要将动态端口上的消息传输的默认属性。 例如，HTTP 适配器可能需要使用代理，需要提供凭据。 用户名、 密码和端口可指定的处理程序配置适配器缓存在运行时。  
  
 要确定动态消息是通过，发送的传输的引擎**OutboundTransportLocation**前缀为适配器的别名。 在安装时，适配器可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中注册一个或多个别名。 引擎分析**OutboundTransportLocation**在运行时查找匹配项。 适配器负责处理**OutboundTransportLocation**无论其前面预置的别名。 下表显示别名的现成可用 BizTalk 适配器已注册的一些示例。  
  
|适配器别名|适配器|OutboundTransportLocation 示例|  
|-------------------|-------------|---------------------------------------|  
|HTTP://|HTTP|http://www。 MyCompany.com/bar|  
|HTTPS://|HTTP|https://www。 MyCompany.com/bar|  
|mailto:|SMTP|mailto:A.User@MyCompany.com|  
|FILE://|FILE|FILE://C:\MyCompany \\%MessageID%.xml|