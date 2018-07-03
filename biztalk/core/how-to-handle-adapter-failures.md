---
title: 如何处理适配器故障 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdceb364-38d6-4aab-a176-bf751da1be25
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac87b905d7eb68bdb37a900840f7bd747c92ed77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971918"
---
# <a name="how-to-handle-adapter-failures"></a>如何处理适配器错误
通常，适配器应挂起无法处理的消息。 例如，虽然接收适配器挂起消息的决策取决于适配器的用途，但在其遇到提交失败时，通常应挂起消息。 关于失败的处理，还应注意安全事项。 例如，如果适配器自动挂起所有失败的消息，则该适配器可能会遭受拒绝服务攻击，导致 BizTalk Server 挂起队列向上填充。  某些适配器（如 HTTP）会向客户端返回失败代码，指示请求已被拒绝。 对于这些类型的适配器，返回失败代码通常要比挂起消息更有意义。 通常，发送适配器仅在已重试了所允许的最大主传输和次要传输重试次数后才会挂起消息。  
  
## <a name="associate-error-processing-with-an-individual-operation-and-not-with-the-batch-that-contains-the-operation"></a>将错误处理与单个操作相关联而不与包含该操作的批相关联  
 适配器的用户应该能够看到适配器内的消息批处理。 这意味着批中某一操作的失败不应影响任何其他操作。 但是，由于批是原子操作，一个消息的失败将会导致整个批出现错误，从而不会再处理任何操作。  
  
 您需要编写负责处理错误的代码，重新提交成功的消息并挂起不成功的消息。 幸运的是，BizTalk Server 可以提供详细的错误结构，使适配器能够确定具体的失败操作。 它允许构造进一步的批，在其中重新提交成功的操作并挂起不成功的操作。  
  
 操作的最终状态不应受适配器内批处理的影响。  
  
## <a name="use-seterrorinfo-to-report-failure-to-biztalk-server"></a>使用 SetErrorInfo 向 BizTalk Server 报告失败  
 如果要挂起消息，必须从前一消息上下文向 BizTalk Server 提供失败信息。 BizTalk Server 提供的错误报告使用的功能**SetErrorInfo**方法同时**IBaseMessage**并**ITransportProxy**接口。 您可以按以下方式报告错误：  
  
- 异常使用时处理消息时失败，则设置**SetErrorInfo (Exception e)** 消息 (**IBaseMessage**) 被挂起。 这会让引擎保留该错误和消息以便以后诊断，并将其记录到事件日志以便通知管理员。  
  
- 如果错误是在初始化或内部簿记过程 （不在消息处理） 遇到应调用**SetErrorInfo (Exception e)** 上**ITransportProxy**指针传递给您在初始化过程中。 如果适配器基于 BaseAdapter 实现，则应始终有权访问该指针。 否则，应确保对它进行缓存。  
  
  使用以上任一方法报告错误均会将错误消息写入到事件日志中。 如果可以，必须将错误与相关消息相关联。  
  
## <a name="handle-a-database-offline-condition"></a>处理数据库脱机情况  
 如果其中一个 BizTalk Server 数据库脱机，则 BizTalk 服务将回收其自身。 在回收服务之前，消息引擎会尽可能关闭所有接收位置。 如果此操作超过 60 秒，则服务将终止。 因为引擎会执行事务处理，因此不会导致数据丢失。  
  
 通过使用以下项可以在注册表中优化此超时：  
  
```  
DWORD   
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingDBFailoverShutdownTimeLimit  
```  
  
 对于独立的适配器，由于 BizTalk Server 不拥有该进程，因此当其中一个 BizTalk Server 数据库脱机时，会禁用这些接收位置。 数据库恢复联机后，会重新启用这些接收位置。  
  
## <a name="write-to-the-event-log"></a>写入事件日志  
 适配器可以通过使用写入事件日志条目**IBTTransportProxy**接口传入异常。 用本机代码开发的适配器需要传入**IErrorInfo**接口， **IBTTransportProxy.SetErrorInfo (异常** `e` **)**。  
  
 对于像传输失败后适配器重试消息、将消息移动到备份传输或挂起消息这样的事件，消息引擎会代表适配器向事件日志中进行写入。 对于此类操作，适配器只需要在调用 API 之前对消息设置异常。 以下代码段演示了这一操作：  
  
```  
IBaseMessage msg;  
...  
// Set exception on msg to indicate why transmission failed...  
msg.SetErrorInfo(  
 new ApplicationException(  
 "The TCP connection was closed by the destination"));  
```  
  
## <a name="handle-receive-specific-batch-errors"></a>处理特定于接收的批错误  
  
### <a name="handle-receive-failures"></a>处理接收失败  
 适配器向 BizTalk Server 提交操作（或批操作）时，可能有多种原因导致失败。 其中两种最主要的原因是：  
  
- 接收管道失败。  
  
- 发布消息时发生路由失败。  
  
  当消息引擎遇到接收管道失败时，会自动尝试挂起消息。 挂起操作有时会失败。 例如，如果消息引擎在发布消息时遭遇路由失败，则引擎甚至不会尝试挂起消息。  
  
  通常，消息很容易失败。 在这种情况下，适配器应显式调用**MoveToSuspendQ** API，应尝试挂起消息。 当适配器尝试挂起消息时，以下条件之一应为真：  
  
- 应该挂起适配器提交的同一个消息对象（建议）。  
  
- 如果适配器必须创建新消息，则应设置新消息的消息上下文，其指针指向原来提交的消息的消息上下文。 这是因为消息的消息上下文包含很多有关该消息和失败的重要信息。 对失败的消息进行调试必需这些信息。  
  
> [!NOTE]
>  如果适配器创建新消息对象并将它挂起，则适配器应将错误信息从旧消息对象复制到新消息对象。  
  
 某些适配器（如与 BizTalk Server 一起提供的 HTTP 适配器）不需要挂起消息。 这些适配器会向其客户端返回一个错误。  
  
#### <a name="causes-of-failure"></a>失败原因  
 失败的简单原因是构造批或时可能发生的错误**ibttransportbatch:: Done**调用。  
  
-   **提交失败。** **提交**调用有限数量的原因，可能会失败，所有这些都是致命。 这些原因包括：  
  
-   BizTalk Server 进程空间发生内存不足错误。  
  
-   已从部署中删除了架构程序集。 在这种情况下，**提交**含义模糊的错误而失败。 在 MQSeries 适配器中，会捕获 BizTalk Server 中的一般失败异常，并会在系统事件日志中写入详细的错误消息。 此消息建议导致错误的一种可能原因是已从部署中以某种形式删除了架构程序集。  
  
     在常规，如果**提交**应尝试挂起消息使用相同的事务将失败。  
  
-   **Ibttransportbatch:: Done 失败。** **Ibttransportbatch:: Done**调用可能会由于多种原因之一失败。 通常，始终应尝试执行挂起操作，如果挂起失败，则结束该事务。 可能会收到从故障中的错误代码之一**ibttransportbatch:: Done**是 BizTalk Server 正在尝试关闭的情况下。 在这种情况下，应只是结束事务，并将它，因为**Terminate**调用可能正在并发发生。 成功构造了批并成功执行时，会出现其他情况**ibttransportbatch:: Done**。 在这些情况下，在返回的错误**BatchComplete** ，适配器必须确定要执行的操作与之和。 本部分的其余内容将对这种情况加以说明。  
  
#### <a name="processing-batchcomplete-errors"></a>处理 BatchComplete 错误  
 **BatchComplete**是由适配器调用的 BizTalk 服务器，用于指示批处理操作的完成状态时提供的回调。  
  
 最重要的参数传递给**BatchComplete**是批状态`hResult`。 它可指示批是成功还是失败。 如果批失败，则意味着该批中的所有操作都已失败。 该适配器将遍历批状态结构，并确定失败的消息 (我们称之为*批的筛选*)。  
  
#### <a name="nontransactional-batchcomplete-errors"></a>非事务性 BatchComplete 错误  
 对于非事务性适配器，您必须选择您的响应为在失败时**SubmitMessage**/**SubmitRequestMessage**或**SubmitResponseMessage**操作。 适配器通过调用挂起消息的通常**MoveToSuspendQ**。  
  
 始终需要传递以下操作： **DeleteMessage**， **MoveToSuspendQ**， **ResubmitMessage**。 如果这些操作失败，则通常意味着适配器中有错误。 在这些情况下，不必编写代码来处理失败。 但是，如果由于其他操作失败而导致批失败，则必须在新批中重新执行这些操作。  
  
 如果适配器调用**MovetoBackupTransport**并失败 （由于没有备份传输），然后应调用该适配器**MoveToSuspendQ**以挂起消息。  
  
#### <a name="transactional-batchcomplete-errors"></a>事务性 BatchComplete 错误  
 在使用适配器创建的事务向 BizTalk Server 提交批时，应该遵循以下两种方案之一：  
  
-   **使用单消息批。** 将包含单个消息的批发送至 BizTalk Server。 如果该单个消息失败，则可以在同一个事务下向 BizTalk Server 发送另一个批，但必须将有问题的消息移动到挂起队列而不是重新提交该消息。 删除失败的消息后，第二个批的提交应该会成功。 之后，当 BizTalk Server 确认第二个批成功时，可以提交该事务。 如果第二个批失败，则适配器必须中止该事务，或查找其他位置以存放该消息。 在此方案中，由于事务回滚处理，性能可能会立即明显降低。  
  
     可以采用一些方法来改善适配器的性能。 例如，MQSeries 适配器在运行时会动态调整其方法。 它运行时处理 100 个消息的批。 如果该适配器遇到错误，它必须结束该批，但会暂时切换到单消息批运行模式以避免错误消息， 然后还原为 100 个消息的批。 如果再次遇到错误，性能会再次降低。  
  
-   **使用抢先挂起功能。** 构造一个在其中抢先挂起错误消息的多消息批。 批处理包含多种**提交**并**MoveToSuspendQ**操作，并为第一个和仅在事务下的批处理。 由于会抢先挂起错误的数据，因此该批应该成功，并可以提交事务（等到收到 BizTalk Server 的确认后）。  
  
     这看起来好象需要了解以后的情况，但这一方法已在 MSMQ 适配器中得到了应用。 这种方法取决于是否具有唯一的消息 ID。 适配器会构造一个消息批。 如果出现任何错误，它将回滚事务（从而回滚该批），但会记住临时数据结构中的消息 ID。 （为防止这一结构无限增长，其中的项目会在一定的时间延迟后被删除。）在提交每个批之前，适配器都会检查错误消息 ID 列表。 如果发现错误消息 ID，适配器就会知道该消息将会失败（因为以前失败过），并会抢先挂起该消息而不尝试提交该消息。  
  
     并不是每个适配器都可靠地拥有唯一消息 ID，事务性存储就有可能不拥有这样的 ID。 因此，很多事务性适配器局限于发送单消息批。  
  
#### <a name="processing-other-errors"></a>处理其他错误  
 在所有其他情况下（如挂起消息失败），适配器必须结束事务。 任何其他结果均会导致消息重复或消息被删除。  
  
 如果批失败，适配器应尽可能地中止事务。 但是，有时适配器无法中止事务。 在这种情况下，适配器应使用同一个事务挂起消息。  
  
#### <a name="processing-errors-on-transactional-receive"></a>处理事务性接收错误  
 常用的事务性处理模式是在发生错误时结束事务。 在这种情况下，所有内容都将返回到其以前的状态，数据不会丢失。 但是，如果要使用事务性源中的数据（例如，从数据库的中间临时表中每次请求一行，或从 MQSeries 或 MSMQ 这样的队列产品中每次请求一个消息），则这种处理模式可能还不够。 如果只是结束事务并返回，然后重新提取相同的数据，则很可能发生同样的错误，系统会进入重复的循环。  
  
 早期版本的 BizTalk Server 中的 SQL 适配器具有这种行为。 但发行后不久，适配器的行为就被更改为尝试挂起失败的消息并提交事务。 将消息移动到同一事务下的挂起队列，然后提交事务，这样可以使数据免于丢失，还可以使适配器绕过错误数据。  
  
 当适配器的接收部分传递一条错误消息，以响应**提交**消息操作，适配器应处理该错误并将消息移至挂起队列。  
  
 如果适配器已经在事务性批中创建了事务对象并在事务下提交了消息，则在发生失败时，适配器应以逻辑方式将消息移到同一事务下的挂起队列。 该事务可确保数据不会被删除，甚至是导致错误的数据也不会被删除。  
  
### <a name="handle-messages-without-subscriptions"></a>处理没有订阅的消息  
 如果未定义接受消息的订阅，则 BizTalk Server 不接受在其 MessageBox 数据库中发布该消息。 订阅由业务流程或发送端口注册。 可以定义多个订阅，在这种情况下，会将消息发送至多个目标。 如果没有订阅，BizTalk Server 将会拒绝该消息，而不会尝试将其挂起。 如果适配器不处理此错误并显式挂起该消息，则该消息将被删除，消息数据可能会丢失。 当然，事务性适配器可以结束事务并将消息返回到消息的目标。  
  
### <a name="support-seek-with-your-receive-stream"></a>使接收流支持 Seek  
 接收端流必须支持**Seek**为 BizTalk Server 能够管道失败时挂起消息的方法。 如果消息流不可查找，则 BizTalk Server 将尝试运行时生成错误**Seek**。  
  
 在许多情况下支持**Seek**并不容易。 例如，在对网络数据进行流式处理时，要返回到网络资源并重新请求数据可能会很难。  
  
 随 BizTalk Server 一起提供的多个适配器会在 BizTalk Server 读取数据的同时，将消息数据假脱机保存到磁盘上的文件中。 这允许适配器以使用**Seek**上该文件，如果遇到错误 （在管道处理的消息数据，例如）。 在内部使用该适配器**ReadOnlySeekableStream**包装不可查找的传入流并达到可配置的大小阈值时溢出到磁盘。 小于该阈值大小的消息不会保存到磁盘。  
  
### <a name="consider-user-configurable-error-handling-options"></a>考虑使用用户可配置的错误处理选项  
 有时，在发生错误时并没有针对该错误的正确响应。 在这种情况下，应该考虑使用用户可配置的选项在行为之间进行选择。 MQSeries 适配器就是这样。  
  
 适配器发现错误时挂起消息这一行为之所以会出现问题，是因为 BizTalk Server 中的挂起队列有点像是一个“黑洞”。 相对而言，让消息进入队列很容易，但让消息再从队列中出来很难。  
  
 某些适配器用户可能不需要挂起队列中的任何内容。 例如，在使用 MQSeries 适配器的情况下，用户可以使用为其提供的配置选项进行以下操作之一：  
  
-   将适配器设置为发现错误时结束当前事务并禁用该其自身。  
  
-   挂起失败消息并提交事务。 即使 BizTalk Server 已成功挂起消息，适配器也会这样做。 尽管此操作会导致事件日志不完全正确，但可以满足客户的要求。  
  
### <a name="implement-receive-ordering-by-using-a-single-thread-and-waiting-on-batchcomplete"></a>通过使用单个线程和等待 BatchComplete 实现接收排序  
 BizTalk Server 接口的设计通过支持并发实现高性能和扩展能力。 但如果想要接收严格排序的消息（比如接收来自 QSeries 或 MSMQ 这样的消息队列产品的消息时就需要如此），则必须在适配器中进行额外操作以禁用某些并发功能。 此操作可以通过以下两步完成：  
  
1. 必须为适配器中的所有数据处理使用单个线程。  
  
2. 必须等待 BizTalk Server 彻底处理每个批。 这一要求很重要，可以通过使用 .NET 线程同步基元实现。 例如，使用**AutoResetEvent**，你将：  
  
   -   声明事件对象，并可通过这两个主工作线程访问并**BatchComplete**回调对象。  
  
   -   像往常一样，在主工作线程上提交到批的消息，但然后调用**AutoResetEvent.Reset**对事件对象对批调用之前**ibttransportbatch:: Done**。  
  
   -   调用**AutoResetEvent.WaitOne**事件对象从同一个线程上。 这会阻止主工作线程。 在中**BatchComplete**从 BizTalk Server 的回调，然后调用**AutoResetEvent.Set**上相同的事件对象，若要取消阻止工作线程，因此它已准备好处理另一条消息。  
  
   强烈建议，*接收排序*像这一点成为可配置，因为它会导致性能明显下降。 许多（即使不是大多数）用户方案不需要对消息进行排序。 挂起消息也会中断排序。 在这种情况下究竟应该如何操作取决于应用程序，因此适配器最好为用户提供一个配置点。  
  
   在排序方案中，一些客户表示更愿意停止这种处理（即禁用适配器），而不是中断排序。 支持排序接收的 MQSeries 适配器恰好可以为用户提供这一选项。  
  
## <a name="handle-send-specific-batch-errors"></a>处理特定于发送的批错误  
  
### <a name="handle-send-retry-and-batching"></a>处理发送重试和批处理  
 以下是发送端批处理的典型示例：  
  
- BizTalk Server 为适配器提供一批消息。  
  
- 如果适配器确定已将消息正确发送至目标，则会在 BizTalk Server 上执行向后删除，指示操作已完成。 （通常，可以任意选择数个删除消息组成批以提高性能。）  
  
  如果发送端适配器不能处理某个消息，则该适配器可以对该消息执行以下几种操作之一：  
  
- 适配器通知 BizTalk Server 想要重试某个消息。 BizTalk Server 不会自动重试消息。 BizTalk Server 会对重试次数进行计数，此计数可以在消息上下文中看到。  
  
- 适配器可以确定其无法处理某个消息。 在这种情况下，适配器可能会将消息移至下一个传输。 适配器执行此操作与**MoveToNextTransport**上调用**批处理**对象。  
  
- 适配器可将消息移至挂起队列。  
  
  适配器可以确定对消息采取的操作。 不过，建议让适配器保持一致的行为，这样可以更易于为 BizTalk Server 系统提供支持。  
  
  强烈建议适配器具有下述行为。 与 BizTalk Server 一起提供的适配器的行为如下。  
  
### <a name="recommended-behavior-for-handling-send-errors-in-a-batch"></a>处理批中发送错误的推荐行为  
 发送适配器接收某些消息，并将这些消息提交给 BizTalk Server。  
  
 对于每个成功的消息，适配器应在 BizTalk Server 上删除该消息。 通过批完成所有与 BizTalk Server 的通信，并且删除操作可以以批的形式进行。 这些批不一定是 BizTalk Server 在适配器上创建的批。 如果有任何响应消息（如在 SolicitResponse 方案中），则这些消息应当与相关联的删除一起提交回 BizTalk Server（使用 SubmitResponse）。  
  
- 如果适配器中的消息处理不成功，请检查重试计数。  
  
  -   如果没有超出重试计数，则将消息重新提交给 BizTalk Server，记住对消息设置重试次数。 消息上下文可提供适配器应当使用的重试计数和重试间隔。  
  
  -   如果已超过重试计数，则适配器应尝试使用移动消息**MoveToNextTransport**。 重新提交并**MoveToNextTransport**消息可以混合回 BizTalk Server 在同一批中删除项目。 这不是必需步骤，但很有用。  
  
- 重新提交并**MoveToNextTransport**方法可供适配器用于处理失败。 但在处理失败的过程中可能会发生失败。 在这种情况下，在处理来自 BizTalk Server 的响应 (在**BatchComplete**方法) 的适配器必须创建另一个批处理对 BizTalk 服务器，用于指示应如何处理该故障。  
  
   如果在处理一个失败的过程中发生另一个失败，请按以下步骤进行操作：  
  
  -   如果重新提交失败，则使用**MoveToNextTransport**。  
  
  -   如果**MoveToNextTransport**失败，使用**MoveToSuspendQ**。  
  
  在 BizTalk Server 上收到成功操作之前，必须一直在 BizTalk Server 上创建批。  
  
### <a name="serialization-of-message-context-property"></a>消息上下文属性的序列化  
 所有分配给消息上下文属性的对象必须可以序列化。 否则，消息引擎将引发类型的异常**E_NOINTERFACE**。 此返回值暗示正在尝试向某个非序列化对象分配消息上下文。