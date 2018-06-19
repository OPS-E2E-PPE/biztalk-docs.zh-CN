---
title: 哪些操作受 SQL 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d413a763823f49b0bf905b42d8513cbbb1e745
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222541"
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a>哪些操作受 SQL 适配器
可以使用适配器客户端在通过 SQL Server 数据库上执行操作：  
  
-   创建 BizTalk 项目  
  
-   使用 WCF 服务模型  
  
-   使用 WCF 通道模型  
  
 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。 有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。  
  
 本部分提供有关使用 SQL Server 数据库上支持的操作的信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 
  
## <a name="see-also"></a>另请参阅  
 [用于 SQL Server 的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)