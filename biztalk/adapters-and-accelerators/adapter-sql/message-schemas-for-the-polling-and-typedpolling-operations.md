---
title: "消息架构的轮询和 BizTalk 中的 SQL 适配器的 TypedPolling 操作 |Microsoft 文档"
description: "轮询间隔和 TypedPolling 消息由 SQL 适配器 BizTalk 适配器包 (BAP) 中使用的结构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f18185e4bfaf5502537a68044579b0f7721cd23
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a>轮询和 TypedPolling 操作的消息架构
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]曲面轮询和 TypedPolling 入站操作以返回到适配器客户端的轮询查询的结果集。  
  
 通过设置绑定属性配置的轮询间隔和 TypedPolling 操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关这些绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 你设置**PollingStatement**绑定属性来指定 SQL 语句 (SELECT 或 EXEC\<存储过程 >) 的轮询查询。 用作数据复制到你的代码在轮询操作中，而是 TypedPolling 操作中的强类型数据，则返回此查询的结果集。 该适配器显示为指定查询由元数据，确定的结果集的结构。  
  
## <a name="polling-message-structure"></a>轮询消息结构 
  
**操作**:`Polling`

**XML 消息**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling">
    <PolledData>
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">
        <any>[Value]</any>
        <any>[Value]</any>
        …
        </DataSet>
    </PolledData>
 </Polling>
```

**说明**： 由 SQL Server 发送到适配器客户端的入站的消息。  


## <a name="typedpolling-message-structure"></a>TypedPolling 消息结构 

**操作**:`TypedPolling`

**XML 消息**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

**说明**： 由 SQL Server 发送到适配器客户端的强类型的入站的消息。
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a>用于轮询和 TypedPolling 操作的消息操作  
 消息操作:  
  
-   轮询操作"轮询"。  
  
-   TypedPolling 操作是"TypedPolling。"  
  
