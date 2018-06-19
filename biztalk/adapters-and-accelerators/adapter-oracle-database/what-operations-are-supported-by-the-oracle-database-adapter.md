---
title: Oracle 数据库适配器支持哪些操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP
- operations, performing
ms.assetid: d78dbeb8-9dab-4a71-982e-f7ada51472e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 014b0fc6158c151d510152550c0093f6ffa9031b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215581"
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a>Oracle 数据库适配器支持何种操作
创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型，适配器客户端可以执行对 Oracle 数据库的操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。 有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Oracle 数据库的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。  
  
 本部分提供有关使用 Oracle 数据库上支持的操作的信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [执行基本的插入、 更新、 删除和 Oracle 表和视图的 Select 操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [对表和视图包含 LOB 数据的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [对函数和 Oracle 数据库中的存储的过程的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [对函数和过程与 Oracle 数据库中的 REF CURSOR 参数的操作](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [对函数和过程与 Oracle 数据库中的记录类型的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [对与 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [对 Oracle 数据库中的同义词的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [Oracle 数据库中的 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [Oracle 数据库中执行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [支持 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [接收更改通知使用数据库的 Oracle 数据库适配器的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [对 Oracle Oracle 数据库中的用户定义类型的支持](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a>另请参阅  
 [用于 Oracle 数据库的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)