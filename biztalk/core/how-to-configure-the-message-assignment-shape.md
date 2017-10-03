---
title: "如何配置消息赋值形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], configuring
- Message Assignment shape [Orchestration Designer], about Message Assignment shape
- configuring [Orchestration Designer], Message Assignment shape
- Message Assignment shape [Orchestration Designer]
ms.assetid: 46920b49-5955-4e15-9a7c-2652e02ba1bf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6be49a61e79ed4f5e03cfca854d4b5b4b57270e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-message-assignment-shape"></a><span data-ttu-id="14055-102">如何配置消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="14055-102">How to Configure the Message Assignment Shape</span></span>
![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")  
<span data-ttu-id="14055-103">消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="14055-103">Message Assignment shape</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14055-104">A**消息分配**形状可以仅在存在**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="14055-104">A **Message Assignment** shape can exist only within a **Construct Message** shape.</span></span> <span data-ttu-id="14055-105">如果设计图面上拖动的其他任何位置消息分配一个新**构造消息**将创建形状。</span><span class="sxs-lookup"><span data-stu-id="14055-105">If you drag a Message Assignment anywhere else on the design surface, a new **Construct Message** shape will be created.</span></span>  
  
### <a name="to-configure-a-message-assignment-shape"></a><span data-ttu-id="14055-106">配置消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="14055-106">To configure a Message Assignment shape</span></span>  
  
1.  <span data-ttu-id="14055-107">如果 BizTalk 表达式编辑器不可见，请右键单击**消息分配**的形状，然后单击**编辑表达式**或在属性窗口中，单击**省略号**(**...**) 按钮**表达式**属性。</span><span class="sxs-lookup"><span data-stu-id="14055-107">If BizTalk Expression Editor is not visible, right-click the **Message Assignment** shape and click **Edit Expression** or, in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="14055-108">在 BizTalk 表达式编辑器中，创建要赋值的表达式。</span><span class="sxs-lookup"><span data-stu-id="14055-108">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="14055-109">有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="14055-109">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>