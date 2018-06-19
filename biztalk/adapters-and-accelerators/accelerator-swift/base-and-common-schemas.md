---
title: 基类型和通用架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ca51abfcdbfe965bc3da8deeb97f72df736903
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209173"
---
# <a name="base-and-common-schemas"></a>基类型和通用架构
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]已实现的记录和所包含独立的架构中的单个消息架构的元素。 此方法提供了一个位置来为字段和格式，使此类更改中的消息架构提供更新。  
  
 基础架构 (**SWIFT 基 Types.xsd**) 包含的消息架构引用通用记录和元素定义。 通用记录和元素定义与 SWIFT FIN 消息字段相对应。 你需要将此架构添加到任何使用的消息架构的项目。 基础架构介绍的规则和常用函数，并定义 A4SWIFT 使用来验证相应的消息实例的格式。 SWIFT 基 Types.xsd 架构定义 XSD **simpleType**和 SWIFT 字段的复杂元素。 已定义 SWIFT **simpleType**元素的所有基字段，如量、 速率、 价格和等等，SWIFT 使用中的许多字段。 SWIFT 基 Types.xsd 架构还定义包括许多自定义的字段的 XSD 复杂元素**simpleTypes**架构中定义。 例如， **BankIdentifierCode**复杂元素使用银行代码、 国家/地区代码、 区号和分支代码。 用户可以添加新**simpleTypes**和镜像 SWIFT 字段，并可以修改现有类型的复杂元素。 你应注意，但是，当你修改现有类型，因为业务规则引擎 (BRE) 验证和 XML 验证功能都依赖于这些定义的类型。  
  
 公用架构 (**SWIFT 常见数据 Types.xsd**) 基础架构中定义相应的字段的字符集。 SWIFT 定义中引用这些字符集*SWIFT 用户手册*。 你还需要将公用架构添加到架构项目。  
  
## <a name="see-also"></a>另请参阅  
 [使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)