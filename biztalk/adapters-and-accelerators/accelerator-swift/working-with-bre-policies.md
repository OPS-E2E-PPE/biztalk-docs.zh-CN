---
title: "使用的 BRE 策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624af2a9c05e1a419acac66eeb6a1aea8d29d695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-bre-policies"></a>使用的 BRE 策略
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]验证 SWIFT 消息通过业务规则引擎 (BRE) 策略中所述*SWIFT 参考指南*。 这些策略包括：  
  
-   格式设置  
  
-   值范围  
  
-   有效的列表项  
  
-   使用相应的错误代码的网络规则  
  
-   可以从消息内容验证的使用规则  
  
 这些策略不包括一般不依赖于消息内容或任何跨消息验证的做法。  
  
 XSD 架构的消息 （和标头和尾） 实现基本字段可选性和基数，同时实现 SWIFT 基 Types.xsd 架构的格式设置引用的消息架构。 每种消息类型的两个特定策略定义与每个消息关联的规则：  
  
-   主策略 (MT*xxx*_Master_Policy.xml)  
  
-   验证策略 (MT*xxx*_Validation_Policy.xml)  
  
 每种消息类型的主策略时将应用于该消息类型的特定策略，将调用。 这些特定策略包括特殊字段检查该常见函数实现、 网络规则和使用规则。 消息的主策略是运行该消息的第一个策略。 策略的列表包括消息类型的验证策略。 每个主策略有构造"如果此消息类型，然后运行策略的列表"。  
  
 每种消息类型的验证策略列出的其他外部规则实现，如域代码的单一字段检查，或者为该字段中使用的特定词汇。 这些单独的规则是跨两个或多条消息，通常通用，因为它们是特定于字段的。 不编程代码，BRE 词汇中的 A4SWIFT_Codelists 提供允许的字段值。  
  
 *SWIFT 参考指南*独立实现每个网络规则。 每个网络规则地址的一套消息类型*SWIFT 参考指南*定义。  
  
 A4SWIFT 安装程序安装 A4SWIFT 时未安装规则。 你选择的架构，并生成和部署程序集后，你可以使用 BRE 部署实用工具来选择和部署架构集的相应规则。 若要部署的所选的消息的规则，运行该实用程序，并选择相关的程序集。 该工具选择相应的主策略、 验证策略和任何引用的网络或其他规则。  
  
 A4SWIFT 将两种类型的词汇与 A4SWIFT 规则相关联。 第一个词汇是 A4SWIFT_Codelist，其中包含各种代码列表值。 第二个词汇是 A4SWIFT_Functions。 这些词汇是[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]逻辑验证和计算类。  
  
 可以通过将 BRE 验证配置参数设置为 true 来调用由 A4SWIFT 拆装器接收管道中的规则。 你也可以调用业务流程中的规则。 不能调用通过 A4SWIFT 汇编程序 (ASM) 的规则。 你必须使用一个业务流程或接收管道能够验证针对架构的实例并调用规则。  
  
 如果消息未能通过架构验证或业务规则，A4SWIFT 准备包含找到的错误说明的错误集合和相对值的错误中的字段或发生错误的消息中的位置。 有关详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。  
  
 你可以添加到 A4SWIFT 提供集的其他规则。 例如，如果你采用影响一组新的消息的市场做法组规则，你可以实现包括所需的一个或多个新验证主策略的新版本。 同样，如果你在施加额外的单一字段检查，你可以将这些检查添加到消息验证策略的新版本。 你可以实现新的验证为新的规则或词汇函数。  
  
 本部分包含：  
  
-   [启用的 Bank 标识符代码的验证](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  
  
-   [管理 A4SWIFT 数据库中的 Bicplus 表](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  
  
-   [支持前导零量字段验证中](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  
  
-   [设置量验证偏移量](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  
  
-   [删除使用规则验证](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)