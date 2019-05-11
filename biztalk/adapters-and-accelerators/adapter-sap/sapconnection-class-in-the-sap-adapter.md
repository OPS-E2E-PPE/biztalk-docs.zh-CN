---
title: SAP 适配器 SAPConnection 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPConnection, supported methods, classes, and constructors
ms.assetid: a700602d-8135-4f67-a38b-770357d4e28b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14fb1cf2b04fd16aedd8aa97f75f2fa57620e3f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372951"
---
# <a name="sapconnection-class-in-the-sap-adapter"></a>SAP 适配器 SAPConnection 类
以下部分列出的方法和属性**SAPConnection**类。 这表示 ADO.NET 连接到 SAP 应用程序服务器。  
  
 这派生自**System.Data.Common.DbConnection**。  
  
## <a name="supported-properties"></a>支持的属性  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|获取和设置|请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。|  
|**ConnectionTimeout**|获取|不提供支持。 返回 0。|  
|**“数据库”**|获取|SAP 系统 id。|  
|**DataSource**|获取|这将返回 SAP 应用程序服务器主机的名称。|  
|**ServerVersion**|获取|这将显示有关 SAP 实例而不是 SAP 服务器版的发行版号。 例如，如果实例版本编号 620 的情况下，ADO.NET 客户端连接到 SAP 服务器版本 4.6，此属性将显示 620。|  
|**状态**|获取|连接状态。 受支持的状态包括：<br /><br /> - [System.Data.ConnectionState]<br /><br /> -关闭<br /><br /> -打开<br /><br /> -连接|  
  
## <a name="supported-methods"></a>受支持的方法  
  
|“属性”|Description|  
|----------|-----------------|  
|**ChangeDatabase(string)**|不提供支持。|  
|**Close()**|关闭到 SAP 系统的连接。|  
|**CreateCommand()**|返回与此连接关联的新 SAPCommand。|  
|**GetSchema()**|获取已发现 SAP 表的列表。 所有发现的表是在 SAPDiscoveredObjects.xml 的 XML 文件中可用。 该文件位于\<安装驱动器\>: \Program Files\Common Files\Microsoft Shared\Adapters\SAP。|  
|**GetSchema(string)**|获取根据集合名称的架构。 支持集合名称"表"。|  
  
|“属性”|Description|  
|----------|-----------------|  
|**GetSchema(string, string[])**|获取根据集合名称和限制的架构。 下表表示的集合名称和受支持的限制：|  
  
|“属性”|集合名称|限制|Description|  
|----------|---------------------|------------------|-----------------|  
|**GetSchema(string, string[])**|表|-|已发现 SAP 表的列表|  
|**GetSchema(string, string[])**|过程|-|已发现的 Rfc 的列表|  
|**GetSchema(string, string[])**|SearchRFCs|arr[0]:搜索 expr|匹配 Rfc 的列表|  
|**GetSchema(string, string[])**|ImportParameters|arr[1]:RFC 名称|导入 RFC 的参数|  
|**GetSchema(string, string[])**|ImportParameterColumn|arr[1]:RFC 名称<br /><br /> arr[2]:参数名称|导入参数架构|  
|**GetSchema(string, string[])**|ExportParameters|arr[1]:RFC 名称|导出 RFC 的参数|  
|**GetSchema(string, string[])**|ExportParameterColumn|arr[1]:RFC 名称<br /><br /> arr[2]:参数名称|导出参数架构|  
|**GetSchema(string, string[])**|TableParameters|arr[1]:RFC 名称|表参数的 RFC|  
|**GetSchema(string, string[])**|TableParameterColumn|arr[1]:RFC 名称<br /><br /> arr[2]:参数名称|表参数架构|  
|**GetSchema(string, string[])**|ChangingParameters|arr[1]:RFC 名称|更改参数的 RFC|  
|**GetSchema(string, string[])**|ChangingParameterColumn|arr[1]:RFC 名称<br /><br /> arr[2]:参数名称|更改参数架构|  
|**GetSchema(string, string[])**|列|arr[1]:表名|SAP 表列架构|  
  
|“属性”|Description|  
|----------|-----------------|  
|**Open()**|将打开基于连接字符串上的 SAP 连接。|  
  
> [!NOTE]
>  除了表、 过程和 SearchRFCs 集合项，对于所有其他集合项必须指定 arr [0] 的虚拟值。  
  
## <a name="supported-constructors"></a>受支持的构造函数  
  
|“属性”|Description|  
|----------|-----------------|  
|**SAPConnection()**|创建 SAPConnection 对象实例。|  
|**SAPConnection(string)**|接受 SAP 连接字符串。 如果连接字符串无效，将引发异常。|  
  
## <a name="see-also"></a>请参阅  
 [扩展 ADO.NET 接口，与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)