---
title: Oracle 数据库适配器支持哪些操作 |Microsoft Docs
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
ms.openlocfilehash: ed048357b98f8b831f53d00495fb9f9961f6afb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375843"
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a>哪些操作支持的 Oracle 数据库适配器
创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型，适配器客户端可以执行对 Oracle 数据库的操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。 有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和消息架构的 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。  
  
 本部分提供有关在 Oracle 数据库使用支持的操作信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [执行基本的 Insert、 Update、 Delete 和 Oracle 表和视图的 Select 操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [对包含 LOB 数据的表和视图的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [对函数和 Oracle 数据库中的存储的过程的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [对 Oracle 数据库中的 REF CURSOR 参数包含函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [对函数和过程的 Oracle 数据库中的记录类型的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [对包含 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [对 Oracle 数据库中的同义词的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [Oracle 数据库中的 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [在 Oracle 数据库中执行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [支持 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [接收数据库更改通知使用的 Oracle 数据库适配器时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [对 Oracle 数据库中的 Oracle 用户定义类型的支持](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a>请参阅  
 [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)