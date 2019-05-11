---
title: Siebel 适配器的 SiebelCommand 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e35ecc56dd95fdd413827bc7744c1a02745eaa87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370582"
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a>Siebel 适配器的 SiebelCommand 类
建立与 Siebel 系统的连接后[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]分析 Siebel 命令字符串和提供的 ADO.NET 客户端的命令参数，并将该命令映射到 WCF 请求消息。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]然后发送到请求[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]并获取响应 XML 以及来自适配器的正文内容。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]然后使用`XMLDataReader`从 XML 正文中检索的关系数据。  
  
 使用的实例`Microsoft.Data.SiebelClient.SiebelClientFactory`，客户端程序可以获取的实例`System.Data.Common.DbCommand`类来构造 Siebel 命令。  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 或者，可以使用以下方法创建命令：  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 `SiebelCommand`类继承自`DbCommand`。  命名空间中存在`Microsoft.Data.SiebelClient`。  
  
## <a name="supported-properties"></a>支持的属性  
 **SiebelCommand**类支持以下`DbCommand`*保护*属性：  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**DbConnection**|获取和设置|此文件应包含基础`DbConnection`从中实例`DbCommand`获取实例。|  
|**DbParameterCollection**|获取|获取集合的`DbParameter`对象。|  
  
 `SiebelCommand` 此外支持以下`DbCommand`*公共*属性：  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**CommandText**|获取和设置|此文件包含 ADO.NET 客户端想要执行的 SQL 语句。|  
|**CommandType**|获取和设置|仅`CommandType.Text`支持。|  
|**“连接”**|获取和设置|这将使用`DbConnection`成员。|  
|**Parameters**|获取|这将使用`DbParameterCollection`成员。|  
  
> [!IMPORTANT]
>  `SiebelCommand`类将忽略`CommandTimeout`， `DesignTimeVisible`，和`DbTransaction`属性。  
  
## <a name="supported-methods"></a>受支持的方法  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持以下`DbCommand`*保护*方法：  
  
|“属性”|Description|  
|----------|-----------------|  
|**CreateDbParameter**|创建一个新`DbParameter`实例。|  
|**ExecuteDbDataReader**|这将运行的 SELECT 和 EXEC 命令并返回`DbDataReader`。|  
  
 `SiebelCommand` 此外支持以下`DbCommand`*公共*方法：  
  
|“属性”|Description|  
|----------|-----------------|  
|**CreateParameter**|创建一个新`DbParameter`实例通过 `CreateDbParameter().`|  
|**ExecuteReader**|执行`CommandText`针对`Connection`，并返回`DbDataReader`通过`ExecuteDbDataReader()`。|  
|**准备**|这将解析`CommandText`和生成的 SQL 命令分析树。|  
  
## <a name="see-also"></a>请参阅  
 [使用 Siebel 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)