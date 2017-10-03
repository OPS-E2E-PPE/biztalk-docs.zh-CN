---
title: "Siebel 适配器中的 SiebelConnection 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fc99c2e3f019f2ddf88647b0faeb7e41644fd0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a>Siebel 适配器中 SiebelConnection 类
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]访问基础[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`、 `ConnectionFactory`，和`Channel`以连接到 Siebel 系统。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]实现`DbConnection`类，以支持上述功能。  
  
 使用的实例`Microsoft.Data.SiebelClient.SiebelClientFactory`，客户端程序可以获取的实例`System.Data.Common.DbConnection`类连接到 Siebel 系统。  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  
  
 或者，可以使用以下方法创建的连接：  
  
```  
  
SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  
  
 `SiebelConnection`类继承自`DbConnection`。 命名空间中存在`Microsoft.Data.SiebelClient`。  
  
## <a name="supported-properties"></a>受支持的属性  
 `SiebelConnection`类支持以下`DbConnection`属性。  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|获取和设置|获取或设置用于打开连接的字符串。|  
|**数据库**|获取|获取当前数据库后打开某个连接的名称或打开连接之前，连接字符串中指定的数据库名称。 这应该是 Siebel 存储库的名称。|  
|**DataSource**|获取|获取此连接 Siebel 网关的名称。|  
|**ServerVersion**|获取|中的当前版本[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，此属性返回硬编码值，该值不表示 Siebel 服务器的实际版本。|  
|**State**|获取|获取说明连接状态的字符串。 此文件可以包含三个可能值： 打开、 中断或已关闭。|  
  
## <a name="supported-methods"></a>支持的方法  
 `SiebelConnection`类支持以下`DbConnection`方法。  
  
|Name|Description|  
|----------|-----------------|  
|**CreateDbCommand**|此受保护的方法提供的新 DbCommand 实例。|  
|**ChangeDatabase**|此公共方法不受支持，并将引发异常，如果调用。|  
|**打开**|通过创建 WCF 通道 Siebel 系统与打开的连接。|  
|**关闭**|通过关闭 WCF 通道来关闭与 Siebel 系统的连接。|  
|**CreateCommand**|创建命令对象。|  
  
## <a name="see-also"></a>另请参阅  
 [扩展 Siebel 适配器 ADO.NET 接口](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)