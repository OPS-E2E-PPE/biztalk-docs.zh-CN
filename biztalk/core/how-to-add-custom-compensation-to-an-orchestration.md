---
title: 如何向业务流程添加自定义补偿 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- Compensate shape [Orchestration Designer]
- Compensate shape [Orchestration Designer], orchestrations
- Compensation property
- orchestrations, transactional
- orchestrations, customizing
- customizing, orchestrations
- Compensate shape [Orchestration Designer], custom compensation
ms.assetid: d153498d-8f98-42ae-90b9-e3083d669aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c8d6bfa6f935c6d34de093fc066eee420705b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343304"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a><span data-ttu-id="dbf30-102">如何向业务流程添加自定义补偿</span><span class="sxs-lookup"><span data-stu-id="dbf30-102">How to Add Custom Compensation to an Orchestration</span></span>
<span data-ttu-id="dbf30-103">配置为长时间运行的业务流程事务可以具有自定义补偿代码来撤销事务的影响。</span><span class="sxs-lookup"><span data-stu-id="dbf30-103">An orchestration transaction that is configured as long running can have custom compensation code to reverse or undo the effects of the transaction.</span></span> <span data-ttu-id="dbf30-104">如果业务流程已成功完成并已由另一个业务流程调用，调用业务流程可以调用其补偿块使用**补偿**形状。</span><span class="sxs-lookup"><span data-stu-id="dbf30-104">If the orchestration has completed successfully and has been called by another orchestration, the calling orchestration can invoke its compensation block using a **Compensate** shape.</span></span>  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a><span data-ttu-id="dbf30-105">若要指定业务流程将使用自定义补偿</span><span class="sxs-lookup"><span data-stu-id="dbf30-105">To specify that an orchestration will use custom compensation</span></span>  
  
1.  <span data-ttu-id="dbf30-106">在业务流程视图窗口中，选择**业务流程属性**。</span><span class="sxs-lookup"><span data-stu-id="dbf30-106">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="dbf30-107">在属性窗口中，选择**自定义**的下拉列表中**补偿**属性。</span><span class="sxs-lookup"><span data-stu-id="dbf30-107">In the Properties window, select **Custom** in the drop-down for the **Compensation** property.</span></span>  
  
     <span data-ttu-id="dbf30-108">**补偿**选项卡旁边将显示**业务流程**设计图面底部的选项卡。</span><span class="sxs-lookup"><span data-stu-id="dbf30-108">The **Compensation** tab appears next to the **Orchestration** tab at the bottom of the Design Surface.</span></span>  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a><span data-ttu-id="dbf30-109">若要设计为业务流程的自定义补偿</span><span class="sxs-lookup"><span data-stu-id="dbf30-109">To design custom compensation for an orchestration</span></span>  
  
1.  <span data-ttu-id="dbf30-110">单击**补偿**设计图面底部的选项卡。</span><span class="sxs-lookup"><span data-stu-id="dbf30-110">Click the **Compensation** tab at the bottom of the Design Surface.</span></span>  
  
     <span data-ttu-id="dbf30-111">**补偿设计图面**出现。</span><span class="sxs-lookup"><span data-stu-id="dbf30-111">The **Compensation Design Surface** appears.</span></span>  
  
2.  <span data-ttu-id="dbf30-112">添加到形状**补偿设计图面**就像在**业务流程设计图面**。</span><span class="sxs-lookup"><span data-stu-id="dbf30-112">Add shapes to the **Compensation Design Surface** just as you would in the **Orchestration Design Surface**.</span></span>  
  
     <span data-ttu-id="dbf30-113">有关详细信息，请参阅[向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf30-113">For more information, see [Adding Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf30-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbf30-114">See Also</span></span>  
 [<span data-ttu-id="dbf30-115">使业务流程成为事务性业务流程</span><span class="sxs-lookup"><span data-stu-id="dbf30-115">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)