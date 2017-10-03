---
title: "消息和消息架构用于 SQL Server 的 BizTalk Adapter |Microsoft 文档"
description: "SQL Server 适配器用于 BizTalk Server 的消息和数据类型的 XML 结构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b1e45f0a20500253e2ca831138a21efa24df3c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a>消息和用于 SQL Server 的 BizTalk Adapter 的消息架构

## <a name="overview"></a>概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的各节描述了消息的 XML 结构和数据类型，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本的 SQL Server 数据类型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [消息架构为插入、 更新、 删除和选择表和视图上的操作](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [有关过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [查询通知的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [ExecuteNonQuery、 ExecuteReader，和 ExecuteScalar 操作的消息架构](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  
