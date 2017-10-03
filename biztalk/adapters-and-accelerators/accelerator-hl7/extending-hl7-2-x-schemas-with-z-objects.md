---
title: "扩展 HL7 2.X 架构具有 Z 对象 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27ef2bea3e13904f04449a5b77d05672c2b2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a>扩展 HL7 2.X 架构具有 Z 对象
HL7 组织定义 HL7 2.X 架构，并要求所有发件人和接收方，来识别并使用这些架构，因为组织定义它们。 符合架构时，可确保的互操作性。 但是，HL7 标准允许你自定义现有 HL7 2.X 架构为你特定的本地目的。 你还可以定义全新的架构和对象。 使用哪些 HL7 标准调用 Z 对象执行此操作。  
  
 标准 HL7 未定义 Z 对象的值。 已发布的 HL7 架构不包含它们。 可以定义这些本地，并通过与所有本地方协议使用它们。 HL7 组织保留所有消息类型、 触发器事件、 段、 数据类型和表名称以"Z"开头为此本地使用。 由于前缀，HL7 标准调用这些站点定义对象 Z 对象。  
  
> [!NOTE]
>  当你将 Z 对象添加到现有的 HL7 定义架构时，你可以结束使用该架构的多个版本。 若要处理这些多个版本的最佳方式是使用中的 Namespace 功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。 您可以在找到此功能**验证**选项卡中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 （在方级别）。 你还需要更改在部署该项目的架构中的命名空间属性。  
  
 在创建或处理 Z 对象时，你应遵循 HL7 组织已建立的 Z 对象的规则...  
  
 当你将 Z 对象添加到现有架构或创建一个新的 Z 消息架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将使用具有 Z 对象架构来处理 HL7 编码消息。 此类型的 Z 对象是一个声明的 Z 对象。 你还可以使用未声明的 Z 段，该集成引擎不会根据消息架构处理。 有关此类型的 Z 段的详细信息，请参阅[处理未声明 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [自定义消息通过 Z 对象](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)