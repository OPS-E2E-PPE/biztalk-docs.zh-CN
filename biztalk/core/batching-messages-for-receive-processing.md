---
title: 批处理消息接收处理 |Microsoft 文档
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
ms.openlocfilehash: ef14179c1af460afc516b7fa331ee30a758219c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234797"
---
# <a name="batching-messages-for-receive-processing"></a>批处理消息接收处理
## <a name="batch-callbacks"></a>批处理回调  
 提交的批次接收到消息引擎适配器以异步方式处理。 因此该适配器需要一种机制，以便它可以成功或失败的通知并执行任何必要的清除操作将为适配器中某些状态回调。 回调语义可以灵活，这样适配器可以使用一种或三种方法的组合。 这些是：  
  
-   实现对同一对象实例进行所有回调**IBTBatchCallBack**。  
  
-   当请求一个新的批处理用于关联到适配器中的状态回调时，cookie 将传递到引擎。  
  
-   没有实现每个批的不同的回调对象**IBTBatchCallBack**。 此处每个对象保存其自己的私有状态。  
  
 适配器处理批处理时在其实现的回叫**IBTBatchCallBack.BatchComplete**。 由第一个参数，HRESULT 状态指示批处理的总体状态。 如果此值为大于或等于零，则批处理已成功在引擎具有数据的所有权，并且适配器可以随时从网络中删除该数据的意义上。 负状态指示批处理失败： 无批处理中的操作已成功和适配器负责处理失败。  
  
 如果批处理失败，该适配器将需要了解哪一项操作失败，在其中。 例如，假设该适配器已从磁盘并将它们到提交读取 20 个文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用单个批处理。 如果第 10 个文件已损坏，则适配器将需要挂起该一个文件并重新提交剩余 19。 此信息可供第二个和第三个参数中的适配器-`opCount` （操作计数） 的短类型和`operationStatus`，它属于类型 BTBatchOperationStatus []。  
  
> [!NOTE]
>  单个批处理对象上你应永远不会提交一条消息一次以上。 在同一个批处理多次提交同一消息对象所做的工作会引擎错误。  
  
 操作计数表明如何许多类型的操作已在批处理中 (的大小**BTBatchOperationStatus**数组)。 操作状态数组中的每个元素对应于给定的操作类型。 通过使用**BTBatchOperationStatus**数组，该适配器可以确定哪一项中给定的操作失败，通过查看**BTBatchOperationStatus.MessageStatus**为负 HRESULT 数组表明失败的值。 在上述方案中，适配器会创建一个新的批处理包含 19 提交了消息，一条消息挂起。  
  
 下面的代码段演示如何适配器从引擎通过其传输代理请求一个新的批处理，并使用 cookie 方法引擎提交一条消息。 Messaging Engine 调用**BatchComplete**作为批处理回调处理整个批处理的完成方法提交消息。  
  
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
            Int32                         status,   
            Int16                         opCount,   
            BTBatchOperationStatus[]      operationStatus,   
            System.Object                 callbackCookie)  
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
            IBaseMessage                  msg,   
            string                        fileName)  
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
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 包括以下适配器的示例： 文件、 HTTP、 MSMQ 和事务的适配器。 所有这些适配器的构建基于功能调用 BaseAdapter 常见构建基块。 版本 1.0.1 BaseAdapter 包括所有相关的代码，以分析操作状态并重新生成一个新的批次以提交。  
  
## <a name="race-condition"></a>争用条件  
 解决错误，并决定提交批处理的最后结果的两个任务看起来很简单，但实际上它们依赖于从不同的线程的信息：  
  
-   适配器来处理基于信息由传递的错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到适配器的**BatchComplete**回调方法。 在适配器的线程上执行此回调。  
  
-   **DTCCommitConfirm**上是一种方法**IBTDTCCommitConfirm**对象。 实例**IBTDTCCommitConfirm**对象返回批处理**IBTTransportBatch::Done**调用。 此实例位于相同的线程上**IBTTransportBatch::Done**调用，即不同于适配器的回调线程。  
  
 适配器对每次调用**IBTTransportBatch::Done** the Messaging Engine 使相应地调用的回调方法**BatchComplete**在单独的线程来报告的结果批次提交。 在**BatchComplete**批处理适配器需要提交或回滚事务基于是否通过或失败。 在任一情况下，适配器然后应调用**DTCCommitConfirm**报告事务的状态。  
  
 可能的争用情况存在因为适配器的实现**BatchComplete**可以假设**IBTDTCCommitConfirm**返回对象**IBTTransportBatch::Done**始终可用，是何时**BatchComplete**执行。 但是， **BatchComplete**可以在单独的消息传送引擎线程，即使之前调用**IBTTransportBatch::Done**返回。 可能的适配器尝试访问**IBTDTCCommitConfirm**对象作为的一部分**BatchComplete**实现中，存在是访问冲突，因为调用线程不再存在。 使用以下解决方案来避免这种情况。  
  
 在下面的示例中，通过使用事件，可解决问题。 在这里，通过使用事件的属性来访问接口指针。 Get 始终等待要在继续之前完成的集。  
  
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
 总体批处理状态代码指示批处理的结果。 操作状态将授予的每个邮件项的提交状态代码。 由于各种原因，批处理可能会失败。 可能有与安全相关的故障，或消息可能已提交引擎已关闭时。 （通常当引擎关闭时它不接受任何新的工作但允许进程内可完成工作。）下表指示在批处理状态或操作状态中返回一些常见的 HRESULT 值。 它还指示这些是否成功或失败代码。 正确处理这些代码中所述更完全[如何处理适配器故障影响](../core/how-to-handle-adapter-failures.md)。  
  
|（BTTransportProxy 的类中定义） 的代码|成功/失败代码|Description|  
|----------------------------------------------------|---------------------------|-----------------|  
|BTS_S_EPM_SECURITY_CHECK_FAILED|成功|此端口已配置为执行安全检查和删除身份验证失败的消息。 适配器不应挂起返回此状态代码的批处理。|  
|BTS_S_EPM_MESSAGE_SUSPENDED|成功|表示一个或多个消息已挂起，引擎具有数据的所有权。 它的成功代码在于 the Messaging Engine 已接受消息提交。|  
|E_BTS_URL_DISALLOWED|失败|一条消息已提交具有无效**InboundTransportLocation**。|  
  
## <a name="batch-operations"></a>批处理操作  
 下表详细说明的成员方法和操作**IBTTransportBatch**对象，该适配器使用以将工作添加到给定的批处理。  
  
|方法名称|操作类型|Description|  
|-----------------|--------------------|-----------------|  
|**SubmitMessage**|提交|将消息提交到引擎。|  
|**SubmitResponseMessage**|提交|将响应消息提交到引擎。 这是请求-响应对中的响应消息。|  
|**DeleteMessage**|DELETE|删除适配器已成功传输通过网络中使用非阻止发送一条消息。 使用阻止发送的适配器不需要调用此方法，因为消息引擎会将其删除适配器的代表如果适配器返回`true`从**TransmitMesssage**。|  
|**MoveToSuspendQ**|MoveToSuspendQ|将消息移动到已挂起队列中。|  
|**重新提交**|重新提交|一条消息，应在以后的传输重试请求。 这通常称为后传输尝试失败。|  
|**MoveToNextTransport**|MoveToNextTransport|请求，使用其备份传输传输一条消息。 通常称为耗尽所有重试后。 如果存在任何备份的传输，不则此方法将失败|  
|**SubmitRequestMessage**|SubmitRequest|将提交请求消息。 这是请求-响应对中的请求消息。|  
|**CancelRequestForResponse**|CancelRequestForResponse|通知适配器不再想要等待的请求-响应对中的响应消息的引擎。|  
|**Clear**|不适用|清除批次中的所有工作。|  
|**完成**|不适用|将提交一批引擎以进行处理的消息。|  
  
## <a name="batch-management"></a>批处理管理  
 在消息引擎中的本机代码中实现批处理。 出于此原因用托管代码编写的适配器应释放运行时可调用包装 (RCW) 批处理与批次完成之后。 这可在托管代码中使用**Marshal.ReleaseComObject** API。 务必记住，在一段时间中应该调用此 API 循环执行，直到返回的引用计数达到零时。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理同步在一个批处理中的消息。 同时，它提供的信息与适配器中的某些优化机会通过调整应用程序域中的批处理大小，均可以处理许多批处理。 例如，你可能会处理 FTP 站点上的所有文件 （直到命中某些限制）。 对于 SAP 可能到数目的消息，然后提交以批处理方式处理单个流。  
  
 适配器用于传递操作批处理回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不需要完全对应的消息列表的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]赋予适配器。 换而言之，当这样做事务发送必须拆分重新提交操作**MoveToNextTransport**和**MoveToSuspendQ**到单独的批处理文件。 许多适配器对一批消息的多个终结点提交到单独的进一步处理的消息的列表进行排序。  
  
 点是否不有任何规则 （除了与事务关联的那些） 与消息批处理中关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 批处理是只需为使适配器进出分块消息的特定于实现的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 一个适配器可以批处理中的消息较小的多个批处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]授予它较大的批插入到响应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这可能是处理的大量非常小的消息的事务适配器中的一个重要优化。 它最小化"的每个消息的事务总数"比率。  
  
 通常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产生 5-10 的消息之间的发送端批处理。 如果这些是很小的消息、 适配器可能批处理最多 100 个消息或多个提交的事务性批处理中的删除之前回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 一种优化方式如下并不容易实现;你必须确保消息永远不会在适配器内存中，获取遇到有关某一阈值，需满足无休止地等待。  
  
 批处理的重要性所示的性能数字[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如 MQSeries 高吞吐量适配器。 这些适配器可以在至少两次经常与将它们发送接收消息。 默认情况下接收适配器使用批次的 100 个消息并发送适配器使用默认值[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将为其给定的批处理。  
  
## <a name="transactional-batches"></a>事务批  
 当你编写的适配器，创建事务对象，并为到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，表明你接受负责编写的代码，执行下列任务：  
  
-   决定批处理操作的最终结果： 提交或结束事务。 这可能取决于事务的其他分支的范围内的此一个事务不[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖项，例如，对消息队列 (MSMQ) 队列或事务的数据库操作写入。  
  
-   通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过调用的最后结果的**IBTDTCCommitConfirm.DTCCommitConfirm**方法。 返回`true`指示成功提交的事务; 返回`false`表示失败，并回滚事务。  
  
 适配器必须通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]关于事务来维护其内部的最终结果跟踪数据。 适配器通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过调用的结果的**DTCCommitConfirm**。 如果适配器不满足该条件，则会发生大量的内存泄漏和 MSDTC 事务可能会超时，并且尽管成功完成其操作失败。