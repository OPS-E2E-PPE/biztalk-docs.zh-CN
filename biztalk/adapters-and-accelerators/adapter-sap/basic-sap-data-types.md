---
title: MySAP 适配器在 BizTalk 中的基本 SAP 数据类型 |Microsoft Docs
description: MySAP 适配器在 BizTalk 适配器包 (BAP) 的支持的 ABAP 和数据库数据类型
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 296b4813-f175-4a02-8fd3-227ae301bc3d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e878ff1830477bfb888415947cb50169394a9d46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015046"
---
# <a name="basic-sap-data-types"></a>基本 SAP 数据类型
参数类型[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]受支持:  

- ABAP SAP 支持的数据类型  

- SAP 支持的数据库数据类型  

  本部分介绍 ABAP 和数据库数据类型和其相应的.NET 和 XML 架构类型之间的映射。  

> [!NOTE]
>  在本部分中的信息适用于 Rfc、 Trfc 和 Bapi。 SAP 数据类型始终表示为字符串 (xsd: string) Idoc 中。 这是为了支持 BizTalk Server 平面文件分析器。  

## <a name="supported-abap-data-types"></a>受支持的 ABAP 数据类型  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持安全类型化对于某些 ABAP 数据类型。 启用安全键入后，这些数据类型表示为字符串。 配置安全设置键入**EnableSafeTyping**属性绑定。 默认情况下禁用安全键入。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  

 下表显示了未启用安全键入时如何显示 ABAP 数据类型。 (**EnableSafeTyping**为 false)。 启用安全键入以不同方式显示的数据类型都标有星号 （*）。  

|ABAP 数据类型|RFC 类型|XSD 类型|.NET 类型|格式字符串|  
|--------------------|--------------|--------------|---------------|-------------------|  
|我 （整数）|RFC_INT|xsd:int|Int32|-|  
|内部 (RFC_INT1)|RFC_INT1|xsd:unsignedByte|Byte|-|  
|内部 (RFC_INT2)|RFC_INT2|xsd:short|Int16|-|  
|F (Float)|RFC_FLOAT|xsd:double|双精度|-|  
|P （BCD 数字）|RFC_BCD|化如果长度 < = 28<br />xsd: string 如果长度 > 28|Decimal<br />String|十进制数。 使用小数位数为 0<br />十进制数。 使用 > 0 个小数位|  
|C （字符）|RFC_CHAR|xsd:string|String|-|  
|D (Date: YYYYMMDD) *|RFC_DATE|xsd:dateTime|DateTime|在内部，该适配器反序列化到值**DateTime**对象。 然后，调用**DateTime.ToUniversalTime**方法以将此对象的值转换为 UTC。 最后，日期部分 (**DateTime.Date**) 用于创建发送到 SAP 系统的值。 SAP 系统将此日期值作为本地时间。<br /><br /> 您应将日期值指定为 UTC，以避免转换。<br /><br /> -对于化，建议使用以下模式:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)Z"。<br />-对于**DateTime**对象集**DateTime.Kind**到**DateTimeKind.Utc**。|  
|T (时间： HHMMSS) *|RFC_TIME|xsd:dateTime|DateTime|在内部，该适配器反序列化到值**DateTime**对象。 然后，调用**DateTime.ToUniversalTime**方法以将此对象的值转换为 UTC。 最后，时间部分 (**DateTime.Time**) 用于创建发送到 SAP 系统的值。 SAP 系统将此时间值作为本地时间。<br /><br /> 您应将时间值指定为 UTC，以避免转换。<br /><br /> -对于化，建议使用以下模式:"(0001-01-01)T(\d\d:\d\d:\d\d) (。\*)"。<br />-对于**DateTime**对象集**DateTime.Kind**到**DateTimeKind.Utc**。<br /><br /> 例如，如果您的本地时间是上午 9:15，表示为"(001-01-01) T (09: 15:00) Z"|  
|N （数字字符串） *|RFC_NUM|xsd: int 如果 lenrth < = 9<br />化如果长度 > 9 和 < = 19<br />xsd: string 如果长度 > 19|Int32<br />long<br />String|-|  
|X （字节）|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
|字符串|RFC_STRING|xsd:string|String|-|  
|XSTRING|RFC_BYTE|xsd:base64Binary|Byte[]|-|  

 * 指示数据类型显示以不同的方式时启用了安全键入。  

### <a name="safe-typing-enabled"></a>启用安全键入  
 下表显示了以不同的方式启用安全键入时显示的 ABAP 数据类型 ( **EnableSafeTyping**绑定属性为 true)。  

|ABAP 数据类型|RFC 类型|XSD 类型|.NET 类型|格式字符串|  
|--------------------|--------------|--------------|---------------|-------------------|  
|D (Date: YYYYMMDD)|RFC_DATE|xsd:string|String|SAP 日期格式： YYYYMMDD。<br /><br /> 允许使用字符的日期数字，因此该值是实质上是八个字符的字符串|  
|T (时间： HHMMSS)|RFC_TIME|xsd:string|String|SAP 时间格式： HHMMSS。<br /><br /> 允许使用字符时间位数字，因此该值是实质上是六个字符字符串|  
|N （数字字符串）|RFC_NUM|xsd:string|String|一个 n 字符字符串;其中 n = numc 字段的长度。|  

 ABAP 数据类型不在此表中的显示方式与未启用安全键入时。  

### <a name="support-for-date-and-time-fields"></a>对日期和时间字段的支持  
 如果未启用安全键入，ABAP 日期 (D) 和时间 (T) 类型显示为化;但是，显示的日期和时间类型的模式方面是不同的。  

-   日期模式方面是： `(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)`  

     例如，2007 年 7 月 7 日 (2007年-07-07) 表示为：  

     `(2007-07-07)T(00:00:00)`的用户。  

-   时间模式方面是： `(0001-01-01)T(\d\d:\d\d:\d\d)(.*)`  

     例如，（下午 6:30 和 30 秒） 18:30:30 表示为：  

     `(0001-01-01)T(18:30:30)`的用户。  

#### <a name="how-does-the-adapter-represent-minimum-and-maximum-time-values-on-inbound-messages-from-sap"></a>原理适配器表示最小值和入站消息上的最大时间值 （从 SAP) 是什么？  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]它接收来自 SAP 系统的时间值时，使用以下准则：  

-   该适配器将视为 0 小时、 0 分钟和 0 秒 000000 (hhmmss) 和 240000 (hhmmss)。  

## <a name="supported-database-data-types"></a>受支持的数据库数据类型  
 在其中的方式[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]图面数据库数据类型还取决于是否启用安全键入。 下表显示了如何在适配器面数据库数据类型时未启用安全键入 ( **EnableSafeTyping**绑定属性为 false)。 启用安全键入以不同方式显示的数据类型都标有星号 （*）。  


|     数据库数据类型      |  RFC 类型  |                                                                                                                                                                                                                                                                                                              XSD                                                                                                                                                                                                                                                                                                              |                                                     .NET 类型                                                      |
|-----------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
|   ACCP （发布期）\*   |  RFC_NUM   |                                                                                                                                                                                                                                                                                                            xsd:int                                                                                                                                                                                                                                                                                                            |                                                       Int32                                                        |
|            CHAR             |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|        CLNT （客户端）        |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|    当前 （货币字段）    |  RFC_BCD   |                                                                                                                                                 化**注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]舍入小数参数的定义所基于的十进制值。 例如，如果小数参数可以接受小数点后最多五个数字，一个值，例如 4.000028 被四舍五入到 4.00003。                                                                                                                                                  |                                                      Decimal                                                       |
|     CUKY （货币键）     |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|     DATS （日期字段）\*     |  RFC_DATE  |                                                 xsd:dateTime<br /><br /> 在内部，该适配器反序列化到值**DateTime**对象。 然后，调用**DateTime.ToUniversalTime**方法以将此对象的值转换为 UTC。 最后，日期部分 (**DateTime.Date**) 用于创建发送到 SAP 系统的值。 SAP 系统将此日期值作为本地时间。<br /><br /> 您应将日期值指定为 UTC，以避免转换。 建议使用以下模式:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)Z"。                                                 | DateTime<br /><br /> 您应将日期值指定为 UTC (DateTime.Kind = DateTimeKind.Utc) 以避免转换。 |
|        DEC （数量）         |  RFC_BCD   |                                                                                                                                                 化**注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]舍入小数参数的定义所基于的十进制值。 例如，如果小数参数可以接受小数点后最多五个数字，一个值，例如 4.000028 被四舍五入到 4.00003。                                                                                                                                                  |                                                      Decimal                                                       |
|    FLTP （浮点）    | RFC_FLOAT  |                                                                                                                                                                                                                                                                                                          xsd:double                                                                                                                                                                                                                                                                                                           |                                                       双精度                                                       |
|            INT1             |  RFC_INT1  |                                                                                                                                                                                                                                                                                                       xsd:unsignedbyte                                                                                                                                                                                                                                                                                                        |                                                        Byte                                                        |
|            INT2             |  RFC_INT2  |                                                                                                                                                                                                                                                                                                           xsd:short                                                                                                                                                                                                                                                                                                           |                                                       Int16                                                        |
|            INT4             |  RFC_INT   |                                                                                                                                                                                                                                                                                                            xsd:int                                                                                                                                                                                                                                                                                                            |                                                       Int32                                                        |
|     LANG （语言密钥）     |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|            LCHR             | RFC_STRING |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|    LRAW (长字节 seq)     |  RFC_BYTE  |                                                                                                                                                                                                                                                                                                       xsd:base64binary                                                                                                                                                                                                                                                                                                        |                                                       Byte[]                                                       |
|           NUMC\*            |  RFC_NUM   |                                                                                                                                                                                                                                                                                             xsd:int<br />xsd:long<br />xsd:string                                                                                                                                                                                                                                                                                             |                  Int32 如果长度 < = 9<br />Int64 如果长度 > 9 和 < = 19<br />字符串长度 > 19                   |
|       PREC （准确性）       |  RFC_INT2  |                                                                                                                                                                                                                                                                                                           xsd:short                                                                                                                                                                                                                                                                                                           |                                                       Int16                                                        |
|       QUAN （数量）       |  RFC_BCD   |                                                                                                                                                 化**注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]舍入小数参数的定义所基于的十进制值。 例如，如果小数参数可以接受小数点后最多五个数字，一个值，例如 4.000028 被四舍五入到 4.00003。                                                                                                                                                  |                                                      Decimal                                                       |
|     RAW （字节序列）     |  RFC_BYTE  |                                                                                                                                                                                                                                                                                                       xsd:base64binary                                                                                                                                                                                                                                                                                                        |                                                       Byte[]                                                       |
| RAWSTRING （可变长度） |  RFC_BYTE  |                                                                                                                                                                                                                                                                                                       xsd:base64binary                                                                                                                                                                                                                                                                                                        |                                                       Byte[]                                                       |
|  字符串 （可变长度）   | RFC_STRING |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|     TIMS （时间字段）\*     |  RFC_TIME  | xsd:datetime<br /><br /> 在内部，该适配器反序列化到值**DateTime**对象。 然后，调用**DateTime.ToUniversalTime**方法以将此对象的值转换为 UTC。 最后，时间部分 (**DateTime.Time**) 用于创建发送到 SAP 系统的值。 SAP 系统将此时间值作为本地时间。<br /><br /> 您应将时间值指定为 UTC，以避免转换。 建议使用以下模式:"(0001-01-01)T(\d\d:\d\d:\d\d) (。\*)Z"。<br /><br /> 例如，如果您的本地时间是上午 9:15，表示为"(001-01-01) T (09: 15:00) Z" | DateTime<br /><br /> 您应将时间值指定为 UTC (DateTime.Kind = DateTimeKind.Utc) 以避免转换。 |
|     单位 （单位为 Qty）     |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|        [不受支持]        |     --     |                                                                                                                                                                                                                                                                                                              --                                                                                                                                                                                                                                                                                                               |                                                       String                                                       |

 * 指示，该适配器的数据类型以不同的方式时出现安全键入已启用。  

### <a name="safe-typing-enabled"></a>启用安全键入  
 下表显示的数据库时启用了安全键入以不同方式显示的数据类型 ( **EnableSafeTyping**绑定属性为 true)。  

|数据库数据类型|RFC 类型|XSD|.NET 类型|字符串值格式|  
|------------------------|--------------|---------|---------------|-------------------------|  
|ACCP （发布期）|RFC_NUM|xsd:string|String|字符串|  
|NUMC|RFC_NUM|xsd:string|String|字符串|  
|DATS （日期字段）|RFC_DATE|xsd:string|String|YYYYMMDD|  
|TIMS （时间字段）|RFC_TIME|xsd:string|String|HHMMSS|  

 未启用安全键入时，不在此表中的数据类型会显示为相同的方式。  

## <a name="supported-xsd-facets"></a>受支持的 XSD 方面  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下 XSD 方面。  

|RFC 类型|XSD 方面 (**EnableSafeTyping** = false)|XSD 方面 (**EnableSafeTyping** = true)|  
|--------------|-------------------------------------------------|------------------------------------------------|  
|RFC_BCD|**XSD 模式方面**<br /><br /> **零个小数位数：** `"([\\-]{0,1})(([0-9]{1,"`  `+ digitsBeforeDecimal +`  `"}))"`<br /><br /> **一个或多个小数位数：** `"([\\-]{0,1})(([0-9]{0,"` + `digitsBeforeDecimal +``"}\\.[0-9]{0,"``+ digitsAfterDecimal +``"})&#124;([0-9]{1,"``+ digitsBeforeDecimal +``"}))"`|相同|  
|RFC_NUM|**XSD totalDigits 方面**如果长度 < = 19<br /><br /> **XSD 模式方面**如果长度 > 19|**XSD maxLength facet （取决于 SAP 的值的长度）**|  
|RFC_DATE|**XSD 模式方面**<br /><br /> `"(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)"`<br /><br /> 模式包含时间 00:00:00 与兼容 `xsd:datetime`|**XSD maxLength facet = 8**|  
|RFC_TIME|**XSD 模式方面**<br /><br /> `"(0001-01-01)T(\d\d:\d\d:\d\d)(.*)"`<br /><br /> 模式包含要与兼容的日期 0001-01-01 `xsd:datetime`|**XSD maxLength facet = 6**|  
|RFC_CHAR|**XSD maxLength facet**|相同|  

## <a name="unsupported-data-types"></a>不支持的数据类型  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持以下数据类型：  

-   ITAB II （分层） 的表类型  

