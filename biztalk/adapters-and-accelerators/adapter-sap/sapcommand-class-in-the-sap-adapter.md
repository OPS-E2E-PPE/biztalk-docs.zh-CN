---
title: SAP 适配器 SAPCommand 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPCommand, supported methods, classes, and constructors
ms.assetid: 55ad334e-1cc3-47c1-8764-be0f4e93f8b5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f822f7e0cc54385cfc53a99a0a3843d1df241718
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372976"
---
# <a name="sapcommand-class-in-the-sap-adapter"></a>SAP 适配器 SAPCommand 类
此命令表示 SAP 后端上执行的 SQL 查询。 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]目前支持 SELECT 和 EXEC 语句。 SELECT 语句启用单个 SAP 表，从数据中的提取和 EXEC 语句使用户能够在 SAP 服务器上执行 Rfc。  
  
 这派生自**System.Data.Common.DbCommand**。  
  
## <a name="supported-properties"></a>支持的属性  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**CommandText**|获取和设置|支持 SELECT 和 EXEC 语句。 有关 SELECT 语句的详细信息，请参阅[为在 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。 有关在 EXEC 语句的详细信息，请参阅[EXEC 语句在 SAP 中的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)。|  
|**CommandTimeout**|获取和设置|不提供支持。|  
|**CommandType**|获取和设置|支持 CommandType.Text。|  
|**“连接”**|获取和设置|基础 SAP 连接将在其执行此命令。|  
|**DesignTimeVisible**|获取|不提供支持。 返回 false。|  
|**Parameters**|获取|用于此命令的参数集合。|  
|**UpdatedRowSource**|-|不提供支持。|  
  
## <a name="supported-methods"></a>受支持的方法  
  
|“属性”|Description|  
|----------|-----------------|  
|**Cancel()**|取消检索数据时的命令。 检索一批后，将发生取消。|  
|**ExecuteNonQuery()**|不会输出任何 DataReader。 但是，值才可通过绑定参数。|  
|**ExecuteReader()**|输出为结果集的所有导出的复杂类型和表参数 DataReader。 此外可以通过绑定参数获取这些值。|  
|**ExecuteReader(CommandBehavior)**|支持的 CommandBehaviors 是：<br /><br /> -Default<br />-   SingleResult<br />-   SingleRow<br />-   SchemaOnly|  
|**ExecuteScalar()**|将映射到：<br /><br /> -CommandBehaviour.SingleRow SELECT 语句。<br />-CommandBehaviour.SingleResult EXEC 语句。|  
|**Prepare()**|-EXEC 支持绑定参数。<br />-选择支持绑定参数。|  
  
## <a name="supported-constructors"></a>受支持的构造函数  
  
|“属性”|Description|  
|----------|-----------------|  
|**SAPCommand()**|创建 SAPCommand 的新实例。|  
|**SAPCommand(string)**|使用命令文本 SAPCommand。|  
|**SAPCommand(string, SAPConnection)**|将执行该命令具有命令的文本和 SAPConnection 对象使用 SAPCommand|  
  
## <a name="see-also"></a>请参阅  
 [扩展 ADO.NET 接口，与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)