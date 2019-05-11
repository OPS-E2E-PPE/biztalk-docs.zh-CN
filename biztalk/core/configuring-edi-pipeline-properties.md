---
title: 配置 EDI 管道属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.edi.pipeline.properties
ms.assetid: 1b6229b6-a8b0-4824-86bd-39021844c5a8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f886af4019d37c4c9b544733722e64c2a5537687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391290"
---
# <a name="configuring-edi-pipeline-properties"></a>配置 EDI 管道属性
将使用管道属性处理传入或传出 EDI 交换时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定传入或传出交换解析为的协议。 在某些情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用管道属性来处理交换; 而在其他，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用备用协议。 有关详细信息，请参阅[如何验证 EDI 交换是配置的](../core/how-validation-of-an-edi-interchange-is-configured.md)。  
  
 有一些例外情况，此规则：  
  
- 对于 X12，在运行时设置使用的字符是由管道属性确定，即使已确定协议。 在协议中所述的字符集只用于验证协议属性设置。  
  
- 对于 EDIFACT，如果传入交换没有 UNA 段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 EfactDelimiters 管道属性中指定的分隔符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不使用消息解析到协议或后备中定义的属性协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
## <a name="edi-pipeline-properties"></a>EDI 管道属性  
 可以在 EDI 管道中设置以下属性：  
  
|属性|改用|值|管道-阶段|  
|--------------|---------|------------|-----------------------|  
|AllowTrailingDelimiters|生成收到的交换尾部分隔符。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
|CharacterSet|指定要在传出 EDI 交换的运行时验证期间使用的字符集。<br /><br /> 此属性用于 X12 处理，不用于 EDIFACT。|UTF8 （默认值）<br /><br /> 基本<br /><br /> 扩展|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
|ConvertToImpliedDecimal|对于传入的交换，数字转换为 EDI 使用的中间 XML 中 BizTalk Server 的十进制数字值格式 Nn 指定的。<br /><br /> 此属性用于 X12 处理，不用于 EDIFACT。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|CreateXMLTagForTrailingSeparators|为每个尾部分隔符创建空 XML 标记 (如果设置了**AllowTrailingDelimiters**为 true)。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|DetectMID|启用 EDI 拆装器以便解析单个消息中的多个交换。|True （默认值）<br /><br /> False|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|EdiDataValidation|启用对传出 EDI 交换，包括验证字段长度、 可选性和重复计数除了 EDI 数据元素验证之外的 EDI 类型 （数据元素） 验证。|True （默认值）<br /><br /> False|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
|EfactDelimiters|指示要处理传入的交换时使用的分隔符。 如果传入交换没有 UNA 段，使用。<br /><br /> 分隔符包括以下：<br /><br /> -UNA1 （组件数据元素分隔符）<br />-UNA2 （数据元素分隔符）<br />-UNA3 （十进制表示法）<br />-UNA4 （转义指示器）<br />-UNA5 （重复分隔符）<br />-UNA6 （段终止符）**注意：** 此属性用于 EDIFACT 处理，不用于 X12。|0x3A、 0x2B、 0x2C、 0x3F、 0x20、 0x27 （默认值）|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
IgnoreMessageEncoding|指定 BatchMarker 组件不会设置 EDI。EncodingType 上下文属性设置为\<X12\>或\<EDIFACT\>。 这适用于自定义管道处理非 EDI 消息时。|为 false （默认值）<br /><br /> True|EdiReceive - ResolveParty<br /><br /> AS2EdiReceive - ResolveParty|  
|MaskSecurityInformation|屏蔽传入 EDI 交换，以防止信息泄漏的上下文属性中的授权/密码安全信息。 对于 X12 交换; 适用于 ISA1、 ISA2、 ISA3 和 ISA4 字段对于 EDIFACT 交换的 UNB6 字段。|True （默认值）<br /><br /> False|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|PreserveInterchange|指定接收的批将作为单个单元进行处理。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|RouteAckOn2WayPort|经由打开返回 EDI 确认连接的双向请求-响应接收端口。|True （默认值）<br /><br /> False|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|UseDotAsDecimalSeperator|设置为 True 时，EDI 接收管道使用的十进制表示法"。" 而不是传入文档的十进制符号。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|UseIsa11AsRepetitionSeparator|指定 ISA11 将用作重复分隔符而非标准标识符。 **注意：** 此属性用于 X12 处理，不用于 EDIFACT。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装|  
|XmlSchemaValidation|启用扩展 (BTS-XSD) 验证传出 EDI 交换。 这仅适用于已使用其数据类型不是 EDI 数据类型的元素自定义架构。 这些添加的元素不是可由 EDI 验证，以便将受扩展验证进行验证。|为 false （默认值）<br /><br /> True|EdiReceive-拆装<br /><br /> AS2EdiReceive-拆装<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
  
### <a name="to-set-a-pipeline-property"></a>若要设置管道属性  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击接收位置或发送端口使用你想要设置属性，然后单击管道**属性**。  
  
2. 单击你想要设置的属性的管道旁的省略号按钮 （...）。  
  
3. 在中**配置管道**对话框中，为属性输入值，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [如何配置对 EDI 交换的验证](../core/how-validation-of-an-edi-interchange-is-configured.md)