---
title: "配置 EDI 管道属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edir2.edi.pipeline.properties
ms.assetid: 1b6229b6-a8b0-4824-86bd-39021844c5a8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c810b8507a98b91c0b906131e127f189f0a4fd0f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-edi-pipeline-properties"></a>配置 EDI 管道属性
当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定传入或传出交换解析为的协议时，将在处理传入或传出 EDI 交换的过程中可使用管道属性。 在有些情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用管道属性来处理交换；而在其他情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用后备协议。 有关详细信息，请参阅[如何验证 EDI 交换是配置的](../core/how-validation-of-an-edi-interchange-is-configured.md)。  
  
 以下为此规则的一些例外情况：  
  
-   对于 X12，运行时使用的字符集由管道属性确定，即使已确定协议时也是如此。 协议中所述的字符集只用于验证协议属性设置。  
  
-   对于 EDIFACT，如果传入交换没有 UNA 段，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 EfactDelimiters 管道属性中指定的分隔符，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不使用消息解析的协议中或后备协议中定义的属性。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="edi-pipeline-properties"></a>EDI 管道属性  
 可在 EDI 管道中设置下列属性：  
  
|属性|改用|值|管道 - 阶段|  
|--------------|---------|------------|-----------------------|  
|AllowTrailingDelimiters|在收到的交换上生成尾部分隔符。|False（默认值）<br /><br /> True|EdiReceive-反汇编<br /><br /> AS2EdiReceive-反汇编<br /><br /> EdiSend - 组装<br /><br /> AS2EdiSend - 组装|  
|CharacterSet|指定在对传出 EDI 交换执行运行时验证期间使用的字符集。<br /><br /> 此属性仅用于 X12 处理，不用于 EDIFACT。|UTF8（默认值）<br /><br /> 基本<br /><br /> 扩展|EdiReceive - 拆装<br /><br /> AS2EdiReceive-反汇编<br /><br /> EdiSend - 组装<br /><br /> AS2EdiSend - 组装|  
|ConvertToImpliedDecimal|对于传入交换，在 BizTalk Server 的中间 XML 中，将以格式 Nn 指定的 EDI 数值转换为十进制数值。<br /><br /> 此属性仅用于 X12 处理，不用于 EDIFACT。|False（默认值）<br /><br /> True|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|CreateXMLTagForTrailingSeparators|为每个尾随分隔符创建空 XML 标记 (如果已经设置**AllowTrailingDelimiters**为 true)。|False（默认值）<br /><br /> True|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|DetectMID|允许 EDI 拆装器在一个消息中解析多个交换。|True（默认值）<br /><br /> False|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|EdiDataValidation|启用对传出 EDI 交换的 EDI 类型（数据元素）验证，除了 EDI 数据元素验证之外，还验证字段长度、可选性和重复计数。|True（默认值）<br /><br /> False|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装<br /><br /> EdiSend - 组装<br /><br /> AS2EdiSend - 组装|  
|EfactDelimiters|指示处理传入交换时使用的分隔符。 如果传入交换没有 UNA 段，则使用此属性。<br /><br /> 分隔符包括：<br /><br /> -UNA1 （组件数据元素分隔符）<br />-UNA2 （数据元素分隔符）<br />-UNA3 （小数符号）<br />-UNA4 （转义指示器）<br />-UNA5 （重复分隔符）<br />-UNA6 （段终止符）**注意：**此属性用于 EDIFACT 只能，处理不能为 X12。|0x3A、0x2B、0x2C、0x3F、0x20、0x27（默认值）|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
IgnoreMessageEncoding|指定 BatchMarker 组件不会设置 EDI。EncodingType 上下文属性\<X12\>或\<EDIFACT\>。 这适用于处理非 EDI 消息时的自定义管道。|False（默认值）<br /><br /> True|EdiReceive - 解析参与方<br /><br /> AS2EdiReceive - 解析参与方|  
|MaskSecurityInformation|屏蔽传入 EDI 交换上下文属性中的授权/密码安全信息，以防止信息泄露。 对于 X12 交换，适用于 ISA1、ISA2、ISA3 和 ISA4 字段；对于 EDIFACT 交换，适用于 UNB6 字段。|True（默认值）<br /><br /> False|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|PreserveInterchange|指定接收的批将作为一个整体处理。|False（默认值）<br /><br /> True|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|RouteAckOn2WayPort|经由打开的双向请求-响应接收端口连接返回 EDI 确认。|True（默认值）<br /><br /> False|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|UseDotAsDecimalSeperator|设置为 True 时，EDI 接收管道使用的十进制表示法"。" 而不是传入文档的十进制表示法。|False（默认值）<br /><br /> True|EdiReceive – 反汇编<br /><br /> AS2EdiReceive - 拆装|  
|UseIsa11AsRepetitionSeparator|指定 ISA11 将用作重复分隔符而非标准标识符。 **注意：**对于 X12 处理仅，对于 EDIFACT 不使用此属性。|False（默认值）<br /><br /> True|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装|  
|XmlSchemaValidation|启用对传出 EDI 交换的扩展 (BTS-XSD) 验证。 仅当已使用数据类型为非 EDI 数据类型的元素来自定义架构时此属性才适用。 添加的这些元素不通过 EDI 验证来进行验证，因此将包括在扩展验证范围内。|False（默认值）<br /><br /> True|EdiReceive - 拆装<br /><br /> AS2EdiReceive - 拆装<br /><br /> EdiSend - 组装<br /><br /> AS2EdiSend - 组装|  
  
### <a name="to-set-a-pipeline-property"></a>设置管道属性  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击接收位置或发送端口使用你想要设置属性，然后单击管道**属性**。  
  
2.  单击你要设置其属性的管道旁的省略号按钮 (…)。  
  
3.  在**配置管道**对话框中，为属性输入值，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置对 EDI 交换的验证](../core/how-validation-of-an-edi-interchange-is-configured.md)