---
title: "Siebel 适配器中的 SiebelClientFactory 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e47b22c1d5a2575b0da3fae432acd79886e2c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a>Siebel 适配器中 SiebelClientFactory 类
ADO.NET 客户端访问[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用泛型的 ADO.NET 类和接口。 若要启用此功能，[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]继承**System.Data.Common.DbProviderFactory**类。 客户端程序使用客户端，如下所示：  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 替代方法是，如下所示：  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 命名空间 Microsoft.Data.SiebelClient 中存在 SiebelClientFactory。  
  
## <a name="supported-members"></a>受支持的成员  
 **SiebelClientFactory**扩展**System.Data.CommonDbProviderFactory**。  下表提供的成员的说明**SiebelClientFactory**重写。  
  
|Name|Description|  
|----------|-----------------|  
|**实例**|这是一个成员变量。  它提供了 SiebelClientFactory 的单一实例。|  
|**CreateCommand()**|创建 SiebelCommand 的实例。|  
|**CreateConnection()**|创建 SiebelConnection 的实例。|  
|**CreateConnectionStringBuilder()**|创建 SiebelConnectionStringBuilder 的实例。|  
|**CreateParameter()**|创建 SiebelParameter 的实例。|  
  
## <a name="see-also"></a>另请参阅  
 [扩展 Siebel 适配器 ADO.NET 接口](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)