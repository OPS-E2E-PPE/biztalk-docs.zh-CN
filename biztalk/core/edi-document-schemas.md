---
title: EDI 文档架构 |Microsoft Docs
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
ms.openlocfilehash: ebe89a18538cb09c88ecb3098ca556c75422c803
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530805"
---
# <a name="edi-document-schemas"></a>EDI 文档架构
文档架构用于定义 EDI 事务文档类型的正文。  
  
## <a name="schema-delivery-and-setup"></a>架构送达与安装程序  
 EDI 文档架构中的自解压缩可执行文件，采用压缩形式传递[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe。 自解压缩可执行文件可确保适当的文件夹结构创建 （按照编码类型和版本/发行版子类型）。 可执行文件执行时，它 EANCOM、 EDIFACT、 HIPAA 和 X12 架构与可执行文件相同的目录的子文件夹中。  
  
 默认架构命名空间包括：  
  
-   对于 X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`  
  
-   对于 EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`  
  
## <a name="schema-naming-convention"></a>架构命名约定  
 针对 X12 和 EDIFACT 编码类型的命名约定\<编码\>*\<版本\>\<发布\>\\*  \<Doctype\>。 示例包括，X12_00401_864.xsd 架构代表 X12 864 文档类型 （版本为 004、 发行版） 和 EDIFACT AUTHOR 文档类型的 EDIFACT_D01C_AUTHOR.xsd 架构 （版本为 D01、 发行版为 C）。  
  
> [!NOTE]
>  EDIFACT 架构的架构名称是区分大小写。 例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。  
  
## <a name="schema-contents"></a>架构内容  
 文档架构以 ST 事务集标头，X12 编码的文档 SE 事务集尾部结尾。 它以 UNH 消息标头，对于 EDIFACT 编码文档 UNT 消息尾部结尾。 该架构定义这些标头和尾部的每个数据元素。  
  
 文档架构则定义事务集/消息中的每个段和这些段中的数据元素。 例如，X12_00401_864.xsd 架构定义 BMG 段 BMG01、 BMG02 和 BMG03 元素。 该架构指定段的复杂数据类型，例如字段顺序、 分隔符类型和命名空间的特征。 如果有段的跨字段验证规则，该架构定义的规则。 有关详细信息，请参阅[跨字段-段验证](../core/cross-field-segment-validation.md)。  
  
 该架构指定段，如简单数据类型、 最小出现次数、 最小长度和最大长度内每个数据元素的特征。  
  
 如果消息类型中没有循环，该架构定义内的循环中，每个循环、 最小值和最大出现次数的数据元素和循环是有限或不受限制。 架构还定义段的嵌套循环是显式或隐式和。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息结构](../core/edi-message-structure.md)   
 [EDI 消息验证](../core/edi-message-validation.md)