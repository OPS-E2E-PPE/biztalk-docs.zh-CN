---
title: 自定义 Rfc 的数据类型映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d6934847a5c5a9482a9c4f1dc8026c50aec6295
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373547"
---
# <a name="data-type-mapping-for-custom-rfcs"></a>自定义 Rfc 的数据类型映射
下表提供了有关 SAP 数据类型和它们如何映射到.NET 数据类型为 Z_EXTRACT_DATA_OO RFC 的信息。 使用此自定义 RFC [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
> [!NOTE]
>  为 Z_EXECUTE_SAP_QUERY，使用这种[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]要执行 EXECQUERY 命令，所有 SAP 数据类型都转换为.NET 字符串类型。  
  
|SAP 数据类型|.NET 数据类型|  
|-------------------|--------------------|  
|ACCP|-   Int32<br />-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|CHAR|String|  
|CLNT|String|  
|CUKY|String|  
|当前|如果精度应小于或等于 28，十进制<br /><br /> 字符串，如果精度大于 28|  
|DATS|-   DateTime<br />-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|DEC|Decimal|  
|FLTP|双精度|  
|INT1|Byte|  
|INT2|Int16|  
|INT4|Int32|  
|LANG|String|  
|NUMC|-Int32，如果字段长度小于或等于为 9<br />-Int64，如果字段长度大于 9 且小于或等于 19<br />-如果字符串大于 19<br />-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|PREC|Int16|  
|QUAN|Decimal|  
|RAW|Byte]|  
|RSTR|Byte]|  
|SSTR|String|  
|STRG|String|  
|TIMS|-   TimeSpan<br />-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。|  
|UNIT|String|  
|LCHR|String|  
|LRAW|Byte]|  
  
## <a name="see-also"></a>请参阅  
 [消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)