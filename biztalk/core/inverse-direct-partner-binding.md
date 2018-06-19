---
title: 反直接合作伙伴绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c9fe5e51f9f63ea098fa623dafbceeb670e75f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262389"
---
# <a name="inverse-direct-partner-binding"></a><span data-ttu-id="ff3f4-102">反直接合作伙伴绑定</span><span class="sxs-lookup"><span data-stu-id="ff3f4-102">Inverse Direct Partner Binding</span></span>
<span data-ttu-id="ff3f4-103">业务流程管理解决方案设计为在无需停止应用程序的情况下可以更改订单处理阶段。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-103">The Business Process Management solution is designed so that you can change the order processing stages without stopping the application.</span></span> <span data-ttu-id="ff3f4-104">若要分离的处理阶段 (**CableOrder1**， **CableOrder2**) 从进程管理器 (**OrderManager**)，该解决方案使用的不同方法绑定之间这些业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-104">In order to decouple the processing stages (**CableOrder1**, **CableOrder2**) from the process manager (**OrderManager**), the solution uses a different technique for binding ports among these orchestrations.</span></span>  
  
 <span data-ttu-id="ff3f4-105">在绑定的常用的窗体，指示绑定， **OrderManager**业务流程将用作进程阶段业务流程的值的合作伙伴业务流程端口属性。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-105">In the usual form of binding, direct binding, the **OrderManager** orchestration would use the process stage orchestration as the value for the Partner Orchestration Port property.</span></span> <span data-ttu-id="ff3f4-106">在此类的直接绑定中**OrderManager**业务流程依赖于过程阶段的强名称 （其中包括版本）。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-106">In direct binding like this the **OrderManager** orchestration depends on the strong names (which include the versions) of the process stages.</span></span> <span data-ttu-id="ff3f4-107">这使得无法改变过程阶段，而不必重新部署**OrderManager**业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-107">This makes it impossible to alter the process stages without re-deploying the **OrderManager** orchestration.</span></span> <span data-ttu-id="ff3f4-108">有关直接绑定的详细信息，请参阅[端口绑定](../core/port-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-108">For more information about direct binding, see [Port Bindings](../core/port-bindings.md).</span></span> <span data-ttu-id="ff3f4-109">直接绑定可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff3f4-109">Direct Binding might be illustrated this way:</span></span>  
  
 <span data-ttu-id="ff3f4-110">![示意图反直接合作伙伴绑定](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="ff3f4-110">![Diagram of Inverse Direct Partner Binding](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span></span>  
  
 <span data-ttu-id="ff3f4-111">在反转直接合作伙伴绑定中，接收业务流程（而不是源业务流程）将指定绑定。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-111">In inverse direct partner binding, the receiving orchestration specifies the binding, rather than the originating orchestration.</span></span> <span data-ttu-id="ff3f4-112">上的端口**OrderManager**只绑定到自身。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-112">The port on the **OrderManager** is simply bound to itself.</span></span> <span data-ttu-id="ff3f4-113">即上的端口**OrderManager**为指定**PartnerOrchestrationPort**属性。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-113">That is, the port on the **OrderManager** is specified for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="ff3f4-114">但是，使用相应过程阶段业务流程**OrderManager**端口的值作为**PartnerOrchestrationPort**属性。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-114">However, the process stage orchestrations use the appropriate **OrderManager** port as the value for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="ff3f4-115">这会使**OrderManager**从版本的过程阶段业务流程，并允许它们无需重新部署更改**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-115">This decouples the **OrderManager** from the versions of the process stage orchestrations and allows them to be changed without redeploying the **OrderManager**.</span></span> <span data-ttu-id="ff3f4-116">而直接绑定不允许进行此类分离。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-116">Direct binding would not allow this decoupling.</span></span> <span data-ttu-id="ff3f4-117">反转直接合作伙伴绑定可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff3f4-117">Inverse direct partner binding might be shown this way:</span></span>  
  
 <span data-ttu-id="ff3f4-118">![直接绑定示意图](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="ff3f4-118">![Diagram of Direct Binding](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff3f4-119">反转直接绑定也允许像这样与分发列表中的合作伙伴业务流程进行通信。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-119">Inverse direct binding also allows for communicating with partner orchestrations in a distribution-list like way.</span></span> <span data-ttu-id="ff3f4-120">**OrderManger**可以使用单个端口与所有阶段进行通信。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-120">The **OrderManger** can use a single port to communicate with all stages.</span></span> <span data-ttu-id="ff3f4-121">这样，您就可以添加和删除阶段，而无需重新设计业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff3f4-121">This enables you to add and remove stages without redesigning the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3f4-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff3f4-122">See Also</span></span>  
 <span data-ttu-id="ff3f4-123">[实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ff3f4-123">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="ff3f4-124">过程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="ff3f4-124">Process Manager Logic</span></span>](../core/process-manager-logic.md)