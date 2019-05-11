---
title: 与批处理相关的已提升属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea49f40097df45bac158150cd22d124b43831bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378950"
---
# <a name="batch-related-promoted-properties"></a>与批处理相关的已提升的属性
当 SWIFT 反汇编程序发布到 MessageBox 数据库源自的入站批处理的消息时，拆装器会将消息标记与特殊 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提升特定对消息进行批处理的属性。 这些属性提供上下文信息，如从哪些序号位置发出一条消息的批时中的批处理，部件 A4SWIFT 已预留，等等。  
  
 A4SWIFT 设置批处理消息，升级以下的属性：  
  
- **A4SWIFT_BatchId**  
  
- **A4SWIFT_IsMessageHeaderValued**  
  
- **A4SWIFT_IsMessageTrailerValued**  
  
- **A4SWIFT_NumberOfParts**  
  
- **A4SWIFT_PosInBatch**  
  
  有关这些及其他升级的属性的信息，请参阅[A4SWIFT_ * 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
## <a name="failures-during-batch-processing"></a>批处理的处理期间出现的故障  
 SWIFT 反汇编程序当批处理过程中遇到消息失败 （分析或验证） (**入站解除批处理**设置为**True**)，其行为取决于批处理的配置中，为如下所示：  
  
- 用于批处理 (**入站解除批处理**设置为**True**) 与已启用的碎片 (**碎片**设置为**True**)，则拆装器发布到 MessageBox 数据库的失败的消息分别使用相应的错误信息在升级的属性中附加和序列化**ErrorCollection** XML。 如果拆装器发现意外的数据末尾的批处理 （即，拆装器无法分析使用任何指定的架构的数据），拆装器在批处理中的最后一个消息中包括此意外的数据，并将其标记为已失败分析. 如果拆装器在处理期间遇到致命错误，拆装器将发布导致出现错误，以及到交换作为单个消息末尾的所有数据的消息。 拆装器不会严重错误后进行分段的消息。  
  
- 用于批处理 (**入站解除批处理**设置为**True**) 与禁用的碎片 (**碎片**设置为**False**)，则拆装器发布到 MessageBox 数据库的失败的消息分别使用相应的错误信息在升级的属性中附加和序列化**ErrorCollection** XML。 此外，拆装器 （包含一个或多个失败的消息） 的整个批处理到 MessageBox 数据库将作为发布一条消息，以本机形式 （输入的精确副本）。 拆装器将其与标记**A4SWIFT_Failed**提升属性集**True**以指示批处理包含一个或多个失败的消息。 拆装器还会将附加序列化**ErrorCollection**的 XML 与非零碎的批处理，表示遇到批处理内的单个消息中的所有错误的串联。 若要了解失败的消息批次中的每条消息错误详细信息，必须从 MessageBox 数据库中检索单个失败的消息 （通过关联来 A4SWIFT_BatchId 上），并将解压缩**ErrorCollection** XML为每个失败的消息。 如果拆装器发现意外的数据末尾的批处理 （即，拆装器无法分析使用任何指定的架构的数据），拆装器将包括意外的数据的整个失败的批处理 （因为拆装器发布到MessageBox 数据库中逐字字符串），并将其标记为已失败由于意外的数据分析。  
  
- 对于非批处理方案 (**入站解除批处理**设置为**False**)，拆装器始终失败将消息发布到 MessageBox 数据库按预期方式分别。  
  
  有关 A4SWIFT 失败/错误详细信息的已提升属性和**ErrorCollection**对象，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。  
  
## <a name="see-also"></a>请参阅  
 [反汇编入站的批处理](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)   
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)