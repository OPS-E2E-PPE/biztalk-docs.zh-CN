---
title: 如何配置终止形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 177666efceb34d78b492c93b7f365fc36c3855bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340293"
---
# <a name="how-to-configure-the-terminate-shape"></a><span data-ttu-id="a2420-102">如何配置终止形状</span><span class="sxs-lookup"><span data-stu-id="a2420-102">How to Configure the Terminate Shape</span></span>
<span data-ttu-id="a2420-103">![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")</span><span class="sxs-lookup"><span data-stu-id="a2420-103">![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")</span></span>  
<span data-ttu-id="a2420-104">终止形状</span><span class="sxs-lookup"><span data-stu-id="a2420-104">Terminate shape</span></span>  
  
 <span data-ttu-id="a2420-105">终止形状用于结束业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="a2420-105">The Terminate shape is used to end an orchestration instance.</span></span> <span data-ttu-id="a2420-106">可以指定来显示形状时从组中心页的输出中查看的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="a2420-106">You can specify a message string to accompany the shape when viewed in the output from the Group Hub page.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a2420-107">如果将置于**Terminate**形状内**并行操作**形状，并使用分支**终止**上运行它时，该实例将立即完成，而不考虑是否其他分支完成运行。</span><span class="sxs-lookup"><span data-stu-id="a2420-107">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="a2420-108">根据你的设计，结果可能不可预测在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="a2420-108">Depending on your design, results might be unpredictable in this case.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a2420-109">如果**Terminate**形状遇到同步调用业务流程中 (如同**调用**形状) 通过另一个业务流程，则嵌套的实例和所有封闭的业务流程将终止实例。</span><span class="sxs-lookup"><span data-stu-id="a2420-109">If a **Terminate** shape is encountered in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be terminated.</span></span>  
  
### <a name="to-configure-a-terminate-shape"></a><span data-ttu-id="a2420-110">若要配置终止形状</span><span class="sxs-lookup"><span data-stu-id="a2420-110">To configure a Terminate shape</span></span>  
  
-   <span data-ttu-id="a2420-111">可以使用**错误消息**属性来指定你想要与形状时在组中心页上的查询输出中查看相关联的文本。</span><span class="sxs-lookup"><span data-stu-id="a2420-111">You can use the **Error Message** property to specify text that you want to associate with the shape when viewed in the query output on the Group Hub page.</span></span> <span data-ttu-id="a2420-112">文本字符串或表达式的计算结果为此文本可能太**System.String**。</span><span class="sxs-lookup"><span data-stu-id="a2420-112">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="a2420-113">如果输入的文本字符串，必须将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="a2420-113">If you enter a literal string, you must enclose it in quotation marks.</span></span>