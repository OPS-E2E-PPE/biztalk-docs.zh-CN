---
title: 如何测试策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49c682645a534f43476244fcda26453944048168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383727"
---
# <a name="how-to-test-policies"></a><span data-ttu-id="02984-102">如何测试策略</span><span class="sxs-lookup"><span data-stu-id="02984-102">How to Test Policies</span></span>
<span data-ttu-id="02984-103">若要测试策略，需要可对其执行规则的事实。</span><span class="sxs-lookup"><span data-stu-id="02984-103">To test a policy, you need facts on which the rules can be executed.</span></span> <span data-ttu-id="02984-104">可以通过在 XML 文档中指定值添加事实或数据库表，将指向策略测试器，或者您可以使用事实创建器向引擎提供.NET 对象作为事实的数组。</span><span class="sxs-lookup"><span data-stu-id="02984-104">You can add facts by specifying values in XML documents or database tables that you will point to in the policy tester, or you can use a fact creator to supply to the engine an array of .NET objects as facts.</span></span> <span data-ttu-id="02984-105">有关详细信息，请参阅[创建事实创建器](../core/how-to-create-a-fact-creator.md)。</span><span class="sxs-lookup"><span data-stu-id="02984-105">For more information, see [Creating a Fact Creator](../core/how-to-create-a-fact-creator.md).</span></span>  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="02984-106">若要在业务规则编辑器测试策略</span><span class="sxs-lookup"><span data-stu-id="02984-106">To test a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="02984-107">在策略浏览器窗口中，单击你想要测试的策略版本。</span><span class="sxs-lookup"><span data-stu-id="02984-107">In the Policy Explorer window, click the policy version that you want to test.</span></span>  
  
2.  <span data-ttu-id="02984-108">单击**测试策略**菜单栏上的按钮 （绿色箭头）。</span><span class="sxs-lookup"><span data-stu-id="02984-108">Click the **Test Policy** button (green arrow) on the menu bar.</span></span>  
  
     <span data-ttu-id="02984-109">顶部窗格显示策略规则引用的事实类型。</span><span class="sxs-lookup"><span data-stu-id="02984-109">The top pane displays the fact types that the policy rules reference.</span></span>  
  
3.  <span data-ttu-id="02984-110">若要添加事实实例，请单击**XML 文档**或**数据库表**事实类型，然后再单击**添加实例**。</span><span class="sxs-lookup"><span data-stu-id="02984-110">To add a fact instance, click an **XML Document** or **Database Table** fact type, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="02984-111">如果你想要删除事实实例，请单击相应的事实类型，然后单击**删除实例**。</span><span class="sxs-lookup"><span data-stu-id="02984-111">If you want to remove a fact instance, click the corresponding fact type, and then click **Remove Instance**.</span></span>  
  
5.  <span data-ttu-id="02984-112">如果你想要添加已编写事实创建器，请单击**添加**事实创建器窗格中。</span><span class="sxs-lookup"><span data-stu-id="02984-112">If you want to add a fact creator that you have written, click **Add** in the fact creator pane.</span></span>  
  
6.  <span data-ttu-id="02984-113">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="02984-113">Click **Test**.</span></span>  
  
     <span data-ttu-id="02984-114">策略测试跟踪输出将显示在测试输出窗口中。</span><span class="sxs-lookup"><span data-stu-id="02984-114">The policy test trace output appears in the test output window.</span></span>  
  
7.  <span data-ttu-id="02984-115">用鼠标右键单击输出窗口来保存、 清除、 选择，或复制输出文本。</span><span class="sxs-lookup"><span data-stu-id="02984-115">Right-click in the output window to save, clear, select, or copy the output text.</span></span>  
  
     <span data-ttu-id="02984-116">![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")</span><span class="sxs-lookup"><span data-stu-id="02984-116">![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")</span></span>  
<span data-ttu-id="02984-117">选择事实以测试策略</span><span class="sxs-lookup"><span data-stu-id="02984-117">Selecting fact to test a policy</span></span>