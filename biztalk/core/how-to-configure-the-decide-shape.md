---
title: 如何配置判定形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cadca52dade623190b347c0daa3cbd5581c58b2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341035"
---
# <a name="how-to-configure-the-decide-shape"></a><span data-ttu-id="178bd-102">如何配置判定形状</span><span class="sxs-lookup"><span data-stu-id="178bd-102">How to Configure the Decide Shape</span></span>
<span data-ttu-id="178bd-103">![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")</span><span class="sxs-lookup"><span data-stu-id="178bd-103">![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")</span></span>  
<span data-ttu-id="178bd-104">判定形状</span><span class="sxs-lookup"><span data-stu-id="178bd-104">Decide shape</span></span>  
  
 <span data-ttu-id="178bd-105">每个分支**判定**形状，除**其他**分支中，具有与之关联的规则。</span><span class="sxs-lookup"><span data-stu-id="178bd-105">Each branch of a **Decide** shape, except the **else** branch, has a rule associated with it.</span></span> <span data-ttu-id="178bd-106">可以使用 BizTalk 表达式编辑器来创建一个布尔表达式中计算该分支执行的规则。</span><span class="sxs-lookup"><span data-stu-id="178bd-106">You can use BizTalk Expression Editor to create a Boolean expression in the rule that is evaluated for the execution of that branch.</span></span> <span data-ttu-id="178bd-107">因为**其他**分支意味着对前一分支中的布尔表达式的求反运算，它不具有与之关联的表达式。</span><span class="sxs-lookup"><span data-stu-id="178bd-107">Because the **else** branch implies the negation of the Boolean expression in the previous branch, it does not have an expression associated with it.</span></span>  
  
 <span data-ttu-id="178bd-108">该规则下或**else**子句中的分支**判定**形状可以包含其他形状，业务流程的任何其他部分一样。</span><span class="sxs-lookup"><span data-stu-id="178bd-108">Below the rule or **else** clause, a branch of a **Decide** shape can contain additional shapes, just like any other part of the orchestration.</span></span>  
  
### <a name="to-configure-a-decide-shape"></a><span data-ttu-id="178bd-109">若要配置判定形状</span><span class="sxs-lookup"><span data-stu-id="178bd-109">To configure a Decide shape</span></span>  
  
1.  <span data-ttu-id="178bd-110">如果 BizTalk 表达式编辑器不可见，请右键单击该规则，然后单击**编辑布尔表达式**，或在属性窗口中，单击**省略号**(**...**) 按钮**表达式**属性。</span><span class="sxs-lookup"><span data-stu-id="178bd-110">If BizTalk Expression Editor is not visible, right-click the rule and click **Edit Boolean Expression**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="178bd-111">在 BizTalk 表达式编辑器中，创建一个布尔表达式为每个分支除外**Else**分支。</span><span class="sxs-lookup"><span data-stu-id="178bd-111">In BizTalk Expression Editor, create a Boolean expression for each branch except the **Else** branch.</span></span> <span data-ttu-id="178bd-112">例如，</span><span class="sxs-lookup"><span data-stu-id="178bd-112">For example,</span></span>  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a><span data-ttu-id="178bd-113">若要向判定形状添加分支</span><span class="sxs-lookup"><span data-stu-id="178bd-113">To add a branch to a Decide shape</span></span>  
  
1.  <span data-ttu-id="178bd-114">右键单击**判定**形状，然后依次**新建规则分支**。</span><span class="sxs-lookup"><span data-stu-id="178bd-114">Right-click the **Decide** shape, and then click **New Rule Branch**.</span></span>  
  
     <span data-ttu-id="178bd-115">-或-</span><span class="sxs-lookup"><span data-stu-id="178bd-115">—Or—</span></span>  
  
2.  <span data-ttu-id="178bd-116">两个现有分支之间将新形状。</span><span class="sxs-lookup"><span data-stu-id="178bd-116">Drag a new shape between two existing branches.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="178bd-117">若要删除分支起源**判定**形状中，右键单击你想要删除，然后单击的分支**删除**，或选择规则分支，然后按**删除**密钥。</span><span class="sxs-lookup"><span data-stu-id="178bd-117">To remove a branch from a **Decide** shape, right-click the branch you want to remove, and then click **Delete**, or select the rule branch and press the **DELETE** key.</span></span>