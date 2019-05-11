---
title: 批处理消息的接收处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32bf0b70-e9d1-4fab-9c74-160e51390700
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e60bab7b9f6d41268bd60be0b1f37daf07019af1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358294"
---
# <a name="batching-messages-for-receive-processing"></a>批处理消息的接收处理
## <a name="batch-callbacks"></a>批回调  
 提交的批次接收到消息引擎适配器异步处理。 因此适配器需要一种机制来将绑定到适配器中的某些状态回调，因此它可以成功或失败通知并执行任何必要的清理操作。 回调语义非常灵活，以便适配器可以使用一个或这三种方法的组合。 这些是：  
  
- 实现在同一对象实例上进行所有回调**IBTBatchCallBack**。  
  
- 当请求一个新的批处理用于关联到适配器中的状态回调时，cookie 传递到引擎中。  
  
- 没有实现每个批次不同的回调对象**IBTBatchCallBack**。 此处的每个对象包含其自己的私有状态。  
  
  适配器时已处理批，实现其回叫**IBTBatchCallBack.BatchComplete**。 由第一个参数，HRESULT 状态指示批处理的总体状态。 如果此值是大于或等于零，然后在批处理成功意义上说，该引擎还具有数据的所有权和适配器可以自由地从网络中删除该数据。 负值状态表示该批次失败：任何批处理中的操作都成功，适配器负责处理失败。  
  
  如果批失败，适配器需要知道哪一项操作失败，在其中。 例如，假设适配器已从磁盘并将它们到提交读取 20 个文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并用一批。 如果第 10 个文件已损坏，适配器需要挂起的文件，然后重新提交剩余 19。 此信息可供适配器中的第二个和第三个参数 —`opCount` （操作计数） 的 short 类型和`operationStatus`，它属于类型 BTBatchOperationStatus []。  
  
> [!NOTE]
>  在单个批处理对象应永远不会提交一条消息超过一次。 在同一个批处理多次提交同一个消息对象将导致引擎错误。  
  
 将操作计数指示如何许多类型的操作是批处理中 (的大小**BTBatchOperationStatus**数组)。 操作状态数组中的每个元素对应于给定的操作类型。 通过使用**BTBatchOperationStatus**数组，该适配器可以确定哪一项中给定的操作失败，通过查看**BTBatchOperationStatus.MessageStatus**负 HRESULT 的数组表明失败的值。 在上述方案中，适配器创建新的批处理包含 19 提交消息和一条消息挂起。  
  
 下面的代码段演示如何适配器从引擎通过其传输代理请求一个新的批处理，并将一条消息提交到引擎中使用 cookie 的方法。 消息引擎调用**BatchComplete**方法作为批回调处理的整批完成提交消息。  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter :   
                  IBTTransport,   
                  IBTTransportConfig,   
                  IBTTransportControl,  
                  IPersistPropertyBag,   
                  IBaseComponent,  
                  IBTBatchCallBack  
{  
      private IBTTransportProxy _tp;  
  
      public void BatchComplete(      
            Int32                         status,   
            Int16                         opCount,   
            BTBatchOperationStatus[]      operationStatus,   
            System.Object                 callbackCookie)  
      {  
            // Use cookie to correlate callback with work done,  
            // in this example the batch is to submit a single  
            // file the name of which will be in the  
            // callbackCookie  
            string fileName = (string)callbackCookie;  
            if ( status >= 0 )  
                  // DeleteFile from disc  
                  File.Delete(fileName);          
            else  
                  // Rename file to fileName.bad  
                  File.Move(fileName, fileName + ".bad");  
      }  
  
      private void SubmitMessage(  
            IBaseMessage                  msg,   
            string                        fileName)  
      {  
            // Note: Pass in the filename as the cookie  
            IBTTransportBatch batch =   
                  _tp.GetBatch(this, (object)fileName);  
  
            // Add msg to batch for submitting   
            batch.SubmitMessage(msg);   
  
            // Process this batch  
            batch.Done(null);  
      }  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 包括下列适配器的示例：文件、 HTTP、 MSMQ 和事务性适配器。 所有这些适配器是基于名为 BaseAdapter 常见构建基块。 版本 1.0.1 的 baseadapter 包括所有相关的代码分析操作状态并重新生成新的批次提交。  
  
## <a name="race-condition"></a>争用条件  
 解决错误，并决定提交了一批的最终结果的两个任务看似非常简单，但实际上它们依赖于来自不同线程的信息：  
  
- 适配器处理错误时，基于传递的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与适配器的**BatchComplete**回调方法。 适配器的线程上执行此回调。  
  
- **DTCCommitConfirm**上是一种方法**IBTDTCCommitConfirm**对象。 实例**IBTDTCCommitConfirm**对象返回的批处理**ibttransportbatch:: Done**调用。 此实例是作为在同一线程上**ibttransportbatch:: Done**调用，这是不同于适配器的回调线程。  
  
  对于适配器对每个调用**ibttransportbatch:: Done** ，消息引擎会相应地调用的回调方法**BatchComplete**在单独的线程以报告的结果批提交。 在中**BatchComplete**批的适配器需要提交或回滚该事务基于是否通过或失败。 在任一情况下，适配器应然后调用**DTCCommitConfirm**报告事务的状态。  
  
  因为不存在可能出现的争用条件的适配器的实现**BatchComplete**可以假设**IBTDTCCommitConfirm**返回对象**ibttransportbatch:: Done**时，才始终可用**BatchComplete**执行。 但是， **BatchComplete**可以在单独的消息引擎线程，即使之前调用**ibttransportbatch:: Done**返回。 可能的适配器尝试访问**IBTDTCCommitConfirm**对象的一部分**BatchComplete**实现中，则会访问冲突，因为调用线程不能再存在。 使用以下解决方案来避免这种情况。  
  
  在以下示例中，通过使用事件解决此问题。 此处可通过使用事件属性访问的接口指针。 Get 总是等待设置完成，然后继续下一步。  
  
```  
protected IBTDTCCommitConfirm CommitConfirm  
{  
      set  
      {  
            this.commitConfirm = value;  
            this.commitConfirmEvent.Set();  
      }  
      get  
      {  
            this.commitConfirmEvent.WaitOne();  
            return this.commitConfirm;  
      }  
}  
protected IBTDTCCommitConfirm commitConfirm = null;  
private ManualResetEvent commitConfirmEvent = new ManualResetEvent(false);  
```  
  
## <a name="batch-status-codes"></a>批处理状态代码  
 总体批状态代码指示批的结果。 操作状态的提交状态代码为单个消息项。 批次可能会出于各种原因而失败。 可能与安全相关的故障，或者消息可能已提交时引擎已关闭。 （通常在引擎关闭时它不接受任何新的工作，但要完成的进程内工作。）下表指示在批处理状态或操作状态中返回一些常见的 HRESULT 值。 它还指示它们是否成功或失败代码。 正确处理这些代码的方法是更全面中所述[如何处理适配器故障](../core/how-to-handle-adapter-failures.md)。  
  
|代码 （BTTransportProxy 的类中定义）|成功/失败代码|Description|  
|----------------------------------------------------|---------------------------|-----------------|  
|BTS_S_EPM_SECURITY_CHECK_FAILED|成功|该端口已配置为执行安全检查和删除身份验证失败的消息。 适配器应挂起返回此状态代码的批处理。|  
|BTS_S_EPM_MESSAGE_SUSPENDED|成功|指示一个或多个消息被挂起，并且该引擎还具有数据的所有权。 它是成功代码，因为消息引擎已接受提交消息。|  
|E_BTS_URL_DISALLOWED|失败|一条消息已提交具有无效**InboundTransportLocation**。|  
  
## <a name="batch-operations"></a>批处理操作  
 下表详细说明的成员方法和操作**IBTTransportBatch**对象适配器用于将工作添加到给定的批。  
  
|方法名称|操作类型|Description|  
|-----------------|--------------------|-----------------|  
|**SubmitMessage**|提交|将消息提交到引擎中。|  
|**SubmitResponseMessage**|提交|将响应消息提交到引擎。 这是在要求-响应对中的响应消息。|  
|**DeleteMessage**|DELETE|删除适配器已成功传输通过网络使用非阻塞发送一条消息。 使用阻塞发送的适配器无需调用此方法，因为消息引擎将删除该适配器的代表如果适配器返回`true`从**TransmitMesssage**。|  
|**MoveToSuspendQ**|MoveToSuspendQ|将一条消息移至挂起队列。|  
|**重新提交**|重新提交|一条消息，应在更高版本时传输重试请求。 这通常称为后传输尝试已失败。|  
|**MoveToNextTransport**|MoveToNextTransport|请求，如果一条消息将传输使用其备份传输。 已用完所有重试后，通常调用。 如果存在没有备份传输，则此方法将失败|  
|**SubmitRequestMessage**|SubmitRequest|提交请求消息。 这是请求-响应对中的请求消息。|  
|**CancelRequestForResponse**|CancelRequestForResponse|通知引擎，该适配器不再想要等待的请求-响应对中的响应消息。|  
|**Clear**|不适用|清除批处理中的所有工作。|  
|**Done**|不适用|将提交一批引擎进行处理的消息。|  
  
## <a name="batch-management"></a>Batch 管理  
 消息引擎中的本机代码中实现批处理。 出于此原因在托管代码中编写的适配器应释放运行时可调用包装 (RCW) 批处理使用批处理完成之后。 这是通过托管代码中使用**Marshal.ReleaseComObject** API。 务必要记住，应在一段时间中调用此 API 循环播放，直到返回的引用计数达到零时。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理批中的同步消息。 同时，它提供的信息在适配器中的某些优化机会通过调整应用程序域中的批大小，均可以处理许多批处理。 例如，您可能会处理 FTP 站点上的所有文件 （直到命中某些限制）。 在 SAP 的情况下可能有数量的消息，然后作为批处理提交到处理单个流。  
  
 适配器用于将操作的批处理回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不需要完全对应于消息的列表，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给适配器。 换而言之，当执行事务性发送必须重新提交操作将拆分**MoveToNextTransport**并**MoveToSuspendQ**到单独的批。 许多适配器对一批消息的多个终结点提交到单独的进一步处理的消息的列表进行排序。  
  
 在于没有 （除了那些与事务关联） 的规则与中的消息批处理相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 批处理是只需输入和输出消息的分块的消息的适配器的特定于实现的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 适配器可以批处理消息从多个较小批[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供它到较大的批的响应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这可能是在面对大量非常小的消息的事务性适配器中进行了显著优化。 它最小化"的每个消息的事务总数"比率。  
  
 通常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成的 5 到 10 的消息之间的发送端批处理。 如果这些是非常小的消息，适配器可能会将批最多 100 个消息或详细信息之前它将删除的事务性批处理提交回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 一种优化，此类不是可轻松实现;您必须确保消息永远不会在适配器内存中，获取遇到无休止地等待一些必须满足的阈值。  
  
 批处理的重要性所示的性能数字[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如 MQSeries 的高吞吐量适配器。 这些适配器可以在至少两次经常与将它们发送接收消息。 默认情况下，接收适配器使用批 100 个消息和发送适配器将使用默认值[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]赋予它的批处理。  
  
## <a name="transactional-batches"></a>在事务性批  
 当你编写的适配器的创建事务对象，并将其到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，表明您接受负责编写代码，执行以下操作：  
  
- 确定批处理操作的最终结果： 提交或结束事务。 这可能取决于其他事务分支的作用域内的此事务不是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]相关，如写入消息队列 (MSMQ) 队列或事务性数据库操作。  
  
- 告知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过调用将最终结果**IBTDTCCommitConfirm.DTCCommitConfirm**方法。 返回`true`指示成功提交事务; 返回`false`表示失败并回滚该事务。  
  
  适配器必须通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要维护其内部的事务的最终结果跟踪数据。 适配器通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的结果通过调用**DTCCommitConfirm**。 如果适配器不会执行此操作，会发生重大内存泄漏和 MSDTC 事务可能会超时，并且尽管成功完成其操作失败。