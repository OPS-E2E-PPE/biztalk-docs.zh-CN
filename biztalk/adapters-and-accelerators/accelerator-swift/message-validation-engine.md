---
title: "消息验证引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message validation engine
- errors, validating
- XML validation
- parsing validation
- BRE policies, validating
- errors, messages
- messages, errors
- validating, messages
- validating, BRE policies
- validating, XML
- messages, validating
- validating, errors
- validating, parsing
ms.assetid: 4ba0b75e-665b-4771-b04f-5bc3e90d83f0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbdcb375c04e4c9684b2a805c7a7a7315f46f83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-validation-engine"></a>消息验证引擎
提供的最重要功能之一[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是完全验证 SWIFT 从发往 SWIFT 网络，或从 SWIFT （由贸易合作伙伴发送） 的网络接收的后端系统中收到的消息的功能。 验证出站 SWIFT 消息保证的消息符合 SWIFT 标准和 SWIFT 网络则不能拒绝消息。  
  
 验证入站 SWIFT 消息可确保从其他金融机构接收的消息遵循特定协议 （业务规则） 特定于的关系。 在这两种情况下，验证和提交某一消息之前捕获的错误的功能可帮助降低事务成本和总拥有成本 (TCO)。  
  
 以下列表描述构成 A4SWIFT 验证引擎的四个部分：  
  
-   执行的平面文件分析器的结构验证  
  
-   通过 XML 验证读取器执行数据验证  
  
-   执行由业务规则引擎 (BRE) 的 SWIFT 网络和使用情况的规则验证  
  
-   消息标记和收集的"最大程度的"错误  
  
## <a name="structural-validation-parsing"></a>（分析） 的结构验证  
 A4SWIFT 分析为 SWIFT 标准根据每种 SWIFT 消息类型定义的 XSD 架构的 SWIFT 平面文件消息。 为 XML 分析平面文件保证平面文件结构正确。 分析还将生成更轻松地读取、 操作或转换为其他格式或消息类型的 XML。 此外可以验证针对数据的有效性的架构的 XML，并用于更复杂的计算的业务规则引擎 (BRE)。  
  
 SWIFT 反汇编程序调用 BizTalk 平面文件分析器来分析 SWIFT 平面文件消息由 SWIFT 反汇编程序调用。 SWIFT 反汇编程序记录在错误集合中的分析过程中，遇到的任何错误的详细信息，并始终尝试继续在试图收集尽可能上第一次传递的尽可能多的结构化错误分析的数据。 但是，大多数分析错误都是致命的并且暂停在第一个错误的消息处理。  
  
 有关结构化的验证的详细信息，请参阅[使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)。  
  
## <a name="data-validation-xml-validation"></a>数据验证 （XML 验证）  
 你可以定义 SWIFT 结构验证将作为传递格式正确的 XML 符合定义 XSD 架构的消息。 A4SWIFT 生成结构有效 SWIFT 消息在分析阶段的 XML。 然后，A4SWIFT 可以验证此 XML 的数据根据相应的 XSD 架构中定义的约束的正确性。  
  
 这些约束包括多个数据类型、 长度和标准 SWIFT 根据定义的值范围。 SWIFT 反汇编程序调用验证读取器来执行数据验证的 XML。  
  
 SWIFT 反汇编程序记录在错误集合中的 XML 验证过程中遇到任何错误的详细信息，并继续验证要在第一次传递上尽可能收集尽可能多的 XML 验证错误的剩余数据。 （与分析过程中，不同的 XML 验证延续保证。）  
  
 有关数据验证的详细信息，请参阅[使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)。  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a>SWIFT 网络和使用情况规则验证 （BRE 验证）  
 A4SWIFT 用于根据业务规则引擎 (BRE) 策略的业务级正确性结构有效 SWIFT 信验证 XML。 这些策略包括强制实施 SWIFT 网络和使用情况的规则和其他复杂的跨域规则根据 SWIFT 标准定义。 SWIFT 反汇编程序调用 BRE 执行业务级别验证。  
  
 SWIFT 反汇编程序记录在错误集合中的 BRE 验证过程中遇到任何错误的详细信息，并继续验证要在第一次传递上尽可能收集尽可能多的 BRE 验证错误的剩余数据。 （如 XML 验证，BRE 验证延续保证。）  
  
 有关 SWIFT 网络和使用情况规则验证的详细信息，请参阅[使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)。  
  
## <a name="validation-failures-and-message-marking"></a>验证失败和消息标记  
 A4SWIFT 收集验证错误和消息验证的每个阶段的详细信息： 结构分析、 XML 验证和 BRE 验证。 A4SWIFT 收集使用"最大程度"的启发式方法来收集尽可能多的错误信息有关消息可能这些错误。 要包含捕获的所有错误，并且报告一次，而不是让多个迭代的提交，验证、 失败、 修复、 重新提交的失败消息时，此功能。  
  
 具有至少一个错误集合中的任何验证阶段遇到的错误的消息将被视为无效，操作将失败。 A4SWIFT 将这些消息发布到 MessageBox 数据库，但它们被标记为具有提升的属性，以指示消息未通过验证和验证的每个阶段的报告错误计数。  
  
 提升的属性，除了 A4SWIFT 序列化错误集合转换为 XML，并且将附加"错误"的一部分的多部分消息的集合。 最后一条消息包含的正文部分中的失败消息和错误集合 XML 中的错误部分中，并使用提升的 A4SWIFT 属性用来指示故障状态进行增强。 SWIFT 反汇编程序将此多部分消息发布到 MessageBox 数据库。  
  
 BizTalk 发送端口或业务流程可以失败的消息从数据库中检索 MessageBox 通过订阅到特殊的 A4SWIFT 提升属性。 你可以进行订阅以从特定的验证阶段中检索所有失败的消息或仅具有特定数量的错误消息。  
  
 检索失败的消息后，你可以将其发送到报告的应用程序、 修复应用程序或进程或失败的存储库，或放弃它。  
  
 此功能订阅以便失败的消息 （从而区分类型的订阅中的故障），结合了富信息错误集合附加到每个失败的消息的 XML 构成一个功能强大的框架，用于开发简单的错误报表提供应用程序，如消息修复和新 A4SWIFT 安装程序安装的提交功能。  
  
 有关验证错误和消息标记的详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)