---
title: "如何配置终止形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5eb4867970c6acafc8903eb474b67541d22764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-terminate-shape"></a><span data-ttu-id="f3c89-102">如何配置终止形状</span><span class="sxs-lookup"><span data-stu-id="f3c89-102">How to Configure the Terminate Shape</span></span>
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
<span data-ttu-id="f3c89-103">终止形状</span><span class="sxs-lookup"><span data-stu-id="f3c89-103">Terminate shape</span></span>  
  
 <span data-ttu-id="f3c89-104">终止形状用于结束某一业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="f3c89-104">The Terminate shape is used to end an orchestration instance.</span></span> <span data-ttu-id="f3c89-105">可以指定一个消息字符串，以便在“组中心”页的输出中查看时随该形状一起显示。</span><span class="sxs-lookup"><span data-stu-id="f3c89-105">You can specify a message string to accompany the shape when viewed in the output from the Group Hub page.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f3c89-106">如果你将放置**终止**形状内**并行操作**形状和使用分支**终止**上运行，在实例完成立即，而不考虑是否其他分支已完成运行。</span><span class="sxs-lookup"><span data-stu-id="f3c89-106">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="f3c89-107">根据您的设计，在此情况下结果可能不可预测。</span><span class="sxs-lookup"><span data-stu-id="f3c89-107">Depending on your design, results might be unpredictable in this case.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f3c89-108">如果**终止**形状遇到业务流程中同步调用 (与**调用**形状) 通过另一个业务流程、 嵌套的实例和所有封闭的业务流程将终止实例。</span><span class="sxs-lookup"><span data-stu-id="f3c89-108">If a **Terminate** shape is encountered in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be terminated.</span></span>  
  
### <a name="to-configure-a-terminate-shape"></a><span data-ttu-id="f3c89-109">配置终止形状</span><span class="sxs-lookup"><span data-stu-id="f3c89-109">To configure a Terminate shape</span></span>  
  
-   <span data-ttu-id="f3c89-110">你可以使用**错误消息**属性来指定你想要将形状在组中心页面上将查询输出中查看时与关联的文本。</span><span class="sxs-lookup"><span data-stu-id="f3c89-110">You can use the **Error Message** property to specify text that you want to associate with the shape when viewed in the query output on the Group Hub page.</span></span> <span data-ttu-id="f3c89-111">此文本可能是文字字符串或表达式计算结果为**System.String**。</span><span class="sxs-lookup"><span data-stu-id="f3c89-111">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="f3c89-112">如果输入字符串，则必须将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="f3c89-112">If you enter a literal string, you must enclose it in quotation marks.</span></span>