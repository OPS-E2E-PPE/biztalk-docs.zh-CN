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
ms.openlocfilehash: 00258b86f2da320b0ec13963a96a93aca8de477a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530927"
---
# <a name="developing-a-disassembling-pipeline-component"></a><span data-ttu-id="a0b9f-102">开发拆装管道组件</span><span class="sxs-lookup"><span data-stu-id="a0b9f-102">Developing a Disassembling Pipeline Component</span></span>
<span data-ttu-id="a0b9f-103">拆装管道组件接收输入一条消息，并生成输出的零个或多个消息。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-103">A disassembling pipeline component receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="a0b9f-104">拆装组件用于拆分成单个文档的消息交换。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-104">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="a0b9f-105">拆装器组件必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="a0b9f-105">Disassembler components must implement the following interfaces:</span></span>  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- <span data-ttu-id="a0b9f-106">**IPersistPropertyBag。**</span><span class="sxs-lookup"><span data-stu-id="a0b9f-106">**IPersistPropertyBag .**</span></span> <span data-ttu-id="a0b9f-107">请参阅此接口的.NET Framework SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-107">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
  <span data-ttu-id="a0b9f-108">你可以通过扩展来创建自己的拆装组件**FFDasmComp**或**XMLDasmComp**类。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-108">You can create your own disassembling component by extending the **FFDasmComp** or **XMLDasmComp** class.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a0b9f-109">如果自定义拆装器将设置 MessageDestination 上下文属性为 SuspendQueue，拆装器返回的流必须支持挂起 Seek(0) 工作。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-109">If your custom disassembler will be setting the MessageDestination context property to SuspendQueue, the stream returned by the disassembler must to support Seek(0) for the suspension to work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0b9f-110">自定义管道组件应从输入消息复制到输出消息任何其他部分。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-110">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="a0b9f-111">这会保留它们在管道中做进一步处理。</span><span class="sxs-lookup"><span data-stu-id="a0b9f-111">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0b9f-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="a0b9f-112">In This Section</span></span>  
  
-   [<span data-ttu-id="a0b9f-113">处理管道组件中的传入数据流</span><span class="sxs-lookup"><span data-stu-id="a0b9f-113">Handling Incoming Data Streams in Pipeline Components</span></span>](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [<span data-ttu-id="a0b9f-114">在反汇编程序管道组件中处理编码</span><span class="sxs-lookup"><span data-stu-id="a0b9f-114">Handling Encoding in a Disassembler Pipeline Component</span></span>](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a0b9f-115">扩展平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="a0b9f-115">Extending the Flat File Disassembler Pipeline Component</span></span>](../core/extending-the-flat-file-disassembler-pipeline-component.md)