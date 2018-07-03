---
title: 开发拆装管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDisassemblerComponent interface, disassembling
- pipeline components [custom], IDisassemblerComponent
- pipeline components [custom], IBaseComponent
- IBaseComponent interface, disassembling
- pipeline components [custom], disassembling
ms.assetid: 77c0aa7d-4d1b-4a8f-bef8-d38e7e4045c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 843958cdfe00a9fc9d1a2c178cb85adfe4ffc8d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999718"
---
# <a name="developing-a-disassembling-pipeline-component"></a><span data-ttu-id="b1967-102">开发拆装管道组件</span><span class="sxs-lookup"><span data-stu-id="b1967-102">Developing a Disassembling Pipeline Component</span></span>
<span data-ttu-id="b1967-103">拆装管道组件在输入端接收单个消息，在输出端生成零个或多个消息。</span><span class="sxs-lookup"><span data-stu-id="b1967-103">A disassembling pipeline component receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="b1967-104">拆装组件用于将消息交换拆分成单个文档。</span><span class="sxs-lookup"><span data-stu-id="b1967-104">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="b1967-105">拆装器组件必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="b1967-105">Disassembler components must implement the following interfaces:</span></span>  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- <span data-ttu-id="b1967-106">**IPersistPropertyBag。**</span><span class="sxs-lookup"><span data-stu-id="b1967-106">**IPersistPropertyBag .**</span></span> <span data-ttu-id="b1967-107">有关此接口的信息，请参阅 .NET Framework SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="b1967-107">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
  <span data-ttu-id="b1967-108">你可以通过扩展来创建自己的拆装组件**FFDasmComp**或**XMLDasmComp**类。</span><span class="sxs-lookup"><span data-stu-id="b1967-108">You can create your own disassembling component by extending the **FFDasmComp** or **XMLDasmComp** class.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b1967-109">如果要将您的自定义拆装器的 MessageDestination 上下文属性设置为 SuspendQueue，则该拆装器返回的流必须支持 Seek(0) 才能实现挂起。</span><span class="sxs-lookup"><span data-stu-id="b1967-109">If your custom disassembler will be setting the MessageDestination context property to SuspendQueue, the stream returned by the disassembler must to support Seek(0) for the suspension to work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1967-110">自定义管道组件应将输入消息的所有附加部分复制到输出消息。</span><span class="sxs-lookup"><span data-stu-id="b1967-110">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="b1967-111">这样可以在管道中对它们作进一步处理。</span><span class="sxs-lookup"><span data-stu-id="b1967-111">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1967-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b1967-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b1967-113">处理管道组件中的传入数据流</span><span class="sxs-lookup"><span data-stu-id="b1967-113">Handling Incoming Data Streams in Pipeline Components</span></span>](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [<span data-ttu-id="b1967-114">在反汇编程序管道组件中处理编码</span><span class="sxs-lookup"><span data-stu-id="b1967-114">Handling Encoding in a Disassembler Pipeline Component</span></span>](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b1967-115">扩展平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="b1967-115">Extending the Flat File Disassembler Pipeline Component</span></span>](../core/extending-the-flat-file-disassembler-pipeline-component.md)