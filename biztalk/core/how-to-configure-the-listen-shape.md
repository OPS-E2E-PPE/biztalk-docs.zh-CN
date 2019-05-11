---
title: 如何配置侦听形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55a717c45e5c40b4022c38d2b668cae4c615f248
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386054"
---
# <a name="how-to-configure-the-listen-shape"></a><span data-ttu-id="7ec57-102">如何配置侦听形状</span><span class="sxs-lookup"><span data-stu-id="7ec57-102">How to Configure the Listen Shape</span></span>
<span data-ttu-id="7ec57-103">侦听操作使应用程序要等待的时间的一个或多个端口上的若干消息之一，或指定的超时间隔，并根据结果的分支后停止等待。</span><span class="sxs-lookup"><span data-stu-id="7ec57-103">Listen actions enable applications to wait for one of several messages on one or more ports, or to stop waiting after a specified time-out interval, and branch based upon the results.</span></span>  
  
 <span data-ttu-id="7ec57-104">![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")</span><span class="sxs-lookup"><span data-stu-id="7ec57-104">![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")</span></span>  
<span data-ttu-id="7ec57-105">侦听形状</span><span class="sxs-lookup"><span data-stu-id="7ec57-105">Listen shape</span></span>  
  
 <span data-ttu-id="7ec57-106">您可以添加任意数量的分支。</span><span class="sxs-lookup"><span data-stu-id="7ec57-106">You can add as many branches as you like.</span></span> <span data-ttu-id="7ec57-107">可以将放置其他任何形状下方初始**接收**或**延迟**形状。</span><span class="sxs-lookup"><span data-stu-id="7ec57-107">You can place any other shape below the initial **Receive** or **Delay** shape.</span></span>  
  
 <span data-ttu-id="7ec57-108">可以使用激活接收**侦听**形状。</span><span class="sxs-lookup"><span data-stu-id="7ec57-108">It is possible to use an activation receive in a **Listen** shape.</span></span> <span data-ttu-id="7ec57-109">如果的一个分支**侦听**形状包含激活接收，则所有分支都必须都包含激活接收，而且可以使用无超时。</span><span class="sxs-lookup"><span data-stu-id="7ec57-109">If one branch of the **Listen** shape contains an activation receive, then all branches must contain activation receives, and no timeout can be used.</span></span> <span data-ttu-id="7ec57-110">激活接收必须是每个分支中的第一个操作。</span><span class="sxs-lookup"><span data-stu-id="7ec57-110">The activation receive must be the first action in each branch.</span></span>  
  
 <span data-ttu-id="7ec57-111">可以使用**侦听**分支业务流程流的形状基于发生的一个或多个事件。</span><span class="sxs-lookup"><span data-stu-id="7ec57-111">You can use the **Listen** shape to branch orchestration flow based on the occurrence of one or more events.</span></span> <span data-ttu-id="7ec57-112">每个分支中的第一个形状必须是**延迟**或**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="7ec57-112">The first shape in each branch must be either a **Delay** or a **Receive** shape.</span></span> <span data-ttu-id="7ec57-113">满足其条件的第一个分支 — 的超时值的匹配项**延迟**形状或接收的消息**接收**形状，将执行。</span><span class="sxs-lookup"><span data-stu-id="7ec57-113">The first branch that meets its condition—the occurrence of a time-out for a **Delay** shape or the receipt of a message for a **Receive** shape—will execute.</span></span> <span data-ttu-id="7ec57-114">如果需要可以添加其他分支。</span><span class="sxs-lookup"><span data-stu-id="7ec57-114">You can add additional branches if needed.</span></span>  
  
### <a name="to-configure-a-listen-shape"></a><span data-ttu-id="7ec57-115">若要配置侦听形状</span><span class="sxs-lookup"><span data-stu-id="7ec57-115">To configure a Listen shape</span></span>  
  
1.  <span data-ttu-id="7ec57-116">选择分支。</span><span class="sxs-lookup"><span data-stu-id="7ec57-116">Select a branch.</span></span>  
  
2.  <span data-ttu-id="7ec57-117">在属性窗口中，指定**分支类型**属性。</span><span class="sxs-lookup"><span data-stu-id="7ec57-117">In the Properties window, specify the **Branch Type** property.</span></span>  
  
     <span data-ttu-id="7ec57-118">-或-</span><span class="sxs-lookup"><span data-stu-id="7ec57-118">—Or—</span></span>  
  
     <span data-ttu-id="7ec57-119">拖动**延迟**或**接收**形状拖到该分支。</span><span class="sxs-lookup"><span data-stu-id="7ec57-119">Drag a **Delay** or **Receive** shape onto the branch.</span></span>  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a><span data-ttu-id="7ec57-120">若要向侦听形状添加分支</span><span class="sxs-lookup"><span data-stu-id="7ec57-120">To add a branch to a Listen shape</span></span>  
  
-   <span data-ttu-id="7ec57-121">右键单击**侦听**形状，然后单击**新建侦听分支**。</span><span class="sxs-lookup"><span data-stu-id="7ec57-121">Right-click the **Listen** shape and then click **New Listen Branch**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ec57-122">若要删除分支起源**侦听**形状中，右键单击你想要删除，然后单击的分支**删除**。</span><span class="sxs-lookup"><span data-stu-id="7ec57-122">To remove a branch from a **Listen** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>