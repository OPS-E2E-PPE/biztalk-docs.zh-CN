---
title: 未声明的自定义项 |Microsoft 文档
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
ms.openlocfilehash: 77f688e4cf6a4bbb55243d9f5f6f60e144bad862
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206485"
---
# <a name="undeclared-customizations"></a>未声明的自定义项
可以将数据添加到一条消息，而定义的格式或数据的性质。 你使用未声明的 Z 段执行此操作。 未声明的 Z 段是一条消息末尾的意外的实例。 分析器/XML 验证程序不验证段。 它不是由任何架构定义。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 段将其视为二进制大型对象 (BLOB)。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将数据通过的未声明的 Z 分段作为第三部分的由三部分消息传递。 这三部分如下标头、 正文和未声明的 Z 段，也称为 Z 一部分。 字母"Z"，例如，"ZPD"自定义患者人口统计信息的信息，以开头的段 ID 标识的 Z 部分。  
  
## <a name="see-also"></a>另请参阅  
 [声明的自定义项](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)   
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)