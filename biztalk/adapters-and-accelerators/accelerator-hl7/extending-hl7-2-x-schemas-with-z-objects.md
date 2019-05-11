---
title: 扩展 HL7 2.X 架构使用 Z 对象 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 514df3e1676e08d33be3a9fb00c61e47925b7b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267853"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a>使用 Z 对象扩展 HL7 2.X 架构
HL7 组织定义 HL7 2.X 架构，并要求所有发件人和接收方，以便识别和使用这些架构，因为组织定义它们。 符合这些架构可确保互操作性。 但是，HL7 标准允许你自定义现有 HL7 2.X 架构为特定的本地目的。 此外可以定义整个新架构和对象。 使用哪些 HL7 标准调用 Z 对象执行此操作。  
  
 标准 HL7 不定义 Z 对象的值。 已发布的 HL7 架构不包含它们。 可以定义它们本地，并使用它们的所有本地的参与方的协议。 HL7 组织保留所有消息类型、 触发器事件、 段、 数据类型和表名称以供此本地使用开头"Z"。 由于前缀，HL7 标准调用这些站点定义的对象 Z 对象。  
  
> [!NOTE]
>  当将 Z 对象添加到现有的 HL7 定义架构时，你可以结束该架构的多个版本。 处理这些多个版本的最佳方法是使用中的 Namespace 功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。 您可以在找到此功能**验证**选项卡中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 （在参与方级别）。 您还需要更改部署该项目的架构中的命名空间属性。  
  
 在创建或处理 Z 对象中，应遵循的规则为 Z 对象建立 HL7 组织...  
  
 将 Z 对象添加到现有的架构或创建新的 Z 消息架构时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将使用 Z 对象具有架构来处理 HL7 编码的消息。 此类型的 Z 对象是声明的 Z 对象。 此外可以使用未声明的 Z 段，集成引擎不会处理根据消息架构。 有关此类型的 Z 段的详细信息，请参阅[处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建已声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [在架构中创建自定义表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [通过 Z 对象自定义消息](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)