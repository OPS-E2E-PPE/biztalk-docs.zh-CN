---
title: "EDI 标头和尾部 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf1dae3-9570-413d-a85d-94dcbb561906
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 655a7261da5dc66687fdf0cd623802854c0fa4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-headers-and-trailers"></a>EDI 的头部和尾部
EDI 交换的各部分由标头和尾部分隔，而标头和尾部必须遵循 X12 或 EDIFACT 标准。 交换控制标头和尾部只出现一次；功能组和事务集标头和尾部可重复出现，前提是事务集和组在交换内是按批处理的。 每个标头和尾部均由一系列数据元素组成，这些元素包含有关标头和尾部所含内容的信息。  
  
 X12 和 EDIFACT 的标头和尾部很相似。 主要区别在于，在 EDIFACT 中，交换中使用的分隔符是在 UNA 服务字符串建议标头中定义的。 而在 X12 编码中，分隔符是在 ISA 交换控制标头中定义的。  
  
 交换控制和功能组标头和尾部表示为信封段。 当 BizTalk Server 将传入交换分割成事务集时，它将这些信封段另存为上下文属性。 对路由非常有用的主要信封属性可作为单独的属性使用。 当保留交换时，不会出现这种情况，此时信封数据属于消息自身的一部分。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成传出消息时，它根据贸易合作伙伴协议来确定标头和尾部，或者在未确定任何参与方时根据全局协议确定。  
  
 标头字段和尾部字段，以及用于在交换中分隔它们的分隔符均在两个参与方之间的协议中进行定义。 按照对协议的规定，切勿在交换、组或事务集的任何头字段或尾字段的定义中使用分隔符。 如果使用了这样的分隔符，则在作为发送方的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 EDI 组装器中或在接收方的拆装器中将无法处理交换。 如果交换为出站批，它在 EDI 组装器中将失败，因为组装器会根据头控制（服务）架构验证信封。 如果交换未进行批处理，EDI 组装器会将其序列化，但交换在接收协议的拆装器中将无法处理。  
  
## <a name="x12-headers-and-trailers"></a>X12 的标头和尾部  
 X12 编码消息的标头和尾部如下所示：  
  
```  
ISA Interchange Control Header  
  GS Functional Group Header  
    ST Transaction Set Header  
    SE Transaction Set Trailer  
  GE Functional Group Trailer  
IEA Interchange Control Trailer  
```  
  
 如果 ISA 标头后面紧跟 IEA 尾部，则交换为空。 如果事务集存在，则 GS 标头和 GE 尾部必须存在，否则它们将受条件限制。  
  
 在 X12 编码的消息中，ISA 交换控制标头字段是固定长度。 对于某些字段，可以输入小于字段固定长度的值。 如果这样做，交换必须包含尾部空格（对于字符串字段）或前导零（对于数字字段），以便每个字段都具有所需长度。 当创建出站交换时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将输入尾部空格或前导零，以便创建长度正确的交换控制标头。 GS 组标头字段和 ST 事务集标头字段的长度不固定。  
  
 在 X12 编码中，功能安全标头、功能保证标头、功能安全值段和功能安全尾部段均超出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 的范围。 如果收到具有这些段的交换，则会挂起交换并显示错误日志，指示无法识别这些段。  
  
 ST01 字段是事务集 ID 代码；ST02 字段是事务集控制编号。 ST03 字段是架构版本标识符。 SE01 字段指示事务集中包含的段数；SE02 字段与 ST02 字段（事务集控制编号）相同。 当解析传入消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将验证事务集中的段数是否与 SE01 字段的值相对应。 当生成传出消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将 SE01 字段设置为事务集中的正确段数。  
  
 要序列化到传出 EDI 交换中的 XML 事务集应当具有事务集标头和尾部。 但是，如果没有事务集标头或尾部，EDI 组装器将处理相应消息。 X12 和 EDIFACT 架构中的事务集标头和尾部段对 XML 事务集而言是可选的。 如果事务没有标头或尾部，则 EDISend 或 AS2EDISend 发送管道中的 EDI 组装器将会向其添加事务集标头和尾部值。 这些值将基于映射或计算。 EDI 组装器将会为交换 XML（保留批）、批处理的事务集 XML 和事务集 XML 执行此操作。 有关详细信息，请参阅[X12 事务设置标头和预告片段](../core/how-the-edi-assembler-works.md#BKMK_X12)或[EDIFACT 事务设置标头和预告片段](../core/how-the-edi-assembler-works.md#BKMK_EDIFACT)。  
  
## <a name="edifact-headers-and-trailers"></a>EDIFACT 的标头和尾部  
 EDIFACT 编码消息的标头和尾部如下所示：  
  
```  
UNA Service String Advice  
UNB Interchange Control Header  
  UNG Functional Group Header  
    UNH Message Header  
    UNT Message Trailer  
  UNE Functional Group Trailer  
UNZ Interchange Control Trailer  
```  
  
 无需 UNA 标头。 但 UNB 标头是必需的。 如果 UNA 标头存在，则其中将包含要在处理传入消息时使用的分隔符，否则将使用为 EfactDelimiters 管道属性定义的分隔符。  
  
 如果 UNB 标头后面紧跟 UNZ 尾部，则交换为空。 如果 UNG 标头后面紧跟 UNE 尾部，则组为空。 UNG 标头和 UNE 尾部对是条件元素，不一定必须出现在消息中。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息结构](../core/edi-message-structure.md)