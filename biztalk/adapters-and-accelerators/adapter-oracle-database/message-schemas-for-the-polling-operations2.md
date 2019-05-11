---
title: 消息架构的轮询 Operations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POLLINGSTMT operation, message actions for
- POLLINGSTMT operation, message structure for
ms.assetid: b82edcc2-9437-4c7b-ba2b-7b966fff3f15
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bde545d960537d264024d32fbdb053f6b4e2ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376401"
---
# <a name="message-schemas-for-the-polling-operations"></a>轮询操作的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]轮询，具体取决于对 Oracle 数据库的目标对象与相关的各种入站的操作的图面。 若要轮询的表和视图，单个 POLLINGSTMT 操作被发现而每个存储过程、 函数和打包的过程和函数公开为用于轮询的入站操作。  
  
 您可以指定**PollingId**连接要限定 POLLINGSTMT 操作的命名空间 URI 的查询字符串中的参数。 设置此参数仅限定 POLLINGSTMT 操作; 的命名空间它不会更改消息操作。 有关 Oracle 数据库适配器连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
 通过设置绑定属性来配置轮询操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关这些绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 您设置**PollingStatement**绑定属性来指定 SQL 语句、 存储的过程、 函数或轮询查询的包中的过程。 此查询的结果集作为数据返回到轮询操作中的代码。  
  
## <a name="message-structure-for-the-polling-operations"></a>轮询操作的消息结构  
 下表显示了各种轮询操作的 XML 消息结构。  
  
|操作|目标对象|XML 消息|Description|  
|---------------|-------------------|-----------------|-----------------|  
|POLLINGSTMT|-表<br /><br /> 视图|`<?xml version="1.0" encoding="utf-8" ?>  <POLLINGSTMT xmlns="[VERSION]/POLLINGSTMT[POLLING_ID]">   <POLLINGSTMTRECORD>     <POLLINGSTMTRECORD>       <FIELD1_NAME>val1</FIELD1_NAME>        <FIELD2_NAME>val2</FIELD2_NAME>       …     </POLLINGSTMTRECORD>      …    </POLLINGSTMTRECORD> </POLLINGSTMT>`|该适配器显示为 SQL SELECT 查询由元数据，确定结果集包含在 POLLINGSTMTRECORD 类型的结构。<br /><br /> 中的连接 URI 的 PollingId 参数取决于 POLLINGSTMT 操作的命名空间。|  
|[CustomPollingOperation]|-存储过程<br /><br /> -函数<br /><br /> -包|**存储过程**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[SCHEMA]/PollingProcedure">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **函数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingFunction">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **包**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingPackage/[PACKAGE_NAME]/">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`|轮询操作中的结果集的结构取决于目标对象中的元素的数据类型。|  
  
 [Version] = http://Microsoft.LobServices.OracleDB/2007/03。  
  
 [CustomPollingOperation] = 它是与存储的过程、 函数或打包的过程或入站的轮询操作的形式公开的函数名称相同。  
  
 [架构] = Oracle 架构的名称。 例如，SCOTT。  
  
## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)