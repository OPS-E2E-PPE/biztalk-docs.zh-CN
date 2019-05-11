---
title: 反转直接合作伙伴绑定 |Microsoft Docs
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
ms.openlocfilehash: ead2c7e7ddf7a56d9a7746f47a7a3fbf1822d7f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330004"
---
# <a name="inverse-direct-partner-binding"></a><span data-ttu-id="1f627-102">反转直接合作伙伴绑定</span><span class="sxs-lookup"><span data-stu-id="1f627-102">Inverse Direct Partner Binding</span></span>
<span data-ttu-id="1f627-103">业务流程管理解决方案，以便您可以更改订单处理阶段，而无需停止应用程序设计。</span><span class="sxs-lookup"><span data-stu-id="1f627-103">The Business Process Management solution is designed so that you can change the order processing stages without stopping the application.</span></span> <span data-ttu-id="1f627-104">为了将处理阶段 (**CableOrder1**， **CableOrder2**) 从进程管理器 (**OrderManager**)，该解决方案使用的另一种技术这些业务流程之间绑定端口。</span><span class="sxs-lookup"><span data-stu-id="1f627-104">In order to decouple the processing stages (**CableOrder1**, **CableOrder2**) from the process manager (**OrderManager**), the solution uses a different technique for binding ports among these orchestrations.</span></span>  
  
 <span data-ttu-id="1f627-105">在常用的绑定格式，直接绑定**OrderManager**业务流程将处理阶段业务流程作为值使用合作伙伴业务流程端口属性。</span><span class="sxs-lookup"><span data-stu-id="1f627-105">In the usual form of binding, direct binding, the **OrderManager** orchestration would use the process stage orchestration as the value for the Partner Orchestration Port property.</span></span> <span data-ttu-id="1f627-106">在此类的直接绑定**OrderManager**业务流程所依赖的强名称 （其中包括版本） 的处理阶段。</span><span class="sxs-lookup"><span data-stu-id="1f627-106">In direct binding like this the **OrderManager** orchestration depends on the strong names (which include the versions) of the process stages.</span></span> <span data-ttu-id="1f627-107">这使我们无法更改处理阶段无需重新部署**OrderManager**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1f627-107">This makes it impossible to alter the process stages without re-deploying the **OrderManager** orchestration.</span></span> <span data-ttu-id="1f627-108">有关直接绑定的详细信息，请参阅[端口绑定](../core/port-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="1f627-108">For more information about direct binding, see [Port Bindings](../core/port-bindings.md).</span></span> <span data-ttu-id="1f627-109">直接绑定可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="1f627-109">Direct Binding might be illustrated this way:</span></span>  
  
 <span data-ttu-id="1f627-110">![反转直接合作伙伴绑定关系图](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="1f627-110">![Diagram of Inverse Direct Partner Binding](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span></span>  
  
 <span data-ttu-id="1f627-111">在反转直接合作伙伴绑定，接收业务流程指定绑定，而不是源业务流程。</span><span class="sxs-lookup"><span data-stu-id="1f627-111">In inverse direct partner binding, the receiving orchestration specifies the binding, rather than the originating orchestration.</span></span> <span data-ttu-id="1f627-112">上的端口**OrderManager**只绑定到其自身。</span><span class="sxs-lookup"><span data-stu-id="1f627-112">The port on the **OrderManager** is simply bound to itself.</span></span> <span data-ttu-id="1f627-113">也就是说上的端口**OrderManager**为指定**PartnerOrchestrationPort**属性。</span><span class="sxs-lookup"><span data-stu-id="1f627-113">That is, the port on the **OrderManager** is specified for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="1f627-114">但是，处理阶段业务流程使用适当**OrderManager**端口的值作为**PartnerOrchestrationPort**属性。</span><span class="sxs-lookup"><span data-stu-id="1f627-114">However, the process stage orchestrations use the appropriate **OrderManager** port as the value for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="1f627-115">这会使**OrderManager**版本的过程阶段业务流程，并允许它们进行更改而无需重新部署**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="1f627-115">This decouples the **OrderManager** from the versions of the process stage orchestrations and allows them to be changed without redeploying the **OrderManager**.</span></span> <span data-ttu-id="1f627-116">直接绑定不允许进行这种分离。</span><span class="sxs-lookup"><span data-stu-id="1f627-116">Direct binding would not allow this decoupling.</span></span> <span data-ttu-id="1f627-117">反转直接合作伙伴绑定可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="1f627-117">Inverse direct partner binding might be shown this way:</span></span>  
  
 <span data-ttu-id="1f627-118">![直接绑定关系图](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="1f627-118">![Diagram of Direct Binding](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f627-119">反转直接绑定还允许与合作伙伴业务流程等方式分发列表中进行通信。</span><span class="sxs-lookup"><span data-stu-id="1f627-119">Inverse direct binding also allows for communicating with partner orchestrations in a distribution-list like way.</span></span> <span data-ttu-id="1f627-120">**OrderManger**可以使用单个端口与所有阶段进行通信。</span><span class="sxs-lookup"><span data-stu-id="1f627-120">The **OrderManger** can use a single port to communicate with all stages.</span></span> <span data-ttu-id="1f627-121">这使您能够添加和删除阶段，而无需重新设计业务流程。</span><span class="sxs-lookup"><span data-stu-id="1f627-121">This enables you to add and remove stages without redesigning the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f627-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f627-122">See Also</span></span>  
 <span data-ttu-id="1f627-123">[业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="1f627-123">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="1f627-124">进程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="1f627-124">Process Manager Logic</span></span>](../core/process-manager-logic.md)