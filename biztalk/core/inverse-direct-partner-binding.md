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
# <a name="inverse-direct-partner-binding"></a>反转直接合作伙伴绑定
业务流程管理解决方案，以便您可以更改订单处理阶段，而无需停止应用程序设计。 为了将处理阶段 (**CableOrder1**， **CableOrder2**) 从进程管理器 (**OrderManager**)，该解决方案使用的另一种技术这些业务流程之间绑定端口。  
  
 在常用的绑定格式，直接绑定**OrderManager**业务流程将处理阶段业务流程作为值使用合作伙伴业务流程端口属性。 在此类的直接绑定**OrderManager**业务流程所依赖的强名称 （其中包括版本） 的处理阶段。 这使我们无法更改处理阶段无需重新部署**OrderManager**业务流程。 有关直接绑定的详细信息，请参阅[端口绑定](../core/port-bindings.md)。 直接绑定可能如下所示：  
  
 ![反转直接合作伙伴绑定关系图](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")  
  
 在反转直接合作伙伴绑定，接收业务流程指定绑定，而不是源业务流程。 上的端口**OrderManager**只绑定到其自身。 也就是说上的端口**OrderManager**为指定**PartnerOrchestrationPort**属性。 但是，处理阶段业务流程使用适当**OrderManager**端口的值作为**PartnerOrchestrationPort**属性。 这会使**OrderManager**版本的过程阶段业务流程，并允许它们进行更改而无需重新部署**OrderManager**。 直接绑定不允许进行这种分离。 反转直接合作伙伴绑定可能如下所示：  
  
 ![直接绑定关系图](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")  
  
> [!NOTE]
>  反转直接绑定还允许与合作伙伴业务流程等方式分发列表中进行通信。 **OrderManger**可以使用单个端口与所有阶段进行通信。 这使您能够添加和删除阶段，而无需重新设计业务流程。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [进程管理器逻辑](../core/process-manager-logic.md)