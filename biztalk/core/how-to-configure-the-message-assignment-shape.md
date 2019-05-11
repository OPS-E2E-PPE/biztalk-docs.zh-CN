---
title: 如何配置消息赋值形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], configuring
- Message Assignment shape [Orchestration Designer], about Message Assignment shape
- configuring [Orchestration Designer], Message Assignment shape
- Message Assignment shape [Orchestration Designer]
ms.assetid: 46920b49-5955-4e15-9a7c-2652e02ba1bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ef13227071bcb483f541afeaf8465cb83ae9b21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386045"
---
# <a name="how-to-configure-the-message-assignment-shape"></a><span data-ttu-id="5105e-102">如何配置消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="5105e-102">How to Configure the Message Assignment Shape</span></span>
<span data-ttu-id="5105e-103">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span><span class="sxs-lookup"><span data-stu-id="5105e-103">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span></span>  
<span data-ttu-id="5105e-104">消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="5105e-104">Message Assignment shape</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5105e-105">一个**消息赋值**形状可以仅在存在**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="5105e-105">A **Message Assignment** shape can exist only within a **Construct Message** shape.</span></span> <span data-ttu-id="5105e-106">如果在设计图面上，拖动一个消息分配的其他任何位置的新**构造消息**将创建形状。</span><span class="sxs-lookup"><span data-stu-id="5105e-106">If you drag a Message Assignment anywhere else on the design surface, a new **Construct Message** shape will be created.</span></span>  
  
### <a name="to-configure-a-message-assignment-shape"></a><span data-ttu-id="5105e-107">若要配置消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="5105e-107">To configure a Message Assignment shape</span></span>  
  
1.  <span data-ttu-id="5105e-108">如果 BizTalk 表达式编辑器不可见，请右键单击**消息赋值**形状，然后单击**编辑表达式**或在属性窗口中，单击**省略号**(**...**) 按钮**表达式**属性。</span><span class="sxs-lookup"><span data-stu-id="5105e-108">If BizTalk Expression Editor is not visible, right-click the **Message Assignment** shape and click **Edit Expression** or, in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="5105e-109">在 BizTalk 表达式编辑器中，创建要分配值的表达式。</span><span class="sxs-lookup"><span data-stu-id="5105e-109">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="5105e-110">有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="5105e-110">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>