---
title: 数据类型 |Microsoft 文档
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
ms.openlocfilehash: b8580b4f6c2a3f1a9f461b112bb4125f1a11ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204941"
---
# <a name="data-types"></a>数据类型
数据类型规范是重要工具，用于分区的 HL7 标准，复杂性，并了解 HL7 字段的数据内容至关重要。 某些数据类型是简单和包含只有一个组件，并且一些包含许多组件和子组件。 例如，PID.5 患者名称具有数据类型在版本 2.4 的 XPN。 此数据类型支持常见的细分。 一个英语语言的名称，例如，姓氏、 名字、 中间名，以及后缀，前缀，名称类型代码和名称的有效性 （日期） 范围。  
  
 在新 HL7 版本中，则可以添加，但不是删除数据类型。 如果您通过添加新组件为数据类型，添加内容，你可以仅添加它们末尾的范围内，则它们嵌套的结构。 在某些情况下，HL7 组织合并现有数据类型，以形成新的。 这会导致需要支持作为以前个子组件中的原始数据类型的项。  
  
 下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]支持从 2.1 版的所有 HL7 版本的标准数据类型上。  
  
-   在开发接口时，可以在适当的限制数据类型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [数据类型 ID 在 HL7 2.1](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)