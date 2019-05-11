---
title: 基本 SQL Server 数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f744fe14-4134-486d-b060-9ac2d5f21c56
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083e3ff9887a991fe6d2d7a726cdb439abc50d5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370038"
---
# <a name="basic-sql-server-data-types"></a>基本 SQL Server 数据类型
本主题介绍如何将[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]显示基本的 SQL Server 数据类型。  
  
## <a name="supported-sql-server-data-types"></a>支持的 SQL Server 数据类型  
 下表显示了如何将 SQL Server 数据类型发现通过[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
|SQL Server 数据类型|XSD 类型|.NET 类型|注释|  
|--------------------------|--------------|---------------|--------------|  
|Bigint|Long|Long|-|  
|Binary|Base64Binary|Byte[]|-|  
|bit|Boolean|Bool|-|  
|Char|String|String|-|  
|Date|DateTime|DateTime|-|  
|DATETIME|DateTime|DateTime|日期时间字段中写入数据，时适配器始终格林威治标准时间中存储的时间。 如果指定的时区信息时，适配器使用的值转换为格林威治标准时间的有效值，并将其写入到数据库表。 例如，12/31/2008T23:59:59 + 5:30 写入到表作为 2008 年 12 月 31 日下午 6:29:59。<br /><br /> 但是，如果未指定的时区信息，适配器将数值，为格林威治标准时间，并将相同的值写入到表。 例如，12 月 31 日 2008T23:59:59 写入到表作为 12/31/2008年/11:59:59 PM。|  
|Datetime2|DateTime|DateTime|-|  
|Datetimeoffset|DateTime|DateTime|-|  
|Decimal|化如果精度 < = 28<br /><br /> xsd: string 如果精度 > 28|如果精度的十进制 < = 28<br /><br /> 字符串如果精度 > 28|-|  
|文件流|Base64Binary|Byte[]|-|  
|float|双精度|双精度|-|  
|Geography|String|String|-|  
|Geometry|String|String|-|  
|hierarchyid|String|String|-|  
|Image|Base64Binary|Byte[]|-|  
|smallint|smallint|smallint|-|  
|资金|Decimal|Decimal|-|  
|Nchar|String|String|-|  
|Ntext|String|String|-|  
|Numeric|Decimal|Decimal|-|  
|nvarchar|String|String|-|  
|Nvarchar(Max)|String|String|-|  
|Real|float|float|-|  
|Smalldatetime|DateTime|DateTime|-|  
|Smallint|Short|Short|-|  
|Smallmoney|Decimal|Decimal|-|  
|SQLVariant|String|String|-|  
|Text|String|String|-|  
|Time|Duration|时间跨度|-|  
|时间戳|Base64Binary|Byte[]|-|  
|Tinyint|UnsignedByte|Byte|-|  
|Uniqueidentifier|{ http://schemas.microsoft.com/2003/10/Serialization/}:guid|Guid|-|  
|Varbinary|Base64Binary|Byte[]|-|  
|Varbinary(Max)|Base64Binary|Byte[]|-|  
|Varchar|String|String|-|  
|Varchar （max)|String|String|-|  
|XML|String|String|-|  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)