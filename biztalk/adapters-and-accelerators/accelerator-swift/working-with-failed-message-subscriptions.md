---
title: "使用失败消息订阅 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6540259fd6983fd418e57ff700de3f1b550016ec
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="working-with-failed-message-subscriptions"></a>使用失败的邮件订阅
当[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]反汇编程序进程 （分析和验证） 一条消息，这样还有助于提升该消息的属性。 如果 A4SWIFT 作为入站批处理的一部分接收消息，这些提升的属性提供信息的正确性和有效性的消息，以及与批处理相关的信息。 有关这些属性的完整列表，请参阅[A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
 与本机 BizTalk 反汇编程序中，不同 A4SWIFT 反汇编程序不会挂起消息，处理生成错误或失败时。 相反，它将在失败的消息到 MessageBox 数据库发布，就像将有效的消息。 因此，失败的消息可以传送到 MessageBox 数据库的错误详细信息。 可以从 MessageBox 数据库中检索消息、 处理和修复消息，并甚至回 MessageBox 数据库重新提交消息。 你将无法执行大多数这些任务，如果消息已实际*挂起*。  
  
 你可以标识 A4SWIFT 具有由其提升属性发布到 MessageBox 数据库作为失败或错误的消息。 当处理将失败的消息时，SWIFT 反汇编程序填充，并促进**A4SWIFT_Failed**属性，和一个或多个其他的以下属性，发布到 MessageBox 数据库的消息之前对：  
  
-   **A4SWIFT_ParseErrors**指示的分析 （如格式不正确的数据） 处理过程中遇到的错误数。  
  
-   **A4SWIFT_XmlValidationErrors**表示数据 （如无效的数据或架构方面的类型不正确） XML 验证错误处理过程中遇到的数目。  
  
-   **A4SWIFT_BreValidationErrors**指示处理过程中遇到的业务规则引擎 (BRE) （如中断 SWIFT 网络规则的数据） 的验证错误数。  
  
-   **A4SWIFT_Failed**是**true**时的任何计数的上述属性是大于零，或**false**时计数等于零。  
  
 这些属性是所有属于[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.A4SWIFT.Property 命名空间。 有关这些及其他提升的属性的详细信息，请参阅[A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
 若要捕获或检索失败的消息，你需要在其中创建筛选器表达式 （订阅） 发送端口或业务流程接收包括一些上面列出的属性的形状作为**AND**子句的表达式。  
  
 例如，若要订阅所有失败的消息，你将添加以下子句 (作为**AND**子句是否存在其他子句):  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **true**  
  
 若要订阅包含仅分析失败的消息，一起添加以下子句：  
  
 **和** [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **true**，**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors = = 0，**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors = = 0;  
  
 相反，对于发送端口或业务流程用于处理仅有效的消息，包括"**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **false**"作为其筛选器表达式中的子句。  
  
> [!NOTE]
>  如果订阅重叠，A4SWIFT 将完成所有订阅。 即，如果多个服务 （发送端口或业务流程） 具有满足特定的消息的筛选器表达式，所有此类服务将收到同一消息。 例如，如果发送端口订阅的所有失败消息和业务流程订阅到唯一的消息，但分析失败，A4SWIFT 遇到分析错误时处理消息时将能满足这两个订阅。 请务必在服务之间消除不需要的重叠的订阅中。  
  
> [!NOTE]
>  A4SWIFT 如果 A4SWIFT 接收和处理消息，并将该消息发布到 MessageBox 数据库，但消息不满足任何订阅，将会挂起的消息的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]错误，指示缺乏订阅服务器。 例如，如果您具有订阅的所有消息的服务"A4SWIFT_Failed = = false"，但没有任何服务订阅消息其中"A4SWIFT_Failed = = true"，然后分析失败的消息或验证确实将挂起由于缺乏订阅服务器。 实际上，这种情况下，可模拟传统挂起失败的消息。 请确保订阅不希望具有挂起的所有消息。 请参阅 BizTalk Server 帮助以 MessageBox 数据库订阅有关的其他详细信息、 发送端口，业务流程，和筛选表达式。  
  
 本部分包含：  
  
-   [失败的消息和 ErrorCollection 对象](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)