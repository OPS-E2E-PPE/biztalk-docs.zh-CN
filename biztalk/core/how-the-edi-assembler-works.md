---
title: "EDI 汇编器的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3785870-08ab-4fc2-8f7e-7c5a37639a7a
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f11fa41cabb6d5199953c2df005aa79965216f9
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-the-edi-assembler-works"></a>EDI 组装器的工作原理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行大多数将发送到 EDI 发送管道的 EDI 编码交换处理(`Microsoft.BizTalk.DefaultPipelines.EDISendPipeline`)。 此管道包括用于执行下列处理的 EDI 组装器管道组件：  
  
-   序列化 EDI 交换，并将 XML 编码的消息转换成交换中的 EDI 事务集。  
  
-   执行 EDI 架构验证、X12 编码消息的跨字段验证（如果已配置）、EDI 结构验证和扩展架构验证（如果此架构是使用具有非 EDI 数据类型的节点自定义的）。  
  
-   将信封应用于 EDI 消息。  
  
-   处理为响应 EDI 消息而收到的技术和功能确认，如果配置了解除批处理，则会对这些确认执行解除批处理操作。  
  
## <a name="applying-an-envelope-to-an-outgoing-edi-message"></a>将信封应用于传出 EDI 消息  
 当 EDI 发送管道使用中间 XML 文件生成传出 EDI 消息时，它会根据为接收方协议建立的 EDI 属性将包含交换和组标头的信封应用于该消息。 如果发送管道无法根据发送端口确定接收协议，它将使用回退协议来应用信封。  
  
 如果 `EdiOverride.OverrideEdiHeader` 上下文属性设置为 true，EDI 发送管道将使用 EdiOverride 属性集合中指定的值来构造信封。 如果值尚未出现在集中，则将使用协议属性中的相关 EDI 值。 如果值不存在于 EdiOverride 集或协议属性中，则将使用回退 EDI 协议中的属性。  
  
 如果中间 XML 文件具有保留标记或 ReuseEnvelope 上下文属性，则该消息是保留批，将不会对其应用信封应用程序逻辑。  
  
### <a name="sources-for-x12-envelope-values"></a>X12 信封值的来源  
 下表显示了 EDI 发送管道在何处为 X12 信封的每一部分获取其所需的信息：  
  
|标题|数据源|  
|------------|------------|  
|交换控制标头 (ISA)|-EdiOverride 上下文属性 (如果 `EdiOverride.OverrideEdiHeader` 为 true)。<br />-如果定义一个协议，ISA 段定义下的不同页从 **交换设置** 的单向协议属性中的部分 **协议属性** 对话框。<br />-如果没有协议定义，ISA 段定义下的不同页从 **交换设置** 主题中 **EDIFACT 回退设置** 对话框。|  
|功能组标头 (GS)|-EdiOverride 上下文属性 (如果 `EdiOverride.OverrideEdiHeader` 为 true)<br />-GS 如果定义一个协议，则段中的定义 **包络线** 页 (下 **事务设置设置** 部分) 中的单向协议属性 **协议属性** 对话框<br />-如果没有协议定义，GS 段中的定义 **包络线** 页 (下 **事务设置设置** 部分) 中 **X12 回退设置** 对话框<br /><br /> 如果定义了协议，则 GS 数据元素的值是根据事务集标识符 (ST1)、版本和目标命名空间的组合确定的。 这些值进行比较的网格中 **包络线** 页 (下 **事务设置设置** 部分) 的协议属性 （如果定义的协议） 或回退的协议属性 （如果不定义的任何协议）︰<br /><br /> -如果存在不匹配的行，然后匹配的行中包含的值用于 GS 标头。<br />-如果没有匹配项，但定义默认行，默认行填充 GS01 之外的所有 GS 数据元素。 基于 ST1 值动态确定 GS01。<br />-如果没有任何匹配的行，并且没有默认行，则挂起消息。 **注意︰**  要是唯一从其他组的组，不是所有这些值可以是另一个组相同。 <br /><br /> 如果未定义协议，则从回退协议属性中填充 GS 数据元素。|  
  
### <a name="sources-for-edifact-envelope-values"></a>EDIFACT 信封值的来源  
 下表显示了 EDI 发送管道在何处为 EDIFACT 信封的每一部分获取其所需的信息：  
  
|标题|数据源|  
|------------|------------|  
|服务字符串建议 (UNA)|-EdiOverride 上下文属性 (如果 `EdiOverride.OverrideEdiHeader` 为 true)。<br />-如果协议定义，UNA 段中的定义 **字符集和分隔符** 的单向协议属性中的页 **协议属性** 对话框。<br />-如果没有协议定义，UNA 段中的定义 **字符集和分隔符** 页面 **EDIFACT 回退设置** 对话框。|  
|交换控制标头 (UNB)|-EdiOverride 上下文属性 (如果 `EdiOverride.OverrideEdiHeader` 为 true)。<br />-如果协议定义，UNB 段定义下的不同页从 **交换设置** 的单向协议属性中的部分 **协议属性** 对话框。<br />-如果没有协议定义，UNB 段定义下的不同页从 **交换设置** 主题中 **EDIFACT 回退设置** 对话框。|  
|功能组标头 (UNG)|-EdiOverride 上下文属性 (如果 `EdiOverride.OverrideEdiHeader` 为 true)。<br />-如果协议定义，UNG 和新罕布什尔大学段中的定义 **包络线** 页 (下 **事务设置设置** 部分) 中的单向协议属性 **协议属性** 对话框<br />-如果没有协议定义，UNG 和新罕布什尔大学段中的定义 **包络线** 页 (下 **事务设置设置** 部分) 的单向协议属性中 **协议属性** 中的对话框 **EDIFACT 回退设置** 对话框<br /><br /> 如果定义了协议，则 UNG 数据元素的值是根据消息类型 (UNH2.1)、消息发行版号 (UNH2.3)、分配的代码 (UNH2.5)、版本和目标命名空间的组合确定的。 **注意︰**  要是唯一从其他组的组，不是所有这些值可以是另一个组相同。|  
  
### <a name="applying-transaction-set-header-and-trailer-segments"></a>应用事务集标头和尾部段  
 要序列化到传出 EDI 交换中的 XML 事务集应当具有事务集标头和尾部。 但是，如果没有事务集标头或尾部，EDI 组装器将处理相应消息。 X12 和 EDIFACT 架构中的事务集标头和尾部段对 XML 事务集而言是可选的。 如果事务没有标头或尾部，则 EDISend 或 AS2EDISend 发送管道中的 EDI 组装器将会向其添加事务集标头和尾部值。 这些值将基于映射或计算。 EDI 组装器将会为交换 XML（保留批）、批处理的事务集 XML 和事务集 XML 执行此操作。  
  
 如果映射造成验证错误，则 XML 事务集或交换 XML 将会被挂起，并且在事件查看器中会显示相应的错误，例如长度或数据类型无效，或者控制机构代码无效。  
  
####  <a name="BKMK_X12"></a> X12 事务集标头和预告片段  
 对于没有标头和尾部段的 X12 编码的事务集，EDI 组装器会将 ST 和 SE 段设置为以下值：  
  
|标头/尾部段|“值”|  
|----------------------------|-----------|  
|ST01（事务集标识代码）|映射到传入 XML 事务集中的 RootNode 名称的最后三个字符。 例如，映射到“X12_00401_855”中的“855”。 对于具有 TS 标识代码 837P、837D 或 837I 的 HIPAA 声明，使用“837”。|  
|ST02（事务集控制编号）|值 `EdiOverride.ST02` (如果 `EdiOveride.OverrideEdiHeader` 为 true，) 或映射到的值 **事务集控制编号 (ST02)** 中 **本地主机设置** 页 (下 **交换设置**) 中的单向协议选项卡的 **协议属性** 对话框。<br /><br /> 不管如何设置应用的新的或递增控制编号 **Apply 新 ID** 属性。|  
|ST03（版本标识符）|映射到来自传入 XML 事务集的 ST03 值。 例如，适用于 5010 HIPAA 820 文档的“005010 X 218”（工资扣缴）。 ST03 对用于验证事务集的架构进行验证。 **注意︰**  ST03 是必需的所有 HIPAA 版本 5010 事务 835 除外。|  
|SE01（包含的段数）|设置为事务集中的总段数，其中包括 ST 和 SE 段。|  
|SE02（事务集控制编号）|映射到事务集中 ST02 的值。|  
  
 事务集标头中的其他数据元素（如 ST03）是可选的，因而在生成的段中未赋值。  
  
####  <a name="BKMK_EDIFACT"></a> EDIFACT 事务集标头和预告片段  
 对于没有标头和尾部段的 EDIFACT 编码的事务集，EDI 组装器会将 UNH 和 UNT 段设置为以下值：  
  
|标头/尾部段|“值”|  
|----------------------------|-----------|  
|UNH01（消息引用控制编号）|值 `EdiOverride.UNH1` (如果 `EdiOverride.OverrideEdiHeader` 为 true，) 或映射到的值 **参考编号 (UNH1)** 中 **本地主机设置** 页 (下 **交换设置**) 中的单向协议选项卡的 **协议属性** 对话框。 不管如何设置应用的新的或递增控制编号 **Apply 新 ID** 属性。|  
|UNH2.1（消息类型）|映射到传入 XML 事务集中的 RootNode 名称的最后六个字符。 例如，映射到“EFACT_D96A_INVOIC”中的“INVOIC”。|  
|UNH2.2（消息版本号）|映射到传入 XML 事务集中的 RootNode 名称的第七个字符。 例如，映射到“EFACT_D96A_INVOIC”中的“D”。|  
|UNH2.3（消息发行版号）|映射到传入 XML 事务集中的 RootNode 名称的第八、第九和第十个字符。 例如，映射到“EFACT_D96A_INVOIC”中的“96A”。|  
|UNH2.4（控制机构代码）|始终映射到字符串“UN”。|  
|UNT01（包含的段数）|设置为事务集中的总段数，其中包括 UNH 和 UNT 段。|  
|UNT02（消息引用控制编号）|映射到的值 **参考编号 (UNH1)** 中 **本地主机设置** 页 (下 **交换设置**) 中的单向协议选项卡的 **协议属性** 对话框|  
  
 UNH 事务集标头中的其他数据元素（如 UNH3 到 UNH6）是可选的，因而在生成的段中未赋值。 如果这些字段中有任何字段是必需的，则必须将它们设置为传入 XML 事务集中的值。  
  
### <a name="additional-processing-on-envelope-of-an-outgoing-message"></a>对传出消息信封的其他处理  
 EDI 发送管道对传出消息的信封执行以下处理。  
  
#### <a name="control-numbers"></a>控制编号  
 EDI 发送管道会将交换控制编号、组控制编号和事务集控制（或参考）编号输入到每个传出交换的信封段中。 下表显示了这些编号：  
  
|控制编号|X12 字段|EDIFACT 字段|  
|--------------------|---------------|-------------------|  
|交换控制编号|ISA13|UNB5|  
|组控制编号|GS6|UNG5|  
|事务集控制编号 (X12)<br /><br /> 事务集参考编号 (EDIFACT)|ST2|UNH1|  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将设置为根据你在中输入的值的范围发送下一步的交换的交换控制编号**交换控制编号 (ISA13)**属性**本地主机设置**页上 （下**交换设置**) 中的单向协议选项卡的**协议属性**对话框。 它将会为每个后续交换递增此编号，直到达到最大值。  
  
 如果使用 EdiOverride 上下文属性指定交换控制编号，则指定的值将用于此交换，并且不会影响在协议中指定的交换控制编号。  
  
> [!NOTE]
>  如果只能增加组控制编号在 EDIFACT **应用 UNG 段** 中的属性 **包络线** EDIFACT 协议属性页处于选定状态。 第二个字段（参考编号）会递增；前缀和后缀字段不会递增。 如果才会增加事务集控制编号 **应用新的 ID** 选择属性。  
  
> [!NOTE]
>  在保留批交换中，您可以使用消息收集示例创建自定义交换控制编号。 有关详细信息，请参阅[消息扩充示例 （BizTalk Server 示例）](../core/message-enrichment-sample-biztalk-server-sample.md)。  
  
 如果未定义协议，则会从回退协议中的相同页获取编号。 发送管道存储了上次使用的控制编号，然后为下一个交换、组和事务集输入递增编号。  
  
> [!NOTE]
>  如果任何控制编号达到指定范围的最大值，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将会引发错误，并挂起交换。 你可以手动重置控制编号，或配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中为下限，自动重置**本地主机设置**页面**协议属性**对话框，使这两个 X12 和EDIFACT 消息。  
  
> [!NOTE]
>  控制编号保存在 BizTalk MessageBox 数据库的 dbo.EdiSequenceNumbers 表中。 您应根据情况从表中清除控制编号或存档控制编号来管理此数据库。  
  
 在 EDIFACT 中，控制编号由字母数字值构成。 支持以下格式：  
  
-   数字（例如“1”）  
  
-   前缀数字后缀（例如“WA1A”）  
  
-   前缀数字（例如“AA1”）  
  
-   数字后缀（例如“1AA”）  
  
 在这些格式中，数字字符可以为“0”到“9”，前缀和后缀字符可以是数字以外的任何字符。 只有编号递增才可以达到最大值。  
  
#### <a name="count-of-segments"></a>段计数  
 对于交换中的每个事务集，EDI 发送管道都将验证事务集中的段计数，对于 X12，事务集中的段计数在 SE01 数据元素中指示，对于 EDIFACT，则在 UNT01 数据元素中指示。 如果相应数据元素的值与实际计数不符，则发送管道将更新此计数以反映实际段数。 不会因为计数错误而拒绝事务集。 计数的更新将记录在事件查看器中的警告中。 这不适用于对保留批的处理。  
  
## <a name="additional-steps-in-serializing-an-edi-interchange"></a>序列化 EDI 交换过程中的其他步骤  
 在序列化过程中，EDI 发送管道还执行以下步骤。  
  
### <a name="serializing-the-release-indicator"></a>序列化转义指示器  
 在 EDIFACT 消息的序列化过程中，EDI 发送管道会将任何需要的转义指示器插入到 EDI 交换中。 假定路由到发送管道的中间 XML 不包含转义的数据。 例如，如果路由到发送管道的 XML 数据中存在转义指示器，则发送管道将在现有转义指示器前添加另一转义指示器以便对它进行转义。  
  
 进行 EDI 验证时，不会验证转义指示器。 EDI 发送管道在计算长度限制时也不会将转义指示器纳入到计算范围内。  
  
### <a name="adding-trailing-zeroes-to-meet-implied-decimal-requirements"></a>添加尾随零以便满足隐式小数要求  
 如果 EDI 组装器遇到在小数点后的位数不足的数字，它会在小数点后添加尾随零以便满足隐式小数要求。 例如，当数字应采用 N2 格式时，如果 EDI 组装器遇到数字“4.5”，则组装器会将此数字更改为“4.50”。  
  
### <a name="replacing-separators-in-payload-data"></a>替换负载数据中的分隔符  
 如果出站消息中的数据还包含配置为数据、分段或复合元素分隔符的字符，则 EDI 发送管道可以替换这些字符。 例如，如果消息中包含的值为"测试 * 数据"并配置数据元素分隔符为\*，这可能会分析问题导致接收的系统上。  
  
 可以配置 EDI 发送管道进行替换此字符的启用 **替换负载中的分隔符** 属性并指定替换字符。 此属性位于 **字符集和分隔符** 的单向协议选项卡中的页 **协议属性** 对话框。  
  
### <a name="transform-hipaa-records-based-on-trigger-fields"></a>基于触发器字段转换 HIPAA 记录  
 如果出站文档 HIPAA 事务集，EDI 汇编器将转换到匹配的泛型 EDI 段包含触发器字段任何唯一 XML 记录 (请参阅[HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md))。 通过删除 “_”  字符之后 XML 记录名称的后缀，可以完成该操作。  
  
 例如，元素 <N1_PayerIdentification_TS835W1_1000A> 和 <N1_PayeeIdentification_TS835W1_1000B> 都将变为 N1 段。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)