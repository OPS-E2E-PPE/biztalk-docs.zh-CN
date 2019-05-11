---
title: 一些设计原则在业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business processes, design principals
- designing, design principals
- process management solution tutorial, dividing business processes
- patterns [process management solutions], design principals
ms.assetid: 688b970f-8e64-4a47-bcc5-bdb9c5195902
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ac5e05dd1bdedc9d1a24f00031454e88c533e55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243339"
---
# <a name="some-design-principles-in-the-business-process-management-solution"></a>在业务流程管理解决方案中的一些设计原则
本主题开始有关将业务流程划分成阶段的一般准则。 然后将对要考虑的一些解决方案的业务流程、 程序集，以及与这些准则和业务要求相关的应用程序的结构。 有关业务要求的详细信息，请参阅"业务需求"中[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。  
  
## <a name="dividing-business-processes"></a>将业务流程划分  
 通常在考虑业务流程，第一个灵感是将其视为单个整体流程。 这并不总是最佳设计。 对于 Southridge Video 订单是长时间运行的业务流程，一个进程，可能需要一年时间才能完成。 在此期间，可能会更改业务流程本身。 若要允许对业务流程的更新而不会中断在处理订单，Southridge Video 订单处理划分为若干阶段。  
  
 何处划分过程非常重要，到过程的哪些部分可以确定版本，以及允许对未完成的订单进行中断的类型。 Southridge Video 解决方案使用四个常规条件来确定各个阶段：  
  
- 在业务流程中步骤的逻辑分组。  
  
- 业务流程中操作的范围。  
  
- 情况可版本，在给定业务流程的流程元素。  
  
- 完成长期操作后，应该结束业务流程。  
  
  四个，第一个和第三个是最重要因为通常会比逻辑分组或版本的明显元素比以往更多的操作的作用域。 但请注意，不要结束业务流程作用域。  
  
  如果您看一下第一阶段，该业务流程**CableOrder1.odx**，可以看到它有效地以对功能系统的请求-响应序列结尾。 这是因为它是涉及完成此订单的实际物理工作流程的一部分结束该阶段的适当位置。 具有业务流程末尾附近的较长的处理步骤可保证，冻结后，业务流程将快速结束。 这可加快作为一个整体的解决方案移动到较新版本的业务流程。  
  
> [!NOTE]
>  尽管该解决方案将流程拆分成不连续的阶段，但解决方案监视，可看到通过 BAM 使用连续的视图。  
  
## <a name="order-action-broker-and-manager-orchestrations"></a>订单操作、 代理和管理器业务流程  
 除了将订单处理划分阶段，您还会注意到，每个订单操作-分析订单、 订单验证，例如，订单取消 — 在单独的业务流程。 将每个操作放在单独的业务流程将分离的几个阶段的结构中的操作。 这进而使更灵活地设计和版本控制订单处理阶段。  
  
 Orderbroker 和 ordermanager 出于类似原因位于不同的业务流程。 解决方案的设计允许使用多个 ordermanager 来处理其他类型的订单。 将 broker 与 manager 的分离，它们也可以位于不同的位置。 有关 orderbroker 设计的其他详细信息，请参阅"为什么 orderbroker？" 在中[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。 订单管理器的详细信息，请参阅[进程管理器逻辑](../core/process-manager-logic.md)。  
  
## <a name="assemblies"></a>程序集  
 若要支持的组件版本控制，并以支持将组件移至其他服务器进行组织解决方案中的程序集。 例如，架构位于单独的程序集。 特别是，orderbroker 的架构是在其自己的程序集。 这使他们能够进行版本控制而无需更改解决方案的其他元素。 它还使得更容易将 orderbroker 移到单独的组或服务器。 有关版本控制应用程序和架构程序集的详细信息，请参阅[业务流程管理解决方案进行版本控制](../core/versioning-the-business-process-management-solution.md)。  
  
## <a name="applications"></a>应用程序  
 如果您在 BizTalk 管理控制台中查看，可以看到生成的解决方案包含三个单独的应用程序：  
  
- **BTSScn.BPM.OrderBrokerApp**包含 orderbroker 的应用程序  
  
- **BTSScn.BPM.CableOrderApp**包含订单处理组件的应用程序  
  
- **BTSScn.BPM.MessagingApp**，收集共享的其他两个应用程序项目的应用程序  
  
  解决方案的由三部分组成的结构是可能由于 BizTalk 应用程序能够使用同一 BizTalk 组中其他应用程序中的项目的功能。 若要使用另一个应用程序的项目，您将添加对其他应用程序中引用的应用程序的引用。 有关引用其他应用程序的信息，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
  常见项目放置在单独的应用程序中，您可能，以更新组件仅在一个位置。 共享的组件可以是任何内容，包括端口。 例如，解决方案中的业务流程将错误发送给错误报告端口。 该端口位于消息传送应用程序 BTSScn.BPM.MessagingApp 中，整个解决方案可以使用它。  
  
  结构化解决方案，为三个应用程序还可以更轻松地移动到其他服务器上解决方案的部分。 可以将每个应用程序和其引用的应用程序转换成 MSI 文件。 然后可以安装在另一台计算机上的该 MSI 文件。 有关将应用程序转换到 MSI 文件的信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
### <a name="the-test-solution"></a>测试解决方案  
 你将在 BizTalk 管理控制台还三个测试应用程序：**BTSScn.BPM.OrderBrokerApp.Test**， **BTSScn.BPM.CableOrderApp.Test**，和**BTSScn.BPM.MessagingApp.Test**。 以下三个应用程序包含仅用于测试应用程序的端口，并且由主应用程序引用。 使用此结构，以供主应用程序用来构造测试解决方案，同时分离测试端口与该解决方案在的测试端口。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)