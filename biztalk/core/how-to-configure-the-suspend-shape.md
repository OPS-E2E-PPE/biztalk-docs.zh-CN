---
title: 如何配置挂起形状 |Microsoft Docs
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
ms.openlocfilehash: 6a4a60bfc2d5a98d407e917e0271a9987e88c0bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385955"
---
# <a name="how-to-configure-the-suspend-shape"></a><span data-ttu-id="05389-102">如何配置挂起形状</span><span class="sxs-lookup"><span data-stu-id="05389-102">How to Configure the Suspend Shape</span></span>
<span data-ttu-id="05389-103">![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")</span><span class="sxs-lookup"><span data-stu-id="05389-103">![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")</span></span>  
<span data-ttu-id="05389-104">挂起形状</span><span class="sxs-lookup"><span data-stu-id="05389-104">Suspend shape</span></span>  
  
 <span data-ttu-id="05389-105">当挂起业务流程实例时，记录一个错误。</span><span class="sxs-lookup"><span data-stu-id="05389-105">When an orchestration instance is suspended, an error is logged.</span></span> <span data-ttu-id="05389-106">您可以指定一个消息字符串来显示错误帮助管理员诊断这种情况。</span><span class="sxs-lookup"><span data-stu-id="05389-106">You can specify a message string to accompany the error to help the administrator diagnose the situation.</span></span>  
  
 <span data-ttu-id="05389-107">所有业务流程实例的状态信息保存后，并在管理员恢复业务流程实例时恢复过程。</span><span class="sxs-lookup"><span data-stu-id="05389-107">All of the state information for the orchestration instance is saved, and is reinstated if and when the administrator resumes the orchestration instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05389-108">如果**挂起**形状同步调用的业务流程中存在 (如同**调用**形状) 由另一个业务流程，则嵌套的实例和所有封闭业务流程实例将被挂起。</span><span class="sxs-lookup"><span data-stu-id="05389-108">If a **Suspend** shape exists in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05389-109">不能将放置**挂起**在原子事务内的形状。</span><span class="sxs-lookup"><span data-stu-id="05389-109">You cannot place a **Suspend** shape inside an atomic transaction.</span></span>  
  
### <a name="to-configure-a-suspend-shape"></a><span data-ttu-id="05389-110">若要配置挂起形状</span><span class="sxs-lookup"><span data-stu-id="05389-110">To configure a Suspend shape</span></span>  
  
-   <span data-ttu-id="05389-111">可以使用**错误消息**属性来指定你想要的文本记录何时**挂起**遇到形状。</span><span class="sxs-lookup"><span data-stu-id="05389-111">You can use the **Error Message** property to specify text that you want to be logged when a **Suspend** shape is encountered.</span></span> <span data-ttu-id="05389-112">文本字符串或表达式的计算结果为此文本可能太**System.String**。</span><span class="sxs-lookup"><span data-stu-id="05389-112">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="05389-113">如果输入的文本字符串，必须将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="05389-113">If you enter a literal string, you must enclose it in quotation marks.</span></span>