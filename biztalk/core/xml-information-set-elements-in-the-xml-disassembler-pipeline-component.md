---
title: XML 拆装器管道组件中的 XML 信息集合元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b9d2b581a327f8d7009794338d431a2358db748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298480"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a>XML 拆装器管道组件中的 XML 信息集合元素
XML 拆装器处理 XML 信息集合元素，如下所示。  
  
|元素|Description|  
|-------------|-----------------|  
|comment|注释保留在文档;但是，不会保留 XML 信封中的任何注释。|  
|CDATA|CDATA 保留在文档中。 不保留显示在文档 （例如，在一个信封） 外部的 CDATA 元素。|  
|处理指令|XML 拆装器保留显示中或之前的 XML 文档的处理指令。 不保留处理指令，使其不显示在 XML 文档或之前或之后信封。|  
|XML 声明|删除所有传入 XML 消息的 XML 声明元素。|  
  
## <a name="see-also"></a>请参阅  
 [XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)