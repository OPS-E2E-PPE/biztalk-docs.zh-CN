---
title: "Siebel 适配器中的 DbDataReader 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, DbDataReader
- DbDataReader
ms.assetid: 7673cd10-ec1e-4cb0-93c2-f11928d00ca2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00fc3329cbe4dc75a4eccd5b71ded45ad6ebfe63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dbdatareader-class-in-the-siebel-adapter"></a>Siebel 适配器中 DbDataReader 类
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供`DbDataReader`利用 XML 数据读取器。 这使 Siebel 数据源的使用者能够读取的行的只进流。  
  
## <a name="supported-properties"></a>受支持的属性  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持以下`DbDataReader`属性。  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**HasRows**|获取|此属性不受支持，并将引发异常，如果访问。|  
|**关闭**|获取|获取一个值，该值指示是否`DbDataReader`已关闭。|  
|**RecordsAffected**|获取|获取一个值，该值指示是否`DbDataReader`包含一个或多个行。|  
|**Item(Int32)**|获取|获取对象的实例的指定列的值。 使用调用此索引器时所需的列序号。|  
|**Item(String)**|获取|获取对象的实例的指定列的值。 调用此索引器时，请使用所需列的名称。|  
  
## <a name="supported-methods"></a>支持的方法  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持以下`DbDataReader`方法。  
  
|Name|Description|  
|----------|-----------------|  
|**GetSchemaTable**|返回描述 `DbDataReader` 的列元数据的 `DataTable`。 支持的架构列特性[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]是：<br /><br /> -ColumnName<br />-ColumnOrdinal<br />.NET 数据类型<br />长度<br />精度 （如果可用）<br />-缩放 （如果可用）<br />-AllowDBNull<br />-LocalName<br />-扩展 LocalName<br />-Namespace|  
|**GetString**|获取作为 `String` 实例的指定列的值。|  
|**GetValue**|获取作为 `String` 实例的指定列的值。|  
|**isDbNull**|获取一个值，该值指示列是否包含不存在或丢失的值。|  
|**NextResult**|Siebel 数据提供程序始终返回单个结果集;因此此调用完全耗尽当前结果集在返回之前**false**。|  
|**读取**|将读取器前进到结果集中的下一个结果。  它将返回**true**如果成功，和**false**如果读取器左具有更多的记录。|  
|**关闭**|关闭`DbDataReader`对象。 **注意：**完成后使用`DbDataReader`对象，您必须关闭它，以便释放 Siebel COM 库对象。 否则，客户端应用程序的内存和句柄的使用情况将转到上。|  
  
## <a name="see-also"></a>另请参阅  
 [扩展 Siebel 适配器 ADO.NET 接口](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)