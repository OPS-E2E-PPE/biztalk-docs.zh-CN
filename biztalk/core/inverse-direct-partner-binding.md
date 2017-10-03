---
title: "反直接合作伙伴绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c9fe5e51f9f63ea098fa623dafbceeb670e75f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="inverse-direct-partner-binding"></a>反直接合作伙伴绑定
业务流程管理解决方案设计为在无需停止应用程序的情况下可以更改订单处理阶段。 若要分离的处理阶段 (**CableOrder1**， **CableOrder2**) 从进程管理器 (**OrderManager**)，该解决方案使用的不同方法绑定之间这些业务流程的端口。  
  
 在绑定的常用的窗体，指示绑定， **OrderManager**业务流程将用作进程阶段业务流程的值的合作伙伴业务流程端口属性。 在此类的直接绑定中**OrderManager**业务流程依赖于过程阶段的强名称 （其中包括版本）。 这使得无法改变过程阶段，而不必重新部署**OrderManager**业务流程。 有关直接绑定的详细信息，请参阅[端口绑定](../core/port-bindings.md)。 直接绑定可能如下所示：  
  
 ![示意图反直接合作伙伴绑定](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")  
  
 在反转直接合作伙伴绑定中，接收业务流程（而不是源业务流程）将指定绑定。 上的端口**OrderManager**只绑定到自身。 即上的端口**OrderManager**为指定**PartnerOrchestrationPort**属性。 但是，使用相应过程阶段业务流程**OrderManager**端口的值作为**PartnerOrchestrationPort**属性。 这会使**OrderManager**从版本的过程阶段业务流程，并允许它们无需重新部署更改**OrderManager**。 而直接绑定不允许进行此类分离。 反转直接合作伙伴绑定可能如下所示：  
  
 ![直接绑定示意图](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")  
  
> [!NOTE]
>  反转直接绑定也允许像这样与分发列表中的合作伙伴业务流程进行通信。 **OrderManger**可以使用单个端口与所有阶段进行通信。 这样，您就可以添加和删除阶段，而无需重新设计业务流程。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [过程管理器逻辑](../core/process-manager-logic.md)