---
title: "轮询 Operations2 的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- POLLINGSTMT operation, message actions for
- POLLINGSTMT operation, message structure for
ms.assetid: b82edcc2-9437-4c7b-ba2b-7b966fff3f15
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb28e7b769c16f1798023adb8b30c3e636a3407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-polling-operations"></a>轮询操作的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]面，具体取决于对 Oracle 数据库的目标对象的轮询与相关的各种入站的操作。 若要轮询表和视图，单个 POLLINGSTMT 操作显示而每个存储过程、 函数和打包的过程和函数都公开为进行轮询的入站操作。  
  
 你可以指定**PollingId**连接来限定 POLLINGSTMT 操作的命名空间的 URI 查询字符串中的参数。 设置此参数仅限定 POLLINGSTMT 操作中; 的命名空间它不会更改的消息操作。 有关 Oracle 数据库适配器连接 URI 的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
 通过设置绑定属性配置的轮询操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关这些绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 你设置**PollingStatement**绑定属性指定 SQL 语句、 存储的过程、 函数或轮询查询的包内的一个过程。 此查询的结果集都会返回作为数据轮询操作中的代码。  
  
## <a name="message-structure-for-the-polling-operations"></a>轮询操作的消息结构  
 下表显示各种轮询操作的 XML 消息结构。  
  
|运算|目标对象|XML 消息|Description|  
|---------------|-------------------|-----------------|-----------------|  
|POLLINGSTMT|-表<br /><br /> -视图|`<?xml version="1.0" encoding="utf-8" ?>  <POLLINGSTMT xmlns="[VERSION]/POLLINGSTMT[POLLING_ID]">   <POLLINGSTMTRECORD>     <POLLINGSTMTRECORD>       <FIELD1_NAME>val1</FIELD1_NAME>        <FIELD2_NAME>val2</FIELD2_NAME>       …     </POLLINGSTMTRECORD>      …    </POLLINGSTMTRECORD> </POLLINGSTMT>`|该适配器显示为 SQL SELECT 查询由元数据，确定的结果集包含在 POLLINGSTMTRECORD 类型的结构。<br /><br /> 由连接 URI 中的 PollingId 参数确定 POLLINGSTMT 操作的命名空间。|  
|[CustomPollingOperation]|-存储过程<br /><br /> 函数<br /><br /> -包|**存储过程**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[SCHEMA]/PollingProcedure">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **函数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingFunction">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **包**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingPackage/[PACKAGE_NAME]/">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`|轮询操作中的结果集的结构取决于目标对象中的元素的数据类型。|  
  
 [Version] = http://Microsoft.LobServices.OracleDB/2007/03。  
  
 [CustomPollingOperation] = 它等同于存储的过程、 函数或打包的过程或函数名称作为入站的轮询操作公开。  
  
 [架构] = Oracle 架构的名称。 例如，SCOTT。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)