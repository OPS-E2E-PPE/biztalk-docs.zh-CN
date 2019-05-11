---
title: 使用失败消息的订阅 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0244ea33744d592377261c8e532d981cc5d828aa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529672"
---
# <a name="working-with-failed-message-subscriptions"></a>使用失败的消息订阅
当 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]拆装器进程 （分析和验证） 一条消息，它将升级该消息的属性。 如果 A4SWIFT 接收到消息的入站批处理的一部分，这些升级的属性提供的正确性和消息有效性的信息，以及与批处理相关的信息。 有关这些属性的完整列表，请参阅[A4SWIFT_ * 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
 与本机 BizTalk 拆装器，不同 A4SWIFT 拆装器不会挂起一条消息，处理会生成错误或失败时。 相反，它将失败的消息到 MessageBox 数据库发布，就像一样是有效的消息。 因此，失败的消息可以到 MessageBox 数据库中执行错误详细信息。 可以从 MessageBox 数据库中检索消息、 处理和修复消息，并甚至回 MessageBox 数据库中重新提交消息。 你将无法再执行这些任务的大部分，如果消息已实际*挂起*。  
  
 您可以标识 A4SWIFT 已通过升级属性发布到 MessageBox 数据库作为失败或错误消息。 在处理失败的消息时，SWIFT 反汇编程序填充，并将提升**A4SWIFT_Failed**属性，以及一个或多个其他的以下属性，将消息发布到 MessageBox 数据库之前：  
  
- **A4SWIFT_ParseErrors**指示分析错误 （如格式不正确的数据） 处理过程中遇到的数目。  
  
- **A4SWIFT_XmlValidationErrors**指示 XML 验证错误 （例如无效的数据或架构方面的类型不正确） 处理过程中遇到的数目。  
  
- **A4SWIFT_BreValidationErrors**指示处理过程中遇到的业务规则引擎 (BRE) 验证错误 （如中断的 SWIFT 网络规则的数据） 数。  
  
- **A4SWIFT_Failed**是**true**时的任何 count 的上述属性值大于零，或者**false**当计数等于零。  
  
  这些属性是 Microsoft 的所有部分。Solutions.A4SWIFT.Property 命名空间。 有关这些及其他升级的属性的详细信息，请参阅[A4SWIFT_ * 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
  若要捕获或检索失败的消息，您需要在其中创建筛选器表达式 （订阅） 发送端口或业务流程接收形状，包括一些，上面列出的属性作为**AND**表达式的子句。  
  
  例如，若要订阅所有失败消息，您将添加以下子句 (作为**AND**子句是否存在其他子句):  
  
  Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **，则返回 true**  
  
  若要仅分析失败的消息的订阅，同时添加以下子句：  
  
  **和**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **，则返回 true**，**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors = = 0，**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors = = 0;  
  
  相反，对于发送端口或业务流程设计为处理有效的消息，包括"**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **false**"作为其筛选器表达式中的子句。  
  
> [!NOTE]
>  如果订阅重叠，A4SWIFT 将完成的所有订阅。 也就是说，如果 （发送端口或业务流程） 的多个服务有由某个特定消息的筛选器表达式，所有此类服务将收到同一消息。 例如，如果发送端口订阅所有失败消息和业务流程订阅仅分析失败消息，这两个订阅将满足 A4SWIFT 处理某个消息时遇到分析错误时。 请务必跨服务消除不需要的重叠的订阅中。  
> 
> [!NOTE]
>  A4SWIFT A4SWIFT 接收和处理消息，并将该消息发布到 MessageBox 数据库中，但消息不满足任何订阅，如果将挂起的消息的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]错误，指出缺少的订阅服务器。 例如，如果订阅的所有消息的服务"A4SWIFT_Failed = = false"，但没有服务订阅消息的"A4SWIFT_Failed = = true"，则分析失败的消息或验证确实将挂起由于缺乏订阅服务器。 实际上，这种情况下，可模拟传统挂起失败的消息。 请确保订阅不希望具有挂起的所有消息。 有关 MessageBox 数据库订阅的更多详情请参见 BizTalk Server 帮助、 发送端口，业务流程和筛选器表达式。  
  
 本部分包含：  
  
-   [失败的消息和 ErrorCollection 对象](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)