---
title: EDI 替代上下文属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78cd56f-1e34-4503-8ee1-93b52137097f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182ddc6a243a578a890a47dc70faa427b4f6df88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22243237"
---
# <a name="edi-override-context-properties"></a>EDI 替代上下文属性
EdiOverride 全局属性架构中的消息上下文属性可以用来覆盖运行时的 EDI 信封值。 这些消息上下文属性是在 Microsoft.BizTalk.Edi.BaseArtifacts 程序集的 edi-properties.xsd 中定义的。 这些属性的命名空间是 `http://schemas.microsoft.com/BizTalk/2006/edi-properties`。  
  
 只要将对 Microsoft.BizTalk.Edi.BaseArtifacts 程序集的引用添加到业务流程项目中，就还可以在业务流程中使用 EdiOverride 上下文属性。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|OverrideEDIHeader|boolean|如果为 true，则 EDI 发送管道将尝试使用 EdiOverride 属性集合中的值构造 EDI 信封。|  
|ISA01|string|授权信息限定符 (X12)|  
|ISA02|string|授权信息 (X12)|  
|ISA03|string|安全信息限定符 (X12)|  
|ISA04|string|安全信息 (X12)|  
|ISA05|string|交换发送方限定符 (X12)|  
|ISA06|string|交换发送方 ID (X12)|  
|ISA07|string|交换接收方限定符 (X12)|  
|ISA08|string|交换接收方 ID (X12)|  
|ISA09|string|交换日期 (X12)<br /><br /> 此字段应包含实际日期值，而非日期格式。|  
|ISA10|string|交换时间 (X12)<br /><br /> 此字段应包含实际时间值，而非日期值。|  
|ISA11|string|交换控制标准标识符 (X12)|  
|ISA12|string|交换控制版本号 (X12)|  
|ISA13|string|交换控制编号 (X12)<br /><br /> 如果覆盖了交换控制编号，则会将相应的交换尾部段 (IEA) 设置为与指定的值匹配。|  
|ISA14|string|请求确认 (X12)|  
|ISA15|string|测试指示符 (X12)|  
|ISA16|string|组件元素分隔符 (X12)|  
|GS01|string|功能标识符代码 (X12)|  
|GS02|string|应用程序发件人的代码 (X12)|  
|GS03|string|应用程序接收方代码 (X12)|  
|GS04|string|日期 (X12)<br /><br /> 此字段应包含实际日期值，而非日期格式。<br /><br /> 此值应为 CCYYMMDD 或 YYMMDD 格式。 即使提供的日期使用不同于“参与方”属性中选择的格式，仍会使用所提供的日期。|  
|GS05|string|时间 (X12)<br /><br /> 此字段应包含实际时间值，而非时间格式。<br /><br /> 此值应为 HHMM、HHMMSS 或 HHMMSSdd 格式。 即使提供的时间使用不同于“参与方”属性中选择的格式，仍会使用所提供的时间。|  
|GS06|string|组控制编号 (X12)<br /><br /> 覆盖了组控制编号后，会将 GE 段中相应的字段设置为与指定的值匹配。|  
|GS07|string|负责机构代码 (X12)|  
|GS08|string|版本/发行版/行业标识符代码 (X12)|  
|ST02|string|事务集控制编号 (X12)<br /><br /> 如果覆盖了事务集控制编号，则会将事务集尾部段 (SE) 中的相应字段设置为与该值匹配。|  
|GenerateUNA|boolean|确定 EDI 发送管道是否将为出站 EDIFACT 文档设置 UNA 段。<br /><br /> 如果 OverrideEdiHeader 为 True 且 GenerateUNA 也为 True，则将生成 UNA 段。 如果 OverrideEdiHeader 为 True，但“生成 UNA”为 False，将不会生成 UNA 段。<br /><br /> 按以下顺序确定 UNA 段的值：<br /><br /> -EdiOverride 上下文属性，如果所有 UNA 属性都都存在。<br />-如果不是所有上下文属性都都存在，并生成 UNA 段签入参与方属性，上下文属性和参与方属性的组合。<br />-如果不是所有上下文属性都都存在，并生成 UNA 段未参与方属性中的上下文属性和标准 UNA 值的组合**注意：** 如果 OverrideEdiHeader 为 false，此字段项不起作用。|  
|UNA1|string|组件数据元素分隔符 (EDIFACT)|  
|UNA2|string|数据元素分隔符 (EDIFACT)|  
|UNA3|string|小数点符号 (EDIFACT)|  
|UNA4|string|转义符 (EDIFACT)|  
|UNA5|string|重复分隔符 (EDIFACT)|  
|UNA6|string|段终止符 (EDIFACT)|  
|UNA6Suffix|string|段终止符后缀 (EDIFACT)|  
|UNB1_1|string|语法标识符 (EDIFACT)|  
|UNB1_2|string|语法版本号 (EDIFACT)|  
|UNB10|string|通信协议 ID (EDIFACT)|  
|UNB11|string|测试指示符 (EDIFACT)|  
|UNB2_1|string|发送方标识 (EDIFACT)|  
|UNB2_2|string|合作伙伴标识代码限定符 (EDIFACT)|  
|UNB2_3|string|反向路由地址 (EDIFACT)|  
|UNB3_1|string|接收方标识 (EDIFACT)|  
|UNB3_2|string|合作伙伴标识代码限定符 (EDIFACT)|  
|UNB3_3|string|路由地址 (EDIFACT)|  
|UNB4_1|string|日期 (EDIFACT)<br /><br /> 此字段应包含实际日期值，而非日期格式。|  
|UNB4_2|string|时间 (EDIFACT)<br /><br /> 此字段应包含实际时间值，而非时间格式。|  
|UNB5|string|交换控制参考 (EDIFACT)<br /><br /> 覆盖交换控制参考时，则会将交换尾部段 (UNZ) 中的控制编号设置为与指定的值匹配。|  
|UNB6_1|string|接收方参考/密码 (EDIFACT)|  
|UNB7|string|应用程序参考 (EDIFACT)|  
|UNB8|string|处理优先级代码 (EDIFACT)|  
|UNB9|string|确认请求 (EDIFACT)|  
|GenerateUNG|boolean|确定 EDI 发送管道是否将为出站 EDIFACT 文档设置 UNG 段。<br /><br /> 如果 OverrideEdiHeader 为 True 且 GenerateUNG 也为 True，则将生成 UNG 段。 如果 OverrideEdiHeader 为 True，但“生成 UNG”为 False，则将不会生成 UNG 段。<br /><br /> 按以下顺序确定 UNG 段的值：<br /><br /> -EdiOverride 上下文属性，如果所有 UNG 属性都都存在。<br />-如果不是所有上下文属性都都存在，并生成 UNG 段签入参与方属性，上下文属性和参与方属性的组合。<br />-如果不是所有上下文属性都都存在，并生成 UNG 段未参与方属性中的上下文属性和标准 UNA 值的组合**注意：** 如果 OverrideEdiHeader 为 false，此字段项不起作用。|  
|UNG1|string|消息组标识 (EDIFACT)|  
|UNG2_1|string|应用程序发送方标识 (EDIFACT)|  
|UNG2_2|string|标识代码限定符 (EDIFACT)|  
|UNG3_1|string|应用程序接收方标识 (EDIFACT)|  
|UNG3_2|string|标识代码限定符 (EDIFACT)|  
|UNG4_1|string|准备日期 (EDIFACT)<br /><br /> 此字段应包含实际日期值，而非日期格式。|  
|UNG4_2|string|准备时间 (EDIFACT)<br /><br /> 此字段应包含实际时间值，而非时间格式。|  
|UNG5|string|组参考编号 (EDIFACT)<br /><br /> 如果覆盖了组参考编号，则会将组尾部段 (UNZ) 中的相应字段设置为与指定的值匹配。|  
|UNG6|string|控制机构编码 (EDIFACT)|  
|UNG7_1|string|消息版本号 (EDIFACT)|  
|UNG7_2|string|消息发行版号 (EDIFACT)|  
|UNG7_3|string|协会分配的代码 (EDIFACT)|  
|UNG8|string|应用程序密码 (EDIFACT)|  
|UNH1|string|消息参考编号 (EDIFACT)<br /><br /> 如果覆盖了消息参考编号，则会将消息尾部段 (UNT) 中的相应字段设置为与此值匹配。|  
  
## <a name="edioverride-context-property-usage"></a>EDIOverride 上下文属性用法  
 如果**OverrideEdiHeader**上下文属性为 true 时，在 EDIOverride 上下文属性中指定的值将用于创建出站消息的 EDI 信封。 如果没有为 EDIOverride 上下文属性指定值，则将使用相应的“参与方”或“全局”属性。  
  
 根据 X12 或 EDIFACT 标准和任何服务架构扩展，为 EDIOverride 上下文属性指定的值必须有效。  
  
-   字段应包含对于该字段类型有效的值，包括服务架构扩展。  
  
-   控制编号必须是有效的类型，但不必是现有参与方设置中按顺序排列的下一个类型。  
  
-   日期和时间字段应包含日期和时间值，并且应根据相关的 EDI 标准来说是有效的，即使这些值的格式与在“参与方”设置中定义的格式不匹配也是如此。  
  
 仅当由 EDI 发送管道发送的消息为单个事务或事务批时，才支持某些 EDIOverride 上下文属性。 下表列出了每种消息类型支持的上下文属性：  
  
|发送的 EDI 事务|支持的 EDIOverride 上下文属性|  
|--------------------------------|----------------------------------------------|  
|单一事务集|-所有 Isa<br />-所有 GSs<br />-ST02<br />-GenerateUNA<br />-所有 UNAs<br />-所有 UNBs<br />-GenerateUNG<br />-所有 UNGs<br />-UNH1|  
|批处理业务流程发布的批处理事务集或 EDI 接收管道发布的“批次性作业”事务集|-所有 Isa<br />-GS04<br />-GS05<br />-GenerateUNA<br />-所有 UNAs<br />-所有 UNBs<br />-GenerateUNG<br />-UNG4.1<br />-UNG4.2|  
  
 EDIOverride 上下文属性还可用于将进行批处理的消息，但是批处理业务流程只支持 ST01 和 UNH1 EDIOverride 上下文属性。  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)