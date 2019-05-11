---
title: EDI 字符集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57fae748-d66e-4ecf-be00-70147078ef93
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 252fb7425b30040139cbccc78e6e71e3083badca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389241"
---
# <a name="edi-character-sets"></a>EDI 字符集
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用字符集来验证整个 EDI 交换。 对于 X12 编码的消息使用的字符集以及 EDIFACT 或 KEDIFACT 编码的消息都在不同的方式确定。  
  
## <a name="edifact-character-set"></a>EDIFACT 字符集  
 在其字符集方面自描述的 EDIFACT 编码的交换。 使用了 UNB1 数据元素。 EDIFACT 要求标记名称和分隔符是 ASCII 类型;因此，定位 UNB1 来为其余交换相关的代码页来进行应用是可能的。  
  
 处理传入的 EDIFACT 消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定要使用从 UNB1 数据元素，该消息的字符集。 贸易合作伙伴协议中的任何设置不是必需的。  
  
 处理传出的 EDIFACT 消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用贸易合作伙伴协议或后备协议中的字符集。 在中设置 UNB1 数据元素**字符集和分隔符**页中的双向协议选项卡 （如果已定义协议） 或**字符集和分隔符**的协议选项卡中的页**EDIFACT 后备设置**对话框 （如果未定义协议）。 UNB1.1 是必需的复合数据元素名语法标识符。 UNB1.2 是 EDIFACT 字符集的版本。 UNB1 数据元素还用于验证 （不在您离开某一字段选项卡上，或显示其他页） 保存整个属性集时为贸易合作伙伴管理用户界面中的属性输入的值。  
  
 可用的字符集是 KECA、 UNOA、 UNOB、 UNOC、 UNOD、 UNOE、 UNOF、 UNOG、 UNOH、 UNOI、 UNOJ、 UNOK、 UNOX 和 UNOY。 默认值是 UNOB。 这些级别的完整字符集在 ISO 9735 EDIFACT 语法规则中指定。  
  
> [!NOTE]
>  如果对入站或出站交换，EDI 拆装器遇到 UNOC 字符集或 EDI 组装器将使用 latin-1 代码页，而不是 utf-8 代码页。 这是必需的因为 utf-8 不是 UNOC 的超集。 某些在 UNOC 中可接受的字符将导致交换被挂起时作为 utf-8 处理。  
  
 在某些 EDIFACT 字符集中的字符可能是双字节字符，而在其他 EDIFACT 字符集，它们可能是单字节字符。 因此，设置基于该交换中的字符数的批发布条件时的交换中的字节数可能会因使用的字符集。  
  
 UNA 段和段名 UNB 仅限于 ASCII 字符集中的值。  
  
## <a name="kedifact-character-set"></a>KEDIFACT 字符集  
 因为与 EDIFACT 中，字符设置为 UNB1 数据元素中建立 KEDIFACT 编码的交换。 对于 EDIFACT，字符设置为通过应用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在处理 KEDIFACT 交换数据元素中建立**UNB1**的**字符集和分隔符**中的双向页协议选项卡 （如果已定义协议） 或**字符集和分隔符**页的协议选项卡**EDIFACT 后备设置**对话框 （如果未定义协议）。 值**标识符 (UNB1.1)** 元素必须设置为 KECA。  
  
## <a name="x12-character-set"></a>X12 字符集  
 当 BizTalk 接收管道或发送管道执行 EDI 验证的 X12 编码的消息时，它使用 X12 字符集在管道的 CharacterSet 属性中选择的设置。 若要设置此属性，打开属性对话框中的接收位置或发送端口单击接收旁边的省略号或发送管道，，然后设置拆装器或组装器的 CharacterSet 属性。  
  
 管道的 CharacterSet 属性用于验证 X12 交换，因为与 EDIFACT 或 KEDIFACT，不同的 X12 编码交换不自描述在其字符集方面。 读取 ISA 标头使用 ISO 或 UTF 编码可能会导致协议查找不同的值。 因此，BizTalk 必须知道将在处理该消息在协议查找前的 （当它应获得协议的适用字符集） 中使用的适用字符集。  
  
 指定 X12 字符集设置要用于协议验证中**字符集和分隔符**页中的双向协议选项卡 （如果已定义协议） 或**字符集和分隔符**页上的后备协议选项卡**X12 回退设置**对话框 （如果未定义协议）。 但是，BizTalk 仅使用这些设置来验证 （不在您离开某一字段选项卡上，或显示其他页） 保存整个属性集时，为相关属性输入的值。 接收管道或发送管道将忽略这些字符集属性。  
  
> [!NOTE]
>  如果在协议或后备协议中设置指定的字符不匹配的字符集，用于接收或发送管道，则可能发生消息验证错误。 如果的 X12 协议中的字符组属性设置为扩展，而管道属性中的字符属性设置为 Basic X12 是一个示例。  
  
 可用的字符集是基本和扩展 (X12 中所述规范/实现指南)，和 UTF8/Unicode。 默认值为 UTF8。  
  
> [!NOTE]
>  为数据元素分隔符、 组件元素分隔符和段终止符输入的双向协议或后备协议中的值仅限于 ASCII 字符集中的值。 这些属性不会验证针对 X12 字符集。  
  
 基本字符集包括以下大写字母、 数字、 空格和特殊字符：A 到 Z，0 到 9 ！ “ & ’ ( ) * + , - . / : ; ? = （空格）。  
  
 扩展字符集包括基本字符集和小写字母、 选择语言字符，和其他特殊字符的字符： a 到 z、 %@ [] _ {} \ &#124; \< \> ~ # $。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息传递](../core/edi-messaging.md)   
 [EDI 架构](../core/edi-schemas.md)