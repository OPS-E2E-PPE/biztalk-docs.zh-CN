---
title: 如何使用消息内容控制消息处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7791957dba89fab54813212fce3ecbd2c39fe19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393624"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a><span data-ttu-id="cff2d-102">使用消息内容控制消息处理的方法</span><span class="sxs-lookup"><span data-stu-id="cff2d-102">Ways to Use Message Content to Control Message Processing</span></span>
<span data-ttu-id="cff2d-103">有两种类型的属性升级：**可分辨字段**并**属性字段**，后者使用属性架构。</span><span class="sxs-lookup"><span data-stu-id="cff2d-103">There are two types of property promotion: **Distinguished Fields** and **Property Fields**, the latter of which uses property schemas.</span></span> <span data-ttu-id="cff2d-104">在 BizTalk 编辑器中，这两种类型的属性升级使用来管理**升级属性**对话框中，通过使用可访问该**升级属性**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="cff2d-104">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cff2d-105">有一些限制，您可以将升级的值。</span><span class="sxs-lookup"><span data-stu-id="cff2d-105">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="cff2d-106">有关详细信息，请参阅中的表[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cff2d-106">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
 <span data-ttu-id="cff2d-107">您必须决定哪种类型的属性升级为使用基于你的方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cff2d-107">You must decide which type of property promotion to use based on the details of your scenario.</span></span> <span data-ttu-id="cff2d-108">请考虑以下区别**可分辨字段**属性升级和**属性字段**属性升级：</span><span class="sxs-lookup"><span data-stu-id="cff2d-108">Consider the following distinctions between **Distinguished Field** property promotion and **Property Field** property promotion:</span></span>  
  
- <span data-ttu-id="cff2d-109">**可分辨字段**不能参与消息路由，因此它们不显示在筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="cff2d-109">**Distinguished Fields** cannot participate in message routing and therefore they do not appear in the filter expressions.</span></span> <span data-ttu-id="cff2d-110">它们只是业务流程的上下文中可用，但它们具有更少的开销时发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="cff2d-110">They are only available within the context of an orchestration but they have less overhead when sending and receiving messages.</span></span>  
  
- <span data-ttu-id="cff2d-111">**可分辨字段**不具有任何大小限制。</span><span class="sxs-lookup"><span data-stu-id="cff2d-111">**Distinguished Fields** do not have any size limitations.</span></span> <span data-ttu-id="cff2d-112">**属性字段**仅限于 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="cff2d-112">**Property Fields** are limited to 255 characters.</span></span>  
  
- <span data-ttu-id="cff2d-113">**可分辨字段**不需要任何单独的项目，而要创建**属性字段**则需要创建和维护属性架构。</span><span class="sxs-lookup"><span data-stu-id="cff2d-113">**Distinguished Fields** do not require any separate artifacts to be created whereas **Property Fields** require the creation and maintenance of a property schema.</span></span>  
  
  <span data-ttu-id="cff2d-114">绘制这些注意事项后，您应将节点升级为**属性字段**仅当你想要升级的属性用于消息路由或跟踪。</span><span class="sxs-lookup"><span data-stu-id="cff2d-114">Drawing upon these considerations, you should promote nodes as **Property Fields** only when you intend to use the promoted properties for message routing or tracking purposes.</span></span> <span data-ttu-id="cff2d-115">否则，如果仅要访问从业务流程中升级的属性，您应充分利用这一事实，**可分辨字段**是更廉价、 更轻量、 和更易于使用比**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="cff2d-115">Otherwise, if you are only going to access the promoted properties from within your orchestrations, you should take advantage of the fact that **Distinguished Fields** are much cheaper, more lightweight, and more easy-to-use than **Property Fields**.</span></span>  
  
  <span data-ttu-id="cff2d-116">通过使用提升的属性**可分辨字段**机制仅可从业务流程中访问，而不能从管道、 端口等访问。</span><span class="sxs-lookup"><span data-stu-id="cff2d-116">Properties promoted by using the **Distinguished Field** mechanism are only accessible from within orchestrations and cannot be accessed from pipelines, ports, and so on.</span></span> <span data-ttu-id="cff2d-117">但是，通过使用升级属性**属性字段**，属性架构机制，可从所有这些组件访问。</span><span class="sxs-lookup"><span data-stu-id="cff2d-117">On the other hand, properties promoted by using the **Property Fields** and property schema mechanism are accessible from all of these components.</span></span> <span data-ttu-id="cff2d-118">另一个重要区别是属性字段值限制为 255 个字符，并且可分辨的字段的值有没有此类限制。</span><span class="sxs-lookup"><span data-stu-id="cff2d-118">Another important difference is that property field values are limited to 255 characters and distinguished field values have no such limit.</span></span>  
  
  <span data-ttu-id="cff2d-119">本部分提供有关这两种类型的属性升级，包括有关如何建立此类信息如何通过使用 BizTalk 编辑器中升级为消息架构的属性的信息。</span><span class="sxs-lookup"><span data-stu-id="cff2d-119">This section provides information about these two types of property promotion, including how information about how to establish such promoted properties for a message schema by using BizTalk Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cff2d-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="cff2d-120">In This Section</span></span>  
  
-   [<span data-ttu-id="cff2d-121">关于 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="cff2d-121">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)  
  
-   [<span data-ttu-id="cff2d-122">使用可分辨字段处理实例消息</span><span class="sxs-lookup"><span data-stu-id="cff2d-122">Instance Message Processing Using Distinguished Fields</span></span>](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [<span data-ttu-id="cff2d-123">使用属性升级处理实例消息</span><span class="sxs-lookup"><span data-stu-id="cff2d-123">Instance Message Processing Using Property Promotion</span></span>](../core/instance-message-processing-using-property-promotion.md)