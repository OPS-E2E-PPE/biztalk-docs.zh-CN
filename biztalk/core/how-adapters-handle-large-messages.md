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
ms.openlocfilehash: 7a0d4260274354ce68992ddf30e07dcc74991b8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987342"
---
# <a name="how-adapters-handle-large-messages"></a>适配器如何处理大消息
BizTalk 消息引擎可以处理非常大的消息，对消息的最大大小没有限制。 但是，您应该考虑限制消息的大小，以便优化性能和资源管理。 随着消息的增大，每秒处理的消息数将相应减少。 当设计使用方案和计划容量时，请考虑 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将处理的消息的平均大小、类型和数量。  
  
## <a name="stream-based-processing"></a>基于流的处理  
 在开发适配器时，一定要时刻牢记需要处理大消息。 不管数据流有多大都将其整个加载到内存中，这种做法极不可取，因为这可能导致 BizTalk Server 进程中止。 取决于引擎在任意给定时间所处理的消息的大小和数量，虚拟内存过低可能会出现问题。 因此，应该以流的形式处理消息，如下所述：  
  
- **入站消息。** 对于入站消息，接收适配器将网络流附加到 BizTalk 消息，而将流的“提取”留给 BizTalk 消息引擎完成。  
  
- **出站消息。** 对于出站消息，适配器负责提取流。 这可有效地从 MessageBox 数据库提取流并使其通过发送管道。 适配器应该以流的形式通过网络发送数据。  
  
  下图显示消息引擎接收端的基于流的消息处理过程。  
  
  ![](../core/media/streambasedprocessing.gif "Streambasedprocessing")  
  
  当适配器向引擎提交消息时，会将其数据流附加到 BizTalk 消息。 对于某些适配器，这意味着实现网络流。 消息提交后，引擎执行接收管道。 在管道执行期间，要更改数据的管道组件将克隆该消息，同时连接新消息流和上一个消息流。 管道执行完毕后，消息引擎从管道中取出消息，然后运行一个循环程序，读取该消息上的流。 此读取流的操作调用对先前流的读取操作，后者又调用对更靠前流的读取操作，如此类推，直到调用网络流的读取操作。 引擎定期刷新 MessageBox 的数据，以维护平面内存模型。  
  
  **故障排除提示：** 在发送端，适配器负责读取流。 如果发送适配器要读取发送管道中任何升级或写入的消息上下文属性，则要等到整个流都读取以后，才可以写入这些属性。 仅当完全读取该流以后，适配器才能确定所有管道组件都已经执行完毕。  
  
## <a name="locating-a-specific-byte-in-the-stream"></a>在流中定位特定字节  
 在几种情况下适配器可能需要将流返回到开始处，以便处理需要挂起的失败的消息。 例如，一种 HTTP 适配器就属于这种情况，这种适配器接收使用 Chunked 编码以“要求响应对”形式提交响应消息的数据。  
  
 但是，在大多数情况下，可能无法跟踪数据流。 例如，接收使用 Chunked 编码的数据的 HTTP 适配器。 如果数据流的设计要便于您找到失败了的消息，适配器就需要在读取数据的同时将其缓存在内存中或磁盘上。 显然，这不是最佳方案，而且需要额外资源。 而且，许多“即开即用”管道组件以只进流的方式工作。 对于这种情况在 SDK 中的 BaseAdapter 使用名为的帮助器类**为 VirtualStream**。 包含此功能的文件名为 VirtualStream.cs。  
  
> [!NOTE]
>  VirtualStream.cs 文件位于以下两个位置管道 SDK 示例 —: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。  
  
 虚拟流的设计思想是，首先将流中的数据缓存到内存流中，直到数据量达到一个阈值，超过此阈值后，数据将溢出到磁盘上的一个安全位置。 流关闭后，该磁盘文件将被自动删除。 只进流都可以设计为这种方式。