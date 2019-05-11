---
title: XML 组装器管道组件中的 XML 信息集合元素 |Microsoft Docs
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
ms.openlocfilehash: 2c6662f65c82a79fb174fe3b97c10fc24351255b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246398"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中的 XML 信息集合元素
XML 组装器组件，如下所示处理 XML 信息集合元素。  
  
|元素|Description|  
|-------------|-----------------|  
|comment|打开和关闭文档中的 XML 标记之间保留注释。|  
|CDATA|CDATA 保留之间打开和关闭文档中的 XML 标记。 CDATA 值不用于属性升级或可分辨字段。|  
|处理指令|处理指令位于文档 XML 标记进行处理之前根据它们的值 (有关详细信息，请参阅[XML 组装器管道组件中处理指令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。 文档打开和关闭之间的处理指令将保留标记。 XML 结束标记后的处理指令被忽略，因为之前，在中，或信封之后是任何说明。|  
|XML 声明|XML 声明字符串，如`<?xml version='1.0'? encoding='UTF-8'>`，可能会保留 XML 组装器管道组件。 这由控制**添加 XML 声明**属性或在消息上下文，其等效**XMLNorm.AddXMLDeclaration**。<br /><br /> 如果此选项设置为 **，则返回 True**则会向文档添加 XML 声明。 如果已在 XML 声明已存在，它将被覆盖。<br /><br /> 如果此选项设置为**False**，将添加任何 XML 声明，并且将删除任何现有的 XML 声明。 在消息上下文中此属性的值优先于在管道设计器中指定的值。<br /><br /> 默认值：**True** （始终添加 XML 声明）|  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)