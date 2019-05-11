---
title: 用于 mySAP Business Suite 的.NET Framework 数据提供程序的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ec080a571420eea6177429abb524b8fa11a7df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373251"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a>.NET Framework Data Provider for mySAP Business Suite 的限制
以下已知的限制[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持连接到 SAP 系统使用安全网络连接 (SNC)。 SNC 有关详细信息，请参阅[SAP 系统和适配器之间的安全](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)。
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持`DbType`或`Size`的属性`SAPParameter`。 相反，当用户指定的值`SAPParameter`，值在内部强制转换为根据.NET 和 SAP 数据类型之间已建立的映射的.NET 数据类型。  
  
- 为 SAP 数据类型的字段值允许的最大长度`CURR`， `DEC`，和`QUAN`是 29 位数字。 虽然 SAP 以本机方式提供这些数据类型值的 31 位置，但.NET decimal 数据类型转换为实施 29 位数字限制。  
  
- .NET 数据类型之间的映射限制`Double`和 SAP `FLTP` SAP 系统中的数据读入的.NET 类型时，数据类型可能会导致溢出错误。 尽管.NET 类型可以表示双精度 64 位数字，其值范围从-1.79769313486232e308 到正 1.79769313486232 e 308，SAP`FLTP`类型分析[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不能超过 1.8446744073709552E + 19;有效的限制`FLTP`类型是负 1.8446744073709552E + 正 1.8446744073709552E + 19 到 19 的范围。  
  
- 由于基础客户端库，超时处理问题[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持命令，并连接超时。  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持异步命令的行为。  
  
- 当使用 SQL Server Integration Services (SSIS) 项目，使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]无法检索包含超过 8000 个字符的值的列的数据。 这是因为依据的 SSIS 限制：  
  
  -   不支持大于 4000 个字符中的 SSIS 变量的值。  
  
  -   不支持大于 4000 个宽字符的值。  
  
  -   不支持大于 8000 的单字节字符的值。  
  
## <a name="see-also"></a>请参阅  
 [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)