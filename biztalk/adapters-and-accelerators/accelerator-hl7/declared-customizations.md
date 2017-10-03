---
title: "声明自定义项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 767fdd543b1cb5d87bf3ec1c1943ac81d91c6ea4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="declared-customizations"></a>声明的自定义项
借助声明自定义，你可以修改或添加到 HL7 消息灵活。 你甚至可以定义新类型的消息。 你可以在任何通过以下方式来执行此操作：  
  
-   通过定义新的消息类型或触发器事件更改一条消息的定义  
  
-   将新段添加到现有的消息类型  
  
-   更改现有的消息部分 （段、 字段、 组件或子组件） 的数据类型  
  
-   更改可以使用现有的消息部分中的潜在值  
  
    > [!NOTE]
    >  你可以更改声明的 Z 对象或 HL7 架构中的标准对象中使用的枚举值。 若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。  
  
 修改或通过添加、 维护以及关联的当前定义的消息类型中的自定义对象将添加到 HL7 消息。 HL7 标准调用这些自定义对象"Z 对象"来区分它们来自符合 HL7 标准的现有对象。 使用 BizTalk 编辑器定义 Z 对象。 此外可以使用 BizTalk 编辑器若要使用的所有触发器事件传播到 Z 对象更新的功能和抽象的消息，其中包括它。 有关创建 Z 对象的详细信息，请参阅[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)。  
  
 你可以使用 Z 对象来指定为可以以 HL7 标准中未指定的方式使用的段的本地定义。 进行这些更改向架构的 HL7 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 在计算机上安装的安装向导。 然后可以与其他共享这些修改的架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]与其交换消息的安装。  
  
## <a name="types-of-z-objects"></a>类型的 Z 对象  
 HL7 标准 (2.X) 当前支持下列形式的自定义项：  
  
-   **自定义触发事件。** 如果你在本地区域和需要新的消息结构，或想要支持不包含在标准的触发器事件，则可以创建使用 Z 作为前缀，例如，Z05 新触发器事件。 在这种情况下，必须定义抽象的消息和包含的段的模式来创建新的本地消息架构。  
  
-   **自定义的段。** 如果要在已受支持的触发器事件的因而需要进行其他数据的上下文中的本地区域可以创建新的段和包括分段内的需要的数据元素。 必须指定使用现有的 HL7 数据类型的段中的元素。 你可以通过在架构中创建一条新记录在 BizTalk 编辑器中，创建自定义 Z 段。 有关详细信息，请参阅[创建声明 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)。 或者，你可以添加通过访问数据库，然后将该 Z 段添加到消息结构的 Z 段。 有关详细信息，请参阅[解决数据库错误](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)。  
  
-   **自定义数据子类型。** HL7 例如提供支持的数据类型的列表、 格式化文本、 扫描图像，音频数据。 但是，如果你想要定义其他数据类型，你可以执行以便通过前缀用于"Z"助记键，从而创建 Z 数据键入。  
  
    > [!NOTE]
    >  不允许的情况下，该标准中，若要创建新的数据类型，或将元素添加到现有段的范围内。 仍 less 是它允许以执行当前未使用的元素，它重新定义它以满足某些其他目的。 另一方面，支持旧接口的组织可能需要适应这种做法。  
  
-   **自定义的表。** 消息中的许多现有对象有有限的特定值范围被枚举由 HL7 通用架构定义的表中所定义。 你可以修改这些枚举，以通过创建 Z 表启用其他值。  
  
## <a name="see-also"></a>另请参阅  
 [未声明的自定义项](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)   
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)