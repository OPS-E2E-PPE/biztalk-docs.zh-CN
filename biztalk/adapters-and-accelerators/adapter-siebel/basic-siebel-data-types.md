---
title: 基本 Siebel 数据类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Siebel data types, supported
ms.assetid: bf86f639-6c45-49db-9e58-79c3ad2c9978
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0266f445c2fd8a7cba9a0e2089b9542813230580
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22218749"
---
# <a name="basic-siebel-data-types"></a>基本 Siebel 数据类型
本部分介绍如何将 Siebel 数据类型支持上[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
## <a name="supported-siebel-data-types"></a>支持的 Siebel 数据类型  
 下表显示 Siebel 数据类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持以及如何它们表示适配器 BizTalk （XSD 类型） 和 WCF 服务模型 （.NET 类型）。 标有星号的类型，请参阅表后面的备注。  
  
|数据类型|XSD 类型|.NET 类型|Description|  
|---------------|--------------|---------------|-----------------|  
|DTYPE_BOOL|xsd:boolean|Boolean|-|  
|DTYPE_CURRENCY|xsd:decimal|Decimal|-|  
|DTYPE_DATE|xsd:dateTime*|DateTime|值必须不为协调世界时 (UTC)。<br /><br /> -对于化，值应遵循此模式:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)"。<br />-为**DateTime**对象，**DateTime.Kind**必须**DateTimeKind.Unspecified**。<br /><br /> 将适配器忽略时间组件。<br /><br /> 对于出站消息，适配器执行运行时验证，以确保指定的值不是 UTC （z 或 UTC 偏移量）。 如果验证失败，该适配器将引发异常。<br /><br /> 当此类型是作为 xsd: string （基于规则如下所述） 公开：<br /><br /> 的格式是由基础数据库决定的。<br />-未运行时验证的值。|  
|DTYPE_DATETIME|xsd:dateTime*|DateTime|值可以包含日期和时间的组件，并且不得为 UTC。<br /><br /> -为**DateTime**对象， **DateTime.Kind**必须**DateTimeKind.Unspecified**。<br /><br /> 对于出站消息，适配器执行运行时验证以确保满足这些条件;如果验证失败，该适配器将引发异常。<br /><br /> 当此类型是作为 xsd: string （基于规则如下所述） 公开：<br /><br /> 的格式是由基础数据库决定的。<br />-未运行时验证的值。|  
|DTYPE_ID|xsd:string|字符串|-|  
|DTYPE_INTEGER|xsd:int|Int32|-|  
|DTYPE_NOTE|xsd:string|字符串|-|  
|DTYPE_NUMBER|xsd:decimal|Decimal|-|  
|DTYPE_PHONE|xsd:string|字符串|-|  
|DTYPE_TEXT|xsd:string|字符串|-|  
|DTYPE_TIME|xsd:dateTime*|DateTime|值必须不为 UTC。<br /><br /> -对于化，值应遵循此模式: (1753-01-01)T(\d\d:\d\d:\d\d) (。\*)"。<br />-为**DateTime**对象 **，DateTime.Kind**必须**DateTimeKind.Unspecified**。<br /><br /> 对于出站消息，适配器执行运行时验证，以确保指定的值不是 UTC （z 或 UTC 偏移量）。 如果验证失败，该适配器将引发异常。<br /><br /> 当此类型是作为 xsd: string （根据如下所述的规则） 公开：<br /><br /> 的格式是由基础数据库决定的。<br />-未运行时验证的值。|  
|DTYPE_UTCDATETIME|xsd:dateTime*|DateTime|值可以包含日期和时间的组件，并且必须是 UTC。<br /><br /> -对于化，值必须表示 UTC （Z 表示法或 UTC 偏移量）。<br />-为**DateTime**对象**DateTime.Kind**必须**DateTimeKind.Utc**。<br /><br /> 对于出站消息，适配器执行运行时验证以确保满足这些条件;如果验证失败，该适配器将引发异常。<br /><br /> 当此类型是作为 xsd: string （基于规则如下所述） 公开：<br /><br /> 的格式是由基础数据库决定的。<br />-未运行时验证的值。|  
  
 业务服务方法自变量类型如下：  
  
 日期  
 与 DTYPE_DATE 相同。  
  
 Number  
 与 DTYPE_NUMBER 相同。  
  
 字符串  
 与 DTYPE_TEXT 相同。  
  
 层次结构  
 XSD xsd: string 类型，以及为.Net 类型字符串相对应。  在 XML 消息，这必须放置在 CDATA 节点。  
  
 集成对象  
 与层次结构相同。  
  
 * 适配器确定是否使用化或 xsd: string 来按以下方式表示 DTYPE_DATE、 DTYPE_DATETIME、 DTYPE_TIME 和 DTYPE_UTCDATETIME 在业务组件中的字段。  
  
1.  如果业务组件字段具有上述数据类型之一，该适配器将将其作为公开化类型 （在此方法映射到 DateTime 类型的.Net)。  
  
2.  如果业务组件字段不具有任何数据类型，该适配器将公开它作为 xsd: string （在此方法映射到字符串类型的.Net)。  
  
## <a name="supported-facets-for-the-xml-schema-types"></a>对于 XML 架构类型的支持的方面  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]的 XML 架构类型支持以下方面。  
  
|Siebel 类型|方面|  
|-----------------|-----------|  
|DTYPE_BOOL|InclusionThresholdSetting|  
|DTYPE_CURRENCY|精度 (22)，小数位数|  
|DTYPE_DATE|(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)|  
|DTYPE_DATETIME|InclusionThresholdSetting|  
|DTYPE_ID|MaxLength (15)|  
|DTYPE_INTEGER|精度 (22)|  
|DTYPE_NOTE|MaxLength (16384)|  
|DTYPE_NUMBER|精度 (22)，小数位数|  
|DTYPE_PHONE|MaxLength (40)|  
|DTYPE_TEXT|MaxLength (2048)|  
|DTYPE_TIME|(1753-01-01)T(\d\d:\d\d:\d\d)(.*)|  
|DTYPE_UTCDATETIME|InclusionThresholdSetting|  
  
 以下是一些规则来控制如何以及何时会发布方面和它们的值：  
  
 如果该字段的长度属性设置为值大于零且小于或等于 （在前面的表中的括号中指定） 的最大值：  
  
-   Precision facet 发布，如下所示：  
  
    -   如果精度属性设置为该字段中，是作为 Precision facet 发布相同的值。  
  
    -   如果精度属性未设置为该字段中，是作为 Precision facet 发布的长度值。  
  
-   仅当发布缩放方面：  
  
    -   已发布的精度属性  
  
    -   了 Scale 特性设置为该字段的值大于零且小于作为 Precision facet 的一部分发布的值  
  
-   MaxLength 方面是指定 Length 属性的值。 这被选取字段定义存储库。 如果字段定义存储库中不指定长度，获取发布上表中的括号中指定的值。  
  
### <a name="special-cases-related-to-siebel-data-types"></a>Siebel 数据类型相关的特殊情况  
 以下规则影响基于在其中使用它们的操作的上下文在业务组件字段方面。 这些规则都适用于 INSERT 和 UPDATE 操作。 对于查询操作，向用户公开业务组件的所有字段。  
  
 **业务组件字段标记为必需的 Siebel 中**  
  
 即使业务组件字段 Siebel 系统中标记为必需但预默认或后的默认值被设置为该字段，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将标记为可选字段。 因此如果用户提供要插入或更新的一个值，该适配器将处理该值。 如果没有提供任何值，Siebel 将使用前 default/后 default 值。  
  
 **未标记为 READ ONLY Siebel 中的业务组件字段**  
  
 如果业务组件字段未标记为 READ ONLY，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将其公开为可写的字段。 但是，有几个遵循该规则。 这些是︰  
  
-   如果业务组件字段是**计算**字段在 Siebel，它不会出现在 Insert 或 Update 操作因为 Siebel 自动将会负责的**计算**字段。  
  
-   如果通过显式联接 （对另一个表的表联接） 中获得的业务组件字段，它具有通常只读属性。 但是 Siebel 允许数据写入到此字段中，如果它是选择列表字段。 因此，如果业务组件字段是从显式联接，并且该字段不是选择列表字段，然后它将不出现在 Insert 或 Update 操作因为适配器客户端无法写入此类字段的数据。  
  
 **未在业务组件中指定的字段的数据类型**  
  
 如果在业务组件中，未指定字段的数据类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开使用以下启发式技术的字段元数据。  
  
-   字段是否 （即选择列表或联接） 的特殊字段[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将查找目标在业务组件中映射的字段。 如果该字段具有与其关联的类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将公开为字段的类型。 但是，如果该类型是 DTYPE_DATE、 DTYPE_TIME、 DTYPE_DATETIME 或 DTYPE_UTCDATETIME，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将公开为 xsd: string 类型字段。 如果映射的字段不具有关联的类型，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将公开为 xsd: string 类型与原始域。  
  
-   如果该字段不是选择列表或联接字段[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将会将其作为 xsd: string 类型进行公开。  
  
 **数据类型、 字段长度或精度的父业务组件不可用**  
  
 如果数据类型，长度，或字段的父业务组件 （业务组件包含基于选择列表或 MVLs 子业务组件） 的精度[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]获取有关数据类型、 长度、 精度和小数位数从的信息选择列表在业务组件或 MVL 在业务组件。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Siebel eBusiness Applications 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)