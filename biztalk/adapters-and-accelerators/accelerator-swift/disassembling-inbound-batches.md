---
title: "反汇编入站的批处理 SWIFT |Microsoft 文档"
description: "Debatch 入站的消息和自定义批处理 BizTalk Server 中使用 SWIFT 快捷键的架构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11cb5672-1155-4648-b1fd-c9a3bc30e351
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f14a199e3422a45235727d2d16fc1464e2e4927
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="disassemble-inbound-batches"></a>反汇编入站的批处理

## <a name="debatch-inbound-message"></a>Debatch 入站的消息
SWIFT 反汇编程序可以为入站 debatching 它处理或进行反汇编，入站的批处理 （文件或包含多个 SWIFT 消息的消息）。 你启用入站 debatching 使用相同的名称的 SWIFT 反汇编程序配置属性。 启用入站 debatching 后，SWIFT 反汇编程序期望接收要包括多个 SWIFT 消息的批处理的所有消息。 批处理可能包含或不包含批处理信封 （批处理标头和批处理尾部），并在一个批处理中每个单个 SWIFT 消息可能包含或不包含消息信封 （消息标头和消息尾部）。 你可以配置这些批处理属性 （格式），使用以下 SWIFT 反汇编程序配置属性：  
  
-   批处理标头架构  
  
-   批处理尾部架构  
  
-   消息标头架构  
  
-   消息尾部架构  
  
    > [!NOTE]
    >  设置这些属性设置为"None"的任何指示的入站的批处理不包含该特定部分。  
  
 SWIFT 反汇编程序需要具有以下结构的所有入站的批：  
  
 **批处理标头**  
  
 **消息标头**  
  
 **SWIFT 交换/消息 （SWIFT 块 1 到 5）**  
  
 **消息预告片**  
  
 **批处理尾**  
  
 在此结构中，你可以考虑"消息块"是**– SWIFT 交换 – 的消息标头消息预告片**部分。 多个"消息块"的一系列组成批处理中的多个 SWIFT 消息。 批处理标头、 消息标头、 消息尾部和批处理尾是可选的但必须一致重复。  
  
> [!NOTE]
>  不要用 SWIFT 的标头和尾块混淆消息信封 （消息头和消息预告片）。 在上下文中的批处理，应查看作为整体 （原子） 单元包括 SWIFT 标头和尾块 SWIFT 消息 （交换）。 在此上下文中，消息标头和消息尾端引用到批处理中包装每个 SWIFT 消息信封。  
  
 若要更准确地讲 express 此结构，其选项，其可重复性，请考虑如何[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]定义一批：  
  
-   **批处理标头**由**BH**  
  
-   **消息标头**由**MH**  
  
-   **SWIFT 交换**由**SI**  
  
-   **消息预告片**由**MT**  
  
-   **批处理预告片**由**BT**。  
  
 表示预期的批处理结构表达式，如下所示为：  
  
 `[BH] ([MH] SI [MT])* [BT]  `
  
 方括号 ( `[ ] ` ) 指示的部分是可选。 星号 (**\***) 指示是可重复的块。 任何人员都生成消息批必须使用消息标头 (**MH**) 和尾部 (**MT**) 内的每个重复即可一致 (`[MH] SI [MT]`)。  
  
 SWIFT 反汇编程序就能够处理遵循上述结构中，任何入站批次，因为结构中的每个部分符合平面文件架构。 但是，如果不使用可选的批处理标头/尾和消息标头/尾，则消息将符合这些架构。 因此，包含仅连续 SWIFT 消息的批处理将具有批处理标头架构、 批处理尾部架构、 消息标头架构和消息尾部架构属性设置为"None"。  

## <a name="customize-schemas-for-batching"></a>自定义批处理的架构  
 你可以自定义批处理标头/尾和消息标头/尾的架构。 下面的批处理是一个示例：  
  
```  
4  
SWIFT Message # 1  
$  
SWIFT Message # 2  
$  
SWIFT Message # 3  
$  
SWIFT Message # 4  
$  
```  
  
 若要处理这种类型的批处理，将按以下方式设置批的架构属性：  
  
-   分析由回车符分隔是一个数字 （消息计数） 的平面文件架构设置批处理标头架构属性。  
  
-   将消息尾部架构设置为将对单个 $ 符号和回车分析的平面文件架构。  
  
-   将剩余的信封架构 （批处理尾部架构和消息标头架构） 设置为无。  
  
 你可以配置 SWIFT 反汇编程序，以便它可以通过创建并指定合适的平面文件信封架构组合处理几乎任何 SWIFT 消息批次。 此功能是非常灵活。  
  
 SWIFT 拆装器始终尝试完成的整个批处理，处理，即使它遇到此过程中的错误。 这使它能够收集并尽可能在一次报告尽可能多的错误。 若要执行此"最佳效果"启发式，SWIFT 反汇编程序必须进行某些决策和假设选择要在遇到新部件时使用的架构时或发生分析错误。 选择正确的架构并不总是可能具体取决于性质和位置分析错误和信封架构和 SWIFT 交换架构之间的多义性/相似性。 在某些情况下，可以通过使用设计良好的信封架构中定义的错误的架构的可能性降至。 如果拆装器遇到致命的分析错误或反汇编程序无法确定正确的架构，拆装器则该批处理失败而不会处理剩余的数据。  
  
 当**入站 Debatching**是**启用**(设置为**True**)，SWIFT 反汇编程序分析批处理使用指定的批处理信封 （批处理标头架构的架构和批处理尾部架构） 和消息信封 （消息标头架构和消息尾部架构），以及用于分析批处理中的 SWIFT 消息 （交换） 中指定的架构。 批处理中的 SWIFT 消息，消息类型和架构可以动态发现和加载作为单个非批处理消息相同的方式 （通过指定 SWIFT 标头架构）。 有关如何 SWIFT 反汇编程序执行架构解析的详细信息，请参阅[动态消息类型发现和架构解决](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)。  
  
 SWIFT 反汇编程序分析，并单独验证入站批处理中的每个 SWIFT 消息。 它执行以下的批处理操作序列：  
  
1.  如果已指定批处理标头架构，分析批处理标头。  
  
2.  如果已指定消息标头架构，请分析消息信封标头。  
  
3.  分析 SWIFT 交换 （消息）。  
  
4.  如果已启用 XML 验证来验证 SWIFT 消息根据 XML 的约束。  
  
5.  如果已启用 BRE 验证来验证 SWIFT 消息根据 BRE 策略 （SWIFT 网络和使用情况规则）。  
  
6.  如果指定消息尾部架构，请分析消息信封预告片。  
  
7.  重复步骤 2 到 6，直到拆装器找不到更多消息批处理中。  
  
8.  如果已指定批处理尾部架构，分析批处理尾。  
  
 你可以配置 SWIFT 反汇编程序中，若要执行不同的操作与批处理数据分析和验证使用 SWIFT 拆装器配置的以下属性：  
  
-   **碎片**属性确定是否 SWIFT 反汇编程序应逐个每条消息到 MessageBox 数据库批处理中 (即，对于每个消息，在上面的步骤 6 的每个匹配项后)，或如果它应完成所有步骤 1 到 8，然后将整个批处理，发布以本机形式 （输入的精确副本），为到 MessageBox 数据库一条消息。 你设置**碎片**到**True**启用碎片和逐个批处理中的消息。 你设置**碎片**到**False**禁用碎片并发布整个批次，以本机形式处理整个批次后，才在一个消息。 通常情况下，设置**碎片**到**禁用**方案仅在需要时 BizTalk Accelerator for SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) 分析和验证入站的批处理和失败，或转发，在同一个窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]收到它们。 通常设置**碎片**到**已启用**适合你希望[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]来转换或修改某一批处理中的消息后分析和验证，或者当你想[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]进行重新排序为不同于什么订单的批处理中的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]最初收到它们中。 你还设置**碎片**到**已启用**对于其中的入站的批处理包含具有不同的最终目标的消息的方案。  
  
-   **保留批处理标头 / 保留批处理预告片**属性确定 SWIFT 反汇编程序是应放弃还是在分析后保留批处理信封 （标头和尾） 数据。 如果你设置**保留批处理标头或保留批处理预告片**到**True**，拆装器会将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库是作为单条消息。 反汇编程序中的多个部分的消息的正文部分的发布数据。 反汇编程序提升特殊的上下文属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以关联到它原来的批处理和的序号位置在批处理中处于这些消息 （批处理标头的第一个位置，为批处理尾的最后一个位置）。 如果你设置**保留批处理标头或保留批处理预告片**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。  
  
    > [!NOTE]
    >  这些配置属性是有效的仅当启用碎片 (**碎片**设置为**True**)。 当禁用碎片时，反汇编程序发布整个批处理的一个精确副本中的本机窗体中，到 MessageBox 数据库中，以便保留设置是不相关 (*的所有内容*保留)。  
  
-   **保留消息标头** / **保留消息预告片**属性确定应放弃还是保留消息信封 （消息标头和拖车安排） 应 SWIFT 反汇编程序后分析它们。 如果你设置**保留消息标头或保留消息预告片**到**True**，拆装器将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库*连同它所包装的单个 SWIFT 消息*。 反汇编程序发布消息信封标头中的**标头**属于多个部分的消息。 反汇编程序发布中的消息信封拖车安排**预告片**属于多个部分的消息。 反汇编程序发布消息信封中包含的 SWIFT 消息**正文**相同的多个部分消息的一部分。 反汇编程序提升特殊的上下文属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以关联到它原来批处理和批处理中它们所处的序号位置这些消息。 如果你设置**保留消息标头或保留消息预告片**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。  
  
    > [!NOTE]
    >  这些配置属性是有效的仅当启用碎片 (**碎片**设置为**True**)。 当禁用碎片时，反汇编程序发布整个批处理的一个精确副本中的本机窗体中，到 MessageBox 数据库中，以便保留设置是不相关 (*的所有内容*保留)。  
  
 有关详细信息，有关每个配置属性，以及其他使用情况和配置信息，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。 有关 MessageBox 数据库发布和多个部分的消息的详细信息，请参阅 BizTalk Server 帮助。  
  
## <a name="next-step"></a>下一步
  
[与批处理相关的已提升属性](batch-related-promoted-properties.md)
