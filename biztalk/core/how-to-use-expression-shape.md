---
title: "如何使用表达式形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Expression shapes
- Expression shape [Orchestration Designer]
- Expression shape [Orchestration Designer], configuring
- Expression shape [Orchestration Designer], about Expression shape
ms.assetid: 2d702aa9-b824-4f47-a416-70707ce8ef29
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e263454db9674d5bc86b6b7dae1649003f3d129c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expression-shape"></a><span data-ttu-id="11dad-102">如何使用表达式形状</span><span class="sxs-lookup"><span data-stu-id="11dad-102">How to Use Expression Shape</span></span>
<span data-ttu-id="11dad-103">**表达式**形状使您能够输入您的业务流程中选择任何 XLANG/s 表达式。</span><span class="sxs-lookup"><span data-stu-id="11dad-103">The **Expression** shape enables you to enter any XLANG/s expression you choose in your orchestration.</span></span> <span data-ttu-id="11dad-104">例如，您可以借助 .NET 调用来运行外部程序，或仅处理业务流程变量的值。</span><span class="sxs-lookup"><span data-stu-id="11dad-104">For example, you can make a .NET call to run an external program, or simply manipulate the values of your orchestration variables.</span></span>  
  
 <span data-ttu-id="11dad-105">虽然**表达式**形状是非常灵活，则不会使用它来执行高级业务流程逻辑，最好是将是在绘制自身的业务流程中可见的好办法。</span><span class="sxs-lookup"><span data-stu-id="11dad-105">While the **Expression** shape is quite flexible, it is not good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="11dad-106">一般情况下，很容易地理解和维护你的业务流程，如果你**表达式**形状包含简单和模块化表达式。</span><span class="sxs-lookup"><span data-stu-id="11dad-106">In general, it is easier to understand and maintain your orchestrations if your **Expression** shapes contain simple and modular expressions.</span></span>  
  
### <a name="to-configure-an-expression-shape"></a><span data-ttu-id="11dad-107">配置表达式形状</span><span class="sxs-lookup"><span data-stu-id="11dad-107">To configure an Expression shape</span></span>  
  
1.  <span data-ttu-id="11dad-108">如果 BizTalk 表达式编辑器不可见，请右键单击**表达式**的形状，然后单击**编辑表达式**或在属性窗口中，单击省略号 (**...**) 按钮**表达式**属性。</span><span class="sxs-lookup"><span data-stu-id="11dad-108">If BizTalk Expression Editor is not visible, right-click the **Expression** shape and click **Edit Expression** or, in the Properties window, click the Ellipsis (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="11dad-109">在 BizTalk 表达式编辑器中，创建要赋值的表达式。</span><span class="sxs-lookup"><span data-stu-id="11dad-109">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="11dad-110">有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="11dad-110">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11dad-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11dad-111">See Also</span></span>  
 [<span data-ttu-id="11dad-112">XLANG-s 语言</span><span class="sxs-lookup"><span data-stu-id="11dad-112">XLANG-s Language</span></span>](../core/xlang-s-language.md)