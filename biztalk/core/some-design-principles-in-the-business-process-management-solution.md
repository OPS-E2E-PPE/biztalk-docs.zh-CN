---
title: "一些设计中业务流程管理解决方案的原则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business processes, design principals
- designing, design principals
- process management solution tutorial, dividing business processes
- patterns [process management solutions], design principals
ms.assetid: 688b970f-8e64-4a47-bcc5-bdb9c5195902
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b975f94853c155da41f09b2b0ff76a681c1df075
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="some-design-principles-in-the-business-process-management-solution"></a>业务流程管理解决方案中的一些设计原则
本主题将首先介绍有关将业务流程划分为若干阶段的一般准则。 然后将对与这些准则和业务需求有关的该解决方案的某些业务流程、程序集和应用程序的结构进行说明。 有关业务要求的详细信息，请参阅"业务要求"中[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。  
  
## <a name="dividing-business-processes"></a>划分业务流程  
 通常，在考虑业务流程时，首先会将业务流程视为单个整体流程。 这并非总是最佳设计。 对于 Southridge Video，订单是长时间运行的业务流程，即可能需要花费一年时间才能完成的流程。 同时，业务流程本身也可能发生更改。 为允许在不中断正在处理的订单的情况下对业务流程进行更新，可以将 Southridge Video 订单处理划分为若干个阶段。  
  
 在何处划分该流程，这对于可以确定版本的流程部分和允许对未完成的订单进行中断的类型十分重要。 Southridge Video 解决方案使用四个常规条件来确定各个阶段：  
  
-   业务流程中步骤的逻辑分组。  
  
-   业务流程中操作的作用域。  
  
-   在给定业务流程的情况下，可用于确定版本的流程元素。  
  
-   完成长期操作后，应该结束业务流程。  
  
 在以上四个条件中，第一个和第三个是最关键的条件，因为这两个条件适用的操作作用域通常比逻辑分组或要确定版本的明显元素更为广泛。 但是，请注意，不需要在作用域中结束业务流程。  
  
 如果你看一下的第一个阶段，业务流程**CableOrder1.odx**，你将看到它有效地结束与请求-响应序列到设施系统。 这是结束该阶段的适当位置，因为它是涉及完成此订单的实际物理工作的流程的一部分。 将较长的处理步骤放置到接近业务流程末尾处，则可以保证在解除对这些步骤的冻结后将快速结束该业务流程。 这样可以加速将该解决方案整体移至业务流程的更高版本。  
  
> [!NOTE]
>  尽管该解决方案将流程拆分为若干个不连续的阶段，但利用解决方案监视功能，您可以使用 BAM 将其作为连续的视图进行查看。  
  
## <a name="order-action-broker-and-manager-orchestrations"></a>订单操作、OrderBroker 和 OrderManager 业务流程  
 除了将订单处理划分为若干阶段，您还会注意到，每个订单操作（例如分析订单、订单验证和订单取消）都位于单独的业务流程中。 将每个操作放置在单独的业务流程中可以将这些操作与阶段的结构相分离。 因此，这样为设计订单处理阶段并确定其版本提供了更大的灵活性。  
  
 出于类似原因，OrderBroker 和 OrderManager 也位于单独的业务流程中。 该解决方案的设计允许使用多个 OrderManager 来处理其他类型的订单。 通过将 Broker 与 Manager 相分离，它们也可以位于不同的位置。 有关顺序代理的设计的其他详细信息，请参阅"为什么和顺序 Broker？" 在[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。 订单管理器的详细信息，请参阅[过程管理器逻辑](../core/process-manager-logic.md)。  
  
## <a name="assemblies"></a>程序集  
 对该解决方案中的程序集进行组织以支持确定组件的版本以及将组件移至其他服务器。 例如，各架构位于单独的程序集中。 特别是，OrderBroker 的架构位于其自身的程序集中。 这样就可以确定这些架构的版本，而无需更改该解决方案的其他元素。 同时，还可以更便捷地将 OrderBroker 移至单独的组或服务器。 有关版本控制应用程序和架构程序集的详细信息，请参阅[版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md)。  
  
## <a name="applications"></a>应用程序  
 如果你查看在 BizTalk 管理控制台中，你可以看到生成的解决方案由三个单独的应用程序组成：  
  
-   **BTSScn.BPM.OrderBrokerApp**、 包含顺序 broker 的应用程序  
  
-   **BTSScn.BPM.CableOrderApp**、 包含订单处理组件的应用程序  
  
-   **BTSScn.BPM.MessagingApp**的应用程序收集的其他两个应用共享的项目  
  
 该解决方案的结构可以由三部分组成，因为 BizTalk 应用程序能够使用同一 BizTalk 组内其他应用程序中的项目。 若要使用其他应用程序的项目，请添加从引用应用程序指向其他应用程序的引用。 有关引用其他应用程序的信息，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
 通过将常见项目放置在单独的应用程序中，您可能只需在一个位置中更新组件。 共享组件可以是包括端口在内的任何组件。 例如，该解决方案中的业务流程可以将错误发送到错误报告端口。 该端口位于消息传送应用程序 BTSScn.BPM.MessagingApp 中，在该应用程序中，整个解决方案都可使用该端口。  
  
 将解决方案的结构设置为由三个应用程序组成，这样也可以更便捷地将解决方案的各个部分移至其他服务器上。 可以将每个应用程序及其引用的应用程序转换为 MSI 文件。 然后可以将该 MSI 文件安装在其他计算机上。 有关将应用程序转换到 MSI 文件的信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
### <a name="the-test-solution"></a>测试解决方案  
 将 BizTalk 管理控制台中的还三个测试应用程序： **BTSScn.BPM.OrderBrokerApp.Test**， **BTSScn.BPM.CableOrderApp.Test**，和**BTSScn.BPM.MessagingApp.Test**。 这三个应用程序只包含用于测试应用程序的端口，主应用程序将引用这些测试应用程序。 使用这种结构，主应用程序使用的测试端口可以构造测试解决方案，同时允许将这些测试端口与该解决方案相分离。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)