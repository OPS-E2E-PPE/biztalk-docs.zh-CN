---
title: "SAP 适配器中的 SAPCommand 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPCommand, supported methods, classes, and constructors
ms.assetid: 55ad334e-1cc3-47c1-8764-be0f4e93f8b5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee083ed5afea06a5d350e9d73a9103adf157d8b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapcommand-class-in-the-sap-adapter"></a>SAP 适配器中 SAPCommand 类
此命令表示 SQL 查询，以便在 SAP 后端上执行。 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]当前支持 SELECT 和 EXEC 语句。 SELECT 语句启用提取的数据从单个 SAP 表，以及 EXEC 语句使用户能够在 SAP 服务器上执行 Rfc。  
  
 该项派生自**System.Data.Common.DbCommand**。  
  
## <a name="supported-properties"></a>受支持的属性  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**CommandText**|获取和设置|支持 SELECT 和 EXEC 语句。 SELECT 语句的详细信息，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。 有关 EXEC 语句的详细信息，请参阅[中 SAP 的 EXEC 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)。|  
|**CommandTimeout**|获取和设置|不提供支持。|  
|**CommandType**|获取和设置|支持 CommandType.Text。|  
|**连接**|获取和设置|基础的 SAP 连接将在其执行此命令。|  
|**DesignTimeVisible**|获取|不提供支持。 返回 false。|  
|**参数**|获取|用于此命令的参数集合。|  
|**UpdatedRowSource**|-|不提供支持。|  
  
## <a name="supported-methods"></a>支持的方法  
  
|Name|Description|  
|----------|-----------------|  
|**Cancel （)**|检索在批次中的数据时取消的命令。 检索一批后，将发生取消。|  
|**ExecuteNonQuery()**|不会输出任何 DataReader。 但是，值将可通过绑定参数。|  
|**Executereader （)**|作为结果集将输出与所有导出的复杂类型和表参数 DataReader。 此外可以通过绑定参数获取值。|  
|**ExecuteReader(CommandBehavior)**|支持的 CommandBehaviors 是：<br /><br /> 默认<br />-SingleResult<br />-SingleRow<br />-SchemaOnly|  
|**Executescalar （)**|将映射到：<br /><br /> -CommandBehaviour.SingleRow SELECT 语句。<br />-CommandBehaviour.SingleResult EXEC 语句。|  
|**Prepare()**|-EXEC 支持将参数绑定。<br />-选择支持将参数绑定。|  
  
## <a name="supported-constructors"></a>支持的构造函数  
  
|Name|Description|  
|----------|-----------------|  
|**SAPCommand()**|创建 SAPCommand 的新实例。|  
|**SAPCommand(string)**|SAPCommand 具有命令文本。|  
|**SAPCommand (string，SAPConnection)**|该命令将会执行与命令文本和 SAPConnection 对象使用 SAPCommand|  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)