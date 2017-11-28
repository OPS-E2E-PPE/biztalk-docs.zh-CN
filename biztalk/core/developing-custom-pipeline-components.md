---
title: "开发自定义管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723cd04a2a907fdb5d770975c27d47e1752d08ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-pipeline-components"></a><span data-ttu-id="91f77-102">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="91f77-102">Developing Custom Pipeline Components</span></span>
<span data-ttu-id="91f77-103">本部分介绍如何开发管道组件。</span><span class="sxs-lookup"><span data-stu-id="91f77-103">This section describes how to develop a pipeline component.</span></span> <span data-ttu-id="91f77-104">您可以创建三种类型的管道组件：普通、组装和拆卸。</span><span class="sxs-lookup"><span data-stu-id="91f77-104">You can create three types of pipeline components: general, assembling, and disassembling.</span></span> <span data-ttu-id="91f77-105">这三种类型均可实现附加的探测功能。</span><span class="sxs-lookup"><span data-stu-id="91f77-105">Each of the three types can additionally implement probing functionality.</span></span> <span data-ttu-id="91f77-106">每种类型的管道组件具有关联的界面，必须以插入到 BizTalk 消息传送引擎，则组件的实现区分类型的组件的管道接口为**IComponent**， **IAssemblerComponent**，和**IDisassemblerComponent**。</span><span class="sxs-lookup"><span data-stu-id="91f77-106">Each type of pipeline component has an associated interface that must be implemented for the component to be plugged into the BizTalk Messaging Engine; the pipeline interfaces that distinguish the types of components are **IComponent**, **IAssemblerComponent**, and **IDisassemblerComponent**.</span></span> <span data-ttu-id="91f77-107">用于探测组件，则必须实现**IProbeMessage**接口。</span><span class="sxs-lookup"><span data-stu-id="91f77-107">For probing components, you must implement the **IProbeMessage** interface.</span></span>  
  
 <span data-ttu-id="91f77-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含一个示例管道组件，您在创建自己的组件时可以参考。</span><span class="sxs-lookup"><span data-stu-id="91f77-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a sample pipeline component that you can reference when creating your own component.</span></span> <span data-ttu-id="91f77-109">该示例组件演示如何将数据附加到消息的结尾以及如何将数据添加到消息的开头。</span><span class="sxs-lookup"><span data-stu-id="91f77-109">The sample component demonstrates how to append data to the end of a message and add data at the beginning of the message.</span></span> <span data-ttu-id="91f77-110">有关示例管道组件的详细信息，请参阅[CustomComponent （BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="91f77-110">For more information about the sample pipeline component, see [CustomComponent (BizTalk Server Sample)](../core/customcomponent-biztalk-server-sample.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="91f77-111">如果你引用中的管道中的自定义管道组件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可能会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="91f77-111">If you reference a custom pipeline component from a pipeline in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], a compile-time error may occur.</span></span> <span data-ttu-id="91f77-112">若要更正该错误，请在编译前关闭管道设计器，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="91f77-112">To correct the error, close Pipeline Designer and reopen it before compiling.</span></span> <span data-ttu-id="91f77-113">也可以删除该组件，然后添加它。</span><span class="sxs-lookup"><span data-stu-id="91f77-113">Alternatively, you can remove the component, and then add it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91f77-114">在升级到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 时，请确保现有自定义管道组件中的任何字符串变量都不包含任何“\n”之类的换行符。</span><span class="sxs-lookup"><span data-stu-id="91f77-114">When upgrading to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], ensure that any string variables in your existing custom pipeline components do not contain any newline characters such as ‘\n’.</span></span> <span data-ttu-id="91f77-115">否则，在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中编译此组件时将会发生“常数中有换行符”错误。</span><span class="sxs-lookup"><span data-stu-id="91f77-115">Otherwise, a “newline in constant” error will occur when compiling this component in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91f77-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="91f77-116">In This Section</span></span>  
  
-   [<span data-ttu-id="91f77-117">使用管道接口</span><span class="sxs-lookup"><span data-stu-id="91f77-117">Using Pipeline Interfaces</span></span>](../core/using-pipeline-interfaces.md)  
  
-   [<span data-ttu-id="91f77-118">开发的常规管道组件</span><span class="sxs-lookup"><span data-stu-id="91f77-118">Developing a General Pipeline Component</span></span>](../core/developing-a-general-pipeline-component.md)  
  
-   [<span data-ttu-id="91f77-119">开发组装的管道组件</span><span class="sxs-lookup"><span data-stu-id="91f77-119">Developing an Assembling Pipeline Component</span></span>](../core/developing-an-assembling-pipeline-component.md)  
  
-   [<span data-ttu-id="91f77-120">开发分解的管道组件</span><span class="sxs-lookup"><span data-stu-id="91f77-120">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [<span data-ttu-id="91f77-121">开发探测的管道组件</span><span class="sxs-lookup"><span data-stu-id="91f77-121">Developing a Probing Pipeline Component</span></span>](../core/developing-a-probing-pipeline-component.md)  
  
-   [<span data-ttu-id="91f77-122">实现查找托管流式处理管道组件中的方法</span><span class="sxs-lookup"><span data-stu-id="91f77-122">Implementing a Seek Method in a Managed Streaming Pipeline Component</span></span>](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [<span data-ttu-id="91f77-123">使用了分析和序列化引擎</span><span class="sxs-lookup"><span data-stu-id="91f77-123">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [<span data-ttu-id="91f77-124">从管道组件的报告错误</span><span class="sxs-lookup"><span data-stu-id="91f77-124">Reporting Errors from Pipeline Components</span></span>](../core/reporting-errors-from-pipeline-components.md)  
  
-   [<span data-ttu-id="91f77-125">部署管道组件</span><span class="sxs-lookup"><span data-stu-id="91f77-125">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)  
  
-   [<span data-ttu-id="91f77-126">调试自定义管道</span><span class="sxs-lookup"><span data-stu-id="91f77-126">Debugging Custom Pipelines</span></span>](../core/debugging-custom-pipelines.md)