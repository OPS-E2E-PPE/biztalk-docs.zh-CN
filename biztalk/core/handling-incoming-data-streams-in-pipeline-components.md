---
title: 处理管道组件中的传入数据流 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fc34da3a5c8e65f81cd6bbbb699f52506cdc6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246565"
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a><span data-ttu-id="560aa-102">处理管道组件中的传入数据流</span><span class="sxs-lookup"><span data-stu-id="560aa-102">Handling Incoming Data Streams in Pipeline Components</span></span>
<span data-ttu-id="560aa-103">编写管道中的组件的自定义反汇编程序代码时，应进行以下注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="560aa-103">The following considerations should be made when writing custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a><span data-ttu-id="560aa-104">不要在自定义拆装器代码中关闭传入数据流</span><span class="sxs-lookup"><span data-stu-id="560aa-104">Do not close the incoming data stream in custom dissasember code</span></span>  
 <span data-ttu-id="560aa-105">当你编写自定义反汇编程序代码中的管道组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确保不要关闭反汇编程序代码中的对传入数据流。</span><span class="sxs-lookup"><span data-stu-id="560aa-105">When you write custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ensure that you do not close the incoming data stream in the disassembler code.</span></span> <span data-ttu-id="560aa-106">来自输入消息的传入流是共享资源。</span><span class="sxs-lookup"><span data-stu-id="560aa-106">The incoming stream from the input message is a shared resource.</span></span> <span data-ttu-id="560aa-107">跟踪中的组件消息正文也使用传入流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。</span><span class="sxs-lookup"><span data-stu-id="560aa-107">The incoming stream is also used by the message body tracking component in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message engine.</span></span>  
  
 <span data-ttu-id="560aa-108">如果隐式或显式关闭传入流，则跟踪数据可能会丢失，并且将无法使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的消息事件和服务实例跟踪检查流数据。</span><span class="sxs-lookup"><span data-stu-id="560aa-108">If you either implicitly or explicitly close the incoming stream, tracking data may be lost and you will be unable to examine the stream data using message event and service instance tracking in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a><span data-ttu-id="560aa-109">使用 Stream 类的 Seek 方法将数据流指针设置到流的开始位置</span><span class="sxs-lookup"><span data-stu-id="560aa-109">Use the Seek method of the Stream class to set the data stream pointer to the start of the stream</span></span>  
 <span data-ttu-id="560aa-110">确保读取传入数据流时达到流的末尾。</span><span class="sxs-lookup"><span data-stu-id="560aa-110">Ensure that you read from the incoming data stream until the end of the stream is reached.</span></span> <span data-ttu-id="560aa-111">例如，如果自定义代码做出 300 KB 数据的读取请求，并且代码仅收到 34 KB 数据，此时不要认为已达到流的末尾。</span><span class="sxs-lookup"><span data-stu-id="560aa-111">For example, if custom code makes a read request for 300 KB of data and the code only receives 34 KB of data, do not assume that the end of the stream has been reached.</span></span> <span data-ttu-id="560aa-112">自定义代码始终应该从传入流中进行读取，直到返回 0 字节。</span><span class="sxs-lookup"><span data-stu-id="560aa-112">The custom code should always read from the incoming stream until 0 bytes is returned.</span></span>  
  
 <span data-ttu-id="560aa-113">在自定义组件逻辑中返回数据流前，请将数据流指针设置回流的开始位置。</span><span class="sxs-lookup"><span data-stu-id="560aa-113">Before returning the data stream in the custom component logic, set the data stream pointer back to the start of the stream.</span></span> <span data-ttu-id="560aa-114">例如，下面的代码说明了在返回流前使用 Seek 方法指向流的开始位置的逻辑：</span><span class="sxs-lookup"><span data-stu-id="560aa-114">For example, this code illustrates logic to use the seek method to point to the beginning of the stream before returning the stream:</span></span>  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 <span data-ttu-id="560aa-115">如果不这样做，并在当前组件中读取到了流的末尾，由于未将数据流指针设置到流的开始位置，下一个组件收到的将是一个空流。</span><span class="sxs-lookup"><span data-stu-id="560aa-115">If you do not do this and the stream is read to the end in the current component, the next component receives what appears to be an empty stream because the data stream pointer was not set to the start of the stream.</span></span> <span data-ttu-id="560aa-116">这可能会在随后的管道组件中导致意外的解析错误和验证错误。</span><span class="sxs-lookup"><span data-stu-id="560aa-116">This can cause unexpected parsing and validation errors in subsequent pipeline components.</span></span>