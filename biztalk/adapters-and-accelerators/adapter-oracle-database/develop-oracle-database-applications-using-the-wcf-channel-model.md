---
title: 开发 Oracle 数据库应用程序使用 WCF 通道模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c646b49f5787c986120027da89624bb19d0b3340
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376601"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a>开发 Oracle 数据库应用程序使用 WCF 通道模型
可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]通过直接通过使用 Oracle DB 绑定创建通道实例发送 XML 消息。  
  
 通过使用强类型化类和方法，WCF 服务模型公开了使用 WCF 通道模型的一个优点是通道模型提供更精细地控制对 Oracle 数据库执行的操作。 原因是什么？ WCF 通道模型直接控制在通道上发送的消息的内容。  
  
 在某些情况下，此额外级别的控制可能有益。 例如时使用的 WCF 通道模型以执行更新操作的表，将有选择地可以忽略传入的消息更新模板中的列，从而更新目标行中的列。 公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于包括表架构中的每个列的模板使用强类型的记录参数。 如果某一列具有"nillable = false"的 WSDL 中必须更新使用 WCF 服务模型。  
  
 WCF 通道模型提供了对 WCF 服务模型的另一个关键优势是更全面的端到端流式处理的 Oracle 大型对象 (LOB) 数据类型的支持。 通过使用 WCF 通道模型可以执行端到端流式处理：  
  
- 若要更新表中的 LOB 列或查看使用 UpdateLOB 操作。  
  
- 简称和 IN，OUT 参数，其中包含 LOB 数据返回的过程和函数。  
  
- SQLEXECUTE 操作的结果中包含的 LOB 数据。  
  
- 对 LOB POLLINGSTMT 操作中返回的数据列。  
  
- 返回针对表或视图的选择操作的 LOB 数据列。  
  
  这是因为 WCF 通道模型中您可以直接控制如何提供传出消息的消息正文，并对传入的消息的消息正文的处理方式。  
  
  与此相反，WCF 服务模型仅提供：  
  
- 端到端流式处理上一个操作，ReadLOB 操作的 LOB 数据。  
  
- 不是能更新 LOB 数据以流式方式对 Oracle 数据库。  
  
  本主题中的各节说明如何执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Oracle 数据库适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [调用上使用 WCF 通道模型，在 Oracle 数据库的操作](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [在 Oracle 数据库中使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [调用使用 WCF 通道模型的 Oracle 数据库中的函数](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [使用 WCF 通道模型的流式处理 Oracle 数据库 LOB 数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)