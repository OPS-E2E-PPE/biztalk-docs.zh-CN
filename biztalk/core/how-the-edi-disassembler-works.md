---
title: "EDI 反汇编程序的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8da91ba4-e1c9-4e6b-bbd1-fe71ea880118
caps.latest.revision: "43"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66f47db034e0c193d4dab6ee303c13dd8c360661
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-edi-disassembler-works"></a>EDI 拆装器的工作方式
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行 EDI 接收管道 (`Microsoft.BizTalk.DefaultPipelines.EDIReceivePipeline`) 中接收的 EDI 编码交换的大多数处理。 此管道包括用于执行下列处理的 EDI 拆装器管道组件：  
  
-   将单个消息中的多个交换拆分为单独的交换（条件是接收位置的“DetectMID”管道属性设置为 True）。 EDI 拆装器执行此操作的方法是：即使在遇到交换控制尾部（IEA 或 UNZ）之后，也仍将搜索交换控制标头（ISA、UNA 或 UNB）。  
  
-   验证信封。  
  
-   反汇编交换。  
  
-   处理 HIPAA 交换的触发字段。  
  
-   根据需要验证 EDI 和特定于合作伙伴的属性。 这包括 EDI 架构验证、X12 编码消息的跨字段验证（如果已配置）、EDI 结构验证和扩展架构验证（如果此架构是使用具有非 EDI 数据类型的节点自定义的）。 有关详细信息，请参阅[验证的接收 EDI 消息](../core/validation-of-received-edi-messages.md)。  
  
-   验证交换、 组和事务集控制编号是否不存在重复项，如果在启用了检查**验证**页 (下**交换设置**) 的双向语言协议选项卡**协议属性**对话框。 根据以前收到的交换检查交换控制编号。 根据交换中的其他组控制编号检查组控制编号。 根据该组中的其他事务集控制编号检查事务集控制编号。 如果发现重复项，状态报告将指示存在重复记录。  
  
-   为每个事务集生成一个 XML 文档。 在每个 XML 文件中，升级 BTS.MessageType 上下文属性，将其设置为带有命名空间的架构名称。  
  
-   将整个交换转换为 XML，如果**入站批处理选项**属性设置为两种状态之一**保留交换**值。 此属性可以设置从**本地主机设置**下页上**交换设置**的双向协议选项卡**协议属性**对话框。 接收管道将升级 ReuseEnvelope 属性以将交换标识为保留。  
  
-   生成技术确认和/或功能确认（如果已配置）。 这包括对确认进行批处理（如果已配置）。 提升 BTS 的上下文属性。MessageType，将其设置等于 http://schemas.microsoft.com/EDI/ 中的控件模式\<X12 或 EDIFACT > （例如，对于 997 确认 X12_997_Root） 的命名空间。 同时，还将升级 EDI.DestinationPartyName 上下文属性，此属性可确保提取确认以便发送。 有关详细信息，请参阅[发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)。  
  
-   执行 HIPAA 276/277（仅版本 5010 ）834、835（仅版本 4010）和 837 文档拆分（如果适用）。  
  
-   将属性升级或写入到消息上下文（请参阅下一部分）。  
  
## <a name="promoting-or-writing-properties-to-the-context"></a>将属性升级或写入到上下文  
 当 EDI 拆装器处理收到的消息时，该拆装器会将下列属性升级或写入到消息上下文：  
  
-   对于 X12 编码 unbatched 消息中，将以下属性提升从信封： ISA06、 ISA08、 ISA15;GS01、 GS02、 GS03，GS08;ST03 和 ST01。  
  
    > [!NOTE]
    >  为传入的 HIPAA 837 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持三个 HIPAA 837 架构： 声明 Dental_837D、 声明 Institutional_837I 和声明 Professional_837P。 其中每项的 ST01 是"837"。这三个架构版本 5010 中具有不同的值为 GS08: 837I、 837 d"005010X224A1"和"005010 X 222"为 837 P."005010X223A1" 架构版本 4010 中为 GS08 具有不同的值:"004010X096A1"为 837I、 837 d"004010X097A1"和"004010X098A1"为 837 P.  
  
-   对于 EDIFACT 编码 unbatched 消息中，将以下属性提升从信封： UNB2.1、 UNB2.3、 UNB3.1、 UNB11;UNG1，UNG2.1，UNG3.1;UNH2.1，UNH2.2，UNH2.3。  
  
-   如果拆分批交换，请将 ISA_Segment 和 GS_Segment 写入到 X12 编码消息的上下文，或者将 UNA_Segment、UNB_Segment 和 UNG_Segment 写入到 EDIFACT 编码消息的上下文。  
  
    > [!NOTE]
    >  上述各段将被写入到上下文中， 而不是升级。 但是，您可以使用消息收集示例将这些段附加到事务集中。 您还可以采用附加示例的代码将其添加到自定义管道组件中。 有关详细信息，请参阅[消息扩充示例 （BizTalk Server 示例）](../core/message-enrichment-sample-biztalk-server-sample.md)。  
  
    > [!NOTE]
    >  升级的 ISA_Segment 属性包含安全/授权信息（ISA02 包含授权信息，ISA04 包含安全信息），这可能导致信息泄漏。 你可以使用**屏蔽上下文属性中的安全/授权/密码信息属性**(在**本地主机设置**页面**交换设置**为双向协议属性） 来将替换 # 字符 ISA02 和 ISA04 字段中的每个字符。 这是一个单向过程： 无法将 '#' 字符转换为实际字符。  
  
-   对于 X12 和 EDIFACT 编码的消息，升级 ReuseEnvelope，该属性指示拆分或保留批交换。  
  
-   如果批交换得以保留，请升级下列属性：  
  
    -   InboundTransportatLocation  
  
    -   InboundTransportType  
  
    -   ISA05  
  
    -   ISA07  
  
    -   ISA06  
  
    -   ISA08  
  
    -   ISA15  
  
    -   LastInterchangeMessage = {True &#124;False}  
  
    -   MessageType  
  
    -   ReceivePortID  
  
    -   ReceivePortName  
  
    -   ReuseEnvelope  
  
## <a name="parsing-the-envelope"></a>解析信封  
 EDI 接收管道使用标头控制架构解析收到的 EDI 消息的信封，并使用 EDI 文档架构解析交换中的事务集/消息。  
  
 如果 EDIINT/AS2 编码消息是通过 HTTP/HTTPS 传输接收的，EDI 拆装器将检查 BTS.MessageDestination 上下文属性。 如果该属性设置为 SuspendQueue，指示在 AS2 处理过程中发生错误并且消息将挂起，那么 EDI 拆装器将充当直通管道组件，并且该消息将在 MessageBox 中挂起。  
  
 在解析 EDIFACT 交换期间，EDI 接收管道将删除用于转义字符的转义指示器。 转义指示器不包括在 EDI 验证中。 EDI 接收管道在计算长度限制时不包括转义指示器。  
  
 **字符集**  
  
 对于 X12 交换，“管道组件属性”确定在处理交换时 EDI 拆装器将使用的字符集。 字符集可以是“基本”、“扩展”或“UTF8/Unicode”。 EDIFACT 交换的默认值是 UTF8，UNB1.1 字段决定该字符集。  
  
 **动态分隔符发现**  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收 EDI 交换时，没有任何协议属性指示应在交换中使用哪些分隔符。 EDI 拆装器而是在运行时发现应使用哪些分隔符（对于 X12 或 EDIFACT）。  
  
 对于 X12 消息，EDI 拆装器使用来自交换内部的下列字符：  
  
|分隔符|字符|  
|---------------|---------------|  
|数据元素分隔符|ISA 的第 4 个字符|  
|组件元素分隔符|ISA16|  
|段分隔符|ISA 的第 106 个字符|  
|段终止符后缀|ISA 段和 GS 段之间的字符<br /><br /> **值：**无、 CR、 LF 或 CRLF**注意：**分隔符可以采用仅上面的值。|  
|重复分隔符或标准标识符<br /><br /> (具体取决于上的"ISA11 用法"协议属性**包络线**双向协议选项卡页)|ISA11|  
  
 对于 EDIFACT 交换，EDI 拆装器将检查在交换中定义分隔符的 UNA 段。 如果交换没有 UNA 段（可选），拆装器将使用在管道组件属性中定义的默认值。  
  
|分隔符|UNA 的字符|  
|---------------|----------------------|  
|组件元素分隔符|第 4 个字符|  
|数据元素分隔符|第 5 个字符|  
|十进制符号|第 6 个字符|  
|转义符|第 7 个字符|  
|重复字符|第 8 个字符|  
|段分隔符|第 9 个字符|  
|段分隔符后缀|UNA 段和 UNB 段之间的字符<br /><br /> **值：**无、 CR、 LF 或 CRLF**注意：**分隔符可以采用仅上面的值。|  
  
 UNA 字符串是可选的。 如果存在，它定义文件的所有分隔符。 如果不存在，EDI 拆装器将使用 EfactDelimiters 管道组件属性确定分隔符。 有关详细信息，请参阅[配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)。  
  
 **发布错误**  
  
 如果 EDI 拆装器遇到 EDI 处理错误，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在事件查看器中发布以下两个错误（如果已启用此发布功能）：  
  
-   源 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 挂起消息时记录的错误。 该错误是与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理相关的必需错误。  
  
-   源 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 记录的报告事务集中的问题的错误。 该错误特定于 EDI。  
  
## <a name="using-agreement-properties"></a>使用协议属性  
 如果它可以确定该协议，EDI 反汇编程序将使用协议属性 (请参阅[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md))。 如果找不到匹配的协议和相应的值不可用回退协议中，在设置了 EDI 反汇编程序属性**属性**将使用 Visual Studio 窗口。 但是，此回退不会发生如果身份验证需要在接收端口属性 (如果**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**选择). 在这种情况下，必须配置协议；否则，交换将挂起。  
  
 当 EDI 拆装器使用协议属性时，需要设置下列协议属性：  
  
|属性|协议属性页|  
|--------------|-------------------------------|  
|重复分隔符|**包络线**页 (下**交换设置**) 中的双向协议选项卡|  
|执行 EDI 数据类型验证|**验证**下页上**事务设置设置**在双向协议选项卡中 （对于 X12 和 EDIFACT 协议）|  
|扩展验证|**验证**下页上**事务设置设置**在双向协议选项卡中 （对于 X12 和 EDIFACT 协议）|  
|允许前导和尾随零和空间|**验证**下页上**事务设置设置**在双向协议选项卡中 （对于 X12 和 EDIFACT 协议）|  
|创建空 XML 标记（如果尾部分隔符允许）|**本地主机设置**下页上**事务设置设置**在双向协议选项卡中 （对于 X12 和 EDIFACT 协议）|  
|入站批处理选项|**本地主机设置**页 (下**交换设置**) 中的双向协议选项卡 （对于 X12 和 EDIFACT 协议）|  
|默认 EDIFACT 分隔符|-|  
|屏蔽安全/授权/密码信息|**本地主机设置**页 (下**交换设置**) 中的双向协议选项卡 （对于 X12 和 EDIFACT 协议）|  
|将隐式小数格式 Nn 转换为十进制数值|**本地主机设置**下页上**事务设置设置**双向协议选项卡中 (对于 X12 协议)|  
|将确认路由到请求-响应接收端口的发送管道|**本地主机设置**页 (**接收方设置**部分) 下**交换设置**在双向协议选项卡中 （对于 X12 和 EDIFACT 协议）|  
|X12 字符集|X12 交换信封生成**注意：**此设置仅用于验证输入的协议属性的值。 用于运行时处理的 X12 字符集在管道属性中选择。 有关详细信息，请参阅[EDI 字符集](../core/edi-character-sets.md)。|  
  
## <a name="using-hipaa-trigger-fields"></a>使用 HIPAA 触发器字段  
 EDI 段通常包含修改段含义的限定符值。 例如，N1 段可包含一个限定元素“BT”，表示“帐单收件人名字”，或可能包含一个限定元素“ST”，表示“收货方名字”。 通常它从左到业务逻辑来确定如何解释这些字段并拆装器将 N1 段的所有实例都解析为相同的 XML 记录名称;但是，HIPAA 架构附带[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]包含允许 EDI 反汇编程序，创建基于是否存在限定值的唯一 XML 记录的批注 (请参阅[HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md))。  
  
 当收到一个 HIPAA 事务集时，如果 EDI 拆装器遇到一个包含触发器字段的段，它将使用触发器信息来生成一个特定于该段和触发器组合的 XML 记录。  
  
 下表显示了 N1 段是如何基于 N101 值转化成 XML 记录的：  
  
|N1 段|生成的 XML 数据|  
|----------------|------------------------|  
|N1 * PR\*Contoso\*XV\*0000000 ~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|N1 * PE\*Fabrikam\*FI\*9999999 ~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md)