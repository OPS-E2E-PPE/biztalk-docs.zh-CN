---
title: 替代 EDI 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c19d3d-eab2-4d44-8752-25aeadb537a4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e768bb992497651a14558895e4bedf2dbff692fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393370"
---
# <a name="overriding-edi-headers"></a>替代 EDI 标头
将发送的 EDI 编码的交换时，应用于消息的 EDI 信封通常基于接收协议的 EDI 属性或后备协议属性。 但是通常很有用，若要设置 EDI 信封属性基于运行时生成的值。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以使用 EdiOverride 上下文属性以指定用于生成出站文档的 EDI 信封的值。  
  
## <a name="using-edioverride-context-properties"></a>使用 EdiOverride 上下文属性  
 EdiOverride 上下文属性提供对重写全部或部分，用来生成 EDI 信封的值的一种方法。 EDI 发送管道将使用 EdiOverride 上下文属性，其中包含有效的值来构造信封。 如果不填充属性，则管道将使用在协议属性或后备协议属性中指定的值，如果未定义协议。 如果某个属性包含无效的值，则管道将挂起消息并报告验证错误。  
  
> [!NOTE]
>  如果仅使用在 EdiOverride 集合中指定的值`EdiOverride.OverrideEdiHeader`属性写入到消息的上下文的且包含值为"True"。  
>   
>  未设置默认值。  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a>EdiOverride 属性适用于 X12 信封值  
 下表显示了 EdiOverride 上下文属性以及相应的 X12 信封标头：  
  
|Header|属性|  
|------------|----------------|  
|交换控制标头 (ISA)|ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16|  
|功能组标头 (GS)|GS01、 GS02、 GS03、 GS04、 GS05、 GS06、 GS07、 GS08|  
|事务集标头|ST02|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a>EDIFACT 信封值的 EdiOverride 属性  
 下表显示了 EdiOverride 上下文属性以及相应的 EDIFACT 信封段：  
  
|段|属性|  
|-------------|----------------|  
|服务字符串建议 (UNA)|UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix|  
|交换控制标头 (UNB)|UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11|  
|功能组标头 (UNG)|UNG1、 UNG2_1、 UNG2_2、 UNG3_1、 UNG3_2、 UNG4_1、 UNG4_2、 UNG5、 UNG6、 UNG7_1、 UNG7_2、 UNG7_3、 UNG8|  
|消息标头 (UNH)|UNH1|  
  
 因为 UNA 和 UNG EDIFACT 段是可选的可使用 GenerateUNA 和 GenerateUNG 属性来确定这些标头就生成了，而不考虑**应用 UNA 段**协议设置。 下表显示导致生成这些段的值：  
  
|GenerateUNA 上下文属性|应用 UNA 段协议设置|引擎行为|  
|----------------------------------|-----------------------------------------|---------------------|  
|TRUE|检查|生成 UNA|  
|TRUE|未选中状态|生成 UNA|  
|FALSE|检查|不生成 UNA|  
|FALSE|未选中状态|不生成 UNA|  
|不显示 （OverrideEDIHeader 为 false）|检查|生成 UNA|  
|不显示 （OverrideEDIHeader 为 false）|未选中状态|不生成 UNA|  
  
|GenerateUNG 上下文属性|应用 UNG 段协议设置|引擎行为|  
|----------------------------------|------------------------------------------|---------------------|  
|TRUE|检查|生成 UNG|  
|TRUE|未选中状态|生成 UNG|  
|FALSE|检查|不生成 UNG|  
|FALSE|未选中状态|不生成 UNG|  
|不显示 （OverrideEDIHeader 为 false）|检查|生成 UNG|  
|不显示 （OverrideEDIHeader 为 false）|未选中状态|不生成 UNG|  
  
### <a name="group-envelopes"></a>组信封  
 组信封带来一个特殊的难题，因为交换中可以有多个组存在。 若要解决此问题，EDI 发送管道可以将信封应用到交换中的所有组或将信封应用到交换中的唯一组。  
  
 对于单个事务，所有 GS 或 UNG 字段可以重都写，对于成批交换，可以重都写仅以下字段：  
  
-   GS04  
  
-   GS05  
  
-   UNG4_1  
  
-   UNG4_2  
  
### <a name="batching"></a>批处理  
 由批处理业务流程处理批处理消息的事务集控制编号重写。 以下属性可写入到将进行批处理以重写任何消息的上下文的事务集控制编号：  
  
-   ST02 (对于 X12 消息)  
  
-   UNH1 （适用于 EDIFACT 消息  
  
> [!NOTE]
>  如果多个传入消息包含相同的控制编号相同的组中，具有重复编号的消息将被挂起。  
  
> [!NOTE]
>  不要升级 EdiOverride 上下文属性 ISA、 UNA、 GS 或 UNG 是要进行批处理的消息。 如果你需要重写这些属性，将它们提升对输出消息之前发送到 EDI 批处理业务流程的发送管道。  
  
### <a name="delimiter-collision"></a>分隔符冲突  
 分隔符，例如，UNA 标头中，必须包含每个字段的唯一值。 当重写分隔符的值，例如，UNA 标头中，必须确保每个分隔符值不仅中重写，而且还在协议或后备协议设置中使用任何分隔符值之间的值唯一。  
  
 例如，如果您重写 UNA1、 UNA2 和 UNA4，并且 UNA3、 UNA5、 UNA6 和 UNA6Suffix 来自协议属性，每个属性必须包含与其他的唯一值。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)