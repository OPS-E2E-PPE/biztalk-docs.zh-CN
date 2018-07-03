---
title: 为动态消息类型发现创建自定义标头架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf73b5cf02d6fa25fdea1347e56573ff023d934a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009118"
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a>为动态消息类型发现创建自定义标头架构
在大多数情况下，应 SWIFT 标头架构的配置属性的 SWIFT 反汇编程序指定默认 SWIFT 标头架构 (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema)。 SWIFT 反汇编程序使用默认 SWIFT 标头架构来分析消息标头符合 SWIFT 标准规范，并具有所需的已提升属性到促进动态架构解析 （和"双 type"的子类型解析SWIFT 消息，如 MT574_IRSLST 和 MT574_W8BENO）。 有关默认 SWIFT 标头架构并了解如何 SWIFT 反汇编程序执行架构解析的详细信息，请参阅[动态消息类型发现和架构解析](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)。  
  
 对于其他方案，其中，消息包含非 SWIFT 标准标头数据，可用于自定义标头架构标头分析和动态消息类型发现。 若要创建和使用自定义标头架构进行动态架构解析，请执行以下操作：  
  
1. 创建 SWIFT 反汇编程序可用于结构上将解析预期的标头数据格式的自定义架构。  
  
2. 标识架构中的哪些字段将保存的值，该值指示消息类型。  
  
3. 添加 A4SWIFT 属性架构 (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) 到"属性架构列表"的自定义标头架构并将提升在相应的字段，指示消息类型使用以下[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]属性：  
  
   -   **A4SWIFT_MessageType**  
  
   -   **A4SWIFT_MessageType2** (可选如果**A4SWIFT_MessageTypes**使用)  
  
   -   **A4SWIFT_SecondaryMessageType** （可选）  
  
4. 生成和部署自定义标头架构。  
  
5. 将 SWIFT 反汇编程序 （在接收管道项目） SWIFT 标头架构配置属性设置为自定义标头架构。  
  
   有关这些及其他升级的属性的详细信息，请参阅[A4SWIFT_ * 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。 有关使用 BizTalk 编辑器创建和编辑架构、 使用属性架构升级属性和生成和部署架构项目的详细信息，请参阅 BizTalk Server 帮助。  
  
## <a name="see-also"></a>请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)