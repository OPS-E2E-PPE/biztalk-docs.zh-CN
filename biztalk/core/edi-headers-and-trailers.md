---
title: EDI 标头和尾部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf1dae3-9570-413d-a85d-94dcbb561906
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f30def9b680c04fd0078e253dcb4f1049f9d56
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530833"
---
# <a name="edi-headers-and-trailers"></a>EDI 标头和尾部
EDI 交换的部分分隔标头和尾部必须遵循 X12 或 EDIFACT 标准。 交换控制标头和尾部只出现一次;功能组和事务集标头和尾部如果事务集和组进行批处理的交换中重复出现。 每个标头和尾部包含的一系列包含有关标头和尾部所含内容的信息的数据元素。  
  
 标头和尾部 X12 和 EDIFACT 的相似度。 主要区别是对于 EDIFACT，定义在交换中使用的分隔符的 UNA 服务字符串建议标头。 在 X12 编码中，分隔符是在 ISA 交换控制标头中定义的。  
  
 交换控制和功能组标头和尾部表示为信封段中。 当 BizTalk Server 将拆分为事务集传入的交换时，它将为上下文属性保存这些信封段。 可用于路由的主要信封属性可作为单独的属性。 这不会发生时保留交换，在这种情况下，此时信封数据属于消息本身。  
  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成传出消息时，它根据根据标头和尾部，并在贸易合作伙伴协议 （或如果已不确定任何参与方的全局协议）。  
  
 标头和尾部字段以及用于在交换中分隔它们的分隔符被定义两个参与方之间的协议中。 中的任何交换、 组或事务集标头字段或尾字段，定义必须不使用分隔符为协议定义的一样。 如果是，将无法处理交换中发送的 EDI 组装器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或接收方的拆装器中。 交换将失败，EDI 组装器中是否出站批，因为组装器将验证标头控制 （服务） 架构对信封。 如果交换未进行批处理，EDI 组装器将其序列化，但将无法在接收协议的拆装器中的处理。  
  
## <a name="x12-headers-and-trailers"></a>X12 标头和尾部  
 标头和尾部的 X12 编码消息如下所示：  
  
```  
ISA Interchange Control Header  
  GS Functional Group Header  
    ST Transaction Set Header  
    SE Transaction Set Trailer  
  GE Functional Group Trailer  
IEA Interchange Control Trailer  
```  
  
 如果 ISA 标头后面紧跟 IEA 尾部，则交换为空。 如果事务集存在，则 GS 标头和 GE 尾部必须存在;否则，它们是条件。  
  
 在 X12 编码消息中的 ISA 交换控制标头字段是固定长度。 对于某些字段，可以输入小于字段固定的长度的值。 如果这样做，交换必须包含尾随空格 （适用于字符串字段） 或前导零 （对于数字字段），以便每个字段都具有所需长度。 创建出站交换时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将输入尾部空格或前导零，以便创建长度正确的交换控制标头。 GS 组标头字段和 ST 事务集标头字段不是固定长度。  
  
 在 X12 编码、 功能安全标头、 功能保证标头、 功能安全值段和功能安全尾部段均超出范围[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2。 如果收到具有这些段的交换，则会挂起交换并显示错误日志，指示无法识别这些段。  
  
 ST01 字段是事务集 ID 代码;ST02 字段是事务集控制编号。 ST03 字段是架构版本标识符。 SE01 字段指示事务集; 中包含的段数SE02 字段是与 ST02 字段 （事务集控制编号） 相同。 当解析传入消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将验证事务集中的段数对应的 SE01 字段的值。 当生成传出消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将 SE01 字段设置为事务集中的正确段数。  
  
 XML 事务集被序列化到传出 EDI 交换应具有的事务集标头和尾部。 但是，EDI 组装器将处理该消息，如果它不具有事务集标头或尾部。 事务集标头和尾部段在 X12 和 EDIFACT 架构都是可选的 XML 事务集。 如果事务没有标头或尾部，EDI 组装器中 EDISend 或 AS2EDISend 发送管道将向其添加事务集标头和尾部值。 这些值将基于映射或计算。 EDI 组装器将执行此操作为交换 XML （保留批）、 批处理的事务集 XML 和事务集 XML。 有关详细信息，请参阅[X12 事务集标头和尾部段](../core/how-the-edi-assembler-works.md#BKMK_X12)或[EDIFACT 事务集标头和尾部段](../core/how-the-edi-assembler-works.md#BKMK_EDIFACT)。  
  
## <a name="edifact-headers-and-trailers"></a>EDIFACT 的标头和尾部  
 标头和尾部对于 EDIFACT 编码的消息如下所示：  
  
```  
UNA Service String Advice  
UNB Interchange Control Header  
  UNG Functional Group Header  
    UNH Message Header  
    UNT Message Trailer  
  UNE Functional Group Trailer  
UNZ Interchange Control Trailer  
```  
  
 UNA 标头不是必需的。 UNB 标头是必需的。 如果 UNA 标头存在，它包含要处理传入的消息; 时使用的分隔符否则将使用为 EfactDelimiters 管道属性定义的分隔符。  
  
 如果 UNB 标头后面紧跟 UNZ 尾部，则交换为空。 如果 UNG 标头后面紧跟 UNE 尾部，则组为空。 UNG 标头和 UNE 尾部对是条件元素，而不必位于一条消息。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息结构](../core/edi-message-structure.md)