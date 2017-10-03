---
title: "如何使用到控件的消息内容消息处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73d356496d07bb2227aa514ee68f2a2a51e2291b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a><span data-ttu-id="529d5-102">使用消息内容控制消息处理的方法</span><span class="sxs-lookup"><span data-stu-id="529d5-102">Ways to Use Message Content to Control Message Processing</span></span>
<span data-ttu-id="529d5-103">有两种类型的属性提升：**可分辨字段**和**属性字段**，后者将使用属性架构。</span><span class="sxs-lookup"><span data-stu-id="529d5-103">There are two types of property promotion: **Distinguished Fields** and **Property Fields**, the latter of which uses property schemas.</span></span> <span data-ttu-id="529d5-104">在 BizTalk 编辑器中，你通过进行管理这两种类型的属性提升**升级属性**对话框中，这是可访问通过使用**升级属性**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="529d5-104">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="529d5-105">对于可以升级的值有一些限制。</span><span class="sxs-lookup"><span data-stu-id="529d5-105">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="529d5-106">有关详细信息，请参阅中的表[提升属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="529d5-106">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
 <span data-ttu-id="529d5-107">您必须基于具体情况，确定要使用的属性升级的类型。</span><span class="sxs-lookup"><span data-stu-id="529d5-107">You must decide which type of property promotion to use based on the details of your scenario.</span></span> <span data-ttu-id="529d5-108">请考虑以下区别**可分辨字段**属性提升和**属性字段**属性提升：</span><span class="sxs-lookup"><span data-stu-id="529d5-108">Consider the following distinctions between **Distinguished Field** property promotion and **Property Field** property promotion:</span></span>  
  
-   <span data-ttu-id="529d5-109">**可分辨字段**不能参与邮件路由，因此它们不会出现在筛选表达式中。</span><span class="sxs-lookup"><span data-stu-id="529d5-109">**Distinguished Fields** cannot participate in message routing and therefore they do not appear in the filter expressions.</span></span> <span data-ttu-id="529d5-110">它们只能用于业务流程的上下文中，但在发送和接收消息时的系统开销较小。</span><span class="sxs-lookup"><span data-stu-id="529d5-110">They are only available within the context of an orchestration but they have less overhead when sending and receiving messages.</span></span>  
  
-   <span data-ttu-id="529d5-111">**可分辨字段**不具有任何大小限制。</span><span class="sxs-lookup"><span data-stu-id="529d5-111">**Distinguished Fields** do not have any size limitations.</span></span> <span data-ttu-id="529d5-112">**属性字段**限于 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="529d5-112">**Property Fields** are limited to 255 characters.</span></span>  
  
-   <span data-ttu-id="529d5-113">**可分辨字段**不需要任何单独的项目，而要创建**属性字段**需要的创建和维护属性架构。</span><span class="sxs-lookup"><span data-stu-id="529d5-113">**Distinguished Fields** do not require any separate artifacts to be created whereas **Property Fields** require the creation and maintenance of a property schema.</span></span>  
  
 <span data-ttu-id="529d5-114">绘制这些注意事项时，你应升级节点**属性字段**仅当你想要使用提升的属性路由或跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="529d5-114">Drawing upon these considerations, you should promote nodes as **Property Fields** only when you intend to use the promoted properties for message routing or tracking purposes.</span></span> <span data-ttu-id="529d5-115">否则，如果你仅要访问从你的业务流程内提升的属性，你应充分利用这一事实，**可分辨字段**是更廉价、 更轻量，和更简单易用的比**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="529d5-115">Otherwise, if you are only going to access the promoted properties from within your orchestrations, you should take advantage of the fact that **Distinguished Fields** are much cheaper, more lightweight, and more easy-to-use than **Property Fields**.</span></span>  
  
 <span data-ttu-id="529d5-116">通过使用提升的属性**可分辨字段**机制仅可从业务流程内访问，而不能从管道、 端口和等等访问。</span><span class="sxs-lookup"><span data-stu-id="529d5-116">Properties promoted by using the **Distinguished Field** mechanism are only accessible from within orchestrations and cannot be accessed from pipelines, ports, and so on.</span></span> <span data-ttu-id="529d5-117">另一方面，属性提升通过**属性字段**，从所有这些组件可访问属性架构机制。</span><span class="sxs-lookup"><span data-stu-id="529d5-117">On the other hand, properties promoted by using the **Property Fields** and property schema mechanism are accessible from all of these components.</span></span> <span data-ttu-id="529d5-118">两者的另一个重要差异是：属性字段值限制为 255 个字符，而可分辨字段值没有这样的限制。</span><span class="sxs-lookup"><span data-stu-id="529d5-118">Another important difference is that property field values are limited to 255 characters and distinguished field values have no such limit.</span></span>  
  
 <span data-ttu-id="529d5-119">本部分提供有关这两种属性升级的信息，包括如何使用 BizTalk 编辑器为消息架构建立此类升级属性的有关信息。</span><span class="sxs-lookup"><span data-stu-id="529d5-119">This section provides information about these two types of property promotion, including how information about how to establish such promoted properties for a message schema by using BizTalk Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="529d5-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="529d5-120">In This Section</span></span>  
  
-   [<span data-ttu-id="529d5-121">有关 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="529d5-121">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)  
  
-   [<span data-ttu-id="529d5-122">实例消息处理使用可分辨字段</span><span class="sxs-lookup"><span data-stu-id="529d5-122">Instance Message Processing Using Distinguished Fields</span></span>](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [<span data-ttu-id="529d5-123">使用属性提升实例消息处理</span><span class="sxs-lookup"><span data-stu-id="529d5-123">Instance Message Processing Using Property Promotion</span></span>](../core/instance-message-processing-using-property-promotion.md)