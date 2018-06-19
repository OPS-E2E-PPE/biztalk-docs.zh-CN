---
title: 为 mySAP Business Suite.NET Framework 数据提供程序的限制 |Microsoft 文档
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
ms.openlocfilehash: 5fd4ad3a57e2b762a53582ceb77eb65f23a535fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216469"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a>为 mySAP Business Suite.NET Framework 数据提供程序的限制
以下已知的限制[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持连接到 SAP 系统使用安全网络连接 (SNC)。 有关 SNC 的详细信息，请参阅[SAP 系统和适配器之间的安全性](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)。
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持`DbType`或`Size`属性`SAPParameter`。 相反，当用户指定的值时，才`SAPParameter`，则这内部强制转换为按照.NET 和 SAP 数据类型之间建立映射的.NET 数据类型。  
  
-   SAP 数据类型的字段值允许的最大长度`CURR`， `DEC`，和`QUAN`是 29 位。 虽然 SAP 以本机方式提供这些数据类型值的 31 的位置，但转换到的目标的.NET decimal 数据类型有一定的 29 位数字限制。  
  
-   .NET 数据类型之间的映射限制`Double`和 SAP`FLTP`从 SAP 系统的数据读入的.NET 类型时，数据类型可能会导致溢出错误。 尽管.NET 类型可以表示一个双精度 64 位数字与范围内的值从负 1.79769313486232 e 308 到正 1.79769313486232 e 308，SAP`FLTP`的分析类型[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不能超过 1.8446744073709552E + 19;有效限制`FLTP`类型是负 1.8446744073709552E + 19 写入到正 1.8446744073709552E + 19 的范围。  
  
-   由于出现超时处理基础的客户端库，问题[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持命令和连接超时。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持异步命令的行为。  
  
-   使用 SQL Server Integration Services (SSIS) 项目，使用时[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]无法检索包含与多个 8000 个字符的值的列的数据。 这是由于依据的 SSIS 限制：  
  
    -   不支持大于 4000 个字符在 SSIS 变量的值。  
  
    -   不支持大于 4000 宽字符的值。  
  
    -   不支持大于 8000 单字节字符的值。  
  
## <a name="see-also"></a>另请参阅  
 [有关.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)