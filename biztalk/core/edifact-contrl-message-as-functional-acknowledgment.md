---
title: 作为功能确认的 EDIFACT CONTRL 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d3c2be0-0993-4b2d-b6c3-286020117078
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e95e61fa4152cdd7485175240b6481f3d28cfc7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007942"
---
# <a name="edifact-contrl-message-as-functional-acknowledgment"></a>作为功能确认的 EDIFACT CONTRL 消息
如果已在业务配置文件设置或贸易合作伙伴协议（或者两个业务配置文件间未定义任何协议，则为后备协议）中选择生成功能确认，或者如果消息中的 UNB9 字段设置为“1”，将会生成 CONTRL 消息作为功能确认 (ACK)。 此确认会报告交换的语法检查结果。  
  
 CONTRL 功能确认包括以下段：  
  
-   UNH 消息标头（必需）  
  
-   UCI 段，用于标识交换主题，指示交换回执的状态，并包含对已接收交换的 UNA、UNB 和 UNZ 段的引用（必需）。 UCI 段的最大出现次数为 1；因此，它将报告在一个控制段中遇到的第一个错误。  
  
-   UCF 段，用于标识组段（由 UNG 标头和 UNE 尾部封装）并指示任何错误的性质（如果存在 UNG 段，则为必需）  
  
-   UCM 段，用于标识消息段（由 UNH 标头和 UNT 尾部封装）并指示任何错误的性质（必需）  
  
-   UCS 段，用于标识事务集并指示任何错误的性质（必需）  
  
-   UCD 段，用于标识错误复合数据元素或错误组件数据元素并指示错误的性质（条件可选）  
  
-   UNT 消息尾部（必需）。  
  
 如果收到的 CONTRL 功能确认仅包含 UNH、UCI 和 UNT 段，则 EDIReceive 管道会将确认作为 CONTRL 回执（技术）确认进行处理。  
  
 某报告级别下的段（即 UCI、UCF、UCM、UCS 和 UCD 段）的每个实例只能报告一个错误。  
  
> [!NOTE]
>  CONTRL 消息包含几个必需的数据元素，这些元素将从收到的交换进行复制。 如果交换中的数据元素丢失或在语法上无效，则无法生成在语法上有效的 CONTRL 消息。 因此，错误必须通过除 CONTRL 消息以外的其他方法进行报告。  
  
> [!NOTE]
>  在 BizTalk Server 中，对收到的交换包含仅一个或多个 CONTRL 消息响应中发送一条 CONTRL 消息 （接收确认，接受或拒绝）。 在 [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 中，将不会发送任何 CONTRL 消息（确认回执、接受或拒绝）来响应仅包含一个或多个 CONTRL 消息的已接收交换。 已接收 CONTRL 消息中的错误必须通过除 CONTRL 消息之外的其他方法进行报告。 如果包含数据消息的交换中包含一个或多个 CONTRL 消息，将会生成 CONTRL 消息作为对该交换的响应，就如同已接收的交换中未包含任何 CONTRL 消息一样。  
  
 **SG 循环**  
  
 CONTRL 功能确认的结构将会不同，具体取决于已接收的交换是包括一个组还是多个组。 如果该交换包括一个组，则每个组的确认将包含一个 UCF 段。 每个消息的每个 UCF 段将包含一个 UCM 段，并且每个 UCM 段将包括一系列一前一后的 UCS 和 UCD 段。  
  
 XML 格式的确认消息将包括一个封装每个 UCF 段的 SG3Loop 元素、一个封装每个 UCM 元素的 SG4Loop 元素以及一个封装每对 UCS 和 UCD 元素的 SG5Loop 元素。 本机 EDI 格式的消息中不存在 SG 循环标记。  
  
 如果该交换不包括组，确认将不包含任何 UCF 段。 而是每个消息的确认将包括一个 UCM 段，并且每个 UCM 段将包括一系列一前一后的 UCS 和 UCD 段。  
  
 XML 格式的确认消息将包括一个封装每个 UCM 元素的 SG1Loop 元素以及一个封装每对 UCS 和 UCD 元素的 SG2Loop 元素。 与包括组的交换一样，本机格式的确认中不存在 SG 标记。  
  
> [!NOTE]
>  根据行业用法，默认情况下接受的事务集不需要 SG1/SG4 循环。 不过，若要支持符合标准，你可以强制生成 SG1/SG4 通过选择**接受的事务集生成 SG1/SG4 循环**中的复选框**确认**页协议两个业务配置文件之间的协议的属性对话框 (或**确认**商业版配置文件的 EDI 设置选项卡页)。 如果选中此复选框，接收管道将是否接受或拒绝事务集生成 SG1/SG4 循环。 否则，将仅为错误事务集生成这些循环（在 UCM5 != 7 时）。  
  
 **数据元素**  
  
 CONTRL 功能确认包括以下数据元素：  
  
|Data 元素|Name|用法|  
|------------------|----------|-----------|  
|UNH1|消息参考编号|-|  
|UNH2|消息标识符子组件|这些子组件为：<br /><br /> -1 = CONTRL<br /><br /> - 2 = 4<br /><br /> - 3 = 1<br /><br /> -4 = 取消|  
|UCI1|交换控制编号|映射自已接收消息的 UNB5 字段。|  
|UCI2|交换发送方|映射自已接收消息的 UNB2 字段。 第一个子组件（标识）是必需的。 第二个子组件（代码限定符）和第三个组件（反向路由地址）是可选的。|  
|UCI3|交换接收方|映射自已接收消息的 UNB3 字段。 第一个子组件（标识）是必需的。 第二个子组件（代码限定符）是可选的。|  
|UCI4|操作代码|这些操作代码为：<br /><br /> -如果接受交换的 8<br /><br /> -如果接受交换的 7，但某些事务集将被拒绝<br /><br /> -如果该交换拒绝由于 UNA 或 UNB 段中出现错误的 4<br /><br /> 这是一个必需的数据元素。|  
|UCI5|语法错误代码|标识接收交换中的错误情况（如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。|  
|UCI6|服务段标记|标识在 UCI.5 数据元素中确定了错误情况的段。<br /><br /> 此数据元素为条件可选。|  
|UCI7|数据元素标识|标识在 UCI.5 数据元素中确定了错误情况的数据元素。 UCI7 的子组件为：<br /><br /> 元素的位置错误的数据段 （必需） 中<br /><br /> -错误组件数据元素中位置段 (条件 optionality)<br /><br /> 的段 (条件 optionality) 中的错误的数据元素匹配项|  
|UCI8|-|-|  
|UCF1|组参考编号|映射自已接收消息的 UNG5 字段。<br /><br /> 这是一个必需的数据元素。|  
|UCF2|应用程序发送方的标识|映射自已接收邮件的 UNG2 字段以及子组件<br /><br /> 这是一个条件可选的数据元素。|  
|UCF3|应用程序接收方的标识|映射自已接收邮件的 UNG3 字段以及子组件。<br /><br /> 这是一个条件可选的数据元素。|  
|UCF4|编码的操作|这些操作代码为：<br /><br /> -如果接受交换的 7<br /><br /> -如果该交换拒绝由于 UNA 或 UNB 段中出现错误的 4<br /><br /> 此代码适用于此级别和所有较低级别。<br /><br /> 这是一个必需的数据元素。|  
|UCF5|语法错误，编码|标识组中的错误情况（如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。|  
|UCF6|服务段标记|标识组中错误段。<br /><br /> 此数据元素为条件可选。|  
|UCF7|数据元素标识|标识在 UCF5 数据元素中确定了错误情况的数据元素。 UCF7 的子组件为：<br /><br /> 元素的位置错误的数据段 （必需） 中<br /><br /> -错误组件数据元素中位置段 (条件 optionality)<br /><br /> 的段 （必需） 中的错误的数据元素匹配项|  
|UCM1|消息参考编号|映射自已接收消息的 UNH1 字段。<br /><br /> 这是一个必需的数据元素。|  
|UCM2|消息标识符|映射自已接收邮件的 UNH2 字段以及子组件<br /><br /> 这是一个条件可选的数据元素。|  
|UCM3|编码的操作|这些操作代码为：<br /><br /> -如果接受交换的 7<br /><br /> -如果该交换拒绝由于 UNA 或 UNB 段中出现错误的 4<br /><br /> 此代码适用于此级别和所有较低级别。<br /><br /> 这是一个必需的数据元素。|  
|UCM4|语法错误，编码|标识组中的错误情况（如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。|  
|UCM5|服务段标记|标识错误中的 UNH 或 UNT 段。<br /><br /> 此数据元素为条件可选。|  
|UCM7|数据元素标识|标识在 UCM5 数据元素中确定了错误情况的数据元素。 UCM7 的子组件为：<br /><br /> 元素的位置错误的数据段 （必需） 中<br /><br /> -错误组件数据元素中位置段 (条件 optionality)<br /><br /> 的段 （必需） 中的错误的数据元素匹配项|  
|UCS1|消息正文中的段位置|开头为 1 的新罕布什尔大学的错误段的位置的计数。 若要报告段是缺少，这是处理其中应为缺少的段的位置之前的最后一段的数字计数位置。 通过将组中第一个段标识为缺少来表示缺少的段组。<br /><br /> 这是一个必需的数据元素。|  
|UCS2|语法错误编码|标识组中的错误情况（如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。|  
|UCD1|语法错误编码|标识组中的错误情况（如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。<br /><br /> **注意：** UCD1 数据元素 XSD 验证失败时，将报告的代码值为 12，无效的值。|  
|UCD2|数据元素标识|标识在 UCD1 数据元素中确定了错误情况的数据元素。 UCD2 的子组件为：<br /><br /> 元素的位置错误的数据段 （必需） 中<br /><br /> -错误组件数据元素中位置段 (条件 optionality)<br /><br /> 的段 （必需） 中的错误的数据元素匹配项|  
|UNT1|段计数|-|  
|UNT2|消息参考编号|-|