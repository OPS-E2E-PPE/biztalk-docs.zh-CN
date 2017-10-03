---
title: "数据类型映射自定义的 Rfc |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cac254734a35658e3aa635b086f765e8f06494a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-custom-rfcs"></a>自定义的 Rfc 的数据类型映射
下表提供了有关 SAP 数据类型和它们如何映射到.NET 数据类型为 Z_EXTRACT_DATA_OO RFC 的信息。 使用此自定义的 RFC [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
> [!NOTE]
>  为 Z_EXECUTE_SAP_QUERY，后者由[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]若要执行 EXECQUERY 命令，所有 SAP 数据类型将都转换成.NET 字符串类型。  
  
|SAP 数据类型|.NET 数据类型|  
|-------------------|--------------------|  
|ACCP|-Int32<br />的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|CHAR|字符串|  
|CLNT|字符串|  
|CUKY|字符串|  
|CURR|如果精度应小于或等于 28 的 decimal<br /><br /> 字符串，如果精度大于 28|  
|DAT|-DateTime<br />的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|DEC|Decimal|  
|FLTP|双精度|  
|INT1|Byte|  
|INT2|Int16|  
|INT4|Int32|  
|LANG|字符串|  
|NUMC|-Int32，如果字段长度小于或等于为 9<br />-Int64，如果字段长度大于 9 且小于或等于 19<br />的字符串，如果大于 19<br />的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|PREC|Int16|  
|QUAN|Decimal|  
|RAW|Byte]|  
|RSTR|Byte]|  
|SSTR|字符串|  
|STRG|字符串|  
|TIMS|-TimeSpan<br />的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|单元|字符串|  
|LCHR|字符串|  
|LRAW|Byte]|  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)