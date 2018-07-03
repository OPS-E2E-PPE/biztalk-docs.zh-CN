---
title: 使用 BRE 策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb05d6f11d0d4d4f4ef5fd990d05c51b5e0df64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968950"
---
# <a name="working-with-bre-policies"></a>使用 BRE 策略
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]验证 SWIFT 消息通过使用业务规则引擎 (BRE) 策略，如中所述*SWIFT 参考指南*。 这些策略包括：  

- 格式设置  

- 值范围  

- 有效的列表条目  

- 相应的错误代码的网络规则  

- 可以从消息内容进行验证的使用规则  

  这些策略不包括不依赖于消息内容或任何跨消息验证的常规做法。  

  消息 （和标头和尾部） 的 XSD 架构实现基本字段可选性和基数，同时实现 SWIFT 基本 Types.xsd 架构的格式设置引用的消息架构。 用于每种消息类型的两个特定策略定义与每个消息关联的规则：  

- 主机策略 (MT*xxx*_Master_Policy.xml)  

- 验证策略 (MT*xxx*_Validation_Policy.xml)  

  每种消息类型的主策略调用应用于该消息类型的特定策略。 这些特定的策略包括特殊字段检查的常见函数实现中，网络规则，并使用规则。 消息的主策略是运行该消息的第一个策略。 策略列表包括消息类型的验证策略。 每个主策略已构造"如果此消息类型，然后运行的策略列表"。  

  每种消息类型的验证策略列出了其他外部规则实现，如域代码的单个字段检查，或使用特定词汇的字段。 这些单独的规则有两个或多个消息，在通常通用，因为它们是特定于字段的。 BRE 词汇 A4SWIFT_Codelists 不编程代码中，提供允许的字段值。  

  *SWIFT 参考指南*单独实现每个网络规则。 每个网络规则解决的一套消息类型*SWIFT 参考指南*定义。  

  A4SWIFT 安装时，A4SWIFT 安装程序不会安装规则。 您选择的架构，并生成和部署程序集后，你可以使用 BRE 部署实用工具用于选择和部署架构集中的相应规则。 若要部署的所选消息的规则，运行该实用程序，并选择相关的程序集。 该工具选择相应的主策略、 验证策略和任何被引用的网络或其他规则。  

  A4SWIFT A4SWIFT 规则相关联词汇的两种的类型。 第一个词汇是 A4SWIFT_Codelist，其中包含各种代码列表值。 第二个词汇是 A4SWIFT_Functions。 这些词汇是[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]用于逻辑验证和计算的类。  

  可以通过将 BRE 验证配置参数设置为 true 来调用 A4SWIFT 拆装器在接收管道中，规则。 此外可以调用业务流程中的规则。 不能调用通过 A4SWIFT 组装器 (ASM) 的规则。 必须使用业务流程或接收管道来验证针对该架构的实例并调用规则。  

  如果消息未能通过架构验证或业务规则，A4SWIFT 准备错误集合，其中包含找到的错误的说明及其相对值的指示在错误中的字段或发生错误的消息中的位置。 有关详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。  

  可以将其他规则添加到 A4SWIFT 提供的集合。 例如，如果您采用影响一组新的消息的市场实践组规则，可以实现包括所需的一个或多个新验证的主策略的新版本。 同样，如果施加额外的单个字段检查，您可以将这些检查添加到消息验证策略的新版本。 您可以实现新的验证作为新的规则或词汇函数。  

  本部分包含：  

- [启用银行标识代码验证](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  

- [在 A4SWIFT 数据库中管理 Bicplus 表](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  

- [在金额字段验证中支持前导零](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  

- [为金额验证设置偏移量](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  

- [删除使用规则验证](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)
