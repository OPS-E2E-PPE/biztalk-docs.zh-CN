---
title: 基类和常见的架构 |Microsoft Docs
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
ms.openlocfilehash: 5512c9233e292fdafa232db5c36ac6ff14de53cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378798"
---
# <a name="base-and-common-schemas"></a>基类和通用架构
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]已实现的记录和所包含不同的架构中的单个消息架构的元素。 这种方法提供单个位置来提供更新的字段和格式，使此类更改的消息架构。  
  
 基本架构 (**SWIFT 基 Types.xsd**) 包含消息架构引用的通用记录和元素定义。 通用记录和元素定义对应于 SWIFT FIN 消息字段。 您需要将此架构添加到任何项目都使用消息架构。 基础架构包含的规则和公共函数，并定义 A4SWIFT 用来验证相应的消息实例的格式。 SWIFT 基本 Types.xsd 架构定义 XSD **simpleType**和 SWIFT 字段的复杂元素。 已定义 SWIFT **simpleType**所有基本字段，例如量、 速率、 价格和等等，SWIFT 使用中的许多字段的元素。 SWIFT 基本 Types.xsd 架构还定义了 XSD 包括许多自定义的字段的复杂元素**simpleTypes**在架构中定义。 例如， **BankIdentifierCode**复杂元素使用银行代码、 国家/地区代码、 区号和分支代码。 用户可以添加新**simpleTypes**和镜像 SWIFT 字段，并可以修改现有类型的复杂元素。 您需要采取措施，但是，当您修改现有类型，因为业务规则引擎 (BRE) 验证和 XML 验证功能都依赖于这些定义的类型。  
  
 常见的架构 (**SWIFT 常见数据 Types.xsd**) 基础架构中定义的字段相应的字符集。 SWIFT 定义中引用这些字符集*SWIFT 用户手册*。 此外需要将常见的架构添加到架构项目。  
  
## <a name="see-also"></a>请参阅  
 [处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)