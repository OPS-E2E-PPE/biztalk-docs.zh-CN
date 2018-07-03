---
title: 在 SQL 中使用 BizTalk Server 接收查询通知后接收位置中断 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e70fa4c2-d81b-4eb0-a23d-871b64c881e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f7bf6026ebd9bf506dd84b1a8c309760c38f8d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975454"
---
# <a name="receive-query-notifications-after-a-receive-location-breakdown-in-sql-using-biztalk-server"></a>在 SQL 中使用 BizTalk Server 接收查询通知后接收位置中断
请考虑了 EMPLOYEE 表发生更改时接收数据库更改通知消息的 BizTalk 应用程序的方案。 如果接收位置配置的一部分的 BizTalk 应用程序细分的同时记录添加到 EMPLOYEE 表，则收不到最近添加的记录的通知。 您还不知道当接收位置再次可用时。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开的绑定属性， **NotifyOnListenerStart**，可以配置为接收到通知，接收位置已恢复。 可以指定以下值： **NotifyOnListenerStart**绑定属性：  
  
- 将此属性设置为 **，则返回 True**，接收通知，告知接收位置是否可用，就立即接收位置恢复。  
  
- 将此属性设置为**False**，以便不会收到已恢复的接收位置，接收位置恢复后通知告知。  
  
  默认值是 **，则返回 True**。  
  
## <a name="configuring-the-sql-adapter-behavior"></a>配置 SQL 适配器行为  
 两种方法不需要执行任何特定的任务生成的元数据时或在配置 BizTalk 应用程序。 只需设置**NotifyOnListenerStart**绑定属性相应地在 WCF 自定义或 WCF SQL 接收位置。 若要创建的 BizTalk 应用程序，必须执行一组相同的任务，如中所述[接收查询通知以增量方式从使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)。 但是，在配置 BizTalk 应用程序中使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以尝试更改的值**NotifyOnListenerStart**属性绑定，请参阅在两个配置中的差异。  
  
 下图演示了如何基于的值接收通知**NotifyOnListenerStart**属性绑定。  
  
 ![为通知配置 SQL 适配器](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 请注意，在第一个方案中，当**NotifyOnListenerStart**设置为**true**和向下的接收位置时向数据库表中插入记录，适配器仅向你发送当接收位置重新启动后的通知消息。 适配器不执行任何操作来处理向下的接收位置时插入的记录。 适配器客户端必须实现相关逻辑来处理记录时已关闭的接收位置插入其应用程序中。  
  
## <a name="see-also"></a>请参阅  
 [接收使用 BizTalk Server 的 SQL 查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)