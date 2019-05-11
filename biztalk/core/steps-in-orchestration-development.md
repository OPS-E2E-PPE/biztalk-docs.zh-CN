---
title: 业务流程开发中的步骤 |Microsoft Docs
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
ms.openlocfilehash: 062cff21e067f9e7139c849cf0dd73af5eed1748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244170"
---
# <a name="steps-in-orchestration-development"></a><span data-ttu-id="75a86-102">业务流程开发中的步骤</span><span class="sxs-lookup"><span data-stu-id="75a86-102">Steps in Orchestration Development</span></span>
<span data-ttu-id="75a86-103">若要开发业务流程，通常执行以下基本操作：</span><span class="sxs-lookup"><span data-stu-id="75a86-103">To develop an orchestration, you typically perform the following basic actions:</span></span>  
  
-   <span data-ttu-id="75a86-104">添加形状以表示您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="75a86-104">Add shapes to represent your business processes.</span></span>  
  
     <span data-ttu-id="75a86-105">业务流程设计器为您提供了可用于表示不同的操作或其他抽象形状的工具箱。</span><span class="sxs-lookup"><span data-stu-id="75a86-105">Orchestration Designer provides you with a toolbox of shapes that can be used to represent different actions or other abstractions.</span></span> <span data-ttu-id="75a86-106">有关详细信息，请参阅[业务流程形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-106">For more information, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
-   <span data-ttu-id="75a86-107">定义架构来描述消息的格式。</span><span class="sxs-lookup"><span data-stu-id="75a86-107">Define schemas to describe the format of your messages.</span></span>  
  
     <span data-ttu-id="75a86-108">您可以定义架构使用 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="75a86-108">You can define schemas with BizTalk Editor.</span></span> <span data-ttu-id="75a86-109">有关详细信息，请参阅[如何创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-109">For more information, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span>  
  
-   <span data-ttu-id="75a86-110">定义发送和接收消息是通过该端口。</span><span class="sxs-lookup"><span data-stu-id="75a86-110">Define ports through which messages are sent and received.</span></span>  
  
     <span data-ttu-id="75a86-111">您可以定义端口，以指定如何以及在何处发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="75a86-111">You can define ports to specify how and where messages are sent and received.</span></span> <span data-ttu-id="75a86-112">有关详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
-   <span data-ttu-id="75a86-113">将绑定**发送**并**接收**到端口形状。</span><span class="sxs-lookup"><span data-stu-id="75a86-113">Bind **Send** and **Receive** shapes to ports.</span></span>  
  
     <span data-ttu-id="75a86-114">你可以连接您**发送**并**接收**到端口形状，并指定它们使用的端口操作。</span><span class="sxs-lookup"><span data-stu-id="75a86-114">You can connect your **Send** and **Receive** shapes to ports and specify the port operations that they use.</span></span> <span data-ttu-id="75a86-115">有关详细信息，请参阅[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-115">For more information, see [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span> <span data-ttu-id="75a86-116">另请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-116">Also see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
-   <span data-ttu-id="75a86-117">分配或转换消息之间的数据。</span><span class="sxs-lookup"><span data-stu-id="75a86-117">Assign or transform data between messages.</span></span>  
  
     <span data-ttu-id="75a86-118">可以使用**构造消息**形状来分配消息值或执行操作消息的转换。</span><span class="sxs-lookup"><span data-stu-id="75a86-118">You can use the **Construct Message** shape to assign message values or do message transformations.</span></span> <span data-ttu-id="75a86-119">有关详细信息，请参阅[构造消息](../core/constructing-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-119">For more information, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
-   <span data-ttu-id="75a86-120">确定你可能想要编写或将作为引用中运行您的业务流程添加任何自定义组件。</span><span class="sxs-lookup"><span data-stu-id="75a86-120">Identify any custom components that you might want to write or add as reference to work within your orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75a86-121">如果**Copy Local**引用程序集的属性设置为**True**，业务流程将无法再选取任何初始添加引用发生后对外部程序集所做的更改BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="75a86-121">If the **Copy Local** property of the referenced assembly is set to **True**, Orchestration will not be able to pick up any changes made to the external assembly after the initial add reference takes place in BizTalk project.</span></span>  
  
-   <span data-ttu-id="75a86-122">定义并将业务流程变量来管理在正在运行的业务流程中的数据。</span><span class="sxs-lookup"><span data-stu-id="75a86-122">Define and assign orchestration variables to manage data in your running orchestration.</span></span>  
  
     <span data-ttu-id="75a86-123">可以使用在业务流程视图窗口中的变量文件夹来声明你的业务流程变量和 BizTalk 表达式编辑器来编辑分配并使用各种形状中的变量的表达式。</span><span class="sxs-lookup"><span data-stu-id="75a86-123">You can use the Variables folder in the Orchestration View window to declare your orchestration variables, and BizTalk Expression Editor to edit expressions that assign and use the variables in various shapes.</span></span> <span data-ttu-id="75a86-124">有关详细信息，请参阅[xlang-s 数据类型](../core/xlang-s-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-124">For more information, see [XLANG-s Data Types](../core/xlang-s-data-types.md).</span></span>  
  
-   <span data-ttu-id="75a86-125">构建您的业务流程来测试出于完整性的考虑。</span><span class="sxs-lookup"><span data-stu-id="75a86-125">Build your orchestration to test it for completeness.</span></span>  
  
     <span data-ttu-id="75a86-126">编译项目或解决方案，其中包含它时，您构建您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="75a86-126">You build your orchestration when you compile the project or solution that contains it.</span></span> <span data-ttu-id="75a86-127">有关详细信息，请参阅[如何生成业务流程](../core/how-to-build-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="75a86-127">For more information, see [How to Build Orchestrations](../core/how-to-build-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a86-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="75a86-128">See Also</span></span>  
 <span data-ttu-id="75a86-129">[生成和运行业务流程](../core/building-and-running-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="75a86-129">[Building and Running Orchestrations](../core/building-and-running-orchestrations.md) </span></span>  
 <span data-ttu-id="75a86-130">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="75a86-130">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="75a86-131">使用业务流程设计器创建业务流程</span><span class="sxs-lookup"><span data-stu-id="75a86-131">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)