---
title: 基本 Siebel 数据类型 |Microsoft Docs
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
ms.openlocfilehash: e996e84df20ecf1fad5feb86affae96ba83507e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372005"
---
# <a name="basic-siebel-data-types"></a>基本 Siebel 数据类型
本部分介绍如何在支持 Siebel 数据类型[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  

## <a name="supported-siebel-data-types"></a>支持的 Siebel 数据类型  
 下表显示的 Siebel 数据类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持以及如何它们表示适配器用于 BizTalk （XSD 类型），并在 WCF 服务模型 （.NET 类型）。 标有星号的类型，请参阅下表说明。  


|     数据类型     |    XSD 类型    | .NET 类型 |                                                                                                                                                                                                                                                                                                                                                                             Description                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|----------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    DTYPE_BOOL     |  xsd:boolean   |  Boolean  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|  DTYPE_CURRENCY   |  xsd:decimal   |  Decimal  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_DATE     | xsd:dateTime\* | DateTime  | 值不能协调世界时 (UTC)。<br /><br /> -对于化，值应遵循此模式:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)"。<br />-对于**DateTime**对象，**DateTime.Kind**必须是**DateTimeKind.Unspecified**。<br /><br /> 适配器将忽略时间部分。<br /><br /> 对于出站消息，适配器执行运行时验证以确保指定的值不是 UTC （z 或 UTC 偏移量）。 如果验证失败，适配器将引发异常。<br /><br /> 当此类型公开为 xsd: string （基于规则如下所述）：<br /><br /> 的格式由基础数据库决定。<br />-未运行时验证的值。 |
|  DTYPE_DATETIME   | xsd:dateTime\* | DateTime  |                                                                                          值可以包含日期和时间部分，并且不得为 UTC。<br /><br /> -对于**DateTime**对象， **DateTime.Kind**必须是**DateTimeKind.Unspecified**。<br /><br /> 对于出站消息，适配器将执行运行时验证以确保满足这些条件;如果验证失败，适配器将引发异常。<br /><br /> 当此类型公开为 xsd: string （基于规则如下所述）：<br /><br /> 的格式由基础数据库决定。<br />-未运行时验证的值。                                                                                           |
|     DTYPE_ID      |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|   DTYPE_INTEGER   |    xsd:int     |   Int32   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_NOTE     |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|   DTYPE_NUMBER    |  xsd:decimal   |  Decimal  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_PHONE    |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_TEXT     |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_TIME     | xsd:dateTime\* | DateTime  |                                       值不能为 UTC。<br /><br /> -对于化，值应遵循此模式：(1753年-01-01)T(\d\d:\d\d:\d\d) (。\*)"。<br />-对于**DateTime**对象<strong>，DateTime.Kind</strong>必须是**DateTimeKind.Unspecified**。<br /><br /> 对于出站消息，适配器执行运行时验证以确保指定的值不是 UTC （z 或 UTC 偏移量）。 如果验证失败，适配器将引发异常。<br /><br /> 当此类型公开为 xsd: string （根据如下所述的规则）：<br /><br /> 的格式由基础数据库决定。<br />-未运行时验证的值。                                       |
| DTYPE_UTCDATETIME | xsd:dateTime\* | DateTime  |                                                   值可以包含日期和时间部分，并且必须为 UTC。<br /><br /> -对于化，值必须以 UTC （Z 表示法或 UTC 偏移量） 表示。<br />-对于**DateTime**对象**DateTime.Kind**必须是**DateTimeKind.Utc**。<br /><br /> 对于出站消息，适配器将执行运行时验证以确保满足这些条件;如果验证失败，适配器将引发异常。<br /><br /> 当此类型公开为 xsd: string （基于规则如下所述）：<br /><br /> 的格式由基础数据库决定。<br />-未运行时验证的值。                                                   |

 业务服务方法参数类型如下：  

 Date  
 与 DTYPE_DATE 相同。  

 Number  
 与 DTYPE_NUMBER 相同。  

 String  
 与 DTYPE_TEXT 相同。  

 层次结构  
 XSD 类型 xsd: string，以及为.Net 类型字符串相对应。  在 XML 消息，这必须放置在 CDATA 节点。  

 集成对象  
 与层次结构相同。  

 *，适配器可以确定是否使用化或 xsd: string 来按以下方式表示 DTYPE_DATE、 DTYPE_DATETIME、 DTYPE_TIME 和 DTYPE_UTCDATETIME 业务组件中的字段。  

1.  如果业务组件字段具有上述数据类型之一，该适配器会将其作为公开化类型 （在此值映射到 DateTime 类型的.Net)。  

2.  如果业务组件字段没有数据类型，适配器会将其公开为 xsd: string （在此值映射到字符串类型的.Net)。  

## <a name="supported-facets-for-the-xml-schema-types"></a>对于 XML 架构类型的支持的方面  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持以下方面的 XML 架构类型。  

|Siebel 类型|方面|  
|-----------------|-----------|  
|DTYPE_BOOL|None|  
|DTYPE_CURRENCY|精度 (22)，小数位数|  
|DTYPE_DATE|(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)|  
|DTYPE_DATETIME|None|  
|DTYPE_ID|MaxLength (15)|  
|DTYPE_INTEGER|精度 (22)|  
|DTYPE_NOTE|MaxLength (16384)|  
|DTYPE_NUMBER|精度 (22)，小数位数|  
|DTYPE_PHONE|MaxLength (40)|  
|DTYPE_TEXT|MaxLength (2048)|  
|DTYPE_TIME|(1753-01-01)T(\d\d:\d\d:\d\d)(.*)|  
|DTYPE_UTCDATETIME|None|  

 以下是一些规则，以控制如何以及何时发布方面，并且其值：  

 如果该字段的长度属性设置为值大于零且小于或等于 （在上表中的括号中指定） 的最大值：  

-   精度方面发布，如下所示：  

    -   如果精度属性设置为该字段中，作为精度方面发布相同的值。  

    -   如果精度属性未设置为该字段，作为精度方面发布的长度值。  

-   仅当发布 Scale 方面：  

    -   已发布的精度属性  

    -   缩放属性设置为该字段的值大于零且小于精度方面的过程中发布的值  

-   MaxLength 方面是为 Length 属性指定的值。 这被选取的字段定义存储库。 如果在字段定义存储库中未指定长度，获取发布在上表中的括号中指定的值。  

### <a name="special-cases-related-to-siebel-data-types"></a>Siebel 数据类型相关的特殊情况  
 以下规则会影响业务组件字段分面基于的操作使用它们的上下文。 这些规则是适用于 INSERT 和 UPDATE 操作。 对于查询操作，所有业务组件字段会向用户都公开。  

 **业务组件字段标记为必需在 Siebel 中**  

 即使业务组件字段 Siebel 系统中被标记为必需但预默认值或后默认值将被设置为该字段，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将标记为可选字段。 因此如果用户提供一个值，以插入或更新，适配器将处理此值。 如果未不提供任何值，Siebel 将使用前 default/后 default 值。  

 **未标记为 READ ONLY 在 Siebel 业务组件字段**  

 如果业务组件字段未标记为 READ ONLY，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开为可写字段。 但是，有几个此规则的例外情况。 这些是：  

- 如果业务组件字段**Calculated**字段中 Siebel，它不会出现在 Insert 或 Update 操作因为 Siebel 将自动负责**计算**字段。  

- 如果通过显式联接 （在另一个表的表联接） 获得业务组件字段，则它是通常只读的。 但是，Siebel 允许数据写入到此字段中，如果它是一个选择列表字段。 因此，如果业务组件字段是从显式联接，并且该字段不是选择列表字段，然后它不会在 Insert 或 Update 操作因为适配器客户端无法写入此类字段的数据。  

  **未在业务组件中指定的字段的数据类型**  

  如果在业务组件中，未指定字段的数据类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开使用以下试探法的字段元数据。  

- 如果该字段是特殊字段 （即选择列表或联接）[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将查找目标业务组件中映射的字段。 如果该字段具有与其关联的类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开，作为字段的类型。 但是，如果该类型是 DTYPE_DATE、 DTYPE_TIME、 DTYPE_DATETIME 或 DTYPE_UTCDATETIME，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将公开为 xsd: string 类型的字段。 如果映射的字段不具有关联的类型，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将公开为 xsd: string 类型的原始字段。  

- 如果该字段不是选择列表或联接字段[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]会将其公开为 xsd: string 类型。  

  **数据类型、 字段长度或精度的父业务组件不可用**  

  如果数据类型，长度，或字段的父业务组件 （的业务组件的子业务组件根据选择列表或 MVLs），精度[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]获取有关数据类型、 长度、 精度和小数位数从信息选择列表业务组件或 MVL 的业务组件。  

## <a name="see-also"></a>请参阅  
 [消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)