---
title: "EDI 字符集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57fae748-d66e-4ecf-be00-70147078ef93
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38d7b19c751f2bd380dad29ffc31a2be5f79245e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="edi-character-sets"></a>EDI 字符集
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用字符集来验证整个 EDI 交换。 用于 X12 编码的消息与 EDIFACT 或 KEDIFACT 编码的消息的字符集采用不同的方式确定。  
  
## <a name="edifact-character-set"></a>EDIFACT 字符集  
 EDIFACT 编码的交换在其字符集方面是自描述的。 使用了 UNB1 数据元素。 EDIFACT 要求标记名称和分隔符为 ASCII 类型；因此，可以通过定位 UNB1 来为其余交换应用相关代码页。  
  
 处理传入 EDIFACT 消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从 UNB1 数据元素确定用于该消息的字符集。 不需要贸易合作伙伴协议中的任何设置。  
  
 处理传出 EDIFACT 消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用贸易合作伙伴协议或后备协议中的字符集。 在中设置 UNB1 数据元素**字符集和分隔符**（如果定义的协议） 中的双向协议选项卡页上或**字符集和分隔符**的协议选项卡中的页**EDIFACT 回退设置**对话框中 （如果不定义的任何协议）。 UNB1.1 是一种称作“语法标识符”的必需的复合数据元素。 UNB1.2 是 EDIFACT 字符集的版本。 UNB1 数据元素还用于在保存整个属性集时（而不是在您通过按 Tab 键离开某一字段或显示其他页时）验证在贸易合作伙伴管理用户界面中为属性输入的值。  
  
 可用的字符集有：KECA、UNOA、UNOB、UNOC、UNOD、UNOE、UNOF、UNOG、UNOH、UNOI、UNOJ、UNOK、UNOX 和 UNOY。 默认值是 UNOB。 这些级别的完整字符集在 ISO 9735 EDIFACT 语法规则中指定。  
  
> [!NOTE]
>  如果在入站交换或出站交换中遇到 UNOC 字符集，则 EDI 拆装器或 EDI 组装器将使用 Latin-1 代码页，而非 UTF-8 代码页。 之所以必须要这样做，是因为 UTF-8 不是 UNOC 的超集。 某些在 UNOC 中可以接受的字符在作为 UTF-8 处理时会导致交换挂起。  
  
 一些字符在某些 EDIFACT 字符集中可能是双字节字符，而在其他 EDIFACT 字符集中则可能是单字节字符。 鉴于以上原因，在您根据交换中的字符数设置批的发布条件时，相应交换中的字节数可能会因使用的字符集而不同。  
  
 UNA 段和段名 UNB 仅限使用 ASCII 字符集中的值。  
  
## <a name="kedifact-character-set"></a>KEDIFACT 字符集  
 与 EDIFACT 一样，用于 KEDIFACT 编码的交换的字符集也是在 UNB1 数据元素中建立的。 对于 EDIFACT 字符集才能应用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]当处理 KEDIFACT 交换数据元素中建立**UNB1**的**字符集和分隔符**中的双向页协议选项卡 （如果定义的协议） 或**字符集和分隔符**中的协议选项卡页**EDIFACT 回退设置**对话框中 （如果不定义的任何协议）。 值**标识符 (UNB1.1)**元素必须设置为 KECA。  
  
## <a name="x12-character-set"></a>X12 字符集。  
 BizTalk 接收管道或发送管道对 X12 编码的消息执行 EDI 验证时，它将使用在管道的 CharacterSet 属性中选择的 X12 字符集。 若要设置此属性，请打开接收位置或发送端口的“属性”对话框，单击接收或发送管道旁边的省略号，然后设置拆装器或组装器的 CharacterSet 属性。  
  
 管道的 CharacterSet 属性用于验证 X12 交换，因为与 EDIFACT 或 KEDIFACT 不同，X12 编码的交换在其字符集方面不是自描述的。 使用 ISO 或 UTF 编码读取 ISA 标头可能会导致协议查找到的值不同。 因此，在执行协议查找前（此时它应获得协议的适用字符集），BizTalk 必须知道要在处理消息时使用的适用字符集。  
  
 指定 X12 字符集中的协议验证要用于在**字符集和分隔符**（如果定义的协议） 中的双向协议选项卡页上或**字符集和分隔符**中的后备协议选项卡页**X12 回退设置**对话框中 （如果不定义的任何协议）。 但是，BizTalk 仅使用这些设置在保存整个属性集时（而不是在您通过按 Tab 键离开某一字段或显示其他页时）验证为相关属性输入的值。 接收管道或发送管道将忽略这些字符集属性。  
  
> [!NOTE]
>  如果协议或后备协议中指定的字符集与为接收或发送管道选择的字符集不匹配，则可能发生消息验证错误。 例如，如果协议中的 X12 字符集属性设置为“扩展”，而管道属性中的 X12 字符属性设置为“基本”。  
  
 可用的字符集包括“基本”、“扩展”（在 X12 Specifications/Implementation Guides（《X12 规范/实现指南》）中有相关文字说明）和 UTF8/Unicode。 默认值为 UTF8。  
  
> [!NOTE]
>  在双向协议或后备协议中为数据元素分隔符、组件元素分隔符和段终止符输入的值仅限于使用 ASCII 字符集中的值。 不会按照 X12 字符集对这些属性进行验证。  
  
 基本字符集包括以下大写字母、 数字、 空间和特殊字符： A 到 Z、 0 到 9，！ “ & ’ ( ) * + , - . / : ; ? = （空格）。  
  
 扩展字符集包括在基本字符组和小写字母、 选择的语言字符和其他特殊字符的字符： a 到 z %@ [] _ {} \ &#124;\< \> ~ # $.  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息传递](../core/edi-messaging.md)   
 [EDI 架构](../core/edi-schemas.md)