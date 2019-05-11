---
title: 处理管道组件中的传入数据流 |Microsoft Docs
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
ms.openlocfilehash: 691e0e28b8c3ab6cea273979a69d2eeba0135aa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344667"
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a><span data-ttu-id="0732f-102">处理管道组件中的传入数据流</span><span class="sxs-lookup"><span data-stu-id="0732f-102">Handling Incoming Data Streams in Pipeline Components</span></span>
<span data-ttu-id="0732f-103">编写自定义拆装器管道组件中的代码时应考虑以下注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0732f-103">The following considerations should be made when writing custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a><span data-ttu-id="0732f-104">不要关闭自定义拆装器代码中的传入数据流</span><span class="sxs-lookup"><span data-stu-id="0732f-104">Do not close the incoming data stream in custom dissasember code</span></span>  
 <span data-ttu-id="0732f-105">当你编写自定义拆装器管道组件中的代码[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确保在不关闭传入数据流中的拆装器代码。</span><span class="sxs-lookup"><span data-stu-id="0732f-105">When you write custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ensure that you do not close the incoming data stream in the disassembler code.</span></span> <span data-ttu-id="0732f-106">从输入消息的传入流是共享的资源。</span><span class="sxs-lookup"><span data-stu-id="0732f-106">The incoming stream from the input message is a shared resource.</span></span> <span data-ttu-id="0732f-107">消息正文跟踪组件中的也使用传入流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。</span><span class="sxs-lookup"><span data-stu-id="0732f-107">The incoming stream is also used by the message body tracking component in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message engine.</span></span>  
  
 <span data-ttu-id="0732f-108">如果隐式或显式关闭传入流，跟踪数据可能会丢失，你将不能检查消息事件和服务实例跟踪中的使用的流数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0732f-108">If you either implicitly or explicitly close the incoming stream, tracking data may be lost and you will be unable to examine the stream data using message event and service instance tracking in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a><span data-ttu-id="0732f-109">Stream 类的 Seek 方法用于将数据流指针设置为在流开头</span><span class="sxs-lookup"><span data-stu-id="0732f-109">Use the Seek method of the Stream class to set the data stream pointer to the start of the stream</span></span>  
 <span data-ttu-id="0732f-110">确保直到到达流的末尾读取传入数据流。</span><span class="sxs-lookup"><span data-stu-id="0732f-110">Ensure that you read from the incoming data stream until the end of the stream is reached.</span></span> <span data-ttu-id="0732f-111">例如，如果自定义代码做出 300 kb 数据的读取的请求和代码仅收到 34 KB 的数据，不要假定已到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="0732f-111">For example, if custom code makes a read request for 300 KB of data and the code only receives 34 KB of data, do not assume that the end of the stream has been reached.</span></span> <span data-ttu-id="0732f-112">直到返回 0 字节的自定义代码应始终从传入流中读取。</span><span class="sxs-lookup"><span data-stu-id="0732f-112">The custom code should always read from the incoming stream until 0 bytes is returned.</span></span>  
  
 <span data-ttu-id="0732f-113">自定义组件中返回数据流前逻辑，将数据流指针设置回流的开始。</span><span class="sxs-lookup"><span data-stu-id="0732f-113">Before returning the data stream in the custom component logic, set the data stream pointer back to the start of the stream.</span></span> <span data-ttu-id="0732f-114">例如，以下代码说明了使用 seek 方法指向流的开头之前返回流的逻辑：</span><span class="sxs-lookup"><span data-stu-id="0732f-114">For example, this code illustrates logic to use the seek method to point to the beginning of the stream before returning the stream:</span></span>  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 <span data-ttu-id="0732f-115">如果您不这样做，到当前组件中端读取的流的下一个组件收到的将是一个空流，因为未数据流指针设置为在流开头。</span><span class="sxs-lookup"><span data-stu-id="0732f-115">If you do not do this and the stream is read to the end in the current component, the next component receives what appears to be an empty stream because the data stream pointer was not set to the start of the stream.</span></span> <span data-ttu-id="0732f-116">这会在随后的管道组件中导致意外的分析和验证错误。</span><span class="sxs-lookup"><span data-stu-id="0732f-116">This can cause unexpected parsing and validation errors in subsequent pipeline components.</span></span>