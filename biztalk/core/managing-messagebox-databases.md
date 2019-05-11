---
title: 管理 MessageBox 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75dc3bdcd2d30eb7f8b0f5604d3e7e61cc54de59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380343"
---
# <a name="managing-messagebox-databases"></a>管理 MessageBox 数据库
MessageBox 数据库都有三种基本功能。 它可存储订阅和跟踪信息，还将消息传递给订阅相匹配的服务。 MessageBox 数据库是一个主机平台，为每个 BizTalk 主机存储队列和状态表。 MessageBox 数据库还存储消息和消息属性。  
  
 如果 MessageBox 数据库具有高暴露风险环境中的资产，我们建议你使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 以限制并确保从 MessageBox 数据库之间的通信安全。  
  
 如果使用 Windows Server 2003，则必须启用分布式的事务处理协调器 (DTC) 在 MessageBox 数据库上。 您还必须启用多计算机部署的网络客户端。 有关详细信息，请参阅[管理服务器的端口](../core/ports-for-the-administration-server.md)。  
  
 本部分包含有关管理您的环境中的 MessageBox 数据库的过程信息。 有关 MessageBox 数据库和订阅的概念信息模型 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用来处理消息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)  
  
-   [如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)