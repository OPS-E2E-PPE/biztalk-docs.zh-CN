---
title: XML 信息在 XML 汇编程序管道组件中设置元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], processing instructions
- Add XML declaration property
- XMLNorm.AddXMLDeclaration property
- pipeline components, XML Assembler
- XML Assembler [pipeline component], XML information set
ms.assetid: 5a262763-838e-476b-8117-30c94bc1d64a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b194b85c88f63036cd74fcd9838aa99e73de6556
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289517"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a>XML 信息集 XML 汇编程序管道组件中的元素
XML 组装器组件可处理 XML 信息集合元素，如下所示：  
  
|元素|Description|  
|-------------|-----------------|  
|comment|保留文档中打开与关闭 XML 标记之间的注释。|  
|CDATA|保留文档中打开与关闭 XML 标记之间的 CDATA。 CDATA 值不用于属性升级或可分辨字段。|  
|处理指令|处理指令前处理文档的 XML 标记基于其值 (有关详细信息，请参阅[处理 XML 汇编程序管道组件中的说明](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。 文档打开标记与关闭标记之间的处理指令将保留， XML 结束标记后的处理指令被忽略，因为前后也是所有说明操作，在中，信封。|  
|XML 声明|XML 组装器管道组件可能会保留 XML 声明字符串（例如，`<?xml version='1.0'? encoding='UTF-8'>`）。 这将由控制**添加 XML 声明**属性或在消息上下文中，它的等效项**XMLNorm.AddXMLDeclaration**。<br /><br /> 如果此选项设置为**True**然后 XML 声明将添加到文档。 如果 XML 声明已存在，则会覆盖该声明。<br /><br /> 如果此选项设置为**False**，没有 XML 声明将被添加，并且将删除任何现有的 XML 声明。 消息上下文中此属性的值的优先级高于管道设计器中指定的值。<br /><br /> 默认值： **True** （始终添加 XML 声明）|  
  
## <a name="see-also"></a>另请参阅  
 [XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)