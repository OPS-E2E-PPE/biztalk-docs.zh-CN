---
title: "如何配置侦听形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd8f8bbcc08d41430b95a9d177aeb06a5288be4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-listen-shape"></a><span data-ttu-id="b3381-102">如何配置侦听形状</span><span class="sxs-lookup"><span data-stu-id="b3381-102">How to Configure the Listen Shape</span></span>
<span data-ttu-id="b3381-103">侦听操作使应用程序可以等待一个或多个端口上的若干消息之一，或者在指定的超时间隔后停止等待，以及基于结果进行分支。</span><span class="sxs-lookup"><span data-stu-id="b3381-103">Listen actions enable applications to wait for one of several messages on one or more ports, or to stop waiting after a specified time-out interval, and branch based upon the results.</span></span>  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
<span data-ttu-id="b3381-104">侦听形状</span><span class="sxs-lookup"><span data-stu-id="b3381-104">Listen shape</span></span>  
  
 <span data-ttu-id="b3381-105">可以添加任意数量的分支。</span><span class="sxs-lookup"><span data-stu-id="b3381-105">You can add as many branches as you like.</span></span> <span data-ttu-id="b3381-106">你可以将初始下面的任何其他形状**接收**或**延迟**形状。</span><span class="sxs-lookup"><span data-stu-id="b3381-106">You can place any other shape below the initial **Receive** or **Delay** shape.</span></span>  
  
 <span data-ttu-id="b3381-107">可以使用激活中接收**侦听**形状。</span><span class="sxs-lookup"><span data-stu-id="b3381-107">It is possible to use an activation receive in a **Listen** shape.</span></span> <span data-ttu-id="b3381-108">如果的一个分支**侦听**形状包含激活接收，则所有分支都必须都包含激活接收，而且可以使用无超时。</span><span class="sxs-lookup"><span data-stu-id="b3381-108">If one branch of the **Listen** shape contains an activation receive, then all branches must contain activation receives, and no timeout can be used.</span></span> <span data-ttu-id="b3381-109">激活接收必须是每个分支中的第一个操作。</span><span class="sxs-lookup"><span data-stu-id="b3381-109">The activation receive must be the first action in each branch.</span></span>  
  
 <span data-ttu-id="b3381-110">你可以使用**侦听**形状上的分支业务流程流与基于一个或多个事件的匹配项。</span><span class="sxs-lookup"><span data-stu-id="b3381-110">You can use the **Listen** shape to branch orchestration flow based on the occurrence of one or more events.</span></span> <span data-ttu-id="b3381-111">每个分支中的第一个形状必须是**延迟**或**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="b3381-111">The first shape in each branch must be either a **Delay** or a **Receive** shape.</span></span> <span data-ttu-id="b3381-112">满足其条件的第一个分支-对使用超时的匹配项**延迟**形状或收到的消息**接收**形状-将执行。</span><span class="sxs-lookup"><span data-stu-id="b3381-112">The first branch that meets its condition—the occurrence of a time-out for a **Delay** shape or the receipt of a message for a **Receive** shape—will execute.</span></span> <span data-ttu-id="b3381-113">可以根据需要添加更多的分支。</span><span class="sxs-lookup"><span data-stu-id="b3381-113">You can add additional branches if needed.</span></span>  
  
### <a name="to-configure-a-listen-shape"></a><span data-ttu-id="b3381-114">配置侦听形状</span><span class="sxs-lookup"><span data-stu-id="b3381-114">To configure a Listen shape</span></span>  
  
1.  <span data-ttu-id="b3381-115">选择某一分支。</span><span class="sxs-lookup"><span data-stu-id="b3381-115">Select a branch.</span></span>  
  
2.  <span data-ttu-id="b3381-116">在属性窗口中，指定**分支类型**属性。</span><span class="sxs-lookup"><span data-stu-id="b3381-116">In the Properties window, specify the **Branch Type** property.</span></span>  
  
     <span data-ttu-id="b3381-117">-或者-</span><span class="sxs-lookup"><span data-stu-id="b3381-117">—Or—</span></span>  
  
     <span data-ttu-id="b3381-118">拖动**延迟**或**接收**形状拖到该分支。</span><span class="sxs-lookup"><span data-stu-id="b3381-118">Drag a **Delay** or **Receive** shape onto the branch.</span></span>  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a><span data-ttu-id="b3381-119">向侦听形状添加分支</span><span class="sxs-lookup"><span data-stu-id="b3381-119">To add a branch to a Listen shape</span></span>  
  
-   <span data-ttu-id="b3381-120">右键单击**侦听**形状，然后单击**新侦听分支**。</span><span class="sxs-lookup"><span data-stu-id="b3381-120">Right-click the **Listen** shape and then click **New Listen Branch**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3381-121">若要删除分支起源**侦听**形状，右键单击你想要删除，，然后单击的分支**删除**。</span><span class="sxs-lookup"><span data-stu-id="b3381-121">To remove a branch from a **Listen** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>