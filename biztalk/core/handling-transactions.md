---
title: 处理事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea7601fdb2a11927cee0a9ffcbcb00b5c689e70b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387587"
---
# <a name="handling-transactions"></a>处理事务
## <a name="transacted-receivers"></a>事务性的接收器  
 事务性的接收器和非事务性的接收器之间的主要区别是事务性的接收器创建和使用显式 MSDTC 事务以确保其数据源之间的原子性和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。 一般情况下，适配器的其他方面是相同。  
  
 应注意的是请求-响应接收适配器仅用于事务提交到消息引擎的原始请求消息。 从消息引擎发送到适配器的响应的传输需要不同的事务。 这是因为第一个事务的作用域是在适配器和 MessageBox 数据库之间。 后续的请求消息才会向适配器从消息引擎为原始请求消息的事务提交之前。  
  
 以下对象交互图说明了适配器和消息引擎之间的传入消息事务性提交过程的交互。 在此示例中，以下一系列交互会发生：  
  
1. 适配器从引擎获取新批。  
  
2. 适配器创建新的 MSDTC 事务。  
  
3. 适配器从其已在事务中登记的数据源执行破坏性读取。  
  
4. 适配器提交消息。  
  
5. 适配器调用**完成**上的批处理，传入其 MSDTC 事务并将其**BatchComplete**回调指针。 引擎将返回**IBTDTCCommitConfirm**接口。  
  
6. 引擎处理该批，适配器回调在其**BatchComplete**实现中，并传达其消息处理到适配器的状态。  
  
7. 如果该批成功，则适配器将提交该事务并调用**IBTDTCCommitConfirm.DTCCommitConfirm** API 使用`true`提交的值。  
  
   ![](../core/media/transactedreceiver.gif "TransactedReceiver")  
  
## <a name="transacted-transmitters"></a>事务性的发送器  
 事务性的适配器在大多数情况下非常类似于非事务的适配器。 主要区别在于，事务性的适配器将数据发送消息中对它已在 MSDTC 事务中登记的资源。  
  
 **实现提示：** 对于事务性发送，适配器应使用相同的 MSDTC 事务来将数据写入到目标和用于删除通过**IBTTransportBatch.DeleteMessage**方法调用。 仅这两个操作需要进行事务处理。 任何其他操作，如**IBTTransportBatch.Resubmit**， **IBTTransportBatch.MoveToNextTransport**，并**IBTTransportBatch.MoveToSuspendQ**不一定要事务处理。 这是因为引擎隐式使用事务，并且这些类型的操作不需要是原子就目标而言。  
  
 以下对象交互图说明了适配器和引擎之间的交互。 事件序列如下所示：  
  
1. 引擎从适配器获取新批。  
  
2. 该引擎将两个消息添加到新的批。  
  
3. 引擎将调用**完成**对批，导致适配器将该批发送到提供服务的内部传输队列由其线程池。  
  
4. 适配器创建新的 MSDTC 事务。  
  
5. 适配器传输在 MSDTC 事务中登记目标的消息。 例如，这可能会写入到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。  
  
6. 在传输后，适配器从引擎获取新批。  
  
7. 适配器调用**DeleteMessage**它已成功传输的消息。  
  
8. 适配器调用**完成**上传入其 DTC 事务的批处理。 引擎将返回**IBTDTCCommitConfirm**接口。  
  
9. 引擎处理该批，从应用程序队列中删除消息。  
  
10. 引擎回调适配器**IBTBatchCallback**上成功的删除操作的信息的接口。  
  
11. 如果该批成功，则适配器提交事务。  
  
12. 适配器调用**IBTDTCCommitConfirm.DTCCommitConfirm**以便通知引擎已成功提交事务。  
  
    ![](../core/media/transactedtransmitter.gif "Transactedtransmitter")  
  
### <a name="transacted-solicit-response-adapters"></a>事务性要求-响应适配器  
 与双向接收不同，可能会使用相同的 DTC 事务执行双向发送。 事务性要求-响应适配器应使用相同**IBTTransportBatch**有关**SubmitResponseMessage**并**DeleteMessage**操作。 此批应使用用于收发要求-响应消息对的相同 MSDTC 事务。 这可确保要求-响应消息交换的原子性。  
  
## <a name="service-components-and-byot"></a>服务组件和 BYOT  
 消息引擎 Api 要求提供 MSDTC 事务。 但是某些.NET 组件设计用于为服务组件，并且不允许以编程方式提交或中止的事务。 相反，该平台上的 COM + 运行时自动提交事务。  
  
 对于这种情况，适配器应使用自带您自己事务 (BYOT)。 这允许适配器创建 MSDTC 事务，实例化使用该事务的.NET 组件并使该组件继承创建的事务，而不是创建其自己的事务。 .NET Framework 提供了**System.EnterpriseServices.BYOT**实现此目的。 SDK BaseAdapter 提供帮助器类**BYOTTransaction**，实现此目的。  
  
## <a name="avoiding-race-conditions"></a>避免争用情况  
 当你编写的适配器的创建事务对象，并将其到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，表明您接受负责编写代码，执行以下操作：  
  
- 解析与批处理相关联的消息中的错误。  
  
- 确定与批操作相关联的事务的最终结果。  
  
  适配器必须通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要维护其内部的事务的最终结果跟踪数据。 适配器通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的结果通过调用**DTCConfirmCommit**。 如果适配器不会执行此操作，会发生重大内存泄漏。  
  
  上面列出的两个任务 （解决错误和确定最终结果） 看似非常简单，但实际上它们依赖于来自不同线程的信息：  
  
- 适配器处理错误时，基于传递的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到**BatchComplete**在适配器中的回调。 此回叫是适配器的线程上。  
  
- **DTCConfirmCommit**上是一种方法**IBTDTCCommitConfirm**对象。 实例**IBTDTCCommitConfirm**对象返回的批处理**ibttransportbatch:: Done**调用。 此实例是作为在同一线程上**ibttransportbatch:: Done**调用，这是不同于适配器的线程。  
  
- 对于适配器对每个调用**ibttransportbatch:: Done**没有相应的回调**BatchComplete**，也就是说，消息引擎调用在单独的线程以报告的结果中的批提交。 在中**BatchComplete**批的适配器需要提交或回滚该事务基于是否通过或失败。 在任一情况下，适配器应然后调用**DTCConfirmCommit**报告给消息引擎该事务的状态。  
  
  因为不存在可能出现的争用条件的适配器的实现**BatchComplete**可以假设**IBTDTCCommitConfirm**返回对象**ibttransportbatch:: Done**时，才始终可用**BatchComplete**执行。 但是， **BatchComplete**可以在单独的消息引擎线程，即使之前调用**ibttransportbatch:: Done**返回。 可以当适配器尝试访问**IBTDTCCommitConfirm**对象的一部分**BatchComplete**实现中，没有访问冲突。  
  
  使用下面的示例中的事件解决此问题。 此处可通过使用事件属性访问的接口指针。 Get 总是等待 set。  
  
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
  
 现在，从返回的值将分配**ibttransportbatch:: Done**给此属性，并将其**BatchComplete**调用。  
  
## <a name="see-also"></a>请参阅  
 [事务性消息批](../core/transactional-message-batches.md)