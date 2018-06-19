---
title: 业务流程开发中的步骤 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- designing, orchestrations
- orchestrations, designing
- orchestrations, creating
- creating, orchestrations
- Copy Local property
ms.assetid: 556b1e6c-63a6-4805-a0a5-e555f198fe4e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd0a19754871a6e736365e622513b193dcbf06a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277389"
---
# <a name="steps-in-orchestration-development"></a><span data-ttu-id="ec90c-102">业务流程开发中的步骤</span><span class="sxs-lookup"><span data-stu-id="ec90c-102">Steps in Orchestration Development</span></span>
<span data-ttu-id="ec90c-103">若要开发一个业务流程，您通常执行以下基本操作：</span><span class="sxs-lookup"><span data-stu-id="ec90c-103">To develop an orchestration, you typically perform the following basic actions:</span></span>  
  
-   <span data-ttu-id="ec90c-104">添加形状以表示您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec90c-104">Add shapes to represent your business processes.</span></span>  
  
     <span data-ttu-id="ec90c-105">业务流程设计器为你提供可以用来表示不同的操作或其他抽象的形状的工具箱。</span><span class="sxs-lookup"><span data-stu-id="ec90c-105">Orchestration Designer provides you with a toolbox of shapes that can be used to represent different actions or other abstractions.</span></span> <span data-ttu-id="ec90c-106">有关详细信息，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-106">For more information, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
-   <span data-ttu-id="ec90c-107">定义架构来描述消息的格式。</span><span class="sxs-lookup"><span data-stu-id="ec90c-107">Define schemas to describe the format of your messages.</span></span>  
  
     <span data-ttu-id="ec90c-108">你可以定义架构使用 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="ec90c-108">You can define schemas with BizTalk Editor.</span></span> <span data-ttu-id="ec90c-109">有关详细信息，请参阅[如何创建 XML 消息的架构](../core/how-to-create-schemas-for-xml-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-109">For more information, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span>  
  
-   <span data-ttu-id="ec90c-110">定义的端口通过其发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="ec90c-110">Define ports through which messages are sent and received.</span></span>  
  
     <span data-ttu-id="ec90c-111">你可以定义端口，以指定如何以及在何处发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="ec90c-111">You can define ports to specify how and where messages are sent and received.</span></span> <span data-ttu-id="ec90c-112">有关详细信息，请参阅[在业务流程中使用端口](../core/using-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
-   <span data-ttu-id="ec90c-113">将绑定**发送**和**接收**形状链接到端口。</span><span class="sxs-lookup"><span data-stu-id="ec90c-113">Bind **Send** and **Receive** shapes to ports.</span></span>  
  
     <span data-ttu-id="ec90c-114">你可以连接你**发送**和**接收**形状到端口，并指定它们使用的端口操作。</span><span class="sxs-lookup"><span data-stu-id="ec90c-114">You can connect your **Send** and **Receive** shapes to ports and specify the port operations that they use.</span></span> <span data-ttu-id="ec90c-115">有关详细信息，请参阅[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-115">For more information, see [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span> <span data-ttu-id="ec90c-116">另请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-116">Also see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
-   <span data-ttu-id="ec90c-117">分配或转换消息之间的数据。</span><span class="sxs-lookup"><span data-stu-id="ec90c-117">Assign or transform data between messages.</span></span>  
  
     <span data-ttu-id="ec90c-118">你可以使用**构造消息**调整赋值消息或执行消息转换。</span><span class="sxs-lookup"><span data-stu-id="ec90c-118">You can use the **Construct Message** shape to assign message values or do message transformations.</span></span> <span data-ttu-id="ec90c-119">有关详细信息，请参阅[构造消息](../core/constructing-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-119">For more information, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
-   <span data-ttu-id="ec90c-120">标识你可能想要将添加为引用中运行您的业务流程或编写任何自定义组件。</span><span class="sxs-lookup"><span data-stu-id="ec90c-120">Identify any custom components that you might want to write or add as reference to work within your orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec90c-121">如果**Copy Local**引用程序集的属性设置为**True**，业务流程将无法以拾取之后的初始添加引用发生在对外部程序集所做任何更改BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ec90c-121">If the **Copy Local** property of the referenced assembly is set to **True**, Orchestration will not be able to pick up any changes made to the external assembly after the initial add reference takes place in BizTalk project.</span></span>  
  
-   <span data-ttu-id="ec90c-122">定义并将用于管理运行业务流程中的数据的业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="ec90c-122">Define and assign orchestration variables to manage data in your running orchestration.</span></span>  
  
     <span data-ttu-id="ec90c-123">你可以使用在业务流程视图窗口中变量文件夹声明你的业务流程变量和 BizTalk 表达式编辑器来编辑表达式分配并使用各种形状中的变量。</span><span class="sxs-lookup"><span data-stu-id="ec90c-123">You can use the Variables folder in the Orchestration View window to declare your orchestration variables, and BizTalk Expression Editor to edit expressions that assign and use the variables in various shapes.</span></span> <span data-ttu-id="ec90c-124">有关详细信息，请参阅[XLANG-s 数据类型](../core/xlang-s-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-124">For more information, see [XLANG-s Data Types](../core/xlang-s-data-types.md).</span></span>  
  
-   <span data-ttu-id="ec90c-125">生成您的业务流程，以出于完整性的考虑对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="ec90c-125">Build your orchestration to test it for completeness.</span></span>  
  
     <span data-ttu-id="ec90c-126">编译项目或包含它的解决方案时，你可以生成您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec90c-126">You build your orchestration when you compile the project or solution that contains it.</span></span> <span data-ttu-id="ec90c-127">有关详细信息，请参阅[如何构建业务流程](../core/how-to-build-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="ec90c-127">For more information, see [How to Build Orchestrations](../core/how-to-build-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec90c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec90c-128">See Also</span></span>  
 <span data-ttu-id="ec90c-129">[生成并运行业务流程](../core/building-and-running-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="ec90c-129">[Building and Running Orchestrations](../core/building-and-running-orchestrations.md) </span></span>  
 <span data-ttu-id="ec90c-130">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="ec90c-130">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="ec90c-131">创建使用业务流程设计器的业务流程</span><span class="sxs-lookup"><span data-stu-id="ec90c-131">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)