---
title: "如何配置构造消息形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07b73e7fe62463767894808d7e95f12cf963e4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-construct-message-shape"></a><span data-ttu-id="b5c2f-102">如何配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="b5c2f-102">How to Configure the Construct Message Shape</span></span>
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
<span data-ttu-id="b5c2f-103">构造消息形状</span><span class="sxs-lookup"><span data-stu-id="b5c2f-103">Construct Message shape</span></span>  
  
 <span data-ttu-id="b5c2f-104">指定要构造的消息变量，并对消息或其部分进行赋值。</span><span class="sxs-lookup"><span data-stu-id="b5c2f-104">You specify the message variable that you want to construct, and make assignments to the message or its parts.</span></span> <span data-ttu-id="b5c2f-105">必须在同一构造消息形状中对任何给定消息进行彻底赋值。</span><span class="sxs-lookup"><span data-stu-id="b5c2f-105">All assignments to any given message must take place within the same Construct Message shape.</span></span>  
  
 <span data-ttu-id="b5c2f-106">若要修改已构造的消息的属性（例如已收到的消息），必须构造新的消息实例，方法是：将第一个值赋予第二个值，然后在新的消息实例中修改该属性；在同一构造消息形状中同时发生了构造和修改操作。</span><span class="sxs-lookup"><span data-stu-id="b5c2f-106">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message instance by assigning the first to the second and then modifying the property on the new message instance; both the construction and modification occur within the same Construct Message shape.</span></span>  
  
### <a name="to-configure-a-construct-message-shape"></a><span data-ttu-id="b5c2f-107">若要配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="b5c2f-107">To configure a Construct Message shape</span></span>  
  
1.  <span data-ttu-id="b5c2f-108">在属性窗口中，使用**消息构造**属性来指定哪些消息此形状将构造。</span><span class="sxs-lookup"><span data-stu-id="b5c2f-108">In the Properties window, use the **Messages Constructed** property to specify which messages this shape will construct.</span></span>  
  
2.  <span data-ttu-id="b5c2f-109">添加和配置一个或多个**转换**或**消息分配**内的形状**构造消息形状**。</span><span class="sxs-lookup"><span data-stu-id="b5c2f-109">Add and configure one or more **Transform** or **Message Assignment** shapes inside the **Construct Message shape**.</span></span>