---
title: 消息验证引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd286de8a1f2b0d9947a87cedaafd2a0efbce976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377198"
---
# <a name="message-validation-engine"></a>消息验证引擎
提供的最重要功能之一[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是能够完全验证从后端系统的 SWIFT 网络发往或来自 （由贸易合作伙伴发送） 的 SWIFT 网络接收的 SWIFT 消息。 验证出站 SWIFT 消息可以保证消息符合 SWIFT 标准和 SWIFT 网络将不会拒绝消息。  
  
 验证入站 SWIFT 消息可确保从其他金融机构收到的消息遵循特定协议 （业务规则） 特定于此关系。 在这两种情况下，验证和提交一条消息之前捕获的错误的功能可帮助降低事务成本和总拥有成本 (TCO)。  
  
 以下列表描述了组成 A4SWIFT 验证引擎的四个部分：  
  
-   执行的平面文件分析器的结构验证  
  
-   执行的验证读取器的 XML 的数据验证  
  
-   执行由业务规则引擎 (BRE) 的 SWIFT 网络和使用情况的规则验证  
  
-   消息标记和收集的"最大程度的"错误  
  
## <a name="structural-validation-parsing"></a>（分析） 的结构验证  
 A4SWIFT 分析针对 XSD 架构为 SWIFT 标准根据每个 SWIFT 消息类型定义的 SWIFT 平面文件消息。 将平面文件解析为 XML 保证平面文件结构正确。 分析还会生成更轻松地读取、 处理或转换为其他格式或消息类型的 XML。 此外可以根据数据有效性的架构验证 XML，并用于更复杂的计算业务规则引擎 (BRE)。  
  
 SWIFT 反汇编程序调用 BizTalk 平面文件分析器来分析由 SWIFT 反汇编程序调用的 SWIFT 平面文件消息。 SWIFT 反汇编程序记录错误集合中的分析过程中，遇到的任何错误的详细信息，并始终会尝试继续进行数据分析在试图收集尽可能上第一次传递的任意数量的结构错误。 但是，大多数分析错误都是致命并停止在第一个错误的消息处理。  
  
 有关结构验证的详细信息，请参阅[处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)。  
  
## <a name="data-validation-xml-validation"></a>数据验证 （XML 验证）  
 可以定义传递结构验证为格式正确的 XML 符合定义的 XSD 架构的 SWIFT 消息。 A4SWIFT 在解析阶段生成的具有有效结构的 SWIFT 消息的 XML。 然后，A4SWIFT 可以验证数据正确，根据相应的 XSD 架构中定义的约束对此 XML。  
  
 这些约束包括多个数据类型、 长度和标准 SWIFT 按照定义的值范围。 SWIFT 反汇编程序调用验证读取器来执行数据验证的 XML。  
  
 SWIFT 反汇编程序记录的错误集合中的 XML 验证过程中遇到任何错误的详细信息，并继续验证要在第一次传递上尽可能收集尽可能多的 XML 验证错误的其余数据。 （与不同的分析过程中，延续的 XML 验证的保证。）  
  
 关于数据验证的详细信息，请参阅[处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)。  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a>SWIFT 网络和使用情况规则验证 （BRE 验证）  
 A4SWIFT 验证 XML 的有效结构 SWIFT 消息针对业务规则引擎 (BRE) 策略的业务级别正确。 这些策略包括强制实施 SWIFT 网络和使用情况的规则和其他复杂的跨域规则按照 SWIFT 标准定义。 SWIFT 反汇编程序调用 BRE 执行业务级验证。  
  
 SWIFT 反汇编程序记录的错误集合中的 BRE 验证过程中遇到任何错误的详细信息，并继续验证要在第一次传递上尽可能收集尽可能多的 BRE 验证错误的其余数据。 （例如 XML 验证、 延续 BRE 验证的保证。）  
  
 SWIFT 网络和使用情况的规则验证的详细信息，请参阅[使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)。  
  
## <a name="validation-failures-and-message-marking"></a>验证失败和消息标记  
 A4SWIFT 收集验证错误和消息验证的每个阶段的详细信息： 结构分析、 XML 验证和 BRE 验证。 A4SWIFT 收集使用"最大程度"启发式方法来收集有关消息太多错误的信息尽可能这些错误。 此功能允许具有捕获的所有错误和报告在一次传递，而无需多个迭代的提交，验证、 失败、 修复、 重新提交失败消息。  
  
 具有至少一个错误集合中的任何验证阶段过程中遇到的错误消息将被视为无效并失败。 A4SWIFT 将这些消息发布到 MessageBox 数据库中，但它们被标记为与升级的属性以指示消息未通过验证并对每个验证阶段报告错误计数。  
  
 升级属性，除了 A4SWIFT 序列化到 XML 错误集合并将附加"错误"的一部分的多部分消息的集合。 最后一条消息包含的正文部分中的失败消息和错误集合中的错误部分中，XML 和已增强，A4SWIFT 升级属性用来指示故障状态。 SWIFT 反汇编程序将此多部分消息发布到 MessageBox 数据库。  
  
 BizTalk 发送端口或业务流程可以检索失败的消息从 MessageBox 数据库通过订阅到特殊的 A4SWIFT 提升属性。 您可以进行订阅以检索特定验证阶段中的所有失败的消息或仅使用特定的多个错误消息。  
  
 检索失败的消息后，可以将其发送到报告应用程序、 修复应用程序或进程或失败的存储库，或放弃它。  
  
 这一功能订阅要失败的消息 （并区分类型的订阅中的故障），再加丰富信息的错误集合上附加到每个失败的消息的 XML 构成一个功能强大的框架，用于开发简单的错误报告提供应用程序，如通过消息修复和新提交功能，由 A4SWIFT 安装程序安装。  
  
 有关验证失败和消息标记的详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)