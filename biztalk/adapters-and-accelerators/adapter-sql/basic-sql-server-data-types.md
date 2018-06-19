---
title: 基本的 SQL Server 数据类型 |Microsoft 文档
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
ms.openlocfilehash: a8e60816dc362fc4630e263397048bcdee8d774b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222613"
---
# <a name="basic-sql-server-data-types"></a>基本的 SQL Server 数据类型
本主题介绍如何[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]呈现基本 SQL Server 数据类型。  
  
## <a name="supported-sql-server-data-types"></a>支持的 SQL Server 数据类型  
 下表显示如何将 SQL Server 数据类型显示通过[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
|SQL Server 数据类型|XSD 类型|.NET 类型|注释|  
|--------------------------|--------------|---------------|--------------|  
|Bigint|Long|Long|-|  
|二进制|Base64Binary|Byte[]|-|  
|bit|Boolean|Bool|-|  
|Char|字符串|字符串|-|  
|日期|DateTime|DateTime|-|  
|日期时间|DateTime|DateTime|时将数据写入到 Datetime 字段，该适配器始终按 gmt 格式存储的时间。 如果指定的时区信息，该适配器将使用该值来将值转换为有效的格林威治标准时间值，并将其写入数据库表。 例如，12/31/2008T23:59:59 + 5:30 写入到为 12/31/2008年表 6:29:59 PM。<br /><br /> 但是，如果未指定的时区信息，适配器将会考虑要连接，请为格林威治标准时间的值，并将写入表的相同的值。 例如，12/31/2008T23:59:59 写入到为 12/31/2008年表 11:59:59 PM。|  
|Datetime2|DateTime|DateTime|-|  
|Datetimeoffset|DateTime|DateTime|-|  
|Decimal|化如果精度 < = 28<br /><br /> xsd: string 如果精度 > 28|如果精度十进制 < = 28<br /><br /> 如果精度字符串 > 28|-|  
|Filestream|Base64Binary|Byte[]|-|  
|Float|双精度|双精度|-|  
|Geography|字符串|字符串|-|  
|Geometry|字符串|字符串|-|  
|Hierarchyid|字符串|字符串|-|  
|图像|Base64Binary|Byte[]|-|  
|int|int|int|-|  
|Money|Decimal|Decimal|-|  
|Nchar|字符串|字符串|-|  
|Ntext|字符串|字符串|-|  
|数字|Decimal|Decimal|-|  
|nvarchar|字符串|字符串|-|  
|Nvarchar (max)|字符串|字符串|-|  
|Real|Float|Float|-|  
|Smalldatetime|DateTime|DateTime|-|  
|Smallint|Short|Short|-|  
|Smallmoney|Decimal|Decimal|-|  
|SQLVariant|字符串|字符串|-|  
|Text|字符串|字符串|-|  
|Time|Duration|时间跨度|-|  
|时间戳|Base64Binary|Byte[]|-|  
|Tinyint|UnsignedByte|Byte|-|  
|Uniqueidentifier|{http://schemas.microsoft.com/2003/10/Serialization/}: guid|Guid|-|  
|Varbinary|Base64Binary|Byte[]|-|  
|Varbinary （max)|Base64Binary|Byte[]|-|  
|Varchar|字符串|字符串|-|  
|Varchar （max)|字符串|String|-|  
|XML|String|字符串|-|  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 SQL Server 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)