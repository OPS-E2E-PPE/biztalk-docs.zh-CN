---
title: EDI 文档架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b96089f7f76af1183f457202bb2e22b5be7f146
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968299"
---
# <a name="edi-document-schemas"></a>EDI 文档架构
文档架构用于定义 EDI 事务文档类型的正文。  
  
## <a name="schema-delivery-and-setup"></a>架构送达与安装  
 EDI 文档架构中的自解压可执行文件中的压缩状态传递[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe。 自解压缩可执行文件可确保创建适当的文件夹结构（按照编码类型和版本/发行版子类型）。 此可执行文件执行时，它会将 EANCOM、EDIFACT、HIPAA 和 X12 架构存储在同一目录的子文件夹中作为可执行文件。  
  
 默认的架构命名空间包括：  
  
-   对于 X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`  
  
-   对于 EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`  
  
## <a name="schema-naming-convention"></a>架构命名约定  
 X12 和 EDIFACT 编码类型的命名约定是\<编码\>_\<版本\>\<版本\>\_\<Doctype\>。 例如，X12_00401_864.xsd 架构代表 X12 864 文档类型（版本为 004、发行版为 01），EDIFACT_D01C_AUTHOR.xsd 架构代表 EDIFACT AUTHOR 文档类型（版本为 D01、发行版为 C）。  
  
> [!NOTE]
>  EDIFACT 架构的架构名区分大小写。 例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。  
  
## <a name="schema-contents"></a>架构内容  
 对于 X12 编码的文档，文档架构以 ST 事务集标头开头，以 SE 事务集尾部结尾。 对于 EDIFACT 编码的文档，文档架构以 UNH 消息标头开头，以 UNT 消息尾部结尾。 架构将定义这些标头和尾部的每个数据元素。  
  
 文档架构则定义事务集/消息中的每个段，以及这些段中的数据元素。 例如，X12_00401_864.xsd 架构定义 BMG 段中的 BMG01、BMG02 和 BMG03 元素。 架构指定段的复杂数据类型的特性，例如字段顺序、分隔符类型和命名空间。 如果存在针对段的跨字段验证规则，则架构将定义这些规则。 有关详细信息，请参阅[交叉字段段验证](../core/cross-field-segment-validation.md)。  
  
 架构指定段内每个数据元素的特性，如简单数据类型、最少出现次数、最小长度及最大长度。  
  
 如果消息类型中存在循环，则架构将定义每个循环内的数据元素、循环的最小和最大次数，以及循环是绑定循环还是非绑定循环。 架构还定义段的嵌套，以及循环是显式循环还是隐式循环。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息结构](../core/edi-message-structure.md)   
 [EDI 消息验证](../core/edi-message-validation.md)