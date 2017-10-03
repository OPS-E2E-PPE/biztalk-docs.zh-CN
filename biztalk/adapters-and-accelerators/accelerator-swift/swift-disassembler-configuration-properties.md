---
title: "SWIFT 反汇编程序配置属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: disassembler, configuration properties
ms.assetid: 610cc68f-521f-4a9f-9f81-823a2fe55eb1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28bb9cfb95e253eaf6930d14e3856b5fee64deee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-configuration-properties"></a>SWIFT 反汇编程序配置属性
下表提供 SWIFT 反汇编程序 (DASM) 属性、 说明、 数据类型和值的范围。  
  
|属性名称|Description|数据类型|值范围|  
|-------------------|-----------------|---------------|-----------------|  
|**批处理标头架构**|指定用于分析的批处理信封标头的平面文件架构。 仅当**入站 Debatching**设置为**True**。|字符串|无或任何已部署的架构名称|  
|**批处理尾部架构**|指定要用于分析的批处理信封尾部的平面文件架构。 仅当**入站 Debatching**设置为**True**。|字符串|无或任何已部署的架构名称|  
|**BRE 验证**|启用/禁用的业务规则引擎 (BRE) 验证的调用。 如果设置为**True**，针对已部署策略 （例如，若要强制实施 SWIFT 网络规则） BRE 通过以下方法验证消息。 如果设置为**False**，BRE 验证不会被调用。|Boolean|True、False|  
|**双类型消息列表**|指定必须检查另一个标头字段以确定在动态消息类型解析期间的消息的子类型的 SWIFT 消息类型。 默认值列表是**102 103 521 523 574**。 **注意：**如果任何或所有消息类型字符串都会从双类型消息列表中，则对于 MT574 以外的所有消息，原始架构其业务规则使用和处理消息。 例如，MT102 加上实例使用 MT102、 MT103PLUS 实例使用 MT103、 MT521_ISITC 实例使用 MT521，和 MT523_ISITC 实例使用 MT523。 对于所有 MT574 实例，返回以下错误： 查找由消息类型的文档规范"http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/ SWIFT/Category5/MT&#574;SWIFT_CATEGORY5_MT574_Interchange"失败。 验证已正确部署架构。"|字符串|3 位数字的空格分隔的列表|  
|**碎片**|启用/禁用的入站批处理的碎片。 如果设置为**True**，入站批处理中的消息发布到 MessageBox 数据库作为单独的消息。 如果设置为**False**，整个的入站的批处理形式 （作为输入的一个精确副本） 的一条消息将发布到 MessageBox 数据库。 仅当入站 debatching 设置为使用**True**。|Boolean|True、False|  
|**入站 Debatching**|启用/禁用处理的入站批处理。 如果设置为**True**，入站的批处理预期会有且在处理期间拆分。 如果设置为**False**，预期会有单个消息，且不需要 debatching。|Boolean|True、False|  
|**消息标头架构**|指定要用于分析的消息信封标头 （批处理中消息） 的平面文件架构。 仅当**入站 Debatching**设置为**True**。|字符串|无或任何已部署的架构名称|  
|**消息尾部架构**|指定要用于分析 （适用于批处理中消息） 的消息信封尾部的平面文件架构。 仅当**入站 Debatching**设置为**True**。|字符串|无或任何已部署的架构名称|  
|**保留批处理标头**|启用/禁用保留的批处理信封标头时**碎片**已启用。 如果设置为**True**，批处理信封标头发布到 MessageBox 数据库作为单独的消息。 如果设置为**False**后对其分析, 的批处理信封标头将被丢弃。 仅当**批处理标头架构**指定。|Boolean|True、False|  
|**保留批处理尾**|启用/禁用批处理信封保留尾部时**碎片**已启用。 如果设置为**True**，批处理信封预告片发布到 MessageBox 数据库作为单独的消息。 如果设置为**False**，批处理信封尾中的内容将被丢弃后对其分析。 仅当**批处理尾部架构**指定。|Boolean|True、False|  
|**保留消息标头**|当启用/禁用消息信封标头 （批处理中消息） 的保留**碎片**已启用。 如果设置为**True**，消息信封标头发布到 MessageBox 数据库在批处理中的相应 SWIFT 消息的标头部分。 如果设置为**False**，则将它解析后，即丢弃消息信封标头。 仅当**消息标头架构**指定。|Boolean|True、False|  
|**保留消息预告片**|当启用/禁用保留的 （对于批处理中消息） 的消息信封预告片**碎片**已启用。 如果设置为**True**，消息信封预告片发布到 MessageBox 数据库中的批处理中的相应 SWIFT 消息的尾部部分。 如果设置为**False**，则将它解析后，即丢弃消息信封预告片。 仅当**消息尾部架构**指定。|Boolean|True、False|  
|**保留会话和序列号**|如果设置为**True**，保留标头块 1 中的会话和序列号字段中的任意字符字符串。<br /><br /> 如果设置为**False**，在这些字段中插入截断的空格。|Boolean|True、False|  
|**提升 A4SWIFT SWIFTBound 属性**|如果设置为**True**，提升**SWIFTBound** （输入） 标头块 2 将与此管道接收的消息的属性。<br /><br /> 如果设置为**False**，不提升**SWIFTBound**在任何情况下的属性。|Boolean|True、False|  
|**禁止显示缺少的策略警告**|启用/禁用日志记录的事件日志中缺少 （未部署） BRE 验证策略中的业务规则引擎 (BRE) 警告。 如果设置为**True**，取消的警告。 如果设置为**False**，每次找不到验证策略时，将记录一个警告。 仅当**BRE 验证**已启用。|Boolean|True、False|  
|**SWIFT 标头架构**|指定要用于分析 SWIFT 消息标头并检查已分析的值以便动态发现消息类型的平面文件架构。 仅指定动态消息类型解析是否需要 （管道将处理不同类型的 SWIFT 消息）。 指定如果**SWIFT 交换架构**未指定。 如果**SWIFT 交换**和**SWIFT 标头架构**是否未指定， **SWIFT 标头架构**默认为**Micrsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**。|字符串|无或任何已部署的架构名称|  
|**SWIFT 交换架构**|指定要用于分析整个 SWIFT 消息 （交换） 的平面文件架构。 仅指定是否动态消息类型解析不需要 （管道将仅用于处理 SWIFT 消息的指定类型）。 如果必须指定**SWIFT 标头架构**未指定。|字符串|无或任何已部署的架构名称|  
|**空白的行视为分析错误**|如果设置为**True**多行的多个字段，在遇到空行时，这些标记为分析的错误 （空行不是根据 SWIFT 很好的做法）。 请注意，对于 debatching 方案，这些分析错误不要终止批处理 （消息将被视为错误的消息并生成一个错误部分），并且未出现错误批处理中的消息进行正确处理。<br /><br /> 如果设置为**False**，在多行的多个字段是否允许有空行。|Boolean|True、False|  
|**XML 验证**|启用/禁用的 XML 验证调用。 如果设置为**True**，验证根据架构约束 （例如，若要强制执行的长度或范围值） 的读取器的 XML 通过以下方法验证消息。 如果设置为**False**，XML 验证不会被调用。|Boolean|True、False|  
  
## <a name="see-also"></a>另请参阅  
 [配置 SWIFT 反汇编程序](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)   
 [配置 SWIFT 汇编程序](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)