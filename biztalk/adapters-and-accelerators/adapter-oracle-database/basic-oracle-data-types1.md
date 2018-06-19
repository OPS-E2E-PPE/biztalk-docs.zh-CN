---
title: 基本 Oracle 数据类型 1> |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, supported
- data types, unsupported
ms.assetid: 491230b9-b946-4681-a048-5da46102c370
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86349adae1a3ae061cb07c6c770532cf92c74dc8
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25964475"
---
# <a name="basic-oracle-data-types"></a>基本 Oracle 数据类型
本主题介绍如何[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现基本 Oracle 数据类型。  
  
## <a name="supported-oracle-data-types"></a>支持的 Oracle 数据类型  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持安全类型的某些 Oracle 数据类型。 启用安全键入后，这些数据类型表示为字符串。 配置通过设置安全键入**EnableSafeTyping**绑定属性。 默认情况下禁用安全键入。 有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
> [!NOTE]
>  如果数据类型都是在用户定义类型 (Udt)，则不支持安全键入。  
  
 下表显示如何 Oracle 数据类型中加以表示禁用安全键入 (**EnableSafeTyping**为 false)。 Oracle 数据类型受**EnableSafeTyping**属性绑定都标有星号 （*）。  
  
|Oracle 数据类型|XSD 类型|.NET 类型|注释|  
|----------------------|--------------|---------------|--------------|  
|BFile|输入： xsd: string<br />输出： xsd:base64Binary|字符串<br />Byte[]|内 （例如 RecordType、 TableType、 UDT 和 VArray） 的复杂类型不支持 BFile 数据类型。|  
|Blob|xsd:base64Binary|Byte[]|支持表操作和过程。|  
|Char|xsd:string|字符串|支持表操作和过程。|  
|Clob|xsd:string|字符串|支持表操作和过程。|  
|日期 *<br /><br /> （不安全键入如果位于内部 UDT）|xsd:dateTime|DateTime|日期值不能包含时区信息 （UTC 还是基于 UTC 偏移量）：<br /><br /> -化值不能包含 UTC 或 UTC 偏移量<br />-   **DateTime.Kind**必须**DateTimeKind.Unspecified**<br /><br /> 如果指定时区信息，则将引发适配器**XmlReaderParsingException**异常，并附带一条消息，指示该字段。|  
|Float * *|化如果 prec < = 7<br />化如果 prec > 7 和 < = 15<br />xsd: string 如果 prec > 15|Float<br />双精度<br />字符串|-|  
|IntervalYM|xsd:string<br /><br /> 如果位于内部 UDT 化|字符串<br /><br /> 长如果在 UDT|值应以 Oracle 本机格式表示： 年-月;例如，"1-2"（1 年和 2 个月）。|  
|IntervalDS|xsd:string<br /><br /> 如果位于内部 UDT xsd:duration|字符串<br /><br /> 如果位于内部 UDT 的 Timespan|值应以 Oracle 本机格式表示： 天 HH:MI:SSxFF;例如，"5 15:30:12.99"|  
|Long|xsd:string|字符串|支持的所有表操作、 存储的过程和函数。 **注意：** 从 Oracle 数据库 9i 版开始，LONG 数据类型已弃用。 Oracle 建议改为使用 LOB 数据类型。 因此，执行操作上将 Oracle 数据库时使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，我们建议使用运行的 Oracle 数据库项目 LOB 数据类型和不是长数据类型。|  
|LongRaw|xsd:base64Binary|Byte[]|-|  
|NChar|xsd:string|字符串|-|  
|NClob|xsd:string|字符串|支持表操作和过程。|  
|数 * *|化如果 prec < = 28<br />xsd: string 如果 prec > 28|Decimal<br />字符串|-|  
|NVarchar2|xsd:string|字符串|-|  
|原始|xsd:base64Binary|Byte[]|支持表操作和过程。|  
|RowID|xsd:string|字符串|-|  
|TimeStamp*<br /><br /> （不安全键入如果位于内部 UDT）|xsd:dateTime if prec <= 7<br />xsd: string 如果 prec > 7|DateTime<br />字符串|时间戳值不能包含时区信息 （UTC 还是基于 UTC 偏移量）：<br /><br /> -化值不能包含 UTC 或 UTC 偏移量<br />-   **DateTime.Kind**必须**DateTimeKind.Unspecified**<br /><br /> 如果指定时区信息，则将引发适配器**XmlReaderParsingException**异常，并附带一条消息，指示该字段。|  
|TimeStampLTZ|xsd:string|字符串|Udt 内不支持 TimeStampLTZ。<br /><br /> **外部 UDT**： 应在 NLS_TIMESTAMP_TZ_FORMAT 表示值。|  
|TimeStampTZ|xsd:string<br /><br /> 如果位于内部 UDT 化|字符串<br /><br /> 如果位于内部 UDT 的 DateTime|**外部 UDT**： 应在 NLS_TIMESTAMP_TZ_FORMAT 表示值。|  
|Decimal**|化如果 prec < = 28<br />xsd: string 如果 prec > 28|Decimal<br />字符串|-|  
|varchar2|xsd:string|字符串|-|  
|二进制 Float * *|化如果 prec < = 7<br />xsd: string 如果 prec > 7|Float<br />字符串|必须在与你的区域设置一致的表单中指定的值 (**System.Globalization.CultureInfo.CurrentCulture**)。 例如，对于英语区域设置中使用句点字符 ('。) 来指定小数点;对于法语的区域设置，请使用逗号字符 （'，'）。|  
|二进制双 * *|化如果 prec < = 15<br />xsd: string 如果 prec > 15|双精度<br />字符串|-|  
|二进制整数 * *|xsd:integer|Int32|过程、 函数和包的支持。|  
|Boolean|xsd:boolean|可以为 null 的布尔值||  
|XMLTYPE|xsd:string|字符串|支持顶部级别过程参数。<br /><br /> 保留 XML 字符，如**\<**'，'**\>** 必须与相应实体的表示形式替换 **(&lt;， &gt;)** 开发 BizTalk 中的应用程序时，以及何时使用 WCF 通道模型。 这不是在 WCF 服务模型的情况下必需的。|  
  
 \*在其中这些 Oracle 数据类型中加以表示的方法受**EnableSafeTyping**绑定属性。  
  
 \*\*在这些受的 Oracle 内部数据集和弱类型 REF CURSOR 的数值数据类型中加以表示的方法**EnableSafeTyping**绑定属性。  
  
> [!IMPORTANT]
>  -   在 Oracle 数据类型中的值的最大长度[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受适用于 Oracle 数据类型的 ODP.NET 支持的值的最大长度。  
> -   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]内部.NET 十进制表示形式将 Udt 内的 Oracle 数值数据类型。 但是，在常规 （这是外部 Udt）、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]内部视为 OracleDecimal Oracle 数值数据类型。  
  
### <a name="safe-typing-enabled"></a>启用安全键入  
 下表显示如何受安全键入 Oracle 数据类型可进行更改时**EnableSafeTyping**绑定属性为 true。  
  
|Oracle 数据类型|XSD 类型|.NET 类型|注释|  
|----------------------|--------------|---------------|-------------|  
|日期|xsd:string|字符串|值应用 Oracle NLS_DATE_FORMAT 表示。|  
|TimeStamp|xsd:string|字符串|值应用 Oracle NLS_TIMESTAMP_FORMAT 表示。|  
  
> [!IMPORTANT]
>  如果启用了安全键入，在数据集和弱类型 REF CURSOR 内的 Oracle 数值数据类型始终显示为字符串。  
  
 安全键入是启用还是禁用，oracle 数据类型不在此表将显示相同的方式。  
  
### <a name="validation"></a>验证  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]对 Oracle 数据类型指定的值执行任何显式验证。 但是，具体取决于 Oracle 数据类型和安全键入是启用还是禁用，可能会执行隐式验证：  
  
-   当反序列化之间 XML 传入消息和内部使用的适配器的.NET 类型。  
  
-   通过 ODP.NET 对于某些数据类型。  
  
