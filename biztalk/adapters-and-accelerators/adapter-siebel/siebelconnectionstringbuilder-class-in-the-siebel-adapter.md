---
title: Siebel 适配器中的 SiebelConnectionStringBuilder 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelConnectionStringBuilder, supported properties and methods
- Data Provider for Siebel, SiebelConnectionStringBuilder
- SiebelConnectionStringBuilder
ms.assetid: 4995fce8-7e62-4af9-a731-47b16438067c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 088748c63983e76e64d32f54b3e999fadd88d23a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222005"
---
# <a name="siebelconnectionstringbuilder-class-in-the-siebel-adapter"></a>Siebel 适配器中 SiebelConnectionStringBuilder 类
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供`DbConnectionStringBuilder`实现以启用 SQL Server Integration Services (SSIS) 和 Visual Studio 资源管理器工具环境中，以获取的连接属性[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]并将其显示形式的 GUI 由驱动属性网格。  
  
 若要创建 SiebelConnectionStringBuilder，请使用以下方法：  
  
```  
  
//In this example, factory is an instance of SiebelClientFactory  
SiebelConnectionStringBuilder bldr = (SiebelConnectionStringBuilder)factory.CreateConnectionStringBuilder();  
bldr.ConnectionString = connstr;  
```  
  
 或者，只需：  
  
```  
  
SiebelConnectionStringBuilder bldr = new SiebelConnectionStringBuilder();  
```  
  
 若要查看的键和值的一部分支持`DbConnectionStringBuilder`，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 Siebel 适配器 ADO.NET 接口](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)