---
title: "SAP 适配器中的 SAPConnection 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPConnection, supported methods, classes, and constructors
ms.assetid: a700602d-8135-4f67-a38b-770357d4e28b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b27bb8f88686fe1726aed16113ce227347151996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapconnection-class-in-the-sap-adapter"></a>SAP 适配器中 SAPConnection 类
以下部分列出的方法和属性**SAPConnection**类。 这表示与 SAP 应用程序服务器的 ADO.NET 连接。  
  
 该项派生自**System.Data.Common.DbConnection**。  
  
## <a name="supported-properties"></a>受支持的属性  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|获取和设置|请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。|  
|**ConnectionTimeout**|获取|不提供支持。 返回 0。|  
|**数据库**|获取|SAP 系统 id。|  
|**DataSource**|获取|这将返回的 SAP 应用程序服务器主机的名称。|  
|**ServerVersion**|获取|这将显示 SAP 实例而不是 SAP 服务器版的发行版号。 例如，如果使用实例发行版号 620 情况下，ADO.NET 客户端连接到 SAP 服务器版本 4.6，则此属性将显示 620。|  
|**State**|获取|连接状态。 支持的状态包括：<br /><br /> -[System.Data.ConnectionState]<br /><br /> 关闭<br /><br /> -打开<br /><br /> -连接|  
  
## <a name="supported-methods"></a>支持的方法  
  
|Name|Description|  
|----------|-----------------|  
|**ChangeDatabase(string)**|不提供支持。|  
|**Close （)**|关闭到 SAP 系统的连接。|  
|**CreateCommand()**|返回与此连接关联新 SAPCommand。|  
|**GetSchema()**|获取发现 SAP 表的列表。 所有发现在 XML 文件 SAPDiscoveredObjects.xml 表才可用。 该文件位于\<安装驱动器 >: \program Files\Microsoft Shared\Adapters\SAP。|  
|**GetSchema(string)**|获取基于集合名称的架构。 支持集合名称"Tables"。|  
  
|Name|Description|  
|----------|-----------------|  
|**GetSchema （string，string[])**|获取根据集合名称和限制的架构。 下表表示的集合名称和支持的限制：|  
  
|Name|集合名称|限制|Description|  
|----------|---------------------|------------------|-----------------|  
|**GetSchema （string，string[])**|表|-|发现 SAP 表的列表|  
|**GetSchema （string，string[])**|过程|-|发现 Rfc 的列表|  
|**GetSchema （string，string[])**|SearchRFCs|arr [0]: 搜索 expr|匹配 Rfc 的列表|  
|**GetSchema （string，string[])**|ImportParameters|arr [1]: RFC 名称|导入 RFC 的参数|  
|**GetSchema （string，string[])**|ImportParameterColumn|arr [1]: RFC 名称<br /><br /> arr [2]: name|导入参数架构|  
|**GetSchema （string，string[])**|ExportParameters|arr [1]: RFC 名称|导出 RFC 的参数|  
|**GetSchema （string，string[])**|ExportParameterColumn|arr [1]: RFC 名称<br /><br /> arr [2]: name|导出参数架构|  
|**GetSchema （string，string[])**|TableParameters|arr [1]: RFC 名称|RFC 的表参数|  
|**GetSchema （string，string[])**|TableParameterColumn|arr [1]: RFC 名称<br /><br /> arr [2]: name|表参数架构|  
|**GetSchema （string，string[])**|ChangingParameters|arr [1]: RFC 名称|更改 RFC 的参数|  
|**GetSchema （string，string[])**|ChangingParameterColumn|arr [1]: RFC 名称<br /><br /> arr [2]: name|更改参数架构|  
|**GetSchema （string，string[])**|列|arr [1]: 表名|SAP 表列架构|  
  
|Name|Description|  
|----------|-----------------|  
|**Open （)**|将打开基于连接字符串的 SAP 连接。|  
  
> [!NOTE]
>  表、 过程以及 SearchRFCs 收集条目除外的所有其他集合条目必须指定 arr [0] dummy 值。  
  
## <a name="supported-constructors"></a>支持的构造函数  
  
|Name|Description|  
|----------|-----------------|  
|**SAPConnection()**|创建 SAPConnection 对象实例。|  
|**SAPConnection(string)**|接受一个 SAP 连接字符串。 如果连接字符串无效，则引发异常。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)