---
title: "开发 Oracle 数据库应用程序使用 WCF 通道模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming
- channel programming, streaming
- WCF channel model, performing operations
- developing applications, by using the WCF channel model
- streaming, using the WCF channel model
- WCF channel model, developingn applications
- channel programming, performing operations
ms.assetid: cb6bf5fd-ff90-44bd-a9dd-03b00f12a78d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77fb9b6ca1fc70a55b59c6708450b8d94a01eff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a>开发 Oracle 数据库应用程序使用 WCF 通道模型
你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]通过直接通过使用 Oracle DB 绑定创建的通道实例发送 XML 消息。  
  
 通过使用的强类型类和 WCF 服务模型公开的方法使用 WCF 通道模型的一个优点是通道模型提供更好地细化控制对 Oracle 数据库执行的操作。 原因是什么？ WCF 通道模型直接控制通过通道发送的消息的内容。  
  
 在某些情况下，此额外级别是控制的有益的。 例如，当使用 WCF 通道模型来执行更新操作在表上的，你有选择地可以直接更新目标行中的列，通过省略消息中传递的更新模板中的列。 由公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于表架构中包含的每个列的模板使用强类型的记录参数。 如果某一列具有"nillable = false"在 WSDL，必须更新使用 WCF 服务模型。  
  
 WCF 通道模型提供了对 WCF 服务模型的另一个关键优势是更全面支持的端到端流式处理的 Oracle 大型对象 (LOB) 数据类型。 通过使用 WCF 通道模型中，你可以执行端到端流式处理：  
  
-   若要更新表中的 LOB 列或查看使用 UpdateLOB 操作。  
  
-   在扩展和 OUT 参数包含 IN LOB 过程和函数返回的数据。  
  
-   SQLEXECUTE 操作的结果中包含的 LOB 数据。  
  
-   在 POLLINGSTMT 操作中返回的 LOB 数据列。  
  
-   返回由对表或视图的选择操作的 LOB 数据列。  
  
 这是因为在 WCF 通道模型你直接控制如何提供传出消息的消息正文，并对传入的消息的消息正文的处理方式。  
  
 与此相反，WCF 服务模型仅提供：  
  
-   端到端上一个操作，ReadLOB 操作的 LOB 数据流式处理。  
  
-   若要更新在流处理方式中对 Oracle 数据库的 LOB 数据没有任何功能。  
  
 本主题中的各节说明如何执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 Oracle 数据库适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [调用使用 WCF 通道模型对 Oracle 数据库的操作](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [使用 WCF 通道模型的 Oracle 数据库中运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [调用中使用 WCF 通道模型的 Oracle 数据库的函数](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [使用 WCF 通道模型的流式处理 Oracle 数据库 LOB 数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)