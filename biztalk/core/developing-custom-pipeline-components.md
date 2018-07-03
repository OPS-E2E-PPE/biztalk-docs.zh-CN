---
title: 开发自定义管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom]
- pipeline components [custom], about pipeline components
- pipeline components [custom], creating
- customizing, pipeline components
- pipeline interfaces
- IDisassemblerComponent
- pipeline interfaces, about pipeline interfaces
- creating, pipeline components [custom]
- IAssemblerComponent
- IComponent
- pipeline components [custom], customizing
- pipeline interfaces, interface types
- pipeline components [custom], interfaces
- pipeline components [custom], component types
ms.assetid: cce61e0d-f1e3-4ec2-b38c-7c6eaf83ac10
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74828d31b55a4b50bdb18a537fbf7bb293445545
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008966"
---
# <a name="developing-custom-pipeline-components"></a><span data-ttu-id="b52d6-102">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="b52d6-102">Developing Custom Pipeline Components</span></span>
<span data-ttu-id="b52d6-103">本部分介绍如何开发管道组件。</span><span class="sxs-lookup"><span data-stu-id="b52d6-103">This section describes how to develop a pipeline component.</span></span> <span data-ttu-id="b52d6-104">您可以创建三种类型的管道组件：普通、组装和拆卸。</span><span class="sxs-lookup"><span data-stu-id="b52d6-104">You can create three types of pipeline components: general, assembling, and disassembling.</span></span> <span data-ttu-id="b52d6-105">这三种类型均可实现附加的探测功能。</span><span class="sxs-lookup"><span data-stu-id="b52d6-105">Each of the three types can additionally implement probing functionality.</span></span> <span data-ttu-id="b52d6-106">每种类型的管道组件具有关联的界面，必须为要插入到 BizTalk 消息引擎; 的组件实现区分组件类型的管道接口**IComponent**， **IAssemblerComponent**，并**IDisassemblerComponent**。</span><span class="sxs-lookup"><span data-stu-id="b52d6-106">Each type of pipeline component has an associated interface that must be implemented for the component to be plugged into the BizTalk Messaging Engine; the pipeline interfaces that distinguish the types of components are **IComponent**, **IAssemblerComponent**, and **IDisassemblerComponent**.</span></span> <span data-ttu-id="b52d6-107">探测组件，必须实现**IProbeMessage**接口。</span><span class="sxs-lookup"><span data-stu-id="b52d6-107">For probing components, you must implement the **IProbeMessage** interface.</span></span>  
  
 <span data-ttu-id="b52d6-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含一个示例管道组件，您在创建自己的组件时可以参考。</span><span class="sxs-lookup"><span data-stu-id="b52d6-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a sample pipeline component that you can reference when creating your own component.</span></span> <span data-ttu-id="b52d6-109">该示例组件演示如何将数据附加到消息的结尾以及如何将数据添加到消息的开头。</span><span class="sxs-lookup"><span data-stu-id="b52d6-109">The sample component demonstrates how to append data to the end of a message and add data at the beginning of the message.</span></span> <span data-ttu-id="b52d6-110">有关示例管道组件的详细信息，请参阅[CustomComponent （BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="b52d6-110">For more information about the sample pipeline component, see [CustomComponent (BizTalk Server Sample)](../core/customcomponent-biztalk-server-sample.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b52d6-111">如果引用的自定义管道组件的管道中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可能会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="b52d6-111">If you reference a custom pipeline component from a pipeline in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], a compile-time error may occur.</span></span> <span data-ttu-id="b52d6-112">若要更正该错误，请在编译前关闭管道设计器，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="b52d6-112">To correct the error, close Pipeline Designer and reopen it before compiling.</span></span> <span data-ttu-id="b52d6-113">也可以删除该组件，然后添加它。</span><span class="sxs-lookup"><span data-stu-id="b52d6-113">Alternatively, you can remove the component, and then add it.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="b52d6-114">升级到 BizTalk Server 时，请确保现有自定义管道组件中的任何字符串变量不包含任何 \n 之类的换行符。</span><span class="sxs-lookup"><span data-stu-id="b52d6-114">When upgrading to BizTalk Server, ensure that any string variables in your existing custom pipeline components do not contain any newline characters such as ‘\n’.</span></span> <span data-ttu-id="b52d6-115">否则，在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中编译此组件时将会发生“常数中有换行符”错误。</span><span class="sxs-lookup"><span data-stu-id="b52d6-115">Otherwise, a “newline in constant” error will occur when compiling this component in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b52d6-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="b52d6-116">In This Section</span></span>  
  
-   [<span data-ttu-id="b52d6-117">使用管道接口</span><span class="sxs-lookup"><span data-stu-id="b52d6-117">Using Pipeline Interfaces</span></span>](../core/using-pipeline-interfaces.md)  
  
-   [<span data-ttu-id="b52d6-118">开发常规管道组件</span><span class="sxs-lookup"><span data-stu-id="b52d6-118">Developing a General Pipeline Component</span></span>](../core/developing-a-general-pipeline-component.md)  
  
-   [<span data-ttu-id="b52d6-119">开发汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="b52d6-119">Developing an Assembling Pipeline Component</span></span>](../core/developing-an-assembling-pipeline-component.md)  
  
-   [<span data-ttu-id="b52d6-120">开发拆装管道组件</span><span class="sxs-lookup"><span data-stu-id="b52d6-120">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [<span data-ttu-id="b52d6-121">开发探测管道组件</span><span class="sxs-lookup"><span data-stu-id="b52d6-121">Developing a Probing Pipeline Component</span></span>](../core/developing-a-probing-pipeline-component.md)  
  
-   [<span data-ttu-id="b52d6-122">在托管流管道组件中实现 Seek 方法</span><span class="sxs-lookup"><span data-stu-id="b52d6-122">Implementing a Seek Method in a Managed Streaming Pipeline Component</span></span>](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [<span data-ttu-id="b52d6-123">使用解析和序列化引擎</span><span class="sxs-lookup"><span data-stu-id="b52d6-123">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [<span data-ttu-id="b52d6-124">报告来自管道组件的错误</span><span class="sxs-lookup"><span data-stu-id="b52d6-124">Reporting Errors from Pipeline Components</span></span>](../core/reporting-errors-from-pipeline-components.md)  
  
-   [<span data-ttu-id="b52d6-125">部署管道组件</span><span class="sxs-lookup"><span data-stu-id="b52d6-125">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)  
  
-   [<span data-ttu-id="b52d6-126">调试自定义管道</span><span class="sxs-lookup"><span data-stu-id="b52d6-126">Debugging Custom Pipelines</span></span>](../core/debugging-custom-pipelines.md)