---
title: "管理 MessageBox 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e854ad0f7014de8241f8a7b6af6addd49cb4da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-messagebox-databases"></a>管理 MessageBox 数据库
MessageBox 数据库具有三种基本功能。 它可存储订阅和跟踪信息，还可将消息送达与订阅相匹配的服务。 MessageBox 数据库是一种为每台 BizTalk 主机存储队列和状态表的主机平台。 MessageBox 数据库还可存储消息和消息属性。  
  
 如果 MessageBox 数据库在您的环境中属于具有高暴露风险的资产，建议使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 以限制与 MessageBox 的通信并确保通信安全。  
  
 如果使用 Windows Server 2003，则必须对 MessageBox 数据库启用分布式事务处理协调器 (DTC)。 还必须为多计算机部署启用网络客户端。 有关详细信息，请参阅[管理服务器的端口](../core/ports-for-the-administration-server.md)。  
  
 本部分包含有关管理您的环境中的 MessageBox 数据库的过程信息。 有关概念性信息 MessageBox 数据库和订阅模型 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用来处理消息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)  
  
-   [如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)