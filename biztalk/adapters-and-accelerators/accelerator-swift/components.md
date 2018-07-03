---
title: 组件 |Microsoft Docs
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
ms.openlocfilehash: 6c8595aafb14b42240a5f781faf481977be2b821
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014678"
---
# <a name="components"></a>组件
使用 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]组件来实现 SWIFT 为中心的中间件解决方案，可协助贸易合作伙伴关系、 企业应用程序集成 (EAI) 和应用程序和业务工作流自动化。 这些组件包括：  
  
- **SWIFT 消息架构。** 使用 XML 架构定义语言 (XSD) 的符合架构，以便于本机 SWIFT 的平面文件消息解析为 XML 使用 SWIFT 管道组件和[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]运行时。 将 SWIFT 数据转换为 XML 后，使用映射来将其转换为另一种格式，如分隔平面文件或位置平面文件。 此转换，可将现有应用程序中使用这些文件。 此外可以为仅限验证的方案如使用没有任何映射的 XML 数据。 SWIFT 架构还强制实施 SWIFT 定义的数据和格式规则。 有关此版本中提供的架构的完整列表，请参阅[支持消息](../../adapters-and-accelerators/accelerator-swift/supported-messages.md)。  
  
- **SWIFT 验证策略和框架。** 您使用[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]业务规则引擎 (BRE) 策略来验证和强制实施 SWIFT 定义数据、 格式、 网络和使用情况规则。 SWIFT 反汇编程序和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]验证组件调用 BRE。 验证错误将收集到错误集合对象，且错误的消息发布到 MessageBox 数据库之前标记为特殊的升级属性。  
  
- **SWIFT 管道组件。** 使用 BizTalk 管道拆装器和组装器组件来处理 SWIFT 消息。 SWIFT 反汇编程序动态解析 SWIFT 消息类型、 反汇编 SWIFT 消息批，将消息分析为 XML，并验证消息的 SWIFT 数据格式和网络和使用情况的规则。 SWIFT 汇编程序回 SWIFT 平面文件格式序列化 XML 数据。  
  
- [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]  **验证组件。** [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]程序集提供类应用程序编程接口 (Api) 可以在 BizTalk 业务流程表达式形状中使用。 这些类提供由 SWIFT 反汇编程序执行相同的 SWIFT 消息验证功能。 此功能允许消息验证后要采取的业务流程中的位置 （例如，转换或者修改 SWIFT 消息）。  
  
- **消息修复和新提交。** 使用消息修复和新提交功能修复的消息的未通过验证，或无法分析 SWIFT 反汇编程序，或者如何创建和提交新消息。 此功能实现通过 MrsrRepair 流程，MRSR SharePoint 站点和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
- **FRR 响应对帐。** FRR 响应对帐会 FIN 响应协调与 A4SWIFT，最初发送的消息启用的生成的消息响应相关集的自定义处理。 通过 FrrMain 业务流程实现 FRR、 FRR 接收位置和 MQSeries 的发送端口和 BizTalk 适配器。  
  
- **软件开发工具包 (SDK)。** 该 SDK 提供工具、 教程和示例，帮助开发和部署基于 SWIFT 的 BizTalk 解决方案。 这些解决方案包括：  
  
  -   [端到端教程](../../adapters-and-accelerators/accelerator-swift/end-to-end-tutorial2.md)  
  
  -   [BRE 部署实用工具](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)  
  
  -   [SWIFT 标头和尾部架构](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
- **文档。** [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] 帮助介绍需要规划、 开发、 部署和维护基于 SWIFT 的 BizTalk 解决方案。  
  
## <a name="see-also"></a>请参阅  
[运行时、消息修复、FIN 响应和消息传递](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)