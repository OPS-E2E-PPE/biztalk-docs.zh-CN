---
title: "在 BizTalk 与 Oracle EBS 适配器中的基本 Oracle 数据类型 |Microsoft 文档"
description: "数据和 XSD 类型、 安全类型和 Oracle E-business Suite 中 BizTalk 适配器包 (BAP) 中的验证"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 008bf621-8b4e-450d-b354-ee26b91592f2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9012e2ef6adaf94f55b87bbccfc24b7fb889fbf3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="basic-oracle-data-types"></a>基本 Oracle 数据类型
本主题介绍如何[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]呈现基本 Oracle 数据类型。  
  
## <a name="supported-oracle-data-types"></a>支持的 Oracle 数据类型  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持安全类型的某些 Oracle 数据类型。 启用安全键入后，这些数据类型表示为字符串。 配置通过启用安全键入**EnableSafeTyping**绑定属性 （默认情况下禁用）。 有关详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
> [!NOTE]
>  如果数据类型都是在用户定义类型 (Udt)，则不支持安全键入。  
  
 下表显示如何 Oracle 数据类型中加以表示禁用安全键入 (**EnableSafeTyping**是**false**)。 Oracle 数据类型受**EnableSafeTyping**属性绑定都标有星号 （*）。  
  
|Oracle 数据类型|XSD 类型|.NET 类型|注释|  
|----------------------|--------------|---------------|--------------|  
|BFile|输入： xsd: string<br /><br /> 输出： xsd:base64Binary|字符串<br /><br /> Byte[]|内 （例如 RecordType、 TableType、 UDT 和 VArray） 的复杂类型不支持 BFile 数据类型。|  
|Blob|xsd:base64Binary|Byte[]|-|  
|Char|xsd:string|字符串|-|  
|Clob|xsd:string|字符串|-|  
|日期 *<br /><br /> （不安全键入如果位于内部 UDT）|xsd:dateTime|DateTime|日期值不能包含时区信息 （UTC 还是基于 UTC 偏移量）：<br /><br /> -化值不能包含 UTC 或 UTC 偏移量<br />-   **DateTime.Kind**必须**DateTimeKind.Unspecified**<br /><br /> 如果指定时区信息，则将引发适配器**XmlReaderParsingException**异常，并附带一条消息，指示该字段。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将 Oracle 日期数据类型作为化而不是 xsd:date 公开，因为： <ul><li>Oracle 日期数据类型还可以包含时间值。</li><li>没有任何.NET xsd:date 的等效。</li></ul>|  
|Float * *|化如果 prec < = 7<br /><br /> 化如果 prec > 7 和 < = 15<br /><br /> xsd: string 如果 prec > 15|Float<br /><br /> 双精度<br /><br /> 字符串|必须指定的值与指定的十进制字符和中的组分隔符的格式一致**NumericCharacters**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**NumericCharacters**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。|  
|IntervalDS|xsd:string<br /><br /> 如果位于内部 UDT xsd:duration|字符串<br /><br /> 如果位于内部 UDT 的 Timespan|适配器使用 OracleIntervalDS.ToString 方法以字符串形式返回 IntervalDS 数据。<br /><br /> 值应以 Oracle 本机格式表示： 天 HH:MI:SSxFF (例如，"5 15:30:12.99")。|  
|IntervalYM|xsd:string<br /><br /> 如果位于内部 UDT 化|字符串<br /><br /> 长如果在 UDT|适配器使用 OracleIntervalYM.ToString 方法以字符串形式返回 IntervalYM 数据。<br /><br /> 值应以 Oracle 本机格式表示： 年-月;例如，"1-2"（1 年和 2 个月）。|  
|Long|xsd:string|字符串|从 Oracle 数据库 9i 版开始，已弃用 LONG 数据类型。 Oracle 建议改为使用大型对象 (LOB) 数据类型。 因此，执行操作上将 Oracle 数据库时使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，我们建议使用运行的 Oracle 数据库项目 LOB 数据类型和不是长数据类型。|  
|LongRaw|xsd:base64Binary|Byte[]|-|  
|NChar|xsd:string|字符串|-|  
|NClob|xsd:string|字符串||  
|数 * *|化如果 prec < = 28<br /><br /> xsd: string 如果 prec > 28|Decimal<br />字符串|-|  
|NVarchar2|xsd:string|字符串|-|  
|原始|xsd:base64Binary|Byte[]||  
|RowID|xsd:string|字符串|-|  
|时间戳 *<br /><br /> （不安全键入如果位于内部 UDT）|化如果 prec < = 7<br /><br /> xsd: string 如果 prec > 7|DateTime<br /><br /> 字符串|当公开为字符串 (prec > 7)，则应该在 Oracle NLS_TIMESTAMP_FORMAT 表示值。 你可以指定时间戳中的数据类型的字符串格式**TimeStampFormat**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**TimeStampFormat**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。<br /><br /> 时间戳值不能包含时区信息 （UTC 还是基于 UTC 偏移量）：<br /><br /> -化值不能包含 UTC 或 UTC 偏移量<br />-   **DateTime.Kind**必须**DateTimeKind.Unspecified**<br /><br /> 如果指定时区信息，则将引发适配器**XmlReaderParsingException**异常，并附带一条消息，指示该字段。|  
|TimeStampLTZ|xsd:string|字符串|Udt 内不支持 TimeStampLTZ。<br /><br /> **外部 UDT**： 应在 Oracle NLS_TIMESTAMP_TZ_FORMAT 表示值。 你可以指定用于 TimeStampLTZ 中的数据类型的字符串格式**TimeStampTZFormat**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**TimeStampTZFormat**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。|  
|TimeStampTZ|xsd:string<br /><br /> 如果位于内部 UDT 化|字符串<br /><br /> 如果位于内部 UDT 的 DateTime|**外部 UDT**： 应在 Oracle NLS_TIMESTAMP_TZ_FORMAT 表示值。 你可以指定用于 TimeStampTZ 中的数据类型的字符串格式**TimeStampTZFormat**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**TimeStampTZFormat**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。|  
|小数 * *|化如果 prec < = 28<br /><br /> xsd: string 如果 prec > 28|Decimal<br /><br /> 字符串|-|  
|varchar2|xsd:string|字符串|-|  
|二进制 Float * *|化如果 prec < = 7<br /><br /> xsd: string 如果 prec > 7|Float<br /><br /> 字符串|必须指定的值与指定的十进制字符和中的组分隔符的格式一致**NumericCharacters**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**NumericCharacters**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。|  
|二进制双 * *|化如果 prec < = 15<br /><br /> xsd: string 如果 prec > 15|双精度<br /><br /> 字符串|-|  
|二进制整数 * *|xsd:integer|Int32||  
|Boolean|xsd:boolean|可以为 null 的布尔值||  
|XMLTYPE|xsd:string|字符串|支持顶部级别过程参数。<br /><br /> 保留 XML 字符，如**\<**'，'**\>**必须与相应实体的表示形式替换**(&lt;， &gt;)**开发 BizTalk 中的应用程序时，以及何时使用 WCF 通道模型。 这不是在 WCF 服务模型的情况下必需的。|  
  
 \*在其中这些 Oracle 数据类型中加以表示的方法受**EnableSafeTyping**绑定属性。  
  
 \*\*在这些受的 Oracle 内部数据集和弱类型 REF CURSOR 的数值数据类型中加以表示的方法**EnableSafeTyping**绑定属性。  
  
> [!IMPORTANT]
>  -   在 Oracle 数据类型中的值的最大长度[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]受适用于 Oracle 数据类型的 ODP.NET 支持的值的最大长度。  
> -   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]内部.NET 十进制表示形式将 Udt 内的 Oracle 数值数据类型。 但是，在常规 （这是外部 Udt）、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]内部视为 OracleDecimal Oracle 数值数据类型。  
  
## <a name="safe-typing-enabled"></a>启用安全键入  
 下表显示如何受安全键入 Oracle 数据类型可进行更改时**EnableSafeTyping**绑定属性是**true**。  
  
> [!NOTE]
>  安全键入是启用还是禁用，oracle 数据类型不在此表将显示相同的方式。  
  
|Oracle 数据类型|XSD 类型|.NET 类型|注释|  
|----------------------|--------------|---------------|-------------|  
|日期|xsd:string|字符串|值应用 Oracle NLS_DATE_FORMAT 表示。 你可以指定的格式中的日期数据类型**DateFormat**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**DateFormat**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。|  
|TimeStamp|xsd:string|字符串|值应用 Oracle NLS_TIMESTAMP_FORMAT 表示。 你可以指定时间戳中的数据类型的字符串格式**TimeStampFormat**绑定下的属性**MlsSettings**绑定属性。 如果为不指定任何值**TimeStampFormat**绑定属性，该适配器 MLS 设置个 ODP.NET 客户端使用同一台计算机上是否安装了适配器。|  
  
> [!IMPORTANT]
>  如果启用了安全键入，在数据集和弱类型 REF CURSOR 内的 Oracle 数值数据类型始终显示为字符串。  
  
## <a name="validation"></a>验证  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]对 Oracle 数据类型指定的值执行任何显式验证。 但是，具体取决于 Oracle 数据类型和安全键入是启用还是禁用，可能会执行隐式验证：  
  
-   当反序列化之间 XML 传入消息和内部使用的适配器的.NET 类型。  
  
-   通过 ODP.NET 对于某些数据类型。  
  
## <a name="see-also"></a>另请参阅  
 [用于 Oracle E-Business Suite 的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)