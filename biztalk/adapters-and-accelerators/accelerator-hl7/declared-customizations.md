---
title: 声明自定义设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4d84870448bb8102c9d5c1d684b8fbb22ac74ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255573"
---
# <a name="declared-customizations"></a>声明自定义项
使用声明的自定义项，可以修改或添加到 HL7 消息的灵活性。 甚至可以定义新类型的消息。 可以通过以下方式之一执行此操作：  
  
- 通过定义新的消息类型或触发器事件更改消息的定义  
  
- 将新段添加到现有的消息类型  
  
- 更改现有的消息部分 （段、 字段、 组件或子组件） 的数据类型  
  
- 更改可能可以使用现有的消息部分中的值  
  
  > [!NOTE]
  >  你可以在声明的 Z 对象或 HL7 架构中的标准对象中使用的枚举值。 若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。  
  
  修改或添加到 HL7 消息通过添加、 维护和将在当前定义的消息类型的自定义对象相关联。 HL7 标准调用这些自定义对象"Z 对象"来区分它们来自符合 HL7 标准的现有对象。 使用 BizTalk 编辑器来定义 Z 对象。 此外可以使用 BizTalk 编辑器来处理跨所有触发器事件传播对 Z 对象的更新的功能和将其包含的抽象消息。 有关创建 Z 对象的详细信息，请参阅[使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)。  
  
  可以使用 Z 对象提供的使用方式的 HL7 标准中未指定的段的本地定义。 进行这些更改对架构的 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 在计算机上安装的安装向导。 然后可以与其他共享这些已修改的架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装与之交换消息。  
  
## <a name="types-of-z-objects"></a>Z 对象类型  
 HL7 标准 (2.X) 当前支持自定义以下的形式：  
  
-   **自定义触发器的事件。** 如果在本地区域和需要新的消息结构，或者想要支持不包括在标准的触发器事件，可以创建使用 Z 前缀，例如，Z05 的新触发器事件。 在这种情况下，必须定义抽象的消息和包含的段数模式来创建新的本地消息架构。  
  
-   **自定义的段。** 如果对象在本地区域中，在上下文中的已受支持的触发器事件，并需要其他数据，可以创建一个新段并包括所需的数据元素在段中。 必须指定使用现有的 HL7 数据类型的段中的元素。 您可以通过在架构中创建一个新的记录在 BizTalk 编辑器中，创建自定义的 Z 段。 有关详细信息，请参阅[创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)。 或者，可以添加到 Access 数据库，然后将该 Z 段添加到消息结构的 Z 段。 有关详细信息，请参阅[解决数据库错误](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)。  
  
-   **自定义数据的子类型。** HL7 提供了一系列支持的数据类型，例如，将格式化文本，扫描图像、 音频数据。 但是，如果你想要定义其他数据类型，您可以这样做通过前缀助记键与"Z"一起使用，从而创建 Z 数据键入。  
  
    > [!NOTE]
    >  不允许，标准，若要创建新的数据类型，或将元素添加到现有段范围内。 仍小于是它允许以执行当前未使用的元素，它重新定义以满足某些其他用途。 但是，支持旧接口的组织可能需要以适应这种做法。  
  
-   **自定义的表。** 在消息中的许多现有对象有有限的特定值，范围由通过 HL7 通用架构定义表中的枚举定义。 您可以修改这些枚举，以将通过创建 Z 表启用其他值。  
  
## <a name="see-also"></a>请参阅  
 [未声明的自定义项](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)   
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)