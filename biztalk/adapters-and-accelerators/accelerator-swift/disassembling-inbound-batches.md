---
title: 反汇编入站的批处理与 SWIFT |Microsoft Docs
description: 解除批处理入站的消息，并自定义架构进行批处理在 BizTalk Server 中使用 SWIFT 加速器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11cb5672-1155-4648-b1fd-c9a3bc30e351
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e378f0e7b887a9b3dab5a4ffc770c61ff5279f8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378065"
---
# <a name="disassemble-inbound-batches"></a>反汇编入站的批处理

## <a name="debatch-inbound-message"></a>解除批处理入站的消息
SWIFT 反汇编程序就可以对入站解除批处理它处理或反汇编入站的批处理 （文件或包含多个 SWIFT 消息的消息）。 允许使用 SWIFT 反汇编程序配置属性具有相同名称的入站解除批处理。 启用入站解除批处理后，SWIFT 反汇编程序期望接收要包括多个 SWIFT 消息的批的所有消息。 批处理可能或可能不包括批处理信封 （一个批处理标头和批处理尾部），并在一个批处理中每个 SWIFT 消息可能包含或不包含消息信封 （消息标头和消息尾部）。 你可以配置这些批次属性 （格式），使用以下 SWIFT 反汇编程序配置属性：  
  
- 批处理标头架构  
  
- 批处理尾部架构  
  
- 消息标头架构  
  
- 消息尾部架构  
  
  > [!NOTE]
  >  设置这些属性为"None"的任何指示的入站的批处理不包含该特定部分。  
  
  SWIFT 反汇编程序需要具有以下结构的所有入站的批：  
  
  **批处理标头**  
  
  **消息标头**  
  
  **SWIFT 的交换消息 （SWIFT 块 1 到 5）**  
  
  **消息尾部**  
  
  **批处理尾部**  
  
  在此结构中，可以考虑"消息块"是**消息标头 – SWIFT 交换 – 消息尾部**部件。 多个"消息块"的一系列组成一批中的多个 SWIFT 消息。 批处理标头、 消息标头、 消息尾部和批处理尾部是可选的但在重复必须保持一致。  
  
> [!NOTE]
>  不要用 SWIFT 标头和尾部块混淆消息信封 （消息标头和消息尾部）。 在批处理的上下文中，应查看包含 SWIFT 标头和尾部块作为一个整体 (atomic) 单元的 SWIFT 消息 （交换）。 在此上下文中，消息标头和消息尾部指封装在批处理中的每个 SWIFT 消息的信封。  
  
 若要更准确地讲 express 此结构，其选项，其可重复性，请考虑如何[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]定义批处理：  
  
- **批处理标头**为由**BH**  
  
- **消息标头**为由**MH**  
  
- **SWIFT 交换**为由**SI**  
  
- **消息尾部**为由**MT**  
  
- **批处理尾部**为由**BT**。  
  
  表示预期的批处理结构的表达式如下所示：  
  
  `[BH] ([MH] SI [MT])* [BT]  `
  
  方括号 ( `[ ] ` ) 指示的部分是可选。 星号 (**\\* * *) 指示的块是可重复。无论谁生成消息批，则必须使用消息标头 (*<em>MH</em>*) 和尾部 (*<em>MT</em>*) 中的每次重复的一致地 (`[MH] SI [MT]`)。  
  
  SWIFT 反汇编程序是能够处理遵循上面的结构，任何入站的批处理，因为结构中的每个部件符合平面文件架构。 但是，如果不使用的可选批处理标头/尾部和消息标头/尾部，则消息将符合这些架构。 因此，包含仅连续 SWIFT 消息的批处理将具有批头部架构、 批处理尾部架构、 消息标头架构和消息尾部架构属性设置为"None"。  

## <a name="customize-schemas-for-batching"></a>自定义批处理的架构  
 您可以自定义批处理标头/尾部和消息标头/尾部的架构。 下面的批处理是一个示例：  
  
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
  
 若要处理这种类型的批处理，可以设置批处理的架构属性，如下所示：  
  
- 分析由回车符-分隔的单个数字 （消息计数） 的平面文件架构设置批处理标头架构属性。  
  
- 将对单个 $ 符号和回车符-分析的平面文件架构设置消息尾部架构。  
  
- 将剩余的信封架构 （批处理尾部架构和消息标头架构） 设置为无。  
  
  可以配置 SWIFT 反汇编程序，使它通过创建并指定适当的平面文件信封架构组合处理几乎任何 SWIFT 消息批。 此功能是非常灵活。  
  
  SWIFT 反汇编程序始终会尝试完成的整个批次处理，即使在遇到错误，在此过程。 这使它能够收集并一次性地报告任意多个错误。 若要执行此"最大努力"启发式，SWIFT 反汇编程序必须进行某些决策和假设选择要在遇到新部件时使用的架构时或发生分析错误。 选择正确的架构并不总是可能根据的性质和分析错误和信封架构和 SWIFT 交换架构之间的多义性/相似性的位置。 在某些情况下，可以通过使用精心设计的信封架构中选择错误的架构的可能性降至。 如果拆装器遇到致命的分析错误或拆装器无法确定正确的架构，拆装器将批处理失败而不会处理剩余的数据。  
  
  当**入站解除批处理**是**启用**(设置为**True**)，SWIFT 反汇编程序将使用指定的批处理信封 （批处理标头架构的架构的批处理分析和批处理尾部架构） 和消息信封 （消息标头架构和消息尾部架构），以及指定用于分析的批处理中的 SWIFT 消息 （交换） 的架构。 为批处理中的 SWIFT 消息，消息类型和架构可以被动态地发现和加载单个非批处理消息的方式相同 （通过指定 SWIFT 标头架构）。 SWIFT 反汇编程序如何执行架构解析的详细信息，请参阅[动态消息类型发现和架构解析](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)。  
  
  SWIFT 反汇编程序分析，并单独验证入站批处理中的每个 SWIFT 消息。 它将执行下面的批处理处理序列：  
  
1. 如果已指定批处理标头架构，分析批处理标头。  
  
2. 如果已指定消息标头架构，分析消息信封标头。  
  
3. 分析 SWIFT 交换 （消息）。  
  
4. 如果已启用了 XML 验证，请验证 XML 约束针对的 SWIFT 消息。  
  
5. 如果已启用了 BRE 验证，请验证对 BRE 策略 （SWIFT 网络和使用情况规则） SWIFT 消息。  
  
6. 如果指定消息尾部架构，分析消息信封尾部。  
  
7. 重复步骤 2 到 6，直到拆装器找不到更多消息批次中。  
  
8. 如果已指定批处理尾部架构，分析批处理尾部。  
  
   你可以配置 SWIFT 反汇编程序不同的执行操作的批处理数据，它将分析和验证使用以下 SWIFT 反汇编程序配置属性：  
  
- **碎片**属性确定是否单独 SWIFT 反汇编程序应发布每个消息批处理到 MessageBox 数据库中 (也就是说，对于每个消息，上面的步骤 6 的每个匹配项后)，还是应完成所有步骤 1 到 8，然后将整个批次发布以本机形式 （输入的精确副本），作为单个消息发布到 MessageBox 数据库。 您设置**碎片**到**True**启用碎片和单独发布在批处理中的消息。 您设置**碎片**到**False**禁用碎片并将整批，以本机形式发布为仅在处理整个批次一条消息。 通常情况下，设置**碎片**到**禁用**方案时仅需要 BizTalk Accelerator for SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) 来分析和验证入站的批处理和失败，或转发，在同一个窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]收到它们。 通常设置**碎片**到**已启用**想在其中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]来转换或修改批处理内的消息后分析和验证，或者当你想[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]进行重新排序顺序不同于为批中的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]最初接收到中。 此外设置**碎片**到**已启用**对于入站的批处理中包含有不同的最终目标的消息的方案。  
  
- **保留批处理标头 / 保留批处理尾部**属性确定 SWIFT 反汇编程序是应放弃还是在分析后保留的批处理的信封 （标头和尾部） 数据。 如果您设置**保留批处理标头或保留批尾部**到**True**，拆装器将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库，是作为单条消息。 拆装器将数据发布在多部分消息的正文部分。 拆装器将特殊的上下文属性升级，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可将它们是在批处理中将这些消息给它们原来的位置的批处理和的序号位置相关联 （批处理标头的第一个位置，为批处理尾部的最后一个位置）。 如果您设置**保留批处理标头或保留批尾部**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。  
  
  > [!NOTE]
  >  仅当启用碎片时，这些配置属性都有效 (**碎片**设置为**True**)。 因此保留设置是不相关时碎片处于禁用状态，拆装器会以本机形式，向 MessageBox 数据库中发布整个批次的精确副本 (*一切*保留)。  
  
- **保留消息标头** / **保留消息尾部**属性确定 SWIFT 反汇编程序是应放弃还是保留消息信封 （消息标头和尾部）在解析它们。 如果您设置**保留消息标头或保留消息尾部**到**True**，拆装器将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库*连同它所包装的单个 SWIFT 消息*。 拆装器将发布消息信封中的标头**标头**多部分消息的一部分。 拆装器将发布中的消息信封尾部**尾部**多部分消息的一部分。 拆装器将发布消息信封中包含的 SWIFT 消息**正文**相同的多部分消息的一部分。 拆装器将特殊的上下文属性升级，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可将这些消息给它们原来的批处理和它们所处的批处理中的序号位置相关联。 如果您设置**保留消息标头或保留消息尾部**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。  
  
  > [!NOTE]
  >  仅当启用碎片时，这些配置属性都有效 (**碎片**设置为**True**)。 因此保留设置是不相关时碎片处于禁用状态，拆装器会以本机形式，向 MessageBox 数据库中发布整个批次的精确副本 (*一切*保留)。  
  
  有关每个配置属性，有关详细信息，以及其他使用情况和配置信息，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。 有关 MessageBox 数据库发布和多部分消息的详细信息，请参阅 BizTalk Server 帮助。  
  
## <a name="next-step"></a>下一步
  
[与批处理相关的已提升属性](batch-related-promoted-properties.md)
