---
title: 接收位置分解后接收 Oracle 数据库更改通知 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22ad6da2-2979-4158-b1d1-d54095223af9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f20fdcd30362a87a49be17d061a9fe86595c78c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214085"
---
# <a name="receive-oracle-database-change-notifications-after-a-receive-location-breakdown"></a>接收位置分解后接收 Oracle 数据库更改通知
考虑具有 BizTalk 应用程序 ACCOUNTACTIVITY 表发生更改时接收数据库更改通知消息的其中一个方案。 如果接收位置配置的一部分 BizTalk 应用程序将分解，同时记录添加到 ACCOUNTACTIVITY 表，你将无法收到通知最近添加的记录。 你还不知道时接收位置重新变为可用。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开的绑定属性， **NotifyOnListenerStart**，可以配置为接收到通知，接收位置已恢复。 你可以指定以下值**NotifyOnListenerStart**绑定属性：  
  
-   将此属性设置为**True**来接收通知，告知接收位置恢复时，就会立即是否可用，接收位置。  
  
-   将此属性设置为**False**，以便不会收到接收位置已恢复，接收位置恢复后通知通知。  
  
 默认值是**True**。  
  
## <a name="configuring-the-oracle-database-adapter-behavior"></a>配置 Oracle 数据库适配器行为  
 这两个方法，你不需要执行任何特定的任务，在生成元数据或在配置 BizTalk 应用程序时。 只需设置**NotifyOnListenerStart**绑定属性相应地在 WCF 自定义或 WCF OracleDB 上接收位置。 若要创建 BizTalk 应用程序，你必须执行同一组任务中所述[接收 Oracle 数据库更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)。 但是，在配置 BizTalk 应用程序中使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以尝试更改的值**NotifyOnListenerStart**绑定属性和查看两个配置中的差异。  
  
 下图演示了如何基于的值会收到通知**NotifyOnListenerStart**绑定属性。  
  
 ![配置通知 SQL 适配器](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 请注意，在第一个方案中，当**NotifyOnListenerStart**设置为**True**并记录插入数据库表时接收位置已关闭，适配器仅向你发送当接收位置出现时的通知消息。 适配器不执行任何操作来处理向下接收位置时插入的记录。 适配器客户端必须实现相关逻辑，在其应用程序来处理向下接收位置时插入的记录。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 的接收 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)