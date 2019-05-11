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
ms.openlocfilehash: 863ad82ce429bebb6bb5eb3ce671ca493830e8f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337538"
---
# <a name="how-to-handle-adapter-failures"></a>如何处理适配器故障
一般情况下，适配器应挂起无法处理的消息。 例如，遇到提交失败的接收适配器通常应挂起消息，尽管决策取决于适配器的用途。 此外，还有关于失败的处理的安全注意事项。 例如，如果适配器自动挂起所有失败的消息，适配器可能会受到拒绝服务攻击，导致 BizTalk Server 挂起队列向上填充。  某些适配器，如 HTTP、 可以返回到客户端，该值指示已拒绝该请求的失败代码。 对于这些类型的适配器通常最好返回失败代码而不挂起消息。 通常，发送适配器仅挂起消息后主要和次要传输已用尽所有的重试次数。  
  
## <a name="associate-error-processing-with-an-individual-operation-and-not-with-the-batch-that-contains-the-operation"></a>将错误处理与单个操作，而不包含该操作的批处理相关联  
 批处理中适配器的消息应为适配器的用户看不到。 这意味着在批处理中的某一操作失败不应影响任何方式中的任何其他操作。 但是，由于批是原子，因此一个消息的失败会导致错误的批处理，并会处理任何操作。  
  
 您编写的代码，它负责处理错误、 重新提交成功的消息，并挂起不成功的。 幸运的是，BizTalk Server 提供了一个详细的错误结构，使适配器能够确定具体的失败的操作。 它允许构造进一步的批，在其中重新提交成功的操作，不成功的挂起。  
  
 该操作的最终状态不应受适配器内批处理。  
  
## <a name="use-seterrorinfo-to-report-failure-to-biztalk-server"></a>使用 SetErrorInfo 向 BizTalk Server 报告失败  
 如果要挂起一条消息，必须从以前的消息上下文向 BizTalk Server 提供失败信息。 BizTalk Server 提供的错误报告使用的功能**SetErrorInfo**方法同时**IBaseMessage**并**ITransportProxy**接口。 您可以报告错误，如下所示：  
  
- 异常使用时处理消息时失败，则设置**SetErrorInfo (Exception e)** 消息 (**IBaseMessage**) 被挂起。 这允许引擎保留该错误和消息以便以后诊断，并将其记录到事件日志，向管理员发出警报。  
  
- 如果错误是在初始化或内部簿记过程 （不在消息处理） 遇到应调用**SetErrorInfo (Exception e)** 上**ITransportProxy**指针传递给您在初始化过程中。 如果您的适配器基于 BaseAdapter 实现，应始终有权访问此指针。 否则，应确保其缓存。  
  
  报告与错误消息写入到事件日志中这些方法结果的错误。 该错误关联相关的消息，如果可以为此，至关重要。  
  
## <a name="handle-a-database-offline-condition"></a>处理数据库脱机的情况  
 如果其中一个 BizTalk Server 数据库处于脱机状态，BizTalk 服务将回收其自身。 消息引擎会尽量在回收服务之前关闭所有接收位置。 如果花费的时间超过 60 秒，则服务将中断。 因为引擎会执行事务处理，这不会导致数据丢失。  
  
 通过使用键，可以在注册表中优化此超时：  
  
```  
DWORD   
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingDBFailoverShutdownTimeLimit  
```  
  
 对于独立适配器，因为 BizTalk Server 不拥有该过程中，接收位置将停用一个 BizTalk Server 数据库处于脱机状态。 数据库恢复联机后这些接收位置会重新启用。  
  
## <a name="write-to-the-event-log"></a>写入事件日志  
 适配器可以通过使用写入事件日志条目**IBTTransportProxy**接口传入异常。 用本机代码开发的适配器需要传入**IErrorInfo**接口， **IBTTransportProxy.SetErrorInfo (异常** `e` **)**。  
  
 消息引擎向事件日志写入代表事件适配器等消息传输失败后的适配器重试将一条消息移至其备份传输或挂起消息。 类似这样的操作，适配器只需要调用 API 之前对消息设置异常。 下面的代码段演示了这一点：  
  
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
 适配器向 BizTalk Server 提交操作 （或一批操作） 时可以有多种原因导致失败。 两项最重要的是：  
  
- 接收管道失败。  
  
- 发布消息时发生路由失败。  
  
  消息引擎会自动尝试挂起消息时获取接收管道故障。 挂起操作可能始终无法成功。 例如，如果消息引擎发布消息时遭遇路由失败，然后该引擎不会不甚至尝试挂起消息。  
  
  始终是可能一条消息将失败。 在这种情况下，适配器应显式调用**MoveToSuspendQ** API，应尝试挂起消息。 当适配器尝试挂起消息时，应是以下之一：  
  
- 应暂停的同一个消息对象适配器提交 （推荐）。  
  
- 如果适配器必须创建新的消息，然后它应设置指针的新消息的消息上下文为最初提交的消息的消息上下文。 这是因为一条消息的消息上下文有很多有关该消息和失败的有价值信息。 若要调试失败的消息，需要使用此信息。  
  
> [!NOTE]
>  如果适配器创建新消息对象，并将它挂起，适配器应指向新的消息对象从旧消息对象复制的错误信息。  
  
 某些适配器，如与 BizTalk Server 一起提供的 HTTP 适配器不需要该消息被挂起。 这些适配器可以返回给其客户端返回错误。  
  
#### <a name="causes-of-failure"></a>失败的原因  
 失败的简单原因是构造批或时可能发生的错误**ibttransportbatch:: Done**调用。  
  
-   **提交失败。** **提交**调用有限数量的原因，可能会失败，所有这些都是致命。 由于这些原因包括：  
  
-   在 BizTalk Server 进程空间中发生的内存不足错误。  
  
-   已从部署删除了架构程序集。 在这种情况下，**提交**含义模糊的错误而失败。 在 MQSeries 适配器中，捕获从 BizTalk Server 的一般失败异常，并在系统事件日志中写入扩展的错误消息。 此消息表明错误的可能的原因之一是，以某种方式从部署删除了架构程序集时。  
  
     在常规，如果**提交**应尝试挂起消息使用相同的事务将失败。  
  
-   **Ibttransportbatch:: Done 失败。** **Ibttransportbatch:: Done**调用可能会由于多种原因之一失败。 一般情况下，您始终应尝试挂起操作，然后结束事务，仅当该操作失败。 可能会收到从故障中的错误代码之一**ibttransportbatch:: Done**是 BizTalk Server 正在尝试关闭的情况下。 在这种情况下，应只是结束事务，并将它，因为**Terminate**调用可能正在并发发生。 成功构造了批并成功执行时，会出现其他情况**ibttransportbatch:: Done**。 在这些情况下，在返回的错误**BatchComplete** ，适配器必须确定要执行的操作与之和。 本部分的其余部分处理这种情况。  
  
#### <a name="processing-batchcomplete-errors"></a>处理 BatchComplete 错误  
 **BatchComplete**是由适配器调用的 BizTalk 服务器，用于指示批处理操作的完成状态时提供的回调。  
  
 最重要的参数传递给**BatchComplete**是批状态`hResult`。 这指示成功或失败的批处理。 如果批失败，则表示没有任何批处理中的操作已成功。 该适配器将遍历批状态结构，并确定失败的消息 (我们称之为*批的筛选*)。  
  
#### <a name="nontransactional-batchcomplete-errors"></a>非事务性 BatchComplete 错误  
 对于非事务性适配器，您必须选择您的响应为在失败时**SubmitMessage**/**SubmitRequestMessage**或**SubmitResponseMessage**操作。 适配器通过调用挂起消息的通常**MoveToSuspendQ**。  
  
 传递时，始终需要执行以下操作：**DeleteMessage**， **MoveToSuspendQ**， **ResubmitMessage**。 如果这些操作失败，则通常意味着在适配器中是有 bug。 不需要编写代码来处理在这些情况下失败。 但是如果批失败，因为另一个操作失败，则这些操作必须在新批中重新执行。  
  
 如果适配器调用**MovetoBackupTransport**并失败 （由于没有备份传输），然后应调用该适配器**MoveToSuspendQ**以挂起消息。  
  
#### <a name="transactional-batchcomplete-errors"></a>事务性 BatchComplete 错误  
 当您提交到 BizTalk Server 使用适配器创建的事务的批处理时，应遵循这两种方案之一：  
  
-   **使用单消息批。** 向 BizTalk Server 发送单消息批。 如果这条消息失败，然后，可以合法发送 BizTalk Server 在同一个事务，第二个批处理，但必须将有问题的消息移动到挂起队列，而无需重新提交它。 删除失败的消息后，第二个批的提交应该会成功。 发生这种情况时 BizTalk Server 确认可以提交事务后第二个批已成功完成。 如果第二个批失败，适配器必须中止该事务，或查找其他位置以存放该消息。 在此方案中，可能会立即严重的性能问题由于事务回滚处理。  
  
     有一些技巧，可用于提高适配器的性能。 例如，MQSeries 适配器动态调整其方法在运行时。 使用 100 个消息批运行它。 如果它遇到错误时，它必须结束该批，但它可以将其切换到单消息批，在短时间以错误的消息。 然后还原为 100 个消息批。 如果再次遇到错误，会再次降低。  
  
-   **使用抢先挂起功能。** 构造一个在其中抢先挂起错误消息的多消息批次。 批处理包含多种**提交**并**MoveToSuspendQ**操作，并为第一个和仅在事务下的批处理。 它应成功，因为抢先挂起错误数据，并可以 （在等待从 BizTalk Server 接收确认） 之后提交事务。  
  
     这看起来好象需要了解以后的但已在 MSMQ 适配器使用此方法。 它依赖于具有唯一的消息 Id。 适配器会构造一批消息。 如果出现任何错误，它将回滚该事务 （并因此批处理），但会记住临时数据结构中的消息 ID。 （若要防止此结构无限增长，在其中的项后被删除一些固定的时间延迟。）每个批次提交之前，适配器检查错误消息 Id 的列表。 如果它发现一个，它知道该消息将失败 （因为它未在过去一次），并会抢先挂起它而不是尝试将其提交。  
  
     不是每个适配器都有唯一的消息 ID，并不大可能具有一个事务性存储。 因此，很多事务性适配器被限制为发送单消息批。  
  
#### <a name="processing-other-errors"></a>处理其他错误  
 在所有其他情况下 （如挂起消息失败），适配器必须结束事务。 任何其他结果重复或已删除的消息中。  
  
 适配器可以只要它应中止事务，如果某一批失败。 但是，在其中适配器无法中止事务的方案。 在这种情况下它应挂起使用同一个事务的消息。  
  
#### <a name="processing-errors-on-transactional-receive"></a>处理事务性接收错误  
 常见的事务处理模式是发生错误时结束事务。 在这种情况下的所有内容返回到其以前的状态，不会丢失数据。 但是，如果您正在使用事务性源 （例如，从临时表在数据库中，一次请求一行或从 MQSeries 或 MSMQ 这样的队列产品一次提取一条消息） 中的数据，则这可能不是足够。 如果只是结束事务并返回并获得相同的数据同样，相同的错误可能发生的并且系统会进入重复的循环。  
  
 SQL 适配器的 BizTalk Server 的早期版本中附带了此行为。 但是，发行后不久，适配器的行为已更改尝试挂起失败的消息并提交事务。 将一条消息移到同一事务下的挂起队列，然后提交事务保存中丢失的数据，还允许适配器以绕过错误数据。  
  
 当适配器的接收部分传递一条错误消息，以响应**提交**消息操作，适配器应处理该错误并将消息移至挂起队列。  
  
 在事务性批处理中的适配器已创建的事务对象，并且事务下提交了消息的情况下，适配器应以逻辑方式将消息移到同一事务下的挂起队列发生故障时。 事务可确保未删除数据，并将导致错误甚至数据应不会被删除。  
  
### <a name="handle-messages-without-subscriptions"></a>处理没有订阅的消息  
 BizTalk Server 不接受一条消息，如果不存在定义为接受它的订阅在其 MessageBox 数据库中发布。 订阅注册由业务流程或发送端口。 可以定义多个订阅，在这种情况下将消息发送到多个目标。 如果没有任何订阅，BizTalk Server 会拒绝该消息并不会尝试暂停它。 如果适配器没有处理此错误，并显式挂起该消息，然后删除该消息，其数据可能会丢失。 当然事务性适配器可能结束事务并返回到其目标的消息。  
  
### <a name="support-seek-with-your-receive-stream"></a>支持 Seek 接收 Stream  
 接收端流必须支持**Seek**为 BizTalk Server 能够管道失败时挂起消息的方法。 如果消息流不可查找，则 BizTalk Server 将尝试运行时生成错误**Seek**。  
  
 在许多情况下支持**Seek**并不容易。 当流式处理网络中的数据，例如，可能会难以返回到的网络资源并重新请求数据。  
  
 随 BizTalk Server 的多个适配器假脱机到磁盘上的文件上的消息数据保存在同一时间，BizTalk Server 读取数据。 这允许适配器以使用**Seek**上该文件，如果遇到错误 （在管道处理的消息数据，例如）。 在内部使用该适配器**ReadOnlySeekableStream**包装不可查找的传入流并达到可配置的大小阈值时溢出到磁盘。 对于小于阈值大小的消息，不会保存该磁盘。  
  
### <a name="consider-user-configurable-error-handling-options"></a>请考虑使用用户可配置的错误处理选项  
 有时是未正确响应到错误。 在这种情况下，应考虑行为之间进行选择的用户可配置选项。 MQSeries 适配器执行此操作。  
  
 适配器发现错误时挂起消息的问题是 BizTalk Server 中的挂起队列是类似"黑洞。 它是相对较容易获取消息队列中，但更难以再次推出。  
  
 适配器的某些用户可能不希望在挂起队列中的任何内容。 例如，在 MQSeries 适配器的情况下为用户提供的配置选项执行以下任一操作：  
  
-   设置适配器以结束当前事务并禁用其自身时发现错误。  
  
-   挂起失败的消息并提交该事务。 即使在 BizTalk Server 已成功挂起消息时适配器就是这样。 此操作满足客户的要求，即使它会导致事件日志不是完全正确。  
  
### <a name="implement-receive-ordering-by-using-a-single-thread-and-waiting-on-batchcomplete"></a>实现接收排序使用单个线程和等待 BatchComplete  
 BizTalk Server 的界面专为性能和横向扩展通过支持并发的功能。 但是，如果你想要接收严格排序的消息 （因为有时需要从 MQSeries 或 MSMQ 这样的消息队列产品中接收消息时），然后必须执行额外操作以禁用某些并发的适配器。 这可以在两个步骤：  
  
1. 有关在适配器中的所有数据处理，必须使用单个线程。  
  
2. 你必须等待 BizTalk Server 彻底处理每个批。 此要求很重要，可以通过使用.NET 线程同步基元实现。 例如，使用**AutoResetEvent**，你将：  
  
   -   声明事件对象，并可通过这两个主工作线程访问并**BatchComplete**回调对象。  
  
   -   像往常一样，在主工作线程上提交到批的消息，但然后调用**AutoResetEvent.Reset**对事件对象对批调用之前**ibttransportbatch:: Done**。  
  
   -   调用**AutoResetEvent.WaitOne**事件对象从同一个线程上。 这会阻止主工作线程。 在中**BatchComplete**从 BizTalk Server 的回调，然后调用**AutoResetEvent.Set**上相同的事件对象，若要取消阻止工作线程，因此它已准备好处理另一条消息。  
  
   强烈建议，*接收排序*像这一点成为可配置，因为它会导致性能明显下降。 很多，如果不是大多数用户方案不需要消息的顺序。 挂起消息也会中断排序。 究竟应该如何操作在这种情况下是依赖于应用程序的因此您的适配器来执行操作的最佳操作是将为用户提供一个配置点。  
  
   在排序方案中，一些客户表示更，他们希望停止处理，即禁用适配器，而不会中断排序。 MQSeries 适配器，支持排序接收，向用户提供此选项。  
  
## <a name="handle-send-specific-batch-errors"></a>处理特定于发送的批错误  
  
### <a name="handle-send-retry-and-batching"></a>处理发送重试和批处理  
 下面是发送端批处理的典型示例：  
  
- BizTalk Server 向适配器提供了一批消息。  
  
- 如果适配器确定，这已提供消息到其目标正确，它将执行在完成重新打开 BizTalk Server，该值指示删除。 （像往常一样，数个删除消息可以是任意组成批以提高性能。）  
  
  如果发送端适配器无法处理一条消息，则它可能会执行对该消息的多个操作之一：  
  
- 适配器通知 BizTalk Server 想要重试某个消息。 BizTalk Server 不会自动重试一条消息。 BizTalk Server 保留计数的重试次数，并可以在消息上下文中看到此计数。  
  
- 适配器可以确定它无法处理的消息。 在这种情况下，适配器可能会将消息移到下一个传输。 适配器执行此操作与**MoveToNextTransport**上调用**批处理**对象。  
  
- 适配器可能会将消息移至挂起队列。  
  
  适配器可以确定该消息会发生什么情况。 但是，建议让适配器行为以一致的方式，因为这样可以更轻松地支持 BizTalk Server 安装。  
  
  强烈建议适配器具有下述行为。 与 BizTalk Server 一起提供的适配器的行为如下。  
  
### <a name="recommended-behavior-for-handling-send-errors-in-a-batch"></a>处理一批中的发送错误的推荐行为  
 发送适配器接收某些消息，并将其提交给 BizTalk Server。  
  
 为每个成功的消息，适配器应删除该消息在 BizTalk Server 上。 返回到 BizTalk Server 的所有通信均都通过批处理，并可以组成批删除。 它们无需将在适配器创建 BizTalk Server 在同一个批处理。 如果有任何响应消息 （如在 SolicitResponse 方案），则他们应已提交回 BizTalk Server （使用 SubmitResponse) 以及相关删除。  
  
- 如果适配器中的消息处理不成功，请检查重试计数。  
  
  -   如果未超过重试计数，重新提交到 BizTalk Server，记住对消息设置重试时间的消息。 消息上下文提供的重试计数和适配器应使用的重试间隔。  
  
  -   如果已超过重试计数，则适配器应尝试使用移动消息**MoveToNextTransport**。 重新提交并**MoveToNextTransport**消息可以混合回 BizTalk Server 在同一批中删除项目。 这不是必需的但可能是一个有用的步骤。  
  
- 重新提交并**MoveToNextTransport**方法可供适配器用于处理失败。 但是，在处理过程中失败的故障。 在这种情况下，在处理来自 BizTalk Server 的响应 (在**BatchComplete**方法) 的适配器必须创建另一个批处理对 BizTalk 服务器，用于指示应如何处理该故障。  
  
   处理的另一错误处理过程中发生的故障时，请执行以下步骤：  
  
  -   如果重新提交失败，则使用**MoveToNextTransport**。  
  
  -   如果**MoveToNextTransport**失败，使用**MoveToSuspendQ**。  
  
  您必须保留批处理上创建 BizTalk Server 之前收到成功操作在 BizTalk Server 上。  
  
### <a name="serialization-of-message-context-property"></a>序列化的消息上下文属性  
 分配给消息上下文属性的所有对象必须都可序列化。 否则，消息引擎将引发类型的异常**E_NOINTERFACE**。 此返回值暗示正在尝试分配消息上下文的非可序列化对象。