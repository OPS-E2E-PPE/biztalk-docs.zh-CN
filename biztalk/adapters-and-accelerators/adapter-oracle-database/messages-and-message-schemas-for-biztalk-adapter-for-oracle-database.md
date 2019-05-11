---
title: 消息和消息架构的 BizTalk 适配器用于 Oracle 数据库 |Microsoft Docs
description: 为 BizTalk Server 使用的 Oracle 数据库适配器的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee0a531-b1e6-4b99-bb79-45368c401395
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804143e55a69f775a6d1391f57cfce8cd12d7b3a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529005"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-database"></a>消息和消息架构的 Oracle 数据库的 BizTalk 适配器

## <a name="overview"></a>概述
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本 Oracle 数据类型](../../adapters-and-accelerators/adapter-oracle-database/basic-oracle-data-types1.md)  
  
-   [对表和视图进行基本插入、更新、删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)  
  
-   [函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)  
  
-   [REF CURSORS 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)  
  
-   [RECORD 类型的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)  
  
-   [SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)  
  
-   [轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)  
  
-   [复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)  
  
-   [通知操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)  
  
