---
title: 如何配置挂起形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Suspend shapes
- Suspend shape [Orchestration Designer], literal strings
- Suspend shape [Orchestration Designer], configuring
- Suspend shape [Orchestration Designer]
- atomic transactions, Suspend shape [Orchestration Designer]
- Suspend shape [Orchestration Designer], atomic transactions
- Suspend shape [Orchestration Designer], about Suspend shape
ms.assetid: 62fbb6d4-78d2-4671-84bb-909cbf6b0ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846001b5a2b39a4e23e0d06ed56fb91c8863832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248517"
---
# <a name="how-to-configure-the-suspend-shape"></a><span data-ttu-id="a4e16-102">如何配置挂起形状</span><span class="sxs-lookup"><span data-stu-id="a4e16-102">How to Configure the Suspend Shape</span></span>
![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")  
<span data-ttu-id="a4e16-103">挂起形状</span><span class="sxs-lookup"><span data-stu-id="a4e16-103">Suspend shape</span></span>  
  
 <span data-ttu-id="a4e16-104">当业务流程实例处于挂起状态时，将记录错误。</span><span class="sxs-lookup"><span data-stu-id="a4e16-104">When an orchestration instance is suspended, an error is logged.</span></span> <span data-ttu-id="a4e16-105">你可以指定要伴随错误以帮助管理员在诊断这种情况的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="a4e16-105">You can specify a message string to accompany the error to help the administrator diagnose the situation.</span></span>  
  
 <span data-ttu-id="a4e16-106">所有业务流程实例的状态信息保存，并且如果在管理员恢复业务流程实例恢复过程。</span><span class="sxs-lookup"><span data-stu-id="a4e16-106">All of the state information for the orchestration instance is saved, and is reinstated if and when the administrator resumes the orchestration instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4e16-107">如果**挂起**形状存在业务流程中同步调用 (与**调用**形状) 通过另一个业务流程，将嵌套的实例和所有封闭的业务流程实例已挂起。</span><span class="sxs-lookup"><span data-stu-id="a4e16-107">If a **Suspend** shape exists in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4e16-108">不能放置**挂起**在原子事务的形状。</span><span class="sxs-lookup"><span data-stu-id="a4e16-108">You cannot place a **Suspend** shape inside an atomic transaction.</span></span>  
  
### <a name="to-configure-a-suspend-shape"></a><span data-ttu-id="a4e16-109">若要配置挂起形状</span><span class="sxs-lookup"><span data-stu-id="a4e16-109">To configure a Suspend shape</span></span>  
  
-   <span data-ttu-id="a4e16-110">你可以使用**错误消息**属性来指定你想要的文本记录时**挂起**遇到形状。</span><span class="sxs-lookup"><span data-stu-id="a4e16-110">You can use the **Error Message** property to specify text that you want to be logged when a **Suspend** shape is encountered.</span></span> <span data-ttu-id="a4e16-111">此文本可能是文字字符串或表达式计算结果为**System.String**。</span><span class="sxs-lookup"><span data-stu-id="a4e16-111">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="a4e16-112">如果输入字符串，则必须将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="a4e16-112">If you enter a literal string, you must enclose it in quotation marks.</span></span>