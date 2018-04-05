---
title: 组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, components
ms.assetid: 8793534f-5bd7-4cd3-9a42-8f0895f91007
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca9c5fdb04ffd182a8c51963c1a5c7cf5e7f8c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="components"></a>Components
你使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]组件来实现 SWIFT 为中心的中间件解决方案，以方便贸易合作伙伴关系、 企业应用程序集成 (EAI) 和应用程序和业务工作流自动化。 这些组件包括：  
  
-   **SWIFT 消息架构。** 使用 XML 架构定义语言 (XSD) 的符合标准的架构，以便为使用 SWIFT 的 XML 分析本机 SWIFT 平面文件消息的管道组件和[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]运行时。 将 SWIFT 数据转换为 XML 后，你将使用映射将其转换为另一种格式，如分隔的平面文件或位置的平面文件。 此转换，可使用这些文件中的现有应用程序。 为仅限验证方案还类似于使用而无需任何映射的 XML 数据。 SWIFT 架构还强制实施 SWIFT 定义的数据和格式规则。 有关此版本中提供的架构的完整列表，请参阅[支持消息](../../adapters-and-accelerators/accelerator-swift/supported-messages.md)。  
  
-   **SWIFT 验证策略和框架。** 你使用[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]业务规则引擎 (BRE) 策略来验证，并强制实施 SWIFT 定义数据、 格式、 网络和使用情况规则。 SWIFT 反汇编程序和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]验证组件调用 BRE。 验证错误将收集到错误集合对象，在发布到 MessageBox 数据库之前，具有特殊的提升属性的错误消息标记。  
  
-   **SWIFT 管道组件。** 使用 BizTalk 管道反汇编程序和汇编程序组件来处理 SWIFT 消息。 SWIFT 反汇编程序动态解析 SWIFT 消息类型、 反汇编 SWIFT 消息批次，将消息分析为 XML，并验证针对 SWIFT 数据格式和网络和使用情况的规则的消息。 SWIFT 汇编程序回 SWIFT 平面文件格式序列化 XML 数据。  
  
-   [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]  **验证组件。** [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]程序集提供类应用程序编程接口 (Api) 可以在 BizTalk 业务流程表达式形状中使用。 这些类提供由 SWIFT 反汇编程序执行的相同 SWIFT 消息验证功能。 此功能允许消息验证后要采取在业务流程中的位置 （例如，转换或修改 SWIFT 消息）。  
  
-   **消息修复和新的提交。** 使用消息修复和新提交功能修复的消息的未通过验证，或无法分析 SWIFT 反汇编程序，也可以创建和提交新消息。 此功能通过 MrsrRepair 业务流程，MRSR SharePoint 站点实现和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
-   **FRR 响应对帐。** FRR 响应对帐协调 FIN 响应 A4SWIFT，最初发送的消息与启用的生成消息响应关联集的自定义处理。 FRR 实现通过 FrrMain 业务流程，FRR 接收位置，并为 MQSeries 发送端口和 BizTalk 适配器。  
  
-   **软件开发工具包 (SDK)。** 该 SDK 提供工具、 教程和示例来帮助进行开发和部署基于 SWIFT BizTalk 解决方案。 这些解决方案包括：  
  
    -   [端到端教程](../../adapters-and-accelerators/accelerator-swift/end-to-end-tutorial2.md)  
  
    -   [BRE 部署实用工具](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)  
  
    -   [SWIFT 标头和预告片架构](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   **文档。** [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]帮助介绍需要规划、 开发、 部署和维护基于 SWIFT BizTalk 解决方案。  
  
## <a name="see-also"></a>另请参阅  
[运行时、 消息修复、 FIN 响应和消息传送](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)