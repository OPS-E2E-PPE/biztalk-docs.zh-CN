---
title: 文档结构强制规定在 XML 组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ef167df5aaef827e11d33fc73191d46b68afb2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389527"
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中的文档结构强制规定
如果在 XML 组装器中显式引用文档或信封架构，XML 组装器可确保与对应于引用的架构的消息类型的唯一文档进行处理。 不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。  
  
> [!NOTE]
>  信封架构仅取自第一条消息。 信封的属性始终取自第一条消息。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)