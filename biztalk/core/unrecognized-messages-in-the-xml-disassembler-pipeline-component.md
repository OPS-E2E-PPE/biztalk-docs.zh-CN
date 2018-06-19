---
title: 无法识别的消息中 XML 反汇编程序管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82396002ff9d35484af5f0000dc3468c8ad37fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286741"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a>无法识别的消息中 XML 反汇编程序管道组件
如果出现以下情况，则 XML 拆装器组件可将消息作为“无法识别”进行处理：  
  
-   收到不带任何正文、正文为空或正文中的数据为空的 XML 消息。  
  
-   收到 XML 消息，但未为该消息部署任何架构。  
  
 无法识别的消息处理基于**允许无法识别的消息**属性 (或在**XMLNorm.AllowUnrecognizedMessage**消息上下文属性)。  
  
 如果**允许无法识别的消息**设置为**True**，将发生以下情况：  
  
-   不带任何正文、正文为空或正文中的数据为空的消息将不做更改地通过 XML 拆装器。  
  
-   没有与其相关联的已部署架构的 XML 文档将不做更改地通过 XML 拆装器。  
  
-   具有与其相关联的已部署架构的 XML 文档将由 XML 拆装器进行处理，而不管是否在组件属性中显式引用了该架构或是否在架构解析的过程中发现了该架构。  
  
 如果**允许无法识别的消息**设置为**False**，将发生以下情况：  
  
-   不带任何正文、正文为空或正文中的数据为空的消息将不会通过 XML 拆装器。  
  
-   没有与其相关联的已部署架构的 XML 文档将不会通过 XML 拆装器。 如果可能，将会报告错误并挂起该消息。  
  
-   具有与其相关联的已部署架构的 XML 文档将由 XML 拆装器进行处理，而不管是否在组件属性中显式引用了该架构或是否在架构解析的过程中发现了该架构。  
  
 默认情况下，XML 拆装器将不允许无法识别的消息。  
  
> [!NOTE]
>  无论采用何种 XML 反汇编程序不处理非 XML 消息**允许无法识别的消息**属性设置。  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)