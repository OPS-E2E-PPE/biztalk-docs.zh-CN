---
title: 未声明的自定义设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a33abb76d49cfa5db640b1d15d9fde420f19c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974222"
---
# <a name="undeclared-customizations"></a>未声明的自定义项
而无需定义的格式或数据的性质，可以将数据添加到一条消息。 您使用未声明的 Z 段执行此操作。 未声明的 Z 段是一条消息末尾的意外的实例。 分析器/XML 验证器不会验证段。 它不由任何架构定义。 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将视为二进制大型对象 (BLOB) 的段。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将未声明的 Z 段数据，通过传递作为三部分组成的消息的第三个部分。 三个部分是标头、 正文和未声明的 Z 段，也称为 Z 一部分。 以字母"Z"，例如，"ZPD"自定义患者的人口统计信息的信息，开头的段 ID 标识的 Z 部分。  
  
## <a name="see-also"></a>请参阅  
 [声明自定义项](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)   
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)