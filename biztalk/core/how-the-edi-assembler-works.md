---
title: EDI 组装器的工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3785870-08ab-4fc2-8f7e-7c5a37639a7a
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 480bb6c17bc4e6085147e2c79ab3e3ba58d2746e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344105"
---
# <a name="how-the-edi-assembler-works"></a>EDI 组装器的工作原理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行的 EDI 编码的交换，EDI 发送管道中发送的大多数处理 (`Microsoft.BizTalk.DefaultPipelines.EDISendPipeline`)。 此管道包括 EDI 组装器管道组件，用于执行以下处理：  
  
-   序列化 EDI 交换，将 XML 编码的消息转换成交换中的 EDI 事务集。  
  
-   执行 EDI 架构验证、 X12 编码的消息 （如果已配置） 的跨字段验证、 EDI 结构验证和扩展的架构验证 （如果该架构使用具有非 EDI 数据类型的节点自定义）。  
  
-   将信封应用于 EDI 消息。  
  
-   处理对 EDI 消息，解除批处理确认，如果配置的响应中收到的技术和功能确认。  
  
## <a name="applying-an-envelope-to-an-outgoing-edi-message"></a>将信封应用到传出的 EDI 消息  
 当 EDI 发送管道生成传出 EDI 消息的中间 XML 文件时，它包含到根据为接收方协议建立的 EDI 属性的消息的交换和组标头的信封应用。 如果发送管道无法确定接收协议从发送端口，它将使用后备协议来应用信封。  
  
 如果`EdiOverride.OverrideEdiHeader`上下文属性设置为 true 时，EDI 发送管道将使用 EdiOverride 属性集合中指定的值来构造信封。 如果值在协议中不存在于集合的相关 EDI 值将使用属性。 如果在 EdiOverride 集合或协议属性中不存在一个值，将使用回退 EDI 协议中的属性。  
  
 如果中间 XML 文件具有保留的标记或 ReuseEnvelope 上下文属性，消息是保留的批，将不会应用信封应用程序逻辑。  
  
### <a name="sources-for-x12-envelope-values"></a>源为 X12 信封值  
 下表显示 EDI 发送管道在何处获取的信息，每个部分的 X12 信封：  
  
|Header|Source|  
|------------|------------|  
|交换控制标头 (ISA)|-EdiOverride 上下文属性 (如果`EdiOverride.OverrideEdiHeader`为 true)。<br />-如果定义了协议，ISA 会分段下不同页的定义**交换设置**部分中的单向协议属性中**协议属性**对话框。<br />-如果未定义协议，ISA 会分段下不同页的定义**交换设置**主题中**EDIFACT 后备设置**对话框。|  
|功能组标头 (GS)|-EdiOverride 上下文属性 (如果`EdiOverride.OverrideEdiHeader`为 true)<br />-如果定义了协议，GS 会分段**信封**页 (下**事务集设置**部分) 中的单向协议属性中**协议属性**对话框<br />-如果未定义协议，GS 会分段**信封**页 (下**事务集设置**部分) 中**X12 后备设置**对话框<br /><br /> 如果定义了协议，GS 数据元素的值是根据事务集标识符 (ST1)、 版本和目标命名空间的组合确定的。 这些值进行比较的网格中**信封**页 (下**事务集设置**部分) 的协议属性 （如果已定义协议） 或后备协议属性 （如果未定义协议）：<br /><br /> -如果没有匹配的行，然后匹配的行中包含的值用于 GS 标头。<br />-如果没有匹配项，但定义了默认行，从默认行中填充 （GS01 除外） 的所有 GS 数据元素。 基于 ST1 值动态确定 GS01。<br />-如果没有任何匹配的行，并且没有默认的行，则挂起消息。 **注意：** 要将其他组中唯一的组，不是所有这些值可以是不同于另一个组。 <br /><br /> 如果未定义协议，然后从回退协议属性中填充 GS 数据元素。|  
  
### <a name="sources-for-edifact-envelope-values"></a>EDIFACT 信封值的源  
 下表显示 EDI 发送管道在何处获取所需的 EDIFACT 信封的每个部分的信息：  
  
|Header|Source|  
|------------|------------|  
|服务字符串建议 (UNA)|-EdiOverride 上下文属性 (如果`EdiOverride.OverrideEdiHeader`为 true)。<br />-如果定义了协议，UNA 会分段**字符集和分隔符**页的单向协议属性中**协议属性**对话框。<br />-如果未定义协议，UNA 会分段**字符集和分隔符**页面**EDIFACT 后备设置**对话框。|  
|交换控制标头 (UNB)|-EdiOverride 上下文属性 (如果`EdiOverride.OverrideEdiHeader`为 true)。<br />-如果定义了协议，UNB 会分段下不同页的定义**交换设置**部分中的单向协议属性中**协议属性**对话框。<br />-如果未定义协议，UNB 会分段下不同页的定义**交换设置**主题中**EDIFACT 后备设置**对话框。|  
|功能组标头 (UNG)|-EdiOverride 上下文属性 (如果`EdiOverride.OverrideEdiHeader`为 true)。<br />-如果定义了协议，UNG 和 UNH 会分段**信封**页 (下**事务集设置**部分) 中的单向协议属性中**协议属性**对话框<br />-如果未定义协议，UNG 和 UNH 会分段**信封**页 (下**事务集设置**部分) 中的单向协议属性中**协议属性**对话框中的**EDIFACT 后备设置**对话框<br /><br /> 如果定义了协议，UNG 数据元素的值是根据消息类型 (UNH2.1)、 消息发行版号 (UNH2.3)、 分配代码 (UNH2.5)、 版本和目标命名空间的组合确定的。 **注意：** 要将其他组中唯一的组，不是所有这些值可以是不同于另一个组。|  
  
### <a name="applying-transaction-set-header-and-trailer-segments"></a>应用事务集标头和尾部段  
 XML 事务集被序列化到传出 EDI 交换应具有的事务集标头和尾部。 但是，EDI 组装器将处理该消息，如果它不具有事务集标头或尾部。 事务集标头和尾部段在 X12 和 EDIFACT 架构都是可选的 XML 事务集。 如果事务没有标头或尾部，EDI 组装器中 EDISend 或 AS2EDISend 发送管道将向其添加事务集标头和尾部值。 这些值将基于映射或计算。 EDI 组装器将执行此操作为交换 XML （保留批）、 批处理的事务集 XML 和事务集 XML。  
  
 如果映射造成验证错误，XML 事务集或交换 XML 会挂起因相应的错误在事件查看器中，如无效的长度或数据类型或控制机构代码无效。  
  
####  <a name="BKMK_X12"></a> X12 事务集标头和尾部段  
 对于没有标头和尾部段的 X12 编码的事务集，EDI 组装器将 ST 和 SE 段设置为以下：  
  
|标头/尾部段|ReplTest1|  
|----------------------------|-----------|  
|ST01 （事务集标识符代码）|映射到最后一个传入 XML 事务集中的 RootNode 名称的三个字符。 例如，从"X12_00401_855"的"855"。 对于具有 TS 标识代码的 837p、 837 837p、837d 或 837I 的 HIPAA 声明，"837"使用。|  
|ST02 （事务集控制编号）|值`EdiOverride.ST02`(如果`EdiOveride.OverrideEdiHeader`为 true，) 或映射到的值**事务集控制编号 (ST02)** 中**本地主机设置**页 (下**交换设置**) 中的单向协议选项卡**协议属性**对话框。<br /><br /> 如何设置应用新的或递增的控制编号**应用新 ID**属性。|  
|ST03 （版本标识符）|映射到的 ST03 值来自传入 XML 事务集。 例如，"005010 X 218"5010 HIPAA 820 文档 （工资扣缴）。 St03 对用于验证事务集的架构。 **注意：** ST03 是必需的所有 HIPAA 版本 5010 事务 （835 除外）。|  
|SE01 （包括的段的数量）|将设置为事务集，其中包括 ST 和 SE 段中的段的总数。|  
|SE02 （事务集控制编号）|映射到事务集中 ST02 的值。|  
  
 在事务中的其他数据元素设置标头，如 ST03、 是可选的因而不在生成的段中赋值。  
  
####  <a name="BKMK_EDIFACT"></a> EDIFACT 事务集标头和尾部段  
 对于没有标头和尾部段的 EDIFACT 编码的事务集，EDI 组装器将 UNH 和 UNT 段设置为以下：  
  
|标头/尾部段|ReplTest1|  
|----------------------------|-----------|  
|UNH01 （消息引用控制编号）|值`EdiOverride.UNH1`(如果`EdiOverride.OverrideEdiHeader`为 true，) 或映射到的值**参考编号 (UNH1)** 中**本地主机设置**页 (下**交换设置**)在单向协议选项卡**协议属性**对话框。 如何设置应用新的或递增的控制编号**应用新 ID**属性。|  
|UNH2.1 （消息类型）|映射到最后一个传入 XML 事务集中的 RootNode 名称的六个字符。 例如，"efact_d96a_invoic"的"INVOIC"。|  
|UNH2.2 （消息版本号）|从传入 XML 事务集映射到的 RootNode 名称的第七个字符。 例如，"efact_d96a_invoic""D"。|  
|UNH2.3 （消息发行版号）|第九个映射到第八个，并从传入 XML 事务的 RootNode 名称的第十个字符设置。 例如，"efact_d96a_invoic"的"96A"。|  
|UNH2.4 （控制机构代码）|始终映射到字符串取消。|  
|UNT01 （包括的段的数量）|将设置为事务集，其中包括 UNH 和 UNT 段中的段的总数。|  
|UNT02 （消息引用控制编号）|映射到的值**参考编号 (UNH1)** 中**本地主机设置**页 (在**交换设置**) 中的单向协议选项卡**协议属性**对话框|  
  
 UNH 事务集标头，如 UNH3 到 UNH6 中的其他数据元素是可选的因而不在生成的段中赋值。 如果任何这些字段是必需的必须将它们设置为传入 XML 事务集中的值。  
  
### <a name="additional-processing-on-envelope-of-an-outgoing-message"></a>附加处理的传出消息信封  
 EDI 发送管道对传出消息的信封执行以下处理。  
  
#### <a name="control-numbers"></a>控制编号  
 EDI 发送管道将输入交换控制编号、 组控制编号和事务集控制 （或参考） 编号的每个传出交换的信封段。 这些数字是下表中所示：  
  
|控制编号|X12 字段|EDIFACT 字段|  
|--------------------|---------------|-------------------|  
|交换控制编号|ISA13|UNB5|  
|组控制编号|GS6|UNG5|  
|事务集控制编号 (X12)<br /><br /> 事务集参考编号 (EDIFACT)|ST2|UNH1|  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将设置发送基于范围的值中输入的下一个交换的交换控制编号**交换控制编号 (ISA13)** 上的属性**本地主机设置**页上 （下**交换设置**) 中的单向协议选项卡**协议属性**对话框。 它将递增此编号对于每个后续交换，直到达到最大值。  
  
 如果使用 EdiOverride 上下文属性指定交换控制编号，则指定的值将用于此交换，并且将不会影响协议中指定的交换控制编号。  
  
> [!NOTE]
>  在 EDIFACT 中的组控制编号才会递增**应用 UNG 段**属性中的**信封**选择 EDIFACT 协议属性页。 第二个字段 （参考编号） 将增加;前缀和后缀字段不会增加。 如果事务集控制编号才会递增**将应用新 ID**选择属性。  
  
> [!NOTE]
>  在保留的批交换，可以创建使用消息收集示例对自定义交换控制编号。 有关详细信息，请参阅[消息充实示例 （BizTalk Server 示例）](../core/message-enrichment-sample-biztalk-server-sample.md)。  
  
 如果未定义协议，会从同一页面中在后备协议中获取编号。 发送管道存储上次使用的控制编号，然后进入下一步的交换、 组和事务集的递增的数字。  
  
> [!NOTE]
>  如果任何控制编号达到指定范围的最大值[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会引发错误并挂起该交换。 你可以手动重置控制编号，或配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以自动重置为下限，在**本地主机设置**页中**协议属性**对话框中，对于这两个 X12 和EDIFACT 消息。  
> 
> [!NOTE]
>  控制编号保存在 dbo。EdiSequenceNumbers BizTalk MessageBox 数据库的表。 应通过从表中清除控制编号或存档控制编号，根据需要来管理此数据库表。  
  
 在 EDIFACT 中，控制编号由字母数字值构成。 支持以下格式：  
  
- 数字 (例如，"1")  
  
- 前缀数字后缀 (例如，"WA1A")  
  
- 前缀数字 (例如，"AA1")  
  
- 数字后缀 (例如，"1AA")  
  
  在这些格式中，数字的字符可从"0"到"9"和前缀和后缀字符可以是任何非数字字符。 只有数量将会递增，直到达到最大值。  
  
#### <a name="count-of-segments"></a>段的计数  
 对于每个交换中事务集，EDI 发送管道将验证事务集中的段的计数在 SE01 数据元素适用于 X12 和 EDIFACT 的 UNT01 数据元素中所示。 如果相应的数据元素的值与实际计数不匹配，发送管道将更新此计数以反映实际段数。 不会由于计数错误而拒绝事务集。 计数的更新将记录在事件查看器中的警告。 这不适用于保留批的处理。  
  
## <a name="additional-steps-in-serializing-an-edi-interchange"></a>序列化 EDI 交换中的其他步骤  
 EDI 发送管道还在序列化过程中执行以下步骤。  
  
### <a name="serializing-the-release-indicator"></a>序列化转义指示器  
 序列化过程中的 EDIFACT 消息，EDI 发送管道会将任何需要的转义指示器插入到 EDI 交换。 假定，中间路由到发送管道的 XML 不包含转义的数据。 例如，如果路由到发送管道的 XML 数据中存在转义指示器，则发送管道会将另一转义指示器在现有转义指示器前的添加才能对其进行转义。  
  
 转义指示器不会包含在 EDI 验证。 在计算长度限制时，EDI 发送管道将不包括转义指示器。  
  
### <a name="adding-trailing-zeroes-to-meet-implied-decimal-requirements"></a>添加尾随零以便满足隐式小数要求  
 如果 EDI 组装器遇到在小数点后具有数目不足的位数的数字，它将添加尾随零以满足隐式小数要求的小数点后面。 例如，如果数字应采用 N2 格式时，EDI 组装器遇到数字"4.5"，则组装器可以将数更改为"4.50"。  
  
### <a name="replacing-separators-in-payload-data"></a>替换负载数据中的分隔符  
 如果出站消息中的数据包含还配置为数据、 段或组件分隔符的字符，EDI 发送管道可以替换这些字符。 例如，如果该消息包含的值为"测试 * 数据"和数据元素分隔符配置为\*，这可能会在接收系统上引起解析问题。  
  
 可以配置 EDI 发送管道来替换此字符，从而**替换为在通过有效负载中的分隔符**属性并指定替换字符。 此属性位于**字符集和分隔符**的单向协议选项卡中的页**协议属性**对话框。  
  
### <a name="transform-hipaa-records-based-on-trigger-fields"></a>转换 HIPAA 记录基于触发器字段  
 如果出站文档是 HIPAA 事务集，EDI 组装器将转换到匹配的普通 EDI 分段包含触发器字段任何唯一 XML 记录 (请参阅[HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md))。 这被通过删除"_"字符之后 XML 记录名称的后缀。  
  
 例如的元素 < N1_PayerIdentification_TS835W1_1000A > 和 < N1_PayeeIdentification_TS835W1_1000B > 将变为 N1 段。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)