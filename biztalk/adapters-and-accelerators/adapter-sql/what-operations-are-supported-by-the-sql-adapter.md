---
title: 通过 SQL 适配器支持哪些操作 |Microsoft Docs
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
ms.openlocfilehash: 873b74a253bd96c95ecf3d26be884fe83ac53e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367432"
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a>通过 SQL 适配器支持哪些操作
可以使用适配器客户端在通过 SQL Server 数据库上执行操作：  
  
- 创建 BizTalk 项目  
  
- 使用 WCF 服务模型  
  
- 使用 WCF 通道模型  
  
  [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。 有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。  
  
  本部分提供有关使用 SQL Server 数据库上支持的操作信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 
  
## <a name="see-also"></a>请参阅  
 [用于 SQL Server 的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)