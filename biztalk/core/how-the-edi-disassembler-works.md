---
title: EDI 拆装器的工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8da91ba4-e1c9-4e6b-bbd1-fe71ea880118
caps.latest.revision: 43
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b22bf118bbf63db8775c85f6962e8f6d10d55e43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387434"
---
# <a name="how-the-edi-disassembler-works"></a>EDI 拆装器的工作原理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对于接收 EDI 编码的交换，EDI 接收管道中执行大多数的处理 (`Microsoft.BizTalk.DefaultPipelines.EDIReceivePipeline`)。 此管道包括 EDI 拆装器管道组件，用于执行以下处理：  
  
- （如果该接收位置的"DetectMID"管道属性设置为 True），将拆分为单独的交换的多个交换中一条消息。 EDI 拆装器执行，因此通过搜索即使一个交换的交换控制标头 （ISA、 UNA 或 UNB） 控制尾部 （IEA 或 UNZ） 遇到已被取消。  
  
- 验证信封。  
  
- 分解交换。  
  
- 进程触发 HIPAA 交换的字段。  
  
- 验证 EDI 和特定于合作伙伴的属性，（如果适用）。 这包括 EDI 架构验证、 X12 编码的消息 （如果已配置） 的跨字段验证、 EDI 结构验证和扩展的架构验证 （如果该架构使用具有非 EDI 数据类型的节点自定义）。 有关详细信息，请参阅[验证的接收 EDI 消息](../core/validation-of-received-edi-messages.md)。  
  
- 验证交换、 组和事务集控制编号不重复，如果在启用了这些检查**验证**页 (下**交换设置**) 的双向语言协议选项卡**协议属性**对话框。 检查针对以前收到的交换的交换控制编号。 检查针对交换中的其他组控制编号的组控制编号。 检查针对该组中的其他事务集控制编号的事务集控制编号。 如果发现重复项，在状态报告将指示存在重复的记录。  
  
- 生成 XML 文档为每个事务集。 每个 XML 文件，将升级 BTS 的上下文属性。MessageType，将其设置为带有命名空间的架构名称。  
  
- 将整个交换转换为 XML，如果**入站批处理选项**属性设置为两种状态之一**保留交换**值。 此属性可以设置从**本地主机设置**页**交换设置**的双向协议选项卡的**协议属性**对话框。 接收管道将升级 ReuseEnvelope 属性以将交换标识为保留。  
  
- 生成技术和/或功能确认 （如果已配置）。 这包括对确认进行批处理（如果已配置）。 将升级 BTS 上下文的属性。MessageType，将其设置为控制架构中等于 http://schemas.microsoft.com/EDI/\<X12 或 EDIFACT\> （的 x12_997_root 997 确认) 的命名空间。 同时，还将升级 EDI.DestinationPartyName 上下文属性，此属性可确保提取确认以便发送。 有关详细信息，请参阅[发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)。  
  
- 执行 HIPAA 276/277 （仅限版本 5010） 834、 835 （仅版本 4010） 和 837 文档拆分，可能的话。  
  
- 升级或写入到消息上下文属性 （请参阅下一节）。  
  
## <a name="promoting-or-writing-properties-to-the-context"></a>属性升级或写入到上下文  
 当 EDI 拆装器处理收到的消息时，它将升级，或将以下属性写入到消息上下文：  
  
- 对于 X12 编码的未批处理消息，请从信封升级下列属性：ISA06，ISA08，ISA15;GS01，GS02，GS03，GS08;ST03 和 ST01。  
  
  > [!NOTE]
  >  对于传入 HIPAA 837 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持三种 HIPAA 837 架构：声明 Dental_837D、-Institutional_837I 和 Claim-Professional_837P。 有关其中每项功能的 ST01 是"837"。这三种架构版本 5010 中，对于 GS08 有不同的值："005010X223A1"为 837I，"005010X224A1"837 d 和"005010 X 222"的 837 p。 架构版本 4010 中，对于 GS08 有不同的值："004010X096A1"837I、 837 d"004010X097A1"和"004010X098A1"的 837 p。  
  
- 对于 EDIFACT 编码的未批处理消息，请从信封升级下列属性：UNB2.1，UNB2.3，UNB3.1 UNB11;UNG1，UNG2.1 UNG3.1;UNH2.1、 UNH2.2、 UNH2.3。  
  
- 如果拆分批的交换，请将 ISA_Segment 和 gs_segment 写入写入到 X12 编码消息的上下文，或将 UNA_Segment、 UNB_Segment 和 ung_segment 写入写入到 EDIFACT 编码消息的上下文。  
  
  > [!NOTE]
  >  上述各段写入到上下文中。 而不被升级到上下文。 但是，可以将这些段附加到事务集中使用消息收集示例。 此外可以采用附加示例的代码，并将其添加到自定义管道组件。 有关详细信息，请参阅[消息充实示例 （BizTalk Server 示例）](../core/message-enrichment-sample-biztalk-server-sample.md)。  
  
  > [!NOTE]
  >  升级的 ISA_Segment 属性包含安全/授权信息 （ISA02、 授权信息和 ISA04，安全信息），这可能导致信息泄漏。 可以使用**屏蔽上下文属性中的安全/授权/密码信息属性**(在**本地主机设置**页**交换设置**为双向协议属性） 使用 # 字符替换 ISA02 和 ISA04 字段中的每个字符。 这是一个单向过程： 无法将 '#' 字符转换为实际的字符。  
  
- 为 X12-和 EDIFACT-编码的消息，升级 ReuseEnvelope，指示是拆分还是保留批处理的交换。  
  
- 如果保留批的交换，则会将升级以下属性：  
  
  -   InboundTransportatLocation  
  
  -   InboundTransportType  
  
  -   ISA05  
  
  -   ISA07  
  
  -   ISA06  
  
  -   ISA08  
  
  -   ISA15  
  
  -   LastInterchangeMessage = {True&#124;False}  
  
  -   MessageType  
  
  -   ReceivePortID  
  
  -   ReceivePortName  
  
  -   ReuseEnvelope  
  
## <a name="parsing-the-envelope"></a>解析信封  
 EDI 接收管道使用标头控制架构解析收到的 EDI 消息的信封和 EDI 文档架构解析交换中事务集/消息。  
  
 如果通过 HTTP/HTTPS 传输收到的 EDIINT/AS2 编码的消息，EDI 拆装器将检查上下文属性 BTS。MessageDestination。 如果该属性设置为 SuspendQueue，指示在 AS2 处理过程中出错，并且该消息将被挂起，EDI 拆装器将充当直通管道组件，并将挂起到 MessageBox 的消息。  
  
 分析过程中的 EDIFACT 交换，EDI 进行转义的字符转义指示器接收管道将删除。 转义指示器不包括在 EDI 验证。 EDI 接收管道不包括转义指示器时计算长度限制。  
  
 **字符集**  
  
 对于 X12 交换，管道组件属性将确定处理交换时 EDI 拆装器将使用的字符集。 它可以 Basic、 扩展或 UTF8/Unicode。 默认值为 UTF8 的 EDIFACT 交换，UNB1.1 字段确定字符集。  
  
 **动态发现分隔符**  
  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 交换，没有任何协议属性指示在交换中的包含应该是什么。 相反，EDI 拆装器将发现什么分隔符是 （对于 X12 或 EDIFACT 中） 在运行时。  
  
 对于 X12 消息，EDI 拆装器使用从交换中的以下字符：  
  
|Separator|字符|  
|---------------|---------------|  
|数据元素分隔符|ISA 的第四个字符|  
|组件元素分隔符|ISA16|  
|段分隔符|ISA 的第 106 个字符|  
|段终止符后缀|ISA 段和 GS 段之间的字符<br /><br /> **值：** 无、 CR、 LF 或 CRLF**注意：** 分隔符可以采用仅上述值。|  
|重复分隔符或标准标识符<br /><br /> (具体取决于上的"ISA11 用法"协议属性**信封**的双向协议选项卡页)|ISA11|  
  
 对于 EDIFACT 交换，EDI 拆装器会检查交换中定义的分隔符的 UNA 段。 如果交换没有 UNA 段，这是可选的拆装器将使用管道组件属性中定义的默认值。  
  
|Separator|UNA 的字符|  
|---------------|----------------------|  
|组件元素分隔符|第四个|  
|数据元素分隔符|5 日|  
|十进制表示法|6 日|  
|转义符|7|  
|重复字符|8 日|  
|段分隔符|第 9 个|  
|段分隔符后缀|UNA 段和 UNB 段之间的字符<br /><br /> **值：** 无、 CR、 LF 或 CRLF**注意：** 分隔符可以采用仅上述值。|  
  
 UNA 字符串是可选的。 如果存在，它定义的文件的所有分隔符。 如果不存在，EDI 拆装器将使用 EfactDelimiters 管道组件属性确定分隔符。 有关详细信息，请参阅[配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)。  
  
 **发布错误**  
  
 如果 EDI 拆装器遇到 EDI 处理错误，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事件查看器中将发布以下两个错误 （如果已启用此发布）：  
  
- 源记录的错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时挂起消息。 这是与相关的必需的错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理。  
  
- 一种错误报告在事务中的问题记录集中的源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI。 此错误是特定于 EDI 的。  
  
## <a name="using-agreement-properties"></a>使用协议属性  
 如果它可标识协议，EDI 拆装器将使用协议属性 (请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md))。 如果找不到匹配的协议和相应的值不是后备协议中可用，EDI 拆装器属性中设置**属性**将使用 Visual Studio 窗口。 但是，以上后备机制将不发生身份验证需要在接收端口属性 (如果**身份验证失败时删除消息**或**身份验证失败时保留消息**选择). 在这种情况下，必须配置协议;如果没有，则交换将被挂起。  
  
 当 EDI 拆装器使用协议属性时，需要设置下列协议属性：  
  
|属性|协议属性页|  
|--------------|-------------------------------|  
|重复分隔符|**信封**页 (下**交换设置**) 中的双向协议选项卡|  
|执行 EDI 数据类型验证|**验证**页上下**事务集设置**在双向协议选项卡中 （针对 X12 和 EDIFACT 协议）|  
|扩展的验证|**验证**页上下**事务集设置**在双向协议选项卡中 （针对 X12 和 EDIFACT 协议）|  
|允许前导和尾随零及空格|**验证**页上下**事务集设置**在双向协议选项卡中 （针对 X12 和 EDIFACT 协议）|  
|如果允许尾部分隔符，创建空 XML 标记|**本地主机设置**页上下**事务集设置**在双向协议选项卡中 （针对 X12 和 EDIFACT 协议）|  
|入站批处理选项|**本地主机设置**页 (下**交换设置**) 中的双向协议选项卡 （对于 X12 和 EDIFACT 协议）|  
|默认 EDIFACT 分隔符|-|  
|屏蔽安全/授权/密码信息|**本地主机设置**页 (下**交换设置**) 中的双向协议选项卡 （对于 X12 和 EDIFACT 协议）|  
|将隐式小数格式 Nn 十进制数值转换|**本地主机设置**页上下**事务集设置**的双向协议选项卡中 (对于 X12 协议)|  
|将路由到请求-响应发送管道将确认到接收端口|**本地主机设置**页 (**接收方设置**一节) 下**交换设置**在双向协议选项卡中 （针对 X12 和 EDIFACT 协议）|  
|X12 字符集|X12 交换信封生成**注意：** 此设置仅用于验证为协议属性输入的值。 X12 字符集使用的管道属性中选择运行时处理。 有关详细信息，请参阅[EDI 字符集](../core/edi-character-sets.md)。|  
  
## <a name="using-hipaa-trigger-fields"></a>使用 HIPAA 触发器字段  
 EDI 段通常包含修改段含义的限定符值。 例如，N1 段可以包含一个限定元素"BT"来表示"帐单收件人名字，"或它可能包含一个限定元素"ST"，表示"收货方名字。" 通常情况下将由业务逻辑来确定如何解释这些字段和拆装器将 N1 段的所有实例都解析为相同的 XML 记录名称;但是，BizTalk Server 所附带的 HIPAA 架构包含批注允许 EDI 拆装器以便创建唯一 XML 记录根据是否存在限定值 (请参阅[HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md))。  
  
 当接收 HIPAA 事务集，如果 EDI 拆装器遇到包含触发器字段的段时，它使用触发器信息生成特定于该段和触发器组合的 XML 记录。  
  
 下表显示了如何将 N1 段转换成 XML 记录基于 N101 值：  
  
|N1 段|生成的 XML 数据|  
|----------------|------------------------|  
|N1*PR\*Contoso\*XV\*0000000~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|N1*PE\*Fabrikam\*FI\*9999999~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)