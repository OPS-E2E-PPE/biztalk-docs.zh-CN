---
title: 配置属性变量类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, properties
- binding files, properties
- binding files, data types
- adapters, data types
ms.assetid: 703219ce-e275-4a07-a2ad-28010d8363e6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ccb07ff8884b4b874bf1da954a5a0ca22b84c2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356457"
---
# <a name="configuration-property-variable-types"></a>配置属性变量类型
绑定文件的 TransportTypeData\CustomProps 节点中的适配器配置属性遵从 .NET Framework VarEnum 枚举中可用的数据类型。 在下表中列出了相关的数据类型：  
  
|成员名称|Description|ReplTest1|  
|-----------------|-----------------|-----------|  
|VT_EMPTY|指示未指定值。|0|  
|VT_NULL|指示空值（类似于 SQL 中的空值）。|1|  
|VT_I2|指示短整数。|2|  
|VT_I4|指示长整数。|3|  
|VT_R4|指示浮点值。|4|  
|VT_R8|指示双精度值。|5|  
|VT_CY|指示货币值。|6|  
|VT_DATE|指示 DATE 值。|7|  
|VT_BSTR|指示 BSTR 字符串。|8|  
|VT_DISPATCH|指示 IDispatch 指针。|9|  
|VT_ERROR|指示 SCODE。|10|  
|VT_BOOL|指示一个布尔值。|11|  
|VT_VARIANT|指示 VARIANT 指针。|12|  
|VT_UNKNOWN|指示 IUnknown 指针。|13|  
|VT_DECIMAL|指示小数值。|14|  
|VT_I1|指示 char 值。|16|  
|VT_UI1|指示字节。|17|  
|VT_UI2|指示无符号短整数。|18|  
|VT_UI4|指示无符号长整数。|19|  
|VT_I8|指示 64 位整数。|20|  
|VT_UI8|指示 64 位无符号整数。|21|  
|VT_CLSID|指示类 ID。|72|  
|VT_ARRAY|指示 SAFEARRAY 指针。|8192|  
|VT_BYREF|指示值为引用。|16384|