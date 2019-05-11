---
title: 消息和用于 SQL Server 的 BizTalk 适配器的消息架构 |Microsoft Docs
description: 为 BizTalk Server 使用的 SQL Server 适配器的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01d2181423e479a7c39dc680cde34eba2db79fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368519"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a>消息和用于 SQL Server 的 BizTalk 适配器的消息架构

## <a name="overview"></a>概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本 SQL Server 数据类型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [在表和视图中进行插入、更新、删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [查询通知的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [ExecuteNonQuery、ExecuteReader 和 ExecuteScalar 操作的消息架构](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  
