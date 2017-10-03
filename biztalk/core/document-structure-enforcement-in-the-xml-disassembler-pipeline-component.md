---
title: "文档中的 XML 反汇编程序管道组件的结构强制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], document structure
- pipeline components, XML Disassembler
ms.assetid: ac405bf2-f92b-4b45-8256-dd188ec9510a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e14b20292b23a0f50362940e3b873fa37a3f5bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-disassembler-pipeline-component"></a>XML 反汇编程序管道组件中的文档结构强制
如果在 XML 拆装器中显式引用文档架构或信封架构，则 XML 拆装器只处理消息类型符合该架构的文档。 其他文档均不处理，而不管是否为其引用了已部署的架构。  
  
 XML 拆装器强制要求指定的信封架构顺序；但不强制要求文档架构的顺序。  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)