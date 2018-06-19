---
title: 在 BizTalk 与 mySAP 适配器中的基本 SAP 数据类型 |Microsoft 文档
description: MySAP 适配器 BizTalk 适配器的包 (BAP) 中的受支持的 ABAP 和数据库数据类型
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
ms.openlocfilehash: f40e7dc6f98e1de2ff0388a8e7e52fdabafc7681
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22218989"
---
# <a name="basic-sap-data-types"></a>基本 SAP 数据类型
参数类型[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]受支持:  
  
-   SAP 支持的 ABAP 数据类型  
  
-   SAP 支持的数据库数据类型  
  
 本部分介绍 ABAP 和数据库数据类型和其相应的.NET 和 XML 架构类型之间的映射。  
  
> [!NOTE]
>  此部分中的信息适用于 Rfc、 tRFCs 和 BAPIs。 SAP 数据类型始终表示为字符串 (xsd: string) 在 Idoc。 这是为了支持 BizTalk Server 平面文件分析器。  
  
## <a name="supported-abap-data-types"></a>支持的 ABAP 数据类型  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持安全类型的某些 ABAP 数据类型。 启用安全键入后，这些数据类型表示为字符串。 配置通过设置安全键入**EnableSafeTyping**绑定属性。 默认情况下禁用安全键入。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
 下表显示未启用安全键入时，如何显示 ABAP 数据类型。 (**EnableSafeTyping**为 false)。 启用安全键入时，将以不同方式显示的数据类型将标有星号 （*）。  
  
|ABAP 数据类型|RFC 类型|XSD 类型|.NET 类型|格式字符串|  
|--------------------|--------------|--------------|---------------|-------------------|  
|我 （整数）|RFC_INT|xsd:int|Int32|-|  
|内部 (RFC_INT1)|RFC_INT1|xsd:unsignedByte|Byte|-|  
|内部 (RFC_INT2)|RFC_INT2|xsd:short|Int16|-|  
|F (Float)|RFC_FLOAT|xsd:double|双精度|-|  
|P （BCD 数）|RFC_BCD|化如果长度 < = 28<br />xsd: string 如果长度 > 28|Decimal<br />字符串|十进制数。 使用小数位数为 0<br />十进制数。 与 > 小数位数为 0|  
|C （字符）|RFC_CHAR|xsd:string|字符串|-|  
|D (日期： YYYYMMDD) *|RFC_DATE|xsd:dateTime|DateTime|在内部，该适配器反序列化到值**DateTime**对象。 示例然后调用**DateTime.ToUniversalTime**方法将此对象的值转换为 UTC。 最后的日期部分 (**DateTime.Date**) 用于创建发送到 SAP 系统的值。 SAP 系统将此日期值视为本地时间。<br /><br /> 您应将日期值指定为 UTC 以避免转换。<br /><br /> -对于化，建议使用以下模式:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)Z"。<br />-为**DateTime**对象集**DateTime.Kind**到**DateTimeKind.Utc**。|  
|T (时间： HHMMSS) *|RFC_TIME|xsd:dateTime|DateTime|在内部，该适配器反序列化到值**DateTime**对象。 示例然后调用**DateTime.ToUniversalTime**方法将此对象的值转换为 UTC。 最后时间组件 (**DateTime.Time**) 用于创建发送到 SAP 系统的值。 SAP 系统将本地时间视为此时间值。<br /><br /> 您应将时间值指定为 UTC 以避免转换。<br /><br /> -对于化，建议使用以下模式:"(0001-01-01)T(\d\d:\d\d:\d\d) (。\*)"。<br />-为**DateTime**对象集**DateTime.Kind**到**DateTimeKind.Utc**。<br /><br /> 例如，如果您的本地时间，上午 9:15 express 为"(001-01-01) T (09: 15:00) Z"|  
|N （数字字符串） *|RFC_NUM|xsd:int 如果 lenrth < = 9<br />化如果长度 > 9 和 < = 19<br />xsd: string 如果长度 > 19|Int32<br />long<br />字符串|-|  
|X （字节）|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
|字符串|RFC_STRING|xsd:string|字符串|-|  
|XSTRING|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
  
 * 表示启用安全键入，以不同方式显示的数据类型。  
  
### <a name="safe-typing-enabled"></a>启用安全键入  
 下表显示启用了安全键入时，将以不同方式显示的 ABAP 数据类型 ( **EnableSafeTyping**绑定属性为 true)。  
  
|ABAP 数据类型|RFC 类型|XSD 类型|.NET 类型|格式字符串|  
|--------------------|--------------|--------------|---------------|-------------------|  
|D (日期： YYYYMMDD)|RFC_DATE|xsd:string|字符串|SAP 日期格式： YYYYMMDD。<br /><br /> 字符允许用于日期数字，因此值实质上是一个八个字符的字符串|  
|T (时间： HHMMSS)|RFC_TIME|xsd:string|字符串|SAP 时间格式： HHMMSS。<br /><br /> 字符允许用于时间数字，因此值实质上是一个六个字符的字符串|  
|N （数字字符串）|RFC_NUM|xsd:string|字符串|一个 n 字符字符串;其中 n = numc 字段长度。|  
  
 未启用安全键入时，不在此表的 ABAP 数据类型将显示的方式相同。  
  
### <a name="support-for-date-and-time-fields"></a>对日期和时间字段的支持  
 如果没有启用安全键入，作为化; 进行展示 ABAP 日期 (D) 和时间 (T) 类型但是，显示的日期和时间类型的模式方面是不同的。  
  
-   日期模式方面是： `(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)`  
  
     例如，2007 年 7 月 7 日 (2007年-07-07) 表示为：  
  
     `(2007-07-07)T(00:00:00)`中创建已分区表或索引。  
  
-   时间模式方面是： `(0001-01-01)T(\d\d:\d\d:\d\d)(.*)`  
  
     例如，（下午 6:30 和 30 秒） 18:30:30 表示为：  
  
     `(0001-01-01)T(18:30:30)`中创建已分区表或索引。  
  
#### <a name="how-does-the-adapter-represent-minimum-and-maximum-time-values-on-inbound-messages-from-sap"></a>原理适配器表示最小值和最大入站消息的时间值 （来自 SAP) 是什么？  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]时收到来自 SAP 系统的时间值使用以下准则：  
  
-   适配器将视为 0 小时、 0 分钟和 0 秒 000000 (hhmmss) 和 240000 (hhmmss)。  
  
## <a name="supported-database-data-types"></a>受支持的数据库数据类型  
 方式[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]曲面数据库数据类型还取决于是否启用安全键入。 下表显示如何适配器曲面数据库数据类型时未启用安全键入 ( **EnableSafeTyping**绑定属性为 false)。 启用安全键入时，将以不同方式显示的数据类型将标有星号 （*）。  
  
|数据库数据类型|RFC 类型|XSD|.NET 类型|  
|------------------------|--------------|---------|---------------|  
|ACCP （将发布期间） *|RFC_NUM|xsd:int|Int32|  
|CHAR|RFC_CHAR|xsd:string|字符串|  
|CLNT （客户端）|RFC_CHAR|xsd:string|字符串|  
|CURR （货币字段）|RFC_BCD|化**注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]舍入基于十进制参数定义的十进制值。 例如，如果十进制参数可以接受小数点后最多五个数字，如 4.000028 值被舍入为 4.00003。|Decimal|  
|CUKY (Currency Key)|RFC_CHAR|xsd:string|字符串|  
|DAT （日期字段） *|RFC_DATE|xsd:dateTime<br /><br /> 在内部，该适配器反序列化到值**DateTime**对象。 示例然后调用**DateTime.ToUniversalTime**方法将此对象的值转换为 UTC。 最后的日期部分 (**DateTime.Date**) 用于创建发送到 SAP 系统的值。 SAP 系统将此日期值视为本地时间。<br /><br /> 您应将日期值指定为 UTC 以避免转换。 建议使用以下模式:"(\d\d\d\d-\d\d-\d\d) T (00: 00:00)(.*) Z"。|DateTime<br /><br /> 您应将日期值指定为 UTC (DateTime.Kind = DateTimeKind.Utc) 以避免转换。|  
|DEC （量）|RFC_BCD|化**注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]舍入基于十进制参数定义的十进制值。 例如，如果十进制参数可以接受小数点后最多五个数字，如 4.000028 值被舍入为 4.00003。|Decimal|  
|FLTP （浮点）|RFC_FLOAT|xsd:double|双精度|  
|INT1|RFC_INT1|xsd:unsignedbyte|Byte|  
|INT2|RFC_INT2|xsd:short|Int16|  
|INT4|RFC_INT|xsd:int|Int32|  
|LANG （语言密钥）|RFC_CHAR|xsd:string|字符串|  
|LCHR|RFC_STRING|xsd:string|字符串|  
|LRAW (长字节 seq)|RFC_BYTE|xsd:base64binary|Byte[]|  
|NUMC*|RFC_NUM|xsd:int<br />xsd:long<br />xsd:string|Int32 如果长度 < = 9<br />Int64 如果长度 > 9 和 < = 19<br />如果字符串长度 > 19|  
|PREC （准确性）|RFC_INT2|xsd:short|Int16|  
|QUAN （数量）|RFC_BCD|化**注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]舍入基于十进制参数定义的十进制值。 例如，如果十进制参数可以接受小数点后最多五个数字，如 4.000028 值被舍入为 4.00003。|Decimal|  
|RAW （字节序列）|RFC_BYTE|xsd:base64binary|Byte[]|  
|RAWSTRING （可变长度）|RFC_BYTE|xsd:base64binary|Byte[]|  
|字符串 （可变长度）|RFC_STRING|xsd:string|字符串|  
|TIMS （时间字段） *|RFC_TIME|xsd:datetime<br /><br /> 在内部，该适配器反序列化到值**DateTime**对象。 示例然后调用**DateTime.ToUniversalTime**方法将此对象的值转换为 UTC。 最后时间组件 (**DateTime.Time**) 用于创建发送到 SAP 系统的值。 SAP 系统将本地时间视为此时间值。<br /><br /> 您应将时间值指定为 UTC 以避免转换。 建议使用以下模式:"(0001-01-01) T (\d\d:\d\d:\d\d)(.*) Z"。<br /><br /> 例如，如果您的本地时间，上午 9:15 express 为"(001-01-01) T (09: 15:00) Z"|DateTime<br /><br /> 您应将时间值指定为 UTC (DateTime.Kind = DateTimeKind.Utc) 以避免转换。|  
|单位 （Qty 为单位）|RFC_CHAR|xsd:string|字符串|  
|[不受支持]|--|--|字符串|  
  
 * 指示，适配器呈现的数据类型以不同方式启用安全键入。  
  
### <a name="safe-typing-enabled"></a>启用安全键入  
 下表显示的数据库启用了安全键入时，将以不同方式显示的数据类型 ( **EnableSafeTyping**绑定属性为 true)。  
  
|数据库数据类型|RFC 类型|XSD|.NET 类型|字符串值格式|  
|------------------------|--------------|---------|---------------|-------------------------|  
|ACCP （过帐期间）|RFC_NUM|xsd:string|字符串|字符串|  
|NUMC|RFC_NUM|xsd:string|字符串|字符串|  
|DAT （日期字段）|RFC_DATE|xsd:string|字符串|YYYYMMDD|  
|TIMS （时间字段）|RFC_TIME|xsd:string|字符串|HHMMSS|  
  
 未启用安全键入时，不在此表中的数据类型将显示在相同的方式。  
  
## <a name="supported-xsd-facets"></a>支持的 XSD 方面  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下 XSD 方面。  
  
|RFC 类型|XSD 方面 (**EnableSafeTyping** = false)|XSD 方面 (**EnableSafeTyping** = true)|  
|--------------|-------------------------------------------------|------------------------------------------------|  
|RFC_BCD|**XSD 模式方面**<br /><br /> **小数位数为零：** `"([\\-]{0,1})(([0-9]{1,"`  `+ digitsBeforeDecimal +`  `"}))"`<br /><br /> **一个或多个小数位数：** `"([\\-]{0,1})(([0-9]{0,"` + `digitsBeforeDecimal +``"}\\.[0-9]{0,"``+ digitsAfterDecimal +``"})&#124;([0-9]{1,"``+ digitsBeforeDecimal +``"}))"`|相同|  
|RFC_NUM|**XSD totalDigits 方面**如果长度 < = 19<br /><br /> **XSD 模式方面**如果长度 > 19|**XSD maxLength 方面 （取决于 SAP 的值的长度）**|  
|RFC_DATE|**XSD 模式方面**<br /><br /> `"(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)"`<br /><br /> 模式包含时间 00:00:00 才能与兼容 `xsd:datetime`|**XSD maxLength 方面 = 8**|  
|RFC_TIME|**XSD 模式方面**<br /><br /> `"(0001-01-01)T(\d\d:\d\d:\d\d)(.*)"`<br /><br /> 模式包含日期 0001-01-01 才能与兼容 `xsd:datetime`|**XSD maxLength 方面 = 6**|  
|RFC_CHAR|**XSD maxLength 方面**|相同|  
  
## <a name="unsupported-data-types"></a>不支持的数据类型  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持以下数据类型：  
  
-   ITAB II （分层） 的表类型  
  
