---
title: 数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7b8d75be35be01e9c961d6bd054dcaed6d3aee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984670"
---
# <a name="data-types"></a>数据类型
数据类型规范是分区的 HL7 标准复杂性的一个重要工具，了解 HL7 字段的数据内容的关键。 某些数据类型是简单和包含只有一个组件，并且某些包含许多组件和子组件。 例如，PID.5 患者名称具有键入 XPN 版本 2.4 中的数据。 此数据类型支持的常见细分线的一个英语语言的名称，例如，姓氏、 名字、 中间名，以及后缀、 前缀、 名称类型代码和名称的有效性 (date) 范围。  
  
 在新 HL7 版本中，您可以添加，但不是删除数据类型。 如果您通过添加新组件或子组件为数据类型，添加内容，则只在其中它们所嵌套的结构末尾添加它们。 在某些情况下，HL7 组织合并现有的数据类型，以形成新的。 这就会导致需要支持先前在原始数据类型的子组件的项。  
  
 Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 上支持所有 HL7 版本从 2.1 版的标准数据类型。  
  
- 在开发接口时，可以在适当的限制的数据类型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HL7 中的数据类型 ID 2.1](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)