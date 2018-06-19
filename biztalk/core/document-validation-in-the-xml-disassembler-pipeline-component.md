---
title: 文档中的 XML 反汇编程序管道组件的验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dcea790208bf0234c67c8c941e6355fb367d82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239381"
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a>XML 反汇编程序管道组件中的文档验证
默认情况下，XML 拆装器不会根据架构验证 XML 文档。 但是，你可以配置 XML 反汇编程序，以通过设置验证 XML 文档**验证文档结构**属性。  
  
> [!CAUTION]
>  如果要升级的字段声明为简单数据类型，但包含复杂数据，则属性升级将导致不可预知的结果。 若要避免这种情况下，配置 XML 反汇编程序，通过设置执行文档验证**验证文档结构**属性**True**。  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)