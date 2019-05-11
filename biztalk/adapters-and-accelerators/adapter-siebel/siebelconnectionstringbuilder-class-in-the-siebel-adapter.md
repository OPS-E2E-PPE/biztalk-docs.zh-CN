---
title: Siebel 适配器的 SiebelConnectionStringBuilder 类 |Microsoft Docs
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
ms.openlocfilehash: 8824f61fa591636b2c4b43eceb6b1a3aa9e363e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370840"
---
# <a name="siebelconnectionstringbuilder-class-in-the-siebel-adapter"></a>Siebel 适配器的 SiebelConnectionStringBuilder 类
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供了`DbConnectionStringBuilder`实现以启用 SQL Server Integration Services (SSIS) 和 Visual Studio 资源管理器工具获取的连接属性的环境[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]并将其显示形式的由驱动 GUI属性网格。  
  
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
  
 若要查看的键和值作为的一部分支持`DbConnectionStringBuilder`，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 Siebel 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)