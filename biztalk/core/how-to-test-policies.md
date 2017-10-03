---
title: "如何测试策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a0f8c0d63d14d5a529039a6e1c8af5b363cc9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-policies"></a><span data-ttu-id="dc823-102">如何测试策略</span><span class="sxs-lookup"><span data-stu-id="dc823-102">How to Test Policies</span></span>
<span data-ttu-id="dc823-103">若要测试策略，您需要可对其执行规则的事实。</span><span class="sxs-lookup"><span data-stu-id="dc823-103">To test a policy, you need facts on which the rules can be executed.</span></span> <span data-ttu-id="dc823-104">通过在将在策略测试器中指向的 XML 文档或数据库表中指定值，可以添加事实；也可以使用事实创建器向引擎提供 .NET 对象数组作为事实。</span><span class="sxs-lookup"><span data-stu-id="dc823-104">You can add facts by specifying values in XML documents or database tables that you will point to in the policy tester, or you can use a fact creator to supply to the engine an array of .NET objects as facts.</span></span> <span data-ttu-id="dc823-105">有关详细信息，请参阅[创建事实创建者](../core/how-to-create-a-fact-creator.md)。</span><span class="sxs-lookup"><span data-stu-id="dc823-105">For more information, see [Creating a Fact Creator](../core/how-to-create-a-fact-creator.md).</span></span>  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="dc823-106">在业务规则编辑器中测试策略</span><span class="sxs-lookup"><span data-stu-id="dc823-106">To test a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="dc823-107">在“策略浏览器”窗口中，单击要测试的策略版本。</span><span class="sxs-lookup"><span data-stu-id="dc823-107">In the Policy Explorer window, click the policy version that you want to test.</span></span>  
  
2.  <span data-ttu-id="dc823-108">单击**测试策略**菜单栏上的按钮 （绿色箭头）。</span><span class="sxs-lookup"><span data-stu-id="dc823-108">Click the **Test Policy** button (green arrow) on the menu bar.</span></span>  
  
     <span data-ttu-id="dc823-109">顶部窗格将显示策略规则引用的事实类型。</span><span class="sxs-lookup"><span data-stu-id="dc823-109">The top pane displays the fact types that the policy rules reference.</span></span>  
  
3.  <span data-ttu-id="dc823-110">若要添加的事实实例，请单击**XML 文档**或**数据库表**事实键入，然后单击**添加实例**。</span><span class="sxs-lookup"><span data-stu-id="dc823-110">To add a fact instance, click an **XML Document** or **Database Table** fact type, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="dc823-111">如果你想要删除的事实实例，单击相应的事实类型，然后单击**删除实例**。</span><span class="sxs-lookup"><span data-stu-id="dc823-111">If you want to remove a fact instance, click the corresponding fact type, and then click **Remove Instance**.</span></span>  
  
5.  <span data-ttu-id="dc823-112">如果你想要添加你编写了一个事实创建者，请单击**添加**事实创建者窗格中。</span><span class="sxs-lookup"><span data-stu-id="dc823-112">If you want to add a fact creator that you have written, click **Add** in the fact creator pane.</span></span>  
  
6.  <span data-ttu-id="dc823-113">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="dc823-113">Click **Test**.</span></span>  
  
     <span data-ttu-id="dc823-114">策略测试跟踪输出将显示在测试输出窗口中。</span><span class="sxs-lookup"><span data-stu-id="dc823-114">The policy test trace output appears in the test output window.</span></span>  
  
7.  <span data-ttu-id="dc823-115">右键单击输出窗口可保存、清除、选择或复制输出文本。</span><span class="sxs-lookup"><span data-stu-id="dc823-115">Right-click in the output window to save, clear, select, or copy the output text.</span></span>  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
<span data-ttu-id="dc823-116">选择事实以测试策略</span><span class="sxs-lookup"><span data-stu-id="dc823-116">Selecting fact to test a policy</span></span>