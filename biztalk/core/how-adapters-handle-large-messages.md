---
title: 适配器如何处理大消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c48671fd-b6cf-4507-92b4-35a4cd135714
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 131d757e1df910b33d92bbc7b02a576edad8efcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344249"
---
# <a name="how-adapters-handle-large-messages"></a>适配器如何处理大消息
BizTalk 消息引擎可以处理非常大的消息，并施加的一条消息的最大大小没有限制。 但是，应该考虑限制消息大小，以便获得最佳性能和资源管理。 随着消息大小的增加的每个第二个减少处理的消息数。 平均消息大小、 消息类型和正在处理的消息数，请考虑[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时设计使用方案和容量规划。  
  
## <a name="stream-based-processing"></a>基于 Stream 的处理  
 请务必在开发适配器时牢记处理大消息。 整个数据流加载到内存中而不考虑其大小是强烈建议不要使用，因为这可能会无法停止 BizTalk Server 进程。 根据大小和该引擎在任何给定时间处理的消息数，虚拟内存不足可能会成为问题。 相反，应处理消息以流的形式，如下所示：  
  
- **入站消息。** 入站消息的网络流附加到 BizTalk 消息离开"拉拽"的流到 BizTalk 消息引擎接收适配器。  
  
- **出站消息。** 对于出站消息，适配器负责提取流。 这有效地提取从 MessageBox 数据库的流，并通过发送管道。 适配器应通过网络传输流的形式发送数据。  
  
  下图显示了基于流的消息引擎在接收端处理。  
  
  ![](../core/media/streambasedprocessing.gif "Streambasedprocessing")  
  
  适配器提交到引擎的消息时它应将其数据流附加到 BizTalk 消息。 对于某些适配器，这意味着实现网络流。 当提交消息时，引擎执行接收管道。 在管道执行期间想要更改的数据的管道组件将克隆该消息，绑定到上一个消息流来自新的消息流。 管道执行完毕后，消息引擎将从管道中取出消息，并执行循环中读取该消息上的流。 此读取流的调用在上一个流，因此，在返回到网络流上反过来调用读取对先前流读取。 引擎定期刷新数据到 MessageBox，以维护平面内存模型。  
  
  **故障排除提示：** 在发送端适配器负责读取流。 如果发送适配器要读取的任何消息上下文属性升级或写入在发送管道中，读取整个流之前，可能不会写入这些属性。 仅当完全读取流时，适配器才能确保保证所有管道组件已完成执行。  
  
## <a name="locating-a-specific-byte-in-the-stream"></a>在 Stream 中定位特定字节  
 有一个适配器可能需要在其中找到流返回到开始处，以便处理需要挂起的失败的消息的方案。 此示例是 HTTP 适配器接收使用 chunked 编码来提交响应消息，要求-响应对中的数据。  
  
 但是，在许多情况下您可能无法跟踪数据流。 例如，考虑 HTTP 适配器接收使用 chunked 编码数据。 数据流的设计要便于您可以找到失败的消息，适配器将需要它读取时，在内存中或磁盘上缓存数据。 显然，这不是最佳且需要的其他资源。 此外，许多开箱管道组件进行操作以只进流的形式。 对于这种情况在 SDK 中的 BaseAdapter 使用名为的帮助器类**为 VirtualStream**。 包含此功能的文件命名为 VirtualStream.cs。  
  
> [!NOTE]
>  VirtualStream.cs 文件位于以下两个位置管道 SDK 示例 —: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。  
  
 虚拟流背后的理念是直到它达到的阈值，对其数据将溢出到磁盘上的安全位置，在流中的数据被缓存到内存流中。 流已关闭后会自动删除磁盘文件。 以这种方式，可以设计为只进流。